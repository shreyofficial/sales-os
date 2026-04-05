---
skill: Email Deliverability Auditor
phase: 4 — Email Outreach
depends_on: [Business Context Compiler]
estimated_time: 15-20 minutes
---

# Email Deliverability Auditor

## Purpose

Perform a comprehensive technical audit of the user's email sending infrastructure to ensure maximum inbox placement. Poor deliverability is the silent killer of cold email campaigns — you can have the best copy in the world, but if it lands in spam, nobody sees it. This skill diagnoses every technical factor that affects whether emails reach the inbox.

---

## Step 1: Gather Sending Infrastructure Details

### Questions to Ask the User

```
1. What domain(s) do you send outbound email from?
   (e.g., yourdomain.com, or a secondary domain like getbrand.com)

2. What email sending platform do you use?
   (e.g., Gmail/Google Workspace, Outlook/Microsoft 365, custom SMTP,
   or a cold email tool like Instantly, Smartlead, Lemlist, Woodpecker, etc.)

3. How many emails do you currently send per day for outreach?

4. How long have you been sending from this domain?

5. Do you use a separate domain for cold outreach vs. your primary business domain?

6. Have you experienced deliverability problems recently?
   (e.g., emails going to spam, high bounce rates, low open rates below 20%)

7. Do you use any email warm-up tools? If so, which one?
```

---

## Step 2: DNS Authentication Records Audit

### 2a. SPF (Sender Policy Framework)

**What it does:** SPF tells receiving mail servers which IP addresses and servers are authorized to send email on behalf of your domain. Without it, anyone can spoof your domain.

**How to check:**

1. **MXToolbox SPF Lookup:** Go to `https://mxtoolbox.com/spf.aspx` — enter the sending domain
2. **Google Admin Toolbox:** Go to `https://toolbox.googleapps.com/apps/dig/` — query TXT records for the domain
3. **Command line:** Run `dig TXT yourdomain.com` or `nslookup -type=TXT yourdomain.com`

**What to look for:**

- A valid SPF record exists (starts with `v=spf1`)
- It includes the authorized senders (e.g., `include:_spf.google.com` for Google Workspace, `include:spf.protection.outlook.com` for Microsoft 365)
- It ends with `-all` (hard fail) or `~all` (soft fail) — hard fail is stronger
- There is only ONE SPF record (multiple SPF records cause failures)
- The record does not exceed 10 DNS lookups (SPF has a 10-lookup limit)

**Pass criteria:**
- Valid SPF record exists: YES/NO
- Includes all authorized senders: YES/NO
- Ends with `-all` or `~all`: YES/NO
- Single SPF record (no duplicates): YES/NO
- Under 10 DNS lookups: YES/NO

**If missing — setup instructions:**

```
1. Log into your DNS provider (GoDaddy, Cloudflare, Namecheap, etc.)
2. Add a TXT record:
   - Host/Name: @ (or leave blank, depending on provider)
   - Type: TXT
   - Value: v=spf1 include:[your-email-provider-spf] -all

   Examples:
   - Google Workspace: v=spf1 include:_spf.google.com -all
   - Microsoft 365: v=spf1 include:spf.protection.outlook.com -all
   - Multiple senders: v=spf1 include:_spf.google.com include:sendgrid.net -all

3. Save and wait 24-48 hours for DNS propagation
4. Verify using MXToolbox after propagation
```

### 2b. DKIM (DomainKeys Identified Mail)

**What it does:** DKIM adds a cryptographic signature to every email you send. The receiving server checks this signature against a public key published in your DNS. This proves the email was actually sent by you and wasn't tampered with in transit.

**How to check:**

1. **Send a test email to `check-auth@verifier.port25.com`** — you'll get an automated report showing DKIM status
2. **mail-tester.com:** Send an email to the address shown on the site — it grades your DKIM along with everything else
3. **MXToolbox DKIM Lookup:** `https://mxtoolbox.com/dkim.aspx` — you'll need the DKIM selector (e.g., `google` for Google Workspace, `selector1` for Microsoft 365)
4. **Google Admin Toolbox:** Query TXT records for `[selector]._domainkey.yourdomain.com`

