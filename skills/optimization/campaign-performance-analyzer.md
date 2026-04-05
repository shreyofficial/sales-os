---
skill: Campaign Performance Analyzer
phase: 6 — Optimization & Automation
depends_on: [Cold Email Campaign Architect, Weekly Pipeline Review]
estimated_time: 15-20 minutes
---

# Campaign Performance Analyzer

## Purpose

Diagnose exactly where your outreach funnel is breaking down. Most people guess at what's wrong — they rewrite subject lines when emails are going to spam, or change their offer when the problem is actually their CTA. This skill gives you a systematic, data-driven framework for identifying the weakest link in your sales funnel and fixing it with surgical precision.

---

## The Weakest Link Principle

Before diving into diagnostics, understand this core concept: **your funnel is only as strong as its weakest stage.** Optimizing subject lines when your deliverability is broken is like polishing the paint on a car with no engine.

Always diagnose from the TOP of the funnel DOWN. Fix the earliest broken stage first.

The order of diagnosis:
1. Deliverability (are emails reaching inboxes?)
2. Attention (are they opening/seeing your message?)
3. Interest (are they reading to the end?)
4. Response (are they replying?)
5. Conversion (are replies turning into calls?)

Do not skip ahead. Do not work on Stage 4 until Stages 1-3 are healthy.

---

## The Sales Funnel Diagnostic Framework

### Stage 1: Deliverability — Are Emails Reaching Inboxes?

**The Metric:** Delivery rate (emails delivered / emails sent)

**What "Good" Looks Like:**
- Delivery rate: >98%
- Bounce rate: <2%
- Spam complaint rate: <0.1%
- Not landing in spam/promotions tabs (test with seed accounts)

**What "Bad" Looks Like:**
- Delivery rate: <95%
- Bounce rate: >5%
- Emails landing in spam folder when tested
- Sudden drop in open rates across ALL campaigns simultaneously (spam signal)
- Getting blacklisted on major blocklists (Spamhaus, Barracuda)

**The 5 Most Common Reasons for Deliverability Problems:**

1. **Bad email list hygiene**
   - Using unverified email addresses
   - Sending to catch-all domains without verification
   - High hard bounce rate signals to ESPs that you're a spammer
   - *Fix:* Run your entire list through an email verification tool (NeverBounce, ZeroBounce, MillionVerifier). Remove all invalid, risky, and catch-all addresses. Re-verify every 90 days.

2. **Domain/IP reputation is damaged**
   - Sending from a brand new domain without warm-up
   - Previously hitting spam traps
   - Too many spam complaints
   - *Fix:* Check your domain reputation (Google Postmaster Tools, Sender Score). If damaged, set up a new sending domain (subdomain or alternate domain). Warm it up properly — start at 5-10 emails/day, increase by 5-10 per day over 3-4 weeks.

3. **Missing or misconfigured authentication**
   - SPF, DKIM, or DMARC records not set up
   - Authentication failing silently
   - *Fix:* Verify SPF, DKIM, and DMARC records for every sending domain. Use MXToolbox or mail-tester.com to check. Fix any misconfigurations immediately. This is non-negotiable.

4. **Email content triggers spam filters**
   - Too many links (especially in first email)
   - Spammy words ("free," "guaranteed," "act now," "limited time")
   - HTML-heavy emails with images
   - Tracking pixels from certain tools
   - *Fix:* Send plain-text emails with zero links in the first touch. Remove spam trigger words. Disable open tracking if your deliverability is suffering (tracking pixels can trigger filters).

5. **Sending volume too high or too fast**
   - Exceeding sending limits for your domain age
   - Sending hundreds of emails per day from a single inbox
   - No warm-up period
   - *Fix:* Reduce to 30-50 emails per inbox per day maximum. Use multiple inboxes (3-5) to spread volume. Ramp up gradually over 2-4 weeks.

---

### Stage 2: Attention — Are They Opening?

**The Metric:** Open rate (unique opens / emails delivered)

**What "Good" Looks Like:**
- Cold email open rate: >40%
- Follow-up email open rate: >30%
- Note: Open rates are increasingly unreliable due to Apple Mail Privacy Protection and corporate email filtering. Use as directional signal only.

**What "Bad" Looks Like:**
- Open rate: <25%
- Open rate declining over time
- Huge variance between campaigns with similar audiences

**The 5 Most Common Reasons for Low Open Rates:**

1. **Weak subject lines**
   - Too generic ("Quick question" has been overused)
   - Too long (gets cut off on mobile)
   - Sounds like marketing, not a person
   - *Fix:* Test subject lines that are 3-6 words, lowercase, conversational. Best performers: curiosity-driven questions, specific references to their company, pattern interrupts. Examples: "[COMPANY] + [YOUR SERVICE]?", "thought about this for [COMPANY]", "quick [ICP TITLE] question"

