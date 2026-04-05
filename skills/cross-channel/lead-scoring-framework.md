---
skill: Lead Scoring Framework
phase: 5 — Cross-Channel Intelligence
depends_on: [ICP Architect, Omnichannel Sequence Designer]
estimated_time: 15-20 minutes
---

# Lead Scoring Framework

## Purpose

Build a lead scoring model that assigns every prospect a numerical score based on two dimensions — how well they match your Ideal Customer Profile (fit) and how actively they are engaging with your outreach (engagement). The result: every morning you open a prioritized list and know exactly who to follow up with first, second, and third. No more guessing. No more wasting time on cold leads while hot ones go stale.

---

## Why Lead Scoring Matters

### The Problem Without Scoring

Without a scoring system, your daily sales workflow looks like this:
- Scroll through your inbox and LinkedIn notifications randomly
- Follow up with whoever you happen to remember
- Spend 30 minutes crafting a personalized message for someone who was never going to buy
- Miss the prospect who opened your email 4 times and viewed your LinkedIn profile because you didn't notice the signals
- End the day feeling busy but unproductive

### The Reality of Outreach at Scale

When you're running 30-60 omnichannel sequences simultaneously, you might have:
- 15 prospects who opened an email this week
- 8 who accepted a LinkedIn connection
- 3 who replied (one positive, two objections)
- 2 who viewed your profile after receiving an email
- 1 who clicked a link

Without scoring, these signals drown in noise. With scoring, they surface instantly.

### What Scoring Gives You

1. **Prioritization.** Your A-leads get your best energy. Your D-leads get standard sequences.
2. **Time allocation.** Spend 60% of your time on A and B leads, 30% on C leads, 10% on D and F leads.
3. **Personalization decisions.** A-leads get bespoke messages. F-leads get templates.
4. **Pipeline velocity.** Hot leads move faster because you respond faster. Nothing goes stale.
5. **Pattern recognition.** Over time, you learn which Fit + Engagement combinations actually convert — and you optimize your ICP and messaging accordingly.

---

## Two-Axis Scoring Model

Every lead receives two scores that combine into one total:

```
TOTAL SCORE = FIT SCORE (0-50) + ENGAGEMENT SCORE (0-50)
```

**Why two axes?** Because fit and engagement tell you different things:
- A high-fit, low-engagement lead is a **perfect prospect who hasn't noticed you yet** — keep reaching out.
- A low-fit, high-engagement lead is an **interested person who probably won't buy** — qualify carefully before investing more time.
- A high-fit, high-engagement lead is your **golden opportunity** — drop everything and follow up.
- A low-fit, low-engagement lead is **not worth your time** — let the sequence run and move on.

---

## Fit Score Criteria (0-50 Points)

The Fit Score measures how closely a prospect matches your Ideal Customer Profile. This score is assigned ONCE when the lead enters your pipeline, and only updated if you learn new information about them.

### Positive Fit Signals

| Criteria | Exact Match | Close Match | No Match |
|---|---|---|---|
| **Job Title** | +10 (exact ICP title) | +5 (adjacent title, e.g., VP vs. Director) | 0 |
| **Company Size** | +10 (your sweet spot) | +5 (within range) | 0 |
| **Industry** | +10 (target industry) | +5 (adjacent/related) | 0 |
| **Geography** | +5 (target region/market) | +3 (secondary market) | 0 |
| **Budget Indicators** | +5 to +10 | — | 0 |

#### Job Title Scoring Guide

Map your ICP titles to a hierarchy:

```
Exact match (+10):
  [PRIMARY ICP TITLE] — e.g., VP of Marketing, Head of Sales, CEO

Adjacent match (+5):
  One level up or down, or a parallel role that also makes buying decisions
  — e.g., CMO (one up), Marketing Director (one down), Growth Lead (parallel)

No match (0):
  Roles that don't have decision-making authority or aren't in the buying process
  — e.g., Intern, Coordinator, unrelated department
```

#### Company Size Scoring Guide

Define your sweet spot based on what you learned in the ICP Architect skill:

```
Sweet spot (+10): [X] to [Y] employees (or revenue range)
  — These are the companies where your solution delivers the most value
    and where you have the most case studies/proof

Close range (+5): [A] to [X] or [Y] to [B] employees
  — These could work but may be slightly too small (budget concerns)
    or too large (long procurement cycles)

Out of range (0): Below [A] or above [B]
  — Not worth pursuing with current resources
```

#### Industry Scoring Guide