**What to look for:**

- DKIM record exists in DNS
- DKIM signature passes validation when emails are sent
- The key length is at least 1024-bit (2048-bit preferred)

**Pass criteria:**
- DKIM DNS record exists: YES/NO
- DKIM signature validates on test email: YES/NO
- Key length >= 1024 bits: YES/NO

**If missing — setup instructions:**

```
For Google Workspace:
1. Go to Google Admin Console → Apps → Google Workspace → Gmail → Authenticate email
2. Click "Generate new record" — select 2048-bit
3. Copy the DKIM record value
4. In your DNS provider, add a TXT record:
   - Host/Name: google._domainkey
   - Value: [paste the value from Google Admin]
5. Go back to Google Admin and click "Start authentication"

For Microsoft 365:
1. Go to Microsoft 365 Defender → Policies → Email authentication → DKIM
2. Select your domain → Enable DKIM signing
3. Microsoft will provide two CNAME records to add to your DNS
4. Add both CNAME records in your DNS provider
5. Wait for propagation, then enable in Microsoft
```

### 2c. DMARC (Domain-based Message Authentication, Reporting & Conformance)

**What it does:** DMARC tells receiving servers what to do if an email fails SPF and DKIM checks. It also provides reporting so you can see who's sending email on behalf of your domain (including unauthorized senders).

**How to check:**

1. **MXToolbox DMARC Lookup:** `https://mxtoolbox.com/dmarc.aspx`
2. **Command line:** `dig TXT _dmarc.yourdomain.com`
3. **Google Admin Toolbox:** Query TXT records for `_dmarc.yourdomain.com`

**What to look for:**

- A DMARC record exists (starts with `v=DMARC1`)
- Policy is set (`p=none`, `p=quarantine`, or `p=reject`)
- Reporting address is configured (`rua=mailto:...`)

**Recommended DMARC progression:**

```
Stage 1 (Start here): v=DMARC1; p=none; rua=mailto:dmarc-reports@yourdomain.com
  → Monitor mode — no emails are blocked, but you get reports

Stage 2 (After 2-4 weeks of clean reports): v=DMARC1; p=quarantine; rua=mailto:dmarc-reports@yourdomain.com
  → Suspicious emails go to spam

Stage 3 (After confidence is high): v=DMARC1; p=reject; rua=mailto:dmarc-reports@yourdomain.com
  → Unauthorized emails are outright rejected
```

**Pass criteria:**
- DMARC record exists: YES/NO
- Policy is set: YES/NO (and what level)
- Reporting address configured: YES/NO

**If missing — setup instructions:**

```
1. In your DNS provider, add a TXT record:
   - Host/Name: _dmarc
   - Value: v=DMARC1; p=none; rua=mailto:dmarc-reports@yourdomain.com
2. Start with p=none to monitor without affecting delivery
3. Use a DMARC reporting tool (Postmark DMARC, dmarcian, EasyDMARC) to analyze reports
4. Gradually tighten policy over 4-8 weeks
```

### 2d. Custom Tracking Domain

**What it does:** Cold email tools track opens and clicks through a tracking domain. By default, this is a shared domain used by thousands of other senders. If any of those senders are spammy, the shared tracking domain gets flagged, and YOUR emails suffer. A custom tracking domain isolates your reputation.

**How to check:** Log into your cold email platform and check tracking settings. Look for a setting called "Custom tracking domain" or "Custom domain."

**Pass criteria:**
- Custom tracking domain configured: YES/NO
- Tracking domain resolves correctly: YES/NO
- SSL certificate active on tracking domain: YES/NO

**Setup (general process):**

```
1. Choose a subdomain: track.yourdomain.com or link.yourdomain.com
2. In your DNS provider, add a CNAME record:
   - Host/Name: track (or link)
   - Points to: [the tracking URL provided by your email tool]
3. Enable custom tracking domain in your email tool's settings
4. Verify SSL is active (most tools handle this automatically)
```