2. **Poor "from" name / sender identity**
   - Using a company name instead of a person's name
   - Using a full formal name that feels corporate
   - Unfamiliar sender with no prior touchpoint
   - *Fix:* Send from a first name or first + last name. Never a company name. Consider warming them up on LinkedIn first so your name is recognized.

3. **Wrong sending time**
   - Sending when their inbox is flooded (9 AM Monday)
   - Sending outside business hours for their timezone
   - Not accounting for ICP's work patterns
   - *Fix:* Test different send times. Generally: Tuesday-Thursday, 7-9 AM or 1-3 PM in the prospect's timezone. Avoid Monday mornings and Friday afternoons. If targeting executives, early morning (6-7 AM) can work well.

4. **Preview text not optimized**
   - First line of email is generic ("Hope you're doing well")
   - Preview text doesn't create curiosity
   - *Fix:* Make the first line of your email compelling and personalized. The preview text (first 40-90 characters) is nearly as important as the subject line. Lead with something specific to them.

5. **Audience fatigue / over-saturation**
   - Sending to the same people too frequently
   - Your ICP is bombarded by competitors with similar messaging
   - *Fix:* Space out sequences (3-5 days between touches minimum). Rotate subject line styles. If an ICP segment is oversaturated, try different channels (LinkedIn, phone) or different angles.

---

### Stage 3: Interest — Are They Reading to the End?

**The Metric:** Click rate (if links present), read time (if trackable), or inferred from reply quality

**What "Good" Looks Like:**
- Click rate (if applicable): >3%
- Replies reference specific points from your email (they read it)
- Low unsubscribe/complaint rate (<0.5%)

**What "Bad" Looks Like:**
- Click rate: <1%
- Replies say "not interested" without engaging with your content
- High unsubscribe rate
- One-word negative replies

**The 5 Most Common Reasons for Low Interest:**

1. **Email is too long**
   - Prospects scan, they don't read — especially cold emails
   - More than 100 words loses most readers
   - *Fix:* Cut your cold email to 50-80 words. Every sentence must earn its place. If you can delete a sentence and the email still works, delete it.

2. **No relevance in the first two sentences**
   - Opening with "I" instead of "you"
   - No connection to their specific situation
   - Generic value prop that could apply to anyone
   - *Fix:* First sentence must be about THEM — a specific observation, trigger event, or pain point. Second sentence bridges to why you're reaching out. Get to relevance within 2 seconds of reading.

3. **Value proposition is unclear or unbelievable**
   - Vague claims ("we help companies grow")
   - Unbelievable claims without proof ("we guarantee 10x ROI")
   - Feature-focused instead of outcome-focused
   - *Fix:* State a specific, believable outcome. Use social proof: "We helped [SIMILAR COMPANY TYPE] achieve [SPECIFIC RESULT] in [TIMEFRAME]." Be concrete and credible.

4. **Too many CTAs or asks**
   - Asking for a call, a reply, AND to check out a link
   - Making the ask feel high-commitment
   - *Fix:* One CTA per email. Make it low-friction. Best CTAs: a simple question they can reply to with one sentence.

5. **Wrong tone for the audience**
   - Too casual for enterprise buyers
   - Too formal for startup founders
   - Using jargon the prospect doesn't use
   - *Fix:* Match the communication style of your ICP. Read how they write on LinkedIn. Mirror that tone.

---

### Stage 4: Response — Are They Replying?

**The Metric:** Reply rate (total replies / emails delivered), Positive reply rate (interested replies / emails delivered)

**What "Good" Looks Like:**
- Total reply rate: 5-15%
- Positive reply rate: 2-5%
- Positive-to-negative reply ratio: >1:3

**What "Bad" Looks Like:**
- Total reply rate: <3%
- Positive reply rate: <1%
- Almost all replies are negative or "not interested"

**The 5 Most Common Reasons for Low Reply Rates:**

1. **CTA is too high-commitment**
   - Asking for a 30-minute call in the first email
   - Requiring them to do work to respond
   - *Fix:* Use a soft CTA: "Worth exploring?" / "Is this a priority for you right now?" / "Would it be helpful if I shared how [SIMILAR COMPANY TYPE] handled this?" — make it easy to say yes.

2. **No reason to reply NOW**
   - No urgency or timeliness
   - No trigger event connecting to their current situation
   - *Fix:* Reference something timely: recent funding, job change, company news, industry trend, seasonal relevance. Create natural urgency without being pushy.

