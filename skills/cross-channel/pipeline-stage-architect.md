---
skill: Pipeline Stage Architect
phase: 5 — Cross-Channel Intelligence
depends_on: [ICP Architect, Lead Scoring Framework]
estimated_time: 15-20 minutes
---

# Pipeline Stage Architect

## Purpose

Design a structured pipeline that maps every lead from "cold name on a list" to "meeting on the calendar." Clear stages give you visibility into where your leads are, where they're getting stuck, and what actions move them forward. Without defined stages, your pipeline is a black box. With them, it becomes a machine you can measure, diagnose, and optimize.

---

## Why Pipeline Stages Matter

### You Can't Improve What You Can't Measure

Most business owners running outreach have a vague sense of how things are going. They know they've "sent some emails" and "have a few conversations going." But when asked specific questions, they struggle:

- How many leads entered your pipeline this week?
- What percentage of first touches turn into conversations?
- Where are leads most likely to stall out?
- How many prospects do you need to contact to book one meeting?
- Are things getting better or worse compared to last month?

Pipeline stages answer all of these questions with data, not gut feeling.

### The Funnel Visualization

Every pipeline is a funnel — wide at the top, narrow at the bottom. At each stage, some leads advance and some drop off. Understanding the shape of your funnel tells you where to focus:

```
Prospect Identified          [100 leads]
        |
        v
First Touch Sent             [100 leads] — 100% activation
        |
        v
Engaged                      [35 leads]  — 35% engagement rate
        |
        v
Conversation Started         [12 leads]  — 34% of engaged
        |
        v
Interest Confirmed           [8 leads]   — 67% of conversations
        |
        v
Call Requested               [6 leads]   — 75% of interested
        |
        v
Call Booked                  [4 leads]    — 67% of requested
        |
        v
Completed / No-Show          [3 show, 1 no-show]
```

**In this example:** 100 prospects at the top produce 4 booked calls and 3 completed calls. That's a 3% overall conversion rate — typical for B2B outreach. The data also reveals that the biggest drop-off is between First Touch and Engaged (65% lost). That tells you: your opening messages need work.

---

## The Sales OS Pipeline Stages

These eight stages cover the outreach-to-booked-call journey. This pipeline intentionally stops at "Call Booked" — what happens on the call (proposal, close, etc.) is out of scope for the outreach system.

---

### Stage 1: Prospect Identified

**Definition:** A person who matches your ICP criteria has been found and added to your outreach list. No outreach has been sent yet.

**Entry criteria:**
- Matches ICP Fit Score threshold (minimum score of 20+ from the Lead Scoring Framework)
- Has a valid email address or LinkedIn profile (or both)
- Not a duplicate of an existing lead in your pipeline
- Not on your "do not contact" list (previous opt-outs, competitors, existing clients)

**Key actions at this stage:**
- Verify contact information (email validity, LinkedIn profile accuracy)
- Assign initial Fit Score based on available data
- Assign to an omnichannel sequence variant (Aggressive, Relationship, or Hybrid)
- Add to your tracking spreadsheet or CRM with all relevant fields populated

**Expected time in stage:** 0-3 days (batch prospecting, then activate)