### 2e. Reverse DNS (PTR Record)

**What it does:** Reverse DNS maps your sending IP address back to your domain. It's the reverse of normal DNS (which maps domain to IP). Many mail servers check reverse DNS and penalize senders without it.

**How to check:**

1. **MXToolbox Reverse Lookup:** `https://mxtoolbox.com/ReverseLookup.aspx`
2. **Command line:** `dig -x [your-sending-IP]`

**Note:** If you use Google Workspace, Microsoft 365, or a reputable email platform, reverse DNS is handled for you. This is primarily a concern for custom SMTP servers or dedicated IPs.

**Pass criteria:**
- Reverse DNS configured: YES/NO (or N/A if using managed provider)
- PTR record matches sending domain: YES/NO

---

## Step 3: Domain Reputation Assessment

### Domain Age

**Why it matters:** New domains (less than 30 days old) are treated with extreme suspicion by email providers. Domains less than 6 months old still face higher scrutiny. Older domains with clean history get the benefit of the doubt.

**How to check:**
- **WHOIS lookup:** `https://whois.domaintools.com/` or `https://who.is/`
- Look for "Creation Date" in the results

**Risk levels:**
- Domain age < 30 days: HIGH RISK — Do not send cold email. Warm up for 4-6 weeks minimum.
- Domain age 30-90 days: MODERATE RISK — Start with very low volume (5-10/day) and warm up gradually.
- Domain age 3-12 months: LOW RISK — Normal warm-up protocols apply.
- Domain age > 12 months: MINIMAL RISK — Can proceed with standard volume ramp-up.

### Domain Reputation

**How to check:**
1. **Google Postmaster Tools:** `https://postmaster.google.com/` — shows how Google views your domain (requires verification). Provides reputation scores: Bad, Low, Medium, High.
2. **Microsoft SNDS:** `https://sendersupport.olc.protection.outlook.com/snds/` — shows Microsoft's view.
3. **Talos Intelligence (Cisco):** `https://talosintelligence.com/reputation_center` — provides a reputation score.
4. **Sender Score (Validity):** `https://senderscore.org/` — rates your sending IP 0-100.
5. **BarracudaCentral:** `https://www.barracudacentral.org/lookups` — check if you're on their reputation list.

**Pass criteria:**
- Google Postmaster reputation: High or Medium = PASS / Low or Bad = FAIL
- Sender Score > 80 = PASS / 70-80 = WARNING / < 70 = FAIL
- Talos Intelligence: Good or Neutral = PASS / Poor = FAIL

---

## Step 4: Blacklist Check

**How to check:**
1. **MXToolbox Blacklist Check:** `https://mxtoolbox.com/blacklists.aspx` — checks 100+ blacklists simultaneously
2. **MultiRBL:** `https://multirbl.valli.org/` — comprehensive blacklist aggregator

**What to check:** Both your domain AND your sending IP address.

**Common blacklists that matter most:**
- Spamhaus (SBL, XBL, PBL) — the most influential
- Barracuda BRBL
- SORBS
- SpamCop
- CBL (Composite Blocking List)
- URIBL / SURBL (check URLs in email content)

**If blacklisted — removal process:**

```
1. Identify WHY you were listed (each blacklist has a lookup tool that shows the reason)
2. Fix the root cause:
   - High bounce rate → Clean your list with a verification tool
   - Spam complaints → Review your content and targeting
   - Compromised account → Secure your account, change passwords
   - Open relay → Fix server configuration
3. Request delisting:
   - Most blacklists have a self-service removal form
   - Spamhaus: https://check.spamhaus.org/ → follow removal process
   - Some blacklists auto-delist after 1-2 weeks if the problem is resolved
4. Monitor for re-listing after removal
```

**Pass criteria:**
- Domain not on any major blacklists: YES/NO
- Sending IP not on any major blacklists: YES/NO

---