3. **They don't believe you can help**
   - No social proof
   - No specificity about results
   - Sounds like every other outreach they receive
   - *Fix:* Include one specific proof point: a result, a client name (with permission), a metric. Specificity creates credibility.

4. **The follow-up sequence is weak**
   - Only sending 1-2 emails and giving up
   - Follow-ups that just "bump" without adding value
   - *Fix:* Send 4-6 emails over 2-3 weeks. Each follow-up should add NEW value: a case study, a relevant insight, a different angle. Never just say "bumping this to the top of your inbox."

5. **Wrong person or wrong time**
   - Reaching the right company but wrong decision-maker
   - Reaching the right person at the wrong time (no budget, no pain, no authority)
   - *Fix:* Verify your contact targeting. Consider reaching out to multiple people at the same company (but coordinate messaging). Accept that timing is partially luck — this is why volume matters.

---

### Stage 5: Conversion — Are Replies Becoming Calls?

**The Metric:** Meeting book rate (meetings booked / positive replies)

**What "Good" Looks Like:**
- Meeting book rate from positive replies: >50%
- Time from positive reply to booked meeting: <24 hours
- Show rate for booked meetings: >80%

**What "Bad" Looks Like:**
- Meeting book rate: <30%
- Long delays between reply and booking
- High no-show rate (>25%)

**The 5 Most Common Reasons for Low Conversion:**

1. **Slow response time to positive replies**
   - Waiting hours or days to respond to interested prospects
   - *Fix:* Respond within 1 hour during business hours. Set up notifications. The prospect's interest is a depreciating asset — every hour you wait, their motivation drops.

2. **Making it hard to book**
   - Asking them to propose times (back-and-forth)
   - Sending a scheduling link that feels impersonal
   - *Fix:* Offer 2-3 specific times AND a scheduling link. "Would [Day] at [Time] or [Day] at [Time] work? Or grab whatever works here: [link]." Remove all friction.

3. **Overselling in the reply**
   - Writing a long reply that tries to close the deal before the call
   - Attaching decks or case studies they didn't ask for
   - *Fix:* Keep your reply short and focused on booking the call. Save the pitch for the conversation. "Great to hear — let's find 15 minutes to see if there's a fit. Would [Day] at [Time] work?"

4. **No confirmation or reminder process**
   - Not sending a calendar invite immediately
   - No reminder before the meeting
   - *Fix:* Send a calendar invite within minutes of confirming. Send a brief reminder the day before or morning of. Include the agenda or talking points in the invite.

5. **Misaligned expectations**
   - Prospect thinks it's a "quick chat" but you've blocked 60 minutes
   - Prospect expects a demo but you want to do discovery
   - *Fix:* Set clear expectations in the booking message. "It'll be a quick 15-minute conversation to see if there's a fit — no pressure, no pitch deck."

---

## LinkedIn Funnel Analysis

Apply the same stage-by-stage thinking to LinkedIn:

### Connection Request Stage
- **Benchmark:** 30-50% acceptance rate
- **Below 20%:** Your profile looks spammy, your connection note is too salesy, or you're targeting too far outside your network
- **Above 50%:** You're either well-known in your niche or your profile/note is highly relevant
- **Fix low acceptance:** Improve headline, add mutual connections/interests in note, warm up with content engagement first

### DM Response Stage
- **Benchmark:** 15-30% response rate to first DM
- **Below 10%:** DM is too long, too salesy, too generic, or sent too soon after connecting
- **Above 30%:** Your personalization and timing are strong
- **Fix low response:** Wait 1-3 days after connecting before DMing, lead with value/observation not a pitch, keep DMs under 50 words

### Call Booking Stage
- **Benchmark:** 20-40% of positive DM conversations should lead to a call
- **Below 15%:** Transition from DM to call is too abrupt or the value proposition isn't clear
- **Fix low booking:** Build rapport over 2-3 DM exchanges before suggesting a call, make the transition natural

---

## Campaign Comparison Framework

When running multiple campaigns simultaneously, use this side-by-side comparison:

| Metric | Campaign A | Campaign B | Campaign C | Best Performer |
|--------|-----------|-----------|-----------|----------------|
| Audience / ICP Segment | | | | |
| List size | | | | |
| Delivery rate | | | | |
| Open rate | | | | |
| Reply rate (total) | | | | |
| Positive reply rate | | | | |
| Meeting book rate | | | | |
| Emails per meeting | | | | |
| Cost per meeting | | | | |

**Key comparisons to make:**
- Which ICP segment responds best?
- Which messaging angle generates the highest positive reply rate?
- Which channel performs best for each segment?
- What is the cost-per-meeting by campaign?