```
Target industry (+10): [PRIMARY INDUSTRY] — where most of your clients come from
Target industry (+10): [SECONDARY INDUSTRY] — another proven vertical

Adjacent industry (+5): [RELATED INDUSTRY] — shares similar challenges but
  you have less proof/experience

No match (0): Industries you've never served and don't understand
```

#### Budget Indicators (+5 to +10)

Budget signals that suggest the prospect can afford your service:

| Signal | Points | How to Find |
|---|---|---|
| Recent funding round | +10 | Crunchbase, LinkedIn news |
| Revenue above [THRESHOLD] | +10 | Company website, press, databases |
| Active job postings in your area | +5 | LinkedIn Jobs, careers page |
| Using competitor products | +5 | Technographic data, case studies, job posts |
| Publicly stated growth goals | +5 | Earnings calls, press releases, interviews |

### Anti-Fit Signals (Negative Points)

These are disqualifiers — signals that a lead should be deprioritized or removed.

| Signal | Points | Reason |
|---|---|---|
| Company too small (below minimum threshold) | -15 | Can't afford your service |
| Student or intern title | -20 | Not a decision maker |
| Competitor company | -20 | Will never buy |
| Industry you explicitly exclude | -10 | No relevant experience/fit |
| Located in a region you can't serve | -10 | Logistics/compliance barrier |
| Company in financial distress (layoffs, bankruptcy news) | -10 | Budget unlikely |
| Already a customer | -15 | Remove from outreach pipeline |
| Freelancer/solopreneur (if your minimum is team-based) | -10 | Below deal size minimum |

### Fit Score Calculation Example

**Prospect: Sarah Chen, Director of Marketing at a 200-person SaaS company in the US**

| Criteria | Assessment | Points |
|---|---|---|
| Job Title | Director of Marketing — adjacent to VP of Marketing (ICP) | +5 |
| Company Size | 200 employees — sweet spot is 100-500 | +10 |
| Industry | SaaS — primary target industry | +10 |
| Geography | US — target market | +5 |
| Budget Indicators | Series B funded, hiring 3 marketing roles | +10 |
| Anti-Fit Signals | None | 0 |
| **TOTAL FIT SCORE** | | **40/50** |

---

## Engagement Score Criteria (0-50 Points)