## Step 5: Sending Infrastructure Evaluation

### Platform Assessment

| Platform | Max Daily Send (Cold) | Authentication Support | Cold Email Suitability |
|----------|----------------------|----------------------|----------------------|
| Google Workspace | 500/day (total) | Full (SPF, DKIM, DMARC) | Good for low volume |
| Microsoft 365 | 10,000/day (total) | Full | Good for moderate volume |
| Instantly | 50-100/day per inbox | Full + auto-rotation | Purpose-built for cold email |
| Smartlead | 50-100/day per inbox | Full + auto-rotation | Purpose-built for cold email |
| Lemlist | 50-200/day per inbox | Full | Good cold email tool |
| Woodpecker | 50-200/day per inbox | Full | Good cold email tool |
| Mailshake | 50-200/day per inbox | Full | Good cold email tool |
| Custom SMTP (SendGrid, Postmark) | Varies by plan | Full (manual setup) | Advanced users only |

### Dedicated IP vs. Shared IP

- **Shared IP:** Your reputation is partially tied to other senders on the same IP. Good for low volume (<1,000/day). Less control but lower maintenance.
- **Dedicated IP:** Your reputation is entirely yours. Better for high volume (>1,000/day). Requires warm-up. More control but more responsibility.

**Recommendation:** For most cold email operations sending under 500 emails per day, a shared IP through a reputable cold email platform is fine. Only invest in a dedicated IP if you're sending at scale.

---

## Step 6: Spam Trigger Audit

### Content-Level Spam Triggers

**Words and phrases to avoid in subject lines and body copy:**

```
HIGH RISK (almost guaranteed spam filter trigger):
- Free, 100% free, complimentary
- Act now, limited time, urgent, don't miss out
- Guaranteed, no risk, risk-free
- Make money, earn extra cash, income opportunity
- Click here, click below
- Congratulations, you've been selected, you're a winner
- Buy now, order now, shop now
- Increase your ROI, double your revenue (with specific numbers)
- No obligation, no purchase necessary
- Dear friend, dear sir/madam

MODERATE RISK (may trigger filters, especially in combination):
- Discount, sale, save, deal, offer, promotion
- Exclusive, special, amazing, incredible
- Call now, reply now, respond immediately
- As seen on, featured in
- Cancel anytime, no strings attached
- $, $$, money-back guarantee
- Unsubscribe (in cold email context — you need it but placement matters)

LOW RISK BUT WATCH:
- RE: or FW: when it's not actually a reply or forward (deceptive)
- Excessive use of "you" and "your" (can seem salesy)
- Multiple exclamation points!!!
- ALL CAPS FOR EMPHASIS
```

### Formatting Spam Triggers

```
- Image-heavy emails (email clients block images by default in cold email)
- HTML-rich formatting (use plain text or minimal HTML for cold email)
- Too many links (keep to 1-2 maximum in cold email)
- Large attachments (never attach files in cold email — link instead)
- Colored or fancy fonts
- Large font sizes
- Background colors or images
- Embedded forms or videos
- Invisible text (white text on white background — a classic spam trick that's flagged)
- URL shorteners (bit.ly, etc.) — these are heavily penalized
```

### Technical Spam Triggers

```
- Sending too many emails too fast (velocity spikes)
- Inconsistent sending volume (0 one day, 500 the next)
- High bounce rate (above 5%)
- High spam complaint rate (above 0.1%)
- Sending to old, unverified lists
- Sending identical content to hundreds of recipients
- Missing unsubscribe mechanism
- Mismatched "From" name and email address
```

---

## Step 7: Inbox Placement Test

### How to Test Inbox Placement

**Method 1: Seed list testing**

```
1. Create email accounts across major providers:
   - 2-3 Gmail accounts
   - 2-3 Outlook/Hotmail accounts
   - 1-2 Yahoo accounts
   - 1 corporate email account (if possible)
2. Send your actual email (exact content you plan to use) to all seed accounts
3. Check where it lands:
   - Primary inbox = PASS
   - Promotions tab = WARNING (for Gmail)
   - Spam/Junk = FAIL
4. Test at different times of day and with different subject lines
```