### Isolating Variables

When comparing campaigns, only change ONE variable at a time:
- **Compare ICP segments:** Same messaging, different audiences
- **Compare messaging:** Same audience, different email copy
- **Compare channels:** Same audience and value prop, email vs. LinkedIn vs. multi-channel
- **Compare timing:** Same everything, different send times/days

---

## Cohort Analysis

Group your data into cohorts to identify meaningful patterns:

**By ICP Segment:**
- Which job titles respond best?
- Which company sizes convert highest?
- Which industries are most receptive?

**By Time Period:**
- Is performance improving or declining week over week?
- Any seasonal patterns? (e.g., lower response in December, higher in January/Q1)
- Did a specific change (new template, new tool) improve results?

**By Message Type:**
- Pain-point-focused vs. opportunity-focused messaging
- Short emails vs. medium-length emails
- Question CTA vs. statement CTA
- Personalized first line vs. semi-personalized vs. generic

**By Source:**
- Manually built lists vs. purchased lists vs. scraped lists
- LinkedIn connections vs. cold email lists
- Inbound leads vs. outbound leads

---

## The 3-Week Rule

**Never make conclusions about a campaign's performance with less than 3 weeks of data.**

Why 3 weeks:
- Week 1: Your sequence is just starting — many prospects haven't received all touches yet
- Week 2: Follow-ups are landing, replies start coming in, patterns begin to emerge
- Week 3: Full sequence has completed for the first cohort, you have statistically meaningful data

**Minimum sample sizes for reliable conclusions:**
- Subject line test: 200+ opens per variant minimum
- Reply rate test: 500+ emails sent per variant minimum
- Campaign comparison: 1,000+ emails per campaign minimum

**Exception to the 3-week rule:** If you see a red flag alert (below), act immediately.

---

## Red Flag Alerts — Act Immediately

These thresholds should trigger immediate investigation and action:

| Red Flag | Threshold | Immediate Action |
|----------|-----------|-----------------|
| Bounce rate spike | >5% in a single send | Pause campaign, re-verify list |
| Delivery rate crash | <90% | Pause ALL sending, check domain reputation |
| Open rate collapse | Drops >50% from baseline | Check if landing in spam, check domain health |
| Spam complaint spike | >0.3% | Pause campaign, review content and list source |
| Reply rate to zero | 0 replies in 100+ sends | Something is fundamentally broken — full audit |
| All replies negative | >90% negative | Messaging or targeting is severely off |
| Account restriction | LinkedIn or email | Stop all automated activity, review compliance |
| Blacklisted domain | Any major blocklist | Switch to backup domain immediately |

---

## Seasonal and Market Factors

Sometimes low performance is the market, not your campaign. Account for:

**Predictable low periods:**
- Last 2 weeks of December (holidays)
- First week of January (inbox overload)
- Major industry conferences (your ICP is traveling)
- End of quarter (prospects are focused on closing their own deals)
- Summer (July-August, especially in Europe)

**Market-driven factors:**
- Economic downturns (longer sales cycles, more "no budget" responses)
- Industry disruption (prospects are distracted by bigger problems)
- Competitor saturation (too many people selling the same thing to the same buyers)

**How to tell if it's the market vs. your campaign:**
- Check if ALL your campaigns dropped simultaneously (market) vs. one specific campaign (your campaign)
- Ask peers in your space if they're seeing similar trends
- Look at industry benchmarks for the current period
- Check your website traffic and inbound leads — if those dropped too, it's likely market-wide

---

## Improvement Prioritization: Effort vs. Impact Matrix

When you've identified multiple issues, prioritize fixes using this matrix:

**High Impact, Low Effort (DO FIRST):**
- Fix broken authentication (SPF/DKIM/DMARC)
- Shorten overly long emails
- Change a weak CTA
- Remove links from first email
- Speed up reply response time

**High Impact, High Effort (PLAN NEXT):**
- Build new email sequences from scratch
- Set up new sending domains and warm them up
- Rebuild prospect lists with better targeting
- Create industry-specific messaging variants
- Set up multi-channel sequences

**Low Impact, Low Effort (QUICK WINS):**
- Test a new subject line variant
- Adjust sending times
- Update email signature
- Add a P.S. line to emails

**Low Impact, High Effort (SKIP):**
- Building elaborate HTML email templates
- Creating complex lead scoring models before you have data
- Setting up advanced analytics before you have volume
- Perfecting copy before validating the market

---

## Running the Campaign Performance Analysis

### Step 1: Gather Your Data (5 minutes)