The Engagement Score is dynamic — it changes as the prospect interacts (or doesn't interact) with your outreach. Update it daily or whenever you notice new signals.

### Email Engagement Signals

| Signal | Points | Notes |
|---|---|---|
| Email opened | +2 per open (max +8) | Multiple opens = strong interest. Cap to avoid over-scoring automated previews |
| Email replied (positive) | +15 | Any reply expressing interest, asking questions, or requesting more info |
| Email replied (objection) | +5 | "Not interested" or "bad timing" — still engaged enough to reply |
| Email replied (negative/unsubscribe) | -10 | Remove from sequence, respect the request |
| Email link clicked | +5 per click (max +10) | Clicked your resource, calendar link, or website |
| Email forwarded | +10 | Shared your message with a colleague — very strong signal |

### LinkedIn Engagement Signals

| Signal | Points | Notes |
|---|---|---|
| Connection request accepted | +5 | Baseline positive signal |
| LinkedIn DM replied (positive) | +10 | Conversational reply, asking questions |
| LinkedIn DM replied (neutral) | +3 | "Thanks" or short acknowledgment |
| LinkedIn profile viewed your profile | +3 | They're researching you — curiosity signal |
| LinkedIn engaged with YOUR content | +5 | Liked, commented, or shared your post |
| LinkedIn voice note listened to | +5 | If platform provides this data |
| LinkedIn DM — sent voice note back | +10 | High engagement signal |

### Website and Content Engagement Signals

| Signal | Points | Notes |
|---|---|---|
| Visited your website | +5 | Requires website analytics / tracking pixel |
| Visited pricing page | +10 | Strong buying intent signal |
| Downloaded a resource | +10 | Lead magnet, whitepaper, case study |
| Watched a video (>50%) | +5 | Engaged with longer-form content |
| Filled out a form | +15 | Actively requesting information |

### Ultimate Engagement Signal

| Signal | Points | Notes |
|---|---|---|
| Booked a call/meeting | +25 | This is the goal — they've self-selected |

### Engagement Score Calculation Example

**Prospect: Sarah Chen — Week 2 of omnichannel sequence**

| Signal | Occurrence | Points |
|---|---|---|
| Email 1 opened | 3 times | +6 |
| Email 2 opened | 1 time | +2 |
| Email 2 link clicked | 1 time | +5 |
| LinkedIn connection accepted | Yes | +5 |
| Viewed your LinkedIn profile | Yes | +3 |
| DM replied | Not yet | 0 |
| Website visited | Yes (from email link) | +5 |
| **TOTAL ENGAGEMENT SCORE** | | **26/50** |

**Sarah's TOTAL SCORE: 40 (Fit) + 26 (Engagement) = 66 — Grade B (Warm)**

---

## Lead Grades and Action Protocols

### Grade A: Hot (80-100 Points)

**What this means:** This is a high-fit prospect who is actively engaging with your outreach. They are showing clear buying signals across one or more channels.

**Response time:** Within 1 hour during business hours. If the signal comes after hours, first thing the next morning.

**Action protocol:**
1. Stop the automated sequence immediately — switch to 100% personalized outreach
2. Reference their specific engagement: "I noticed you checked out [RESOURCE] — what stood out to you?"
3. Move to a direct call request within 1-2 messages
4. Research their company deeply (10-15 min): recent news, challenges, competitors, org chart
5. Prepare a custom value proposition specific to their situation
6. If they've replied, respond within the hour. If they haven't but signals are strong, send a personalized DM or email that acknowledges a specific trigger: "Saw [COMPANY] just [TRIGGER EVENT] — congrats. I had a thought about how [YOUR SERVICE AREA] could accelerate that."

**Daily time allocation:** 40-50% of your selling time should go to A-leads.

### Grade B: Warm (60-79 Points)

**What this means:** Either a great-fit prospect with moderate engagement, or a moderate-fit prospect with strong engagement. Worth investing significant personalization effort.

**Response time:** Within 24 hours.

**Action protocol:**
1. Continue the omnichannel sequence but add extra personalization to each touchpoint
2. Research their company moderately (5-10 min) and reference specifics in your next message
3. Increase LinkedIn content engagement — comment on their posts more frequently
4. If they haven't replied after 3 touchpoints, try a different angle or channel
5. Consider sending a personalized video or voice note to stand out
6. Track closely — a single additional engagement signal could push them to Grade A

**Daily time allocation:** 25-30% of your selling time.

### Grade C: Interested (40-59 Points)

**What this means:** There's something there — either decent fit with some engagement, or one dimension is strong while the other is weak. Worth continued effort but not maximum investment.

**Response time:** Within 48 hours.

**Action protocol:**
1. Continue standard omnichannel sequence
2. Add light personalization (first name, company name, one specific reference) but don't deep-research
3. Test different angles — if pain point A didn't resonate, try pain point B
4. Review their fit score: if fit is high but engagement is low, the problem is your messaging. If engagement is high but fit is low, qualify before investing more.
5. Batch your C-lead follow-ups into a dedicated 30-minute block

**Daily time allocation:** 15-20% of your selling time.

### Grade D: Monitoring (20-39 Points)

**What this means:** Low fit, low engagement, or both. Not worth personalized effort right now, but shouldn't be abandoned — situations change.

**Response time:** Standard sequence timing (no acceleration).

**Action protocol:**
1. Keep them in the standard automated/templated sequence
2. Do not spend time researching or personalizing beyond basic tokens
3. If they suddenly show a strong engagement signal (reply, call booking), re-score and potentially upgrade
4. After the sequence completes, move to long-term nurture (monthly content, newsletter)
5. Review D-leads monthly — some may have changed roles, companies, or situations

**Daily time allocation:** 5-10% of your selling time.

### Grade F: Cold (0-19 Points)

**What this means:** Poor fit, no engagement, or anti-fit signals detected. Continuing to pursue is a waste of resources.

**Response time:** None — standard sequence only.

**Action protocol:**
1. Let the standard sequence complete on autopilot
2. Do not follow up manually beyond the sequence
3. After sequence completion, archive the lead
4. If anti-fit signals are present (competitor, wrong geography, student), remove from sequence immediately
5. Review F-leads quarterly — rarely, someone re-enters your ICP due to a job change

**Daily time allocation:** 0%.

---

## Lead Score Summary Matrix

| Grade | Score | Response Time | Personalization | Daily Time % | Next Action |
|---|---|---|---|---|---|
| A | 80-100 | < 1 hour | Deep — fully custom messages | 40-50% | Direct call request |
| B | 60-79 | < 24 hours | Moderate — personalized sequences | 25-30% | Enhanced sequence + extras |
| C | 40-59 | < 48 hours | Light — template + specific references | 15-20% | Standard sequence, test angles |
| D | 20-39 | Sequence pace | Minimal — templates only | 5-10% | Autopilot, review monthly |
| F | 0-19 | None | None | 0% | Archive after sequence |

---

## Implementing Scoring Without Expensive Tools

### The Spreadsheet Scoring System

You do not need a $500/month sales tool to run lead scoring. A well-structured spreadsheet does the job for up to 200 active leads.

#### Spreadsheet Structure

**Tab 1: Scoring Criteria**

| Category | Criteria | Exact Match | Close Match | No Match |
|---|---|---|---|---|
| Title | [YOUR ICP TITLE] | 10 | 5 | 0 |
| Size | [YOUR SWEET SPOT] | 10 | 5 | 0 |
| Industry | [YOUR TARGET INDUSTRY] | 10 | 5 | 0 |
| Geography | [YOUR TARGET REGION] | 5 | 3 | 0 |
| Budget | [YOUR INDICATORS] | 10 | 5 | 0 |

**Tab 2: Lead Tracker (Main Tab)**

| Column | Formula / Input |
|---|---|
| A: Prospect Name | Manual |
| B: Company | Manual |
| C: Title | Manual |
| D: Title Score | VLOOKUP or manual (10, 5, or 0) |
| E: Size Score | Manual (10, 5, or 0) |
| F: Industry Score | Manual (10, 5, or 0) |
| G: Geography Score | Manual (5, 3, or 0) |
| H: Budget Score | Manual (5-10 or 0) |
| I: Anti-Fit | Manual (-10 to -20 or 0) |
| **J: FIT SCORE** | **=SUM(D:I)** |
| K: Email Opens | Manual count |
| L: Email Open Score | =MIN(K*2, 8) |
| M: Email Replies | Manual |
| N: Email Reply Score | Manual (15 positive, 5 objection) |
| O: Link Clicks | Manual count |
| P: Link Click Score | =MIN(O*5, 10) |
| Q: LI Connected | Y/N |
| R: LI Connection Score | =IF(Q="Y", 5, 0) |
| S: LI DM Reply | Y/N |
| T: LI DM Score | Manual (10 positive, 3 neutral) |
| U: Profile View | Y/N |
| V: Profile View Score | =IF(U="Y", 3, 0) |
| W: Website Visit | Y/N |
| X: Website Score | =IF(W="Y", 5, 0) |
| Y: Resource Download | Y/N |
| Z: Resource Score | =IF(Y="Y", 10, 0) |
| AA: Call Booked | Y/N |
| AB: Call Score | =IF(AA="Y", 25, 0) |
| **AC: ENGAGEMENT SCORE** | **=SUM(L,N,P,R,T,V,X,Z,AB)** |
| **AD: TOTAL SCORE** | **=J+AC** |
| **AE: GRADE** | **=IFS(AD>=80,"A",AD>=60,"B",AD>=40,"C",AD>=20,"D",TRUE,"F")** |
| AF: Last Updated | Date |
| AG: Next Action | Manual |

**Tab 3: Dashboard**

Use pivot tables or COUNTIF formulas to show:
- Number of leads per grade
- Average score by source
- Engagement score distribution
- Leads that changed grade this week

### Daily Scoring Workflow

1. **Morning (5 min):** Open your email tool and LinkedIn. Note any new opens, clicks, replies, connection acceptances, profile views.
2. **Update spreadsheet (5 min):** Enter new signals into the relevant columns. Scores and grades auto-calculate.
3. **Sort by grade (1 min):** Sort column AE (Grade) to see your A-leads first, then B, etc.
4. **Act accordingly:** Follow the action protocol for each grade.

---

## Scoring Maintenance

### Score Decay

Engagement signals lose relevance over time. A prospect who opened your email 30 days ago is not as hot as one who opened it today.

**Decay schedule:**
- After 7 days with no new engagement: reduce Engagement Score by 20%
- After 14 days with no new engagement: reduce Engagement Score by 50%
- After 30 days with no new engagement: reset Engagement Score to 0

**How to implement decay in your spreadsheet:**
- Add a "Last Engagement Date" column
- Weekly, check the gap between today and Last Engagement Date
- Apply decay multipliers manually or with formulas: `=IF((TODAY()-LastEngagementDate)>30, 0, IF((TODAY()-LastEngagementDate)>14, EngagementScore*0.5, IF((TODAY()-LastEngagementDate)>7, EngagementScore*0.8, EngagementScore)))`

### When to Re-Score Fit

Re-evaluate the Fit Score when you learn new information:
- They changed jobs (new title, new company)
- Their company raised funding or went through layoffs
- You discovered they use a competitor product
- Your own ICP definition evolved based on closed deals

### When to Reset Entirely

- After a complete sequence with zero engagement (reset to 0, move to archive)
- If the lead re-appears after 6+ months (start fresh — old data is stale)
- If your ICP criteria change significantly (re-score all active leads)

---

## How Scoring Changes Your Daily Workflow

### Before Scoring (Reactive)

```
9:00 AM — Open inbox, reply to whoever emailed back
9:30 AM — Check LinkedIn, respond to random DMs
10:00 AM — Look at spreadsheet, pick some people to follow up with
10:30 AM — Realize you forgot about someone from last week
11:00 AM — Send 5 generic follow-ups
11:30 AM — Check inbox again
12:00 PM — Wonder why meetings aren't booking
```

### After Scoring (Proactive)

```
9:00 AM — Open scoring spreadsheet, check today's A-leads (2-3 people)
9:15 AM — Craft deeply personalized messages for each A-lead (high ROI)
9:45 AM — Check B-leads (5-8 people), send personalized sequences
10:15 AM — Batch C-lead follow-ups (10-15 templates with light personalization)
10:45 AM — Let D and F leads run on autopilot
11:00 AM — Update scores based on morning signals
11:15 AM — Focus remaining time on new prospecting to fill the top of funnel
12:00 PM — More meetings booked because the right leads got the right attention
```

---

## Output: Your Custom Lead Scoring Model

Based on your ICP (from the ICP Architect skill) and your available tracking tools, here is your personalized scoring model.

### Your Fit Score Criteria

| Criteria | Your Exact Match (+10) | Your Close Match (+5) | Your Anti-Fit |
|---|---|---|---|
| Job Title | [PRIMARY ICP TITLE] | [ADJACENT TITLES] | [EXCLUDED TITLES] |
| Company Size | [SWEET SPOT RANGE] | [ACCEPTABLE RANGE] | [TOO SMALL / TOO LARGE] |
| Industry | [PRIMARY INDUSTRY] | [ADJACENT INDUSTRIES] | [EXCLUDED INDUSTRIES] |
| Geography | [TARGET REGION] | [SECONDARY REGIONS] | [EXCLUDED REGIONS] |
| Budget | [PRIMARY INDICATORS] | [SECONDARY INDICATORS] | [RED FLAGS] |

### Your Engagement Score Criteria

[Adapted based on which tools/channels you have access to. If you don't track website visits, those points get redistributed. If you use LinkedIn heavily but email lightly, LinkedIn signals are weighted higher.]

| Signal | Points | Your Tracking Method |
|---|---|---|
| Email opened | +2 per (max +8) | [YOUR EMAIL TOOL] |
| Email replied (positive) | +15 | [YOUR EMAIL TOOL] |
| Email link clicked | +5 per (max +10) | [YOUR EMAIL TOOL] |
| LI connection accepted | +5 | LinkedIn notifications |
| LI DM replied | +10 | LinkedIn DMs |
| LI profile view | +3 | LinkedIn "Who viewed your profile" |
| Website visit | +5 | [YOUR ANALYTICS TOOL or N/A] |
| Resource download | +10 | [YOUR TRACKING METHOD or N/A] |
| Call booked | +25 | Calendar / booking tool |

### Your Grade Definitions and Action Protocols

[Customized based on your daily availability and sales bandwidth. If you have 1 hour/day for sales, the thresholds and time allocations are adjusted accordingly.]

### Your Scoring Spreadsheet

[Link to a pre-built template or instructions for building the spreadsheet with your specific criteria pre-filled.]

---

## Quality Checklist

Before deploying your lead scoring model, verify:

- [ ] Fit Score criteria are aligned with your validated ICP from the ICP Architect skill
- [ ] Engagement Score signals are limited to what you can actually track (don't score website visits if you don't have analytics)
- [ ] Anti-fit signals are defined and aggressive enough (don't waste time on leads that will never convert)
- [ ] Grade thresholds make sense: run 10 current prospects through the model and check — do the grades match your gut feeling?
- [ ] Action protocols are realistic for your daily schedule (if you have 1 hour/day, you can't deep-research 5 A-leads)
- [ ] Score decay is set up so stale leads don't sit at artificially high scores
- [ ] You have a clear workflow: when do you update scores? When do you check grades?
- [ ] The spreadsheet (or CRM) is set up and tested with sample data before you start sequences
- [ ] You've identified which engagement signals you currently CANNOT track and have a plan to close those gaps
- [ ] You've committed to reviewing and recalibrating the model after your first 50 scored leads — initial weights are educated guesses that need real-world validation