**Method 2: Use a testing tool**

```
- mail-tester.com — Send to the address shown, get a score out of 10 (aim for 9+)
- GlockApps — Comprehensive inbox placement testing across providers
- Litmus or Email on Acid — Test rendering and placement
- MXToolbox Email Health — Overall sending health check
```

### Mail-Tester.com Scoring Guide

| Score | Rating | Action |
|-------|--------|--------|
| 9-10 | Excellent | Good to send |
| 7-8 | Good | Minor fixes needed — check report details |
| 5-6 | Needs work | Significant issues — fix before sending campaigns |
| Below 5 | Poor | Do NOT send campaigns — major fixes required |

---

## Step 8: Bounce Rate Analysis

### Bounce Rate Benchmarks

```
< 1% bounce rate = EXCELLENT — List is very clean
1-2% bounce rate = ACCEPTABLE — Normal range for verified lists
2-5% bounce rate = WARNING — List needs cleaning, start verifying
5-10% bounce rate = DANGEROUS — Stop sending. Clean and verify entire list immediately.
> 10% bounce rate = CRITICAL — Your domain reputation is being damaged. Stop all sending.
```

### Types of Bounces

- **Hard bounce:** Email address doesn't exist (permanently undeliverable). REMOVE IMMEDIATELY. Never re-send to hard bounces.
- **Soft bounce:** Temporary issue (full inbox, server down, message too large). Can retry, but if soft bounces persist 3+ times, treat as hard bounce.

### How to Reduce Bounce Rate

```
1. Verify all email addresses before adding to campaigns
   - Tools: NeverBounce, ZeroBounce, Bouncer, MillionVerifier, BriteVerify
   - Cost: $3-10 per 1,000 verifications
   - Acceptable verification result: only send to "valid" — never send to "catch-all," "unknown," or "invalid"

2. Remove role-based addresses: info@, admin@, support@, sales@, team@
   (These are monitored by multiple people and more likely to generate spam complaints)

3. Use double opt-in for inbound leads (not applicable to cold outreach but important for overall domain health)

4. Regularly clean your lists: re-verify any list older than 90 days

5. Monitor bounce rates per campaign and pause any campaign exceeding 3%
```

---

## Step 9: Sending Volume Guidelines

### Daily Limits by Provider

```
Google Workspace:
- Hard limit: 500 emails/day per user (2,000 for paid accounts, but throttled)
- Recommended for cold email: 30-50 per inbox per day
- Use multiple inboxes to scale

Microsoft 365:
- Hard limit: 10,000 recipients/day
- Recommended for cold email: 50-80 per inbox per day

Instantly / Smartlead / Lemlist (dedicated cold email tools):
- These tools manage multiple inboxes and rotate sending
- Recommended: 30-50 per inbox per day
- Scale by adding more inboxes, not by increasing per-inbox volume

Custom SMTP (SendGrid, Amazon SES, Postmark):
- Limits vary by plan and reputation
- Requires careful IP warm-up if using dedicated IP
- Recommended: follow provider-specific guidelines
```

### Ramp-Up Schedule (New Inbox or Domain)

```
Week 1:  5-10 emails/day   — Primarily to warm contacts
Week 2:  15-25 emails/day  — Mix of warm and cold
Week 3:  25-40 emails/day  — Increasing cold ratio
Week 4:  40-60 emails/day  — Mostly cold
Week 5:  60-80 emails/day  — Full cold outreach volume
Week 6+: 80-100 emails/day — Maximum recommended per inbox

IMPORTANT: If at any point open rates drop below 20% or bounce rates exceed 3%,
reduce volume immediately and investigate.
```

---

## Step 10: Compile the Deliverability Audit Report

### Output Format