**Expected conversion to next stage:** 95-100% (nearly all identified prospects get a first touch — the only reason they wouldn't is if you discover bad data)

**Red flags:**
- Leads sitting in this stage for more than 5 days (you're prospecting but not activating — start outreach)
- Large volume of prospects being disqualified at this stage (your sourcing criteria are too broad)

---

### Stage 2: First Touch Sent

**Definition:** The first outreach message has been delivered — either an email or a LinkedIn connection request (whichever comes first in your sequence).

**Entry criteria:**
- At least one outreach message has been sent AND confirmed delivered (not bounced, not "pending" connection)
- The prospect's record is updated with the date, channel, and message content of the first touch

**Key actions at this stage:**
- Monitor for immediate engagement signals (email opens within 24 hours, LinkedIn connection acceptance)
- If email bounced: find alternate email, try LinkedIn-first approach, or disqualify
- If LinkedIn connection request is pending after 7 days: send a follow-up request or pivot to email-only
- Continue the omnichannel sequence as designed

**Expected time in stage:** 1-7 days (most engagement signals appear within the first week)

**Expected conversion to next stage:** 25-40% (this is the biggest drop-off in most pipelines — expect 60-75% of first touches to generate zero engagement)

**Benchmark engagement rates by channel:**
| Channel | Good | Average | Needs Work |
|---|---|---|---|
| Email open rate | >50% | 30-50% | <30% |
| Email reply rate | >5% | 2-5% | <2% |
| LinkedIn acceptance rate | >30% | 15-30% | <15% |

**Red flags:**
- Open rates below 25% (subject lines or sender reputation problem)
- Connection acceptance below 10% (your profile needs optimization or your notes are too salesy)
- High bounce rates on email (>5% — list quality issue)
- Leads sitting in this stage for 14+ days with zero signal (sequence may not be reaching them)

---

### Stage 3: Engaged

**Definition:** The prospect has shown at least one engagement signal — they've done something that indicates awareness of your outreach, even if they haven't responded directly.

**Entry criteria (any ONE of the following):**
- Opened your email (at least 1 time)
- Clicked a link in your email
- Accepted your LinkedIn connection request
- Viewed your LinkedIn profile (after you sent outreach)
- Liked or commented on your LinkedIn content (after you engaged with theirs)

**Key actions at this stage:**
- Update their Engagement Score in your Lead Scoring Framework
- If they're now a B-grade or above, increase personalization on remaining sequence touchpoints
- If the engagement signal is strong (multiple opens, link click, profile view), consider accelerating the sequence (move the next touchpoint up by 1-2 days)
- Continue the omnichannel sequence — engagement is encouraging but not yet a conversation

**Expected time in stage:** 3-10 days

**Expected conversion to next stage:** 25-35% (most engaged leads do not convert to conversations — they remain passive observers)

**Red flags:**
- Many leads are "engaged" (opening emails, accepting connections) but none are moving to "Conversation Started" (your CTAs are weak or your value proposition isn't compelling enough)
- Engagement score is being inflated by automated email previews (some email clients auto-open — look for patterns)
- Leads who engage on LinkedIn but not email (or vice versa) may need a channel-specific approach

---

### Stage 4: Conversation Started

**Definition:** A two-way exchange has begun. The prospect has actively communicated back to you — not just opened or clicked, but actually responded.

**Entry criteria (any ONE of the following):**
- Replied to an email (any response other than an unsubscribe or "remove me")
- Replied to a LinkedIn DM
- Sent you a LinkedIn connection message
- Responded to a voice note
- Filled out a form on your website referencing your outreach

**Key actions at this stage:**
- **CRITICAL: Pause the automated sequence immediately.** From this point forward, every message is personal and context-aware.
- Respond within the channel they used (Channel Priority Rules from the Omnichannel Sequence Designer)
- If their reply is positive: move toward qualifying their interest (next stage)
- If their reply is an objection: handle it with a value-driven response, then re-assess
- If their reply is neutral ("thanks for reaching out" / "tell me more"): provide a concise value statement and ask a qualifying question
- Update Lead Score — they're likely a B or A by now

**Expected time in stage:** 1-5 days (conversations that stall beyond 5 days need re-engagement)

**Expected conversion to next stage:** 50-65% (once someone is actually talking to you, roughly half will express genuine interest)

**Response templates by reply type:**

**Positive reply: "Sounds interesting, tell me more"**
```
Great to hear, [FIRST NAME]. Rather than sending a wall of text, the
quickest way to see if there's a fit would be a 15-minute call where I
can learn more about [COMPANY]'s situation and share how we've helped
[SIMILAR COMPANIES].

Would [DAY] or [DAY] work for a quick chat?
```

**Objection reply: "We already have a solution for this"**
```
Totally makes sense, [FIRST NAME] — most [ICP TITLE]s I talk to have
something in place. Curious: how's it working? Most of the companies
we work with came to us not because they had nothing, but because their
current approach was [COMMON LIMITATION].

Not suggesting you switch anything — just curious if that resonates.
```

**Neutral reply: "Thanks for reaching out"**
```
Of course! To give you the quick version: we help [ICP TITLE]s at
[COMPANY TYPE] companies [CORE OUTCOME] by [HIGH-LEVEL METHOD].

Recently, we helped [SIMILAR COMPANY DESCRIPTION] go from [BEFORE
STATE] to [AFTER STATE] in [TIMEFRAME].

Would it be worth a 15-minute call to see if something similar could
work for [COMPANY]?
```

**Red flags:**
- Conversations going back and forth for more than 5 messages without progressing (you're stuck in "email tennis" — push for a call)
- Prospects asking many questions but never agreeing to a call (they may be gathering information with no intent to buy — qualify harder)
- Long gaps between replies (3+ days) — they're losing interest, escalate urgency or add a new value angle

---

### Stage 5: Interest Confirmed

**Definition:** The prospect has explicitly expressed interest in learning more about how you can help. They've moved beyond polite engagement into active curiosity.

**Entry criteria (any ONE of the following):**
- Asked specific questions about your service, pricing, process, or results
- Said something like "This could be useful," "We've been thinking about this," "Tell me more about how it works"
- Requested a resource, case study, or reference
- Introduced you to a colleague ("Let me loop in our [OTHER TITLE]")

**Key actions at this stage:**
- This is the moment to transition from "building interest" to "booking the call"
- Provide concise answers to their questions — do NOT info-dump
- After answering, always redirect to a call: "Happy to dive deeper on [TOPIC] — it's usually easier to cover in a quick call. How's [DAY]?"
- If they introduced a colleague, treat the new person as a warm lead and include them in the call invite
- Research the company more deeply (10-15 minutes) to prepare for the call conversation

**Expected time in stage:** 1-3 days (strike while the iron is hot)

**Expected conversion to next stage:** 70-80% (interested prospects usually agree to a call when asked directly)

**Red flags:**
- Prospect keeps asking questions but won't commit to a call (after answering 2-3 questions, make the ask directly: "I could answer these much better with some context about your specific situation. Can we jump on a quick call?")
- Prospect said "Let me think about it" (follow up in 2 days with a new piece of value; if they say it again, ask directly what's holding them back)
- Prospect goes silent after expressing interest (re-engage within 48 hours with a brief check-in referencing their last question)

---

### Stage 6: Call Requested

**Definition:** You have explicitly asked for a call, and the prospect has not said no. The request is active — either they said "let me check my schedule," they didn't respond to the request yet, or they tentatively agreed but no date is set.

**Entry criteria:**
- You asked for a meeting and received a response that is NOT a "no"
- Examples: "Let me check my calendar," "Maybe next week," "Send me a link," or no response yet to the ask (within 48 hours)

**Key actions at this stage:**
- If they said "send me a link": Send your calendar link IMMEDIATELY (within minutes, not hours). Include 2-3 specific time options as well ("In case the link is easier, I'm also free [DAY at TIME] or [DAY at TIME].")
- If they said "maybe next week": Follow up on Monday morning of that week with specific options
- If they said "let me check my schedule": Follow up in 24 hours: "Hey [FIRST NAME], any luck finding a time? Happy to work around your schedule."
- If no response to the call request within 48 hours: Follow up once. If still no response after another 48 hours, try the other channel.

**Expected time in stage:** 1-5 days

**Expected conversion to next stage:** 60-70% (some prospects agree in principle but never actually book — persistence here matters)

**Red flags:**
- Prospect said "send me a link" but never booked (follow up: "Noticed you haven't had a chance to grab a time — here are a few options: [SPECIFIC TIMES]. Any of these work?")
- More than 3 follow-ups about scheduling with no resolution (they may not want the call but are too polite to say no — give them an out: "Totally understand if the timing isn't right. Want me to circle back in [TIMEFRAME] instead?")
- The prospect keeps pushing the date further out (each push reduces the likelihood of it happening — try to lock in a date within 7 days)

---

### Stage 7: Call Booked

**Definition:** A meeting is confirmed on the calendar. Both parties have a date, time, and meeting link.

**Entry criteria:**
- Calendar invite sent AND accepted (or time confirmed via message)
- Meeting link / dial-in included
- Both parties have acknowledged the meeting

**Key actions at this stage:**
- Send a confirmation message: "Looking forward to our call on [DAY] at [TIME]. Here's what I was thinking we could cover: [1-2 bullet points]. If there's anything specific you'd like to discuss, let me know!"
- Pre-call research (15-20 minutes): deep dive into their company, recent news, competitors, org chart, and any signals from your outreach history
- Prepare a call agenda and discovery questions specific to their situation
- Send a reminder 24 hours before: "Quick reminder about our call tomorrow at [TIME]. Looking forward to it!"
- Send a reminder 1 hour before (optional, for high-value leads): "See you in an hour! [MEETING LINK]"
- Have your CRM / notes open during the call with all outreach history visible

**Expected time in stage:** 1-7 days (however long until the meeting date)

**Expected conversion to completed call:** 70-85% (15-30% no-show rate is typical)

**Red flags:**
- No calendar acceptance after 24 hours (resend the invite, confirm via the channel you've been communicating on)
- Meeting is more than 10 days out (likelihood of no-show increases dramatically — try to pull it closer)
- Prospect reschedules once (that's normal). Prospect reschedules twice (yellow flag — confirm their interest). Prospect reschedules three times (red flag — suggest a shorter call format or ask directly if they'd prefer to postpone)

---

### Stage 8: No-Show

**Definition:** The prospect missed the scheduled call without canceling or rescheduling.

**Entry criteria:**
- Meeting time has passed
- Prospect did not join within 10 minutes of the scheduled start time
- No cancellation or reschedule message was received

**Key actions at this stage:**

**Immediate (within 30 minutes of the missed call):**
```
Hey [FIRST NAME] — I was on the line for our call at [TIME] but didn't
see you join. No worries at all — things come up.

Want to reschedule? I'm free [TIME OPTION 1] and [TIME OPTION 2]
this week.
```

**24 hours after no-show (if no response):**
```
Hi [FIRST NAME] — just circling back on our missed call yesterday.
Totally understand if something came up.

I've got a few openings this week: [CALENDAR LINK]. Happy to find a
time that works.
```

**72 hours after no-show (final attempt):**
```
Hey [FIRST NAME] — I know schedules get hectic, so I'll keep this
short. If you're still interested in discussing [TOPIC], I'm happy
to find a new time.

If the timing isn't right, no problem at all — just let me know and
I'll circle back in a few months.
```

**Expected conversion to rebooked call:** 30-50% (many no-shows do rebook if you follow up promptly and without guilt-tripping)

**Red flags:**
- Serial no-shows (booked and missed twice) — deprioritize significantly. One more attempt, then archive.
- No-showed AND not responding to follow-ups — move to long-term nurture after the 72-hour message

---

## Stage Transition Rules

### Forward Movement

| From | To | Trigger |
|---|---|---|
| Prospect Identified | First Touch Sent | First outreach message delivered |
| First Touch Sent | Engaged | Any engagement signal detected |
| Engaged | Conversation Started | Prospect replies (any channel) |
| Conversation Started | Interest Confirmed | Prospect asks questions or expresses interest |
| Interest Confirmed | Call Requested | You ask for a meeting and don't get a "no" |
| Call Requested | Call Booked | Date, time, and link confirmed |
| Call Booked | Completed or No-Show | Meeting happens or doesn't |

### Backward Movement

| From | To | Trigger |
|---|---|---|
| Conversation Started | Engaged | Prospect goes silent for 7+ days after initial reply |
| Interest Confirmed | Conversation Started | Prospect says "not now" or "maybe later" |
| Call Requested | Interest Confirmed | Prospect declines the meeting but stays engaged |
| Call Booked | Call Requested | Prospect cancels without rescheduling |
| No-Show | Call Booked | Prospect rebooks the call |

### Removal From Pipeline

| Trigger | Action |
|---|---|
| Prospect requests to be removed / unsubscribes | Remove immediately, add to "do not contact" list |
| Prospect is confirmed competitor | Remove immediately |
| Prospect has completed full sequence with zero engagement (F-grade) | Move to archive / long-term nurture list |
| Prospect has no-showed twice with no re-engagement | Move to archive |
| Contact information is invalid (bounced email, deleted LinkedIn) | Remove or replace with updated info |

---

## Pipeline Metrics to Track

### Core Metrics (Track Weekly)

| Metric | Formula | What It Tells You |
|---|---|---|
| **Total leads per stage** | Count of leads in each stage | Pipeline shape and distribution |
| **Stage conversion rate** | (Leads entering next stage / Leads in current stage) x 100 | Where leads are dropping off |
| **Pipeline velocity** | Average days a lead spends in each stage | How fast leads move through |
| **Outreach-to-meeting rate** | (Calls booked / First touches sent) x 100 | Overall pipeline efficiency |
| **No-show rate** | (No-shows / Calls booked) x 100 | Call confirmation process quality |

### Pipeline Health Indicators

**Healthy pipeline shape:** Wide at the top, gradually narrowing. Each stage has fewer leads than the one before it.

```
HEALTHY                    UNHEALTHY (Bottleneck)
===========================     ===========================
Identified:  ########           Identified:  ########
First Touch: #######            First Touch: #######
Engaged:     ####               Engaged:     #######    <-- stuck here
Conversation:###                Conversation:#
Interest:    ##                 Interest:    #
Call Req:    ##                 Call Req:    #
Booked:      #                  Booked:      #
```

**Bottleneck identification:** If any stage has MORE leads than the stage above it (or a disproportionately high number), you have a bottleneck. Common bottlenecks:

| Bottleneck Location | Likely Cause | Fix |
|---|---|---|
| First Touch > Engaged | Messaging doesn't resonate | Rewrite subject lines, opening hooks, LinkedIn notes |
| Engaged > Conversation | CTAs are weak, value prop unclear | Strengthen calls-to-action, add more value before the ask |
| Conversation > Interest | Poor qualification or follow-up | Ask better questions, respond faster, add social proof |
| Interest > Call Booked | Weak close or scheduling friction | Be more direct in asking, reduce friction (send calendar link immediately) |
| Call Booked > Completed | No-shows, scheduling too far out | Better confirmation sequences, book calls sooner |

---

## Setting Up Pipeline Tracking

### Option 1: Spreadsheet-Based Pipeline Tracker

**Tab: Pipeline View**

| Column | Description |
|---|---|
| Prospect Name | Full name |
| Company | Company name |
| Current Stage | Dropdown: the 8 stages |
| Stage Entry Date | When they entered the current stage |
| Days in Stage | =TODAY() - Stage Entry Date |
| Lead Grade | From Lead Scoring Framework (A/B/C/D/F) |
| Next Action | What to do next |
| Next Action Date | When to do it |
| Channel | Primary channel (Email / LinkedIn / Both) |
| Sequence Variant | Aggressive / Relationship / Hybrid |
| Notes | Context, conversation history summary |
| Last Updated | Date of last activity |

**Tab: Stage Summary Dashboard**

| Stage | Count | Avg Days in Stage | Conv. Rate to Next |
|---|---|---|---|
| Prospect Identified | =COUNTIF(Stage, "Identified") | =AVERAGEIF(...) | =Next/Current |
| First Touch Sent | ... | ... | ... |
| Engaged | ... | ... | ... |
| Conversation Started | ... | ... | ... |
| Interest Confirmed | ... | ... | ... |
| Call Requested | ... | ... | ... |
| Call Booked | ... | ... | ... |
| No-Show | ... | ... | ... |

### Option 2: CRM-Based Pipeline

Most CRMs (HubSpot, Pipedrive, Close, Salesforce) have built-in pipeline features. Set up:
- A deal pipeline with the 8 stages as columns
- Required fields when moving a deal to a new stage (ensures data quality)
- Automated notifications when a deal has been in a stage too long
- Dashboard reports showing conversion rates and velocity

**HubSpot (Free Tier):** Supports up to 1 pipeline with custom stages. Perfect for solopreneurs and small teams.

**Pipedrive:** Visual pipeline with drag-and-drop. Strong for sales-focused workflows. Starts at ~$15/month.

**Close:** Built for outreach-heavy teams. Includes email sequencing. Starts at ~$29/month.

---

## Weekly Pipeline Review Process

### The 15-Minute Weekly Review

Every week (pick a consistent day — Friday afternoon or Monday morning), answer these questions:

**1. Volume Check (2 minutes)**
- How many new prospects were identified this week?
- How many first touches were sent?
- Am I hitting my weekly outreach targets?

**2. Flow Check (3 minutes)**
- How many leads moved forward a stage this week?
- How many leads moved backward or were removed?
- Are there bottlenecks forming (stages where leads are piling up)?

**3. Velocity Check (3 minutes)**
- What's the average time leads are spending in each stage?
- Are any stages slowing down compared to last week?
- Are there specific leads that have been stuck for too long?

**4. Outcome Check (3 minutes)**
- How many meetings were booked this week?
- How many were completed vs. no-showed?
- What's my outreach-to-meeting conversion rate this week vs. last?

**5. Action Plan (4 minutes)**
- What are the top 3 actions I need to take next week based on this data?
- Which A and B leads need immediate attention?
- What messaging or process change should I test to address any bottleneck?

---

## Pipeline Capacity Planning

### Working Backward From Your Revenue Goal

To figure out how many prospects you need at the top of your pipeline, work backward from your revenue target.

**Step 1: Define your monthly revenue goal**
```
Monthly revenue target: $[AMOUNT]
Average deal size: $[AMOUNT]
Deals needed per month: = Revenue target / Average deal size
```

**Step 2: Apply your close rate**
```
Deals needed per month: [X]
Close rate (call to client): [Y]%
Calls needed per month: = Deals needed / Close rate
```

**Step 3: Apply your pipeline conversion rates**
```
Calls needed per month: [X]
No-show rate: [Y]%
Meetings to book per month: = Calls needed / (1 - No-show rate)

Outreach-to-meeting rate: [Z]%
First touches needed per month: = Meetings to book / Outreach-to-meeting rate
```

**Example Calculation:**

```
Monthly revenue target: $20,000
Average deal size: $5,000
Deals needed: 4 per month

Close rate: 25%
Calls needed: 4 / 0.25 = 16 per month

No-show rate: 25%
Meetings to book: 16 / 0.75 = ~22 per month

Outreach-to-meeting rate: 3%
First touches needed: 22 / 0.03 = ~733 per month

Weekly outreach volume: 733 / 4 = ~183 first touches per week
Daily outreach volume: 183 / 5 = ~37 first touches per day
```

**This means:** To hit $20,000/month with a $5,000 average deal, you need to send approximately 37 new outreach messages per day (across email and LinkedIn combined). This is well within a single person's capacity if messaging is templated with light personalization.

### Capacity Planning Template

```
YOUR NUMBERS:
Monthly revenue target:         $________
Average deal size:              $________
Deals needed per month:         ________

Close rate (call > client):     ________%
Calls needed per month:         ________

No-show rate:                   ________%
Meetings to book per month:     ________

Outreach-to-meeting rate:       ________%
First touches per month:        ________

Weekly outreach volume:         ________
Daily outreach volume:          ________
```

---

## Output: Your Complete Pipeline Architecture

Based on your business model, ICP, and current resources, here is your customized pipeline.

### Your Pipeline Stages (Customized)

[The 8 stages above, with specific definitions tailored to your service, ICP, and sales process. For example, if your service requires a discovery call before a demo, the stages might be adjusted.]

### Your Conversion Rate Targets

| Stage Transition | Your Target | Industry Benchmark |
|---|---|---|
| Identified > First Touch | 95%+ | 95%+ |
| First Touch > Engaged | [YOUR TARGET]% | 25-40% |
| Engaged > Conversation | [YOUR TARGET]% | 25-35% |
| Conversation > Interest | [YOUR TARGET]% | 50-65% |
| Interest > Call Requested | [YOUR TARGET]% | 70-80% |
| Call Requested > Booked | [YOUR TARGET]% | 60-70% |
| Booked > Completed | [YOUR TARGET]% | 70-85% |

### Your Capacity Model

[Filled-in capacity planning template based on your revenue goals and deal size.]

### Your Tracking Setup

[Specific instructions for setting up tracking in your chosen tool — spreadsheet template, CRM configuration, or purpose-built tool setup.]

---

## Quality Checklist

Before activating your pipeline, verify:

- [ ] All 8 stages have clear, unambiguous entry criteria (no lead should be in a gray area between two stages)
- [ ] Forward and backward transition rules are defined (you know exactly what moves a lead up, down, or out)
- [ ] You have a tracking system in place (spreadsheet or CRM) with all stages represented
- [ ] Conversion rate targets are set for each stage transition (even rough estimates to start)
- [ ] The capacity model is filled out — you know how many first touches you need daily to hit your revenue goal
- [ ] The weekly review process is scheduled on your calendar (recurring event)
- [ ] No-show recovery sequence is written and ready to deploy
- [ ] You've tested the pipeline with 10 existing leads — can you accurately place each one in a stage?
- [ ] Removal criteria are defined — you know when to take a lead out of the pipeline entirely
- [ ] The pipeline is scoped to outreach-to-call only — you have a separate system (or plan for one) to manage post-call stages
- [ ] Your pipeline stages align with your omnichannel sequence touchpoints (you can map each sequence day to a pipeline stage)
- [ ] You've identified who is responsible for each stage's actions (if you're a team, who handles what)