Collect these metrics for each active campaign:
- Emails sent (total)
- Emails delivered
- Bounces (hard and soft)
- Opens (unique)
- Replies (total)
- Positive replies
- Negative replies
- Meetings booked
- For LinkedIn: connection requests sent, accepted, DMs sent, DM replies, meetings booked

### Step 2: Calculate Your Rates (3 minutes)

For each campaign:
- Delivery rate = Delivered / Sent
- Open rate = Unique Opens / Delivered
- Reply rate = Total Replies / Delivered
- Positive reply rate = Positive Replies / Delivered
- Meeting book rate = Meetings Booked / Positive Replies
- Emails per meeting = Emails Sent / Meetings Booked

### Step 3: Identify the Bottleneck (5 minutes)

Walk through each stage top-down:
1. Is delivery rate >98%? If no, STOP — fix deliverability first.
2. Is open rate >40%? If no, focus on subject lines, sender identity, and timing.
3. Is total reply rate >5%? If no, focus on email body, relevance, and CTA.
4. Is positive reply rate >2%? If no, focus on messaging fit and offer.
5. Is meeting book rate >50% from positive replies? If no, focus on reply handling and booking process.

### Step 4: Root Cause Analysis (5 minutes)

For the identified bottleneck stage, review the 5 common reasons listed above. For each:
- Could this be the issue? (Yes/No/Maybe)
- What evidence supports this?
- What would I need to test to confirm?

### Step 5: Build the Fix Plan (5 minutes)

Using the Effort vs. Impact matrix:
1. List all potential fixes for the bottleneck
2. Categorize each fix by effort and expected impact
3. Select the top 1-3 fixes to implement this week
4. Define how you'll measure whether the fix worked
5. Set a review date (minimum 1 week, ideally 2-3 weeks)

---

## Output Format

Present the Campaign Performance Diagnostic as follows:

```
CAMPAIGN PERFORMANCE DIAGNOSTIC
Date: [DATE]
Analysis Period: [START DATE] to [END DATE]
Campaigns Analyzed: [NUMBER]

---

FUNNEL OVERVIEW
[For each campaign, show the full funnel with metrics at each stage]

Campaign: [NAME]
  Sent: [#] → Delivered: [#] ([%]) → Opened: [#] ([%]) → Replied: [#] ([%]) → Positive: [#] ([%]) → Meeting: [#] ([%])
  Emails per meeting: [#]

---

BOTTLENECK IDENTIFIED
Stage: [STAGE NAME]
Current Performance: [METRIC]
Target Benchmark: [BENCHMARK]
Gap: [DIFFERENCE]

---

ROOT CAUSE ANALYSIS
Most Likely Cause: [DESCRIPTION]
Evidence: [WHAT DATA SUPPORTS THIS]
Confidence: [HIGH/MEDIUM/LOW]

Secondary Cause: [DESCRIPTION]
Evidence: [WHAT DATA SUPPORTS THIS]

---

PRIORITIZED FIX RECOMMENDATIONS
1. [FIX #1] — Impact: [HIGH/MED/LOW], Effort: [HIGH/MED/LOW]
   How to implement: [SPECIFIC STEPS]
   Expected improvement: [ESTIMATE]
   Measurement plan: [HOW TO TRACK]

2. [FIX #2] — Impact: [HIGH/MED/LOW], Effort: [HIGH/MED/LOW]
   How to implement: [SPECIFIC STEPS]

3. [FIX #3] — Impact: [HIGH/MED/LOW], Effort: [HIGH/MED/LOW]
   How to implement: [SPECIFIC STEPS]

---

REVIEW SCHEDULE
Next check-in: [DATE — minimum 1 week out]
Success criteria: [SPECIFIC METRIC TARGET]
```

---

## Quality Checklist

Before delivering the diagnostic, verify:

- [ ] All active campaigns are included in the analysis
- [ ] Metrics are calculated correctly (double-check the math)
- [ ] Funnel stages are analyzed in order (top-down)
- [ ] The bottleneck identified is the EARLIEST broken stage, not just the most obvious one
- [ ] Root causes are specific and evidence-based, not generic guesses
- [ ] Fix recommendations are actionable with clear implementation steps
- [ ] Effort and impact are realistically assessed for each fix
- [ ] A review date and success criteria are defined
- [ ] Seasonal or market factors have been considered
- [ ] The 3-week rule has been respected (no premature conclusions on new campaigns)
- [ ] Red flag alerts have been checked and flagged if triggered
- [ ] LinkedIn metrics are included if LinkedIn outreach is active
- [ ] Campaign comparison is included if multiple campaigns are running
- [ ] The output is personalized to the user's actual data, not generic advice