```
============================================
   EMAIL DELIVERABILITY AUDIT REPORT
   Domain: [user's domain]
   Date: [current date]
============================================

OVERALL SCORE: [X/10] — [Excellent / Good / Needs Work / Poor / Critical]

--- DNS AUTHENTICATION ---
| Check              | Status    | Risk Level | Notes                      |
|--------------------|-----------|------------|----------------------------|
| SPF Record         | PASS/FAIL | Low/Med/Hi | [Details]                  |
| DKIM Signing       | PASS/FAIL | Low/Med/Hi | [Details]                  |
| DMARC Policy       | PASS/FAIL | Low/Med/Hi | [Details]                  |
| Custom Tracking    | PASS/FAIL | Low/Med/Hi | [Details]                  |
| Reverse DNS        | PASS/FAIL | Low/Med/Hi | [Details or N/A]           |

--- DOMAIN REPUTATION ---
| Check              | Status    | Risk Level | Notes                      |
|--------------------|-----------|------------|----------------------------|
| Domain Age         | [age]     | Low/Med/Hi | [Recommendation]           |
| Google Postmaster  | [score]   | Low/Med/Hi | [Details]                  |
| Sender Score       | [0-100]   | Low/Med/Hi | [Details]                  |
| Blacklist Status   | CLEAN/HIT | Low/Med/Hi | [Which blacklists if any]  |

--- SENDING INFRASTRUCTURE ---
| Check              | Status    | Risk Level | Notes                      |
|--------------------|-----------|------------|----------------------------|
| Platform           | [name]    | Low/Med/Hi | [Suitability assessment]   |
| IP Type            | Shared/Ded| Low/Med/Hi | [Recommendation]           |
| Daily Volume       | [number]  | Low/Med/Hi | [vs. recommended limits]   |
| Warm-Up Status     | [status]  | Low/Med/Hi | [Recommendation]           |

--- CONTENT & TECHNICAL ---
| Check              | Status    | Risk Level | Notes                      |
|--------------------|-----------|------------|----------------------------|
| Spam Trigger Words | PASS/FAIL | Low/Med/Hi | [Flagged words if any]     |
| Formatting         | PASS/FAIL | Low/Med/Hi | [Issues if any]            |
| Link Count         | PASS/FAIL | Low/Med/Hi | [Number of links]          |
| Inbox Placement    | [where]   | Low/Med/Hi | [Gmail/Outlook results]    |

--- BOUNCE & ENGAGEMENT ---
| Check              | Status    | Risk Level | Notes                      |
|--------------------|-----------|------------|----------------------------|
| Bounce Rate        | [X%]      | Low/Med/Hi | [vs. benchmarks]           |
| Spam Complaint Rate| [X%]      | Low/Med/Hi | [vs. 0.1% threshold]       |

============================================
   PRIORITY FIX LIST (ordered by impact)
============================================

1. [Highest priority fix — what to do and why]
2. [Second priority fix]
3. [Third priority fix]
... (continue for all items that are FAIL or WARNING)

============================================
   RECOMMENDED NEXT STEPS
============================================

- Immediate (do today): [specific actions]
- This week: [specific actions]
- Ongoing: [monitoring actions]
```

---

## Quality Checklist

Before delivering the audit report, verify:

- [ ] All five DNS authentication checks (SPF, DKIM, DMARC, custom tracking domain, reverse DNS) have been evaluated
- [ ] Domain age and reputation have been assessed with specific tools recommended
- [ ] Blacklist status has been checked
- [ ] Sending platform has been evaluated for cold email suitability
- [ ] Daily sending volume has been compared against recommended limits
- [ ] Content-level spam triggers have been audited
- [ ] Inbox placement testing method has been recommended or performed
- [ ] Bounce rate benchmarks have been provided
- [ ] A clear, prioritized list of fixes has been generated
- [ ] Setup instructions have been provided for any missing authentication records
- [ ] Risk levels are assigned to every check (not just pass/fail)
- [ ] The report is actionable — the user can fix every issue without needing to hire a specialist
- [ ] No specific company names, brands, or personal information are referenced in the report template
