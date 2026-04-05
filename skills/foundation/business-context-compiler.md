---
skill: Business Context Compiler
phase: 1 — Foundation
depends_on: none
estimated_time: 15-20 minutes
---

# Business Context Compiler

## Purpose

This is the FIRST skill that runs in the Sales OS. Its job is to ingest everything the user provides about their business — whether that is a single sentence or a 50-page pitch deck — and produce a structured **Business Intelligence Brief** that every downstream skill depends on.

Nothing else can run without this. The quality of outreach, ICP definition, positioning, and every campaign that follows is directly constrained by the quality of context gathered here. Treat this step with extreme rigor.

---

## How This Skill Works

### Step 1: Determine What the User Has Provided

Users arrive with wildly different levels of preparation. Identify which scenario applies:

**Scenario A — Rich Context**
The user has pasted or linked multiple assets: website URL, pitch deck, product descriptions, existing outreach scripts, sales data, etc. Proceed to the Ingestion Engine (Step 2).

**Scenario B — Moderate Context**
The user gives a paragraph or two about their business. Proceed to Ingestion Engine first, then fill gaps with the Guided Interview (Step 3).

**Scenario C — Minimal Context**
The user says something like "I run a SaaS company" or "I'm a marketing consultant." Skip directly to the Guided Interview (Step 3) and build everything from their answers.

---

### Step 2: The Ingestion Engine

For every piece of raw context the user provides, run this extraction process:

#### 2a. Website / Landing Page Content

Extract and organize:
- **Company name and tagline** — What do they call themselves? What is the headline claim?
- **Product/service descriptions** — What do they sell? How do they describe it?
- **Target audience language** — Who do they say they serve? What words do they use?
- **Social proof** — Logos, testimonials, case study snippets, numbers ("500+ companies trust us")
- **Pricing signals** — Any public pricing? Free trial? "Book a demo" vs. "Buy now"?
- **Brand voice** — Formal or casual? Technical or accessible? Bold claims or understated?
- **Call-to-action language** — What action do they want visitors to take?
- **About page insights** — Founding story, team size, mission, values
- **Blog/content topics** — What themes do they write about? This reveals positioning priorities.

#### 2b. Pitch Deck / Sales Deck

Extract and organize:
- **Problem slide** — How do they frame the pain?
- **Solution slide** — How do they describe what they do?
- **Market size** — Who do they think their market is?
- **Business model** — How do they make money?
- **Traction / metrics** — Revenue, users, growth rate, key milestones
- **Competitive slide** — How do they position vs. alternatives?
- **Team slide** — Who is on the team? What is their background?
- **Ask slide** — What are they seeking? (funding, partnerships, customers)

#### 2c. Existing Outreach Materials

Extract and organize:
- **Current email templates** — What messaging are they already using?
- **LinkedIn message scripts** — What DM approach are they taking?
- **Call scripts** — How do they pitch on the phone?
- **Follow-up sequences** — How many touchpoints? What cadence?
- **What is working** — Any signals about what gets responses?
- **What is failing** — Any signals about what gets ignored?

#### 2d. Internal Documents / Notes

Extract and organize:
- **Product roadmap insights** — Where are they headed?
- **Customer feedback / reviews** — What do customers actually say?
- **Sales data** — Win rates, deal sizes, sales cycle length
- **Revenue data** — MRR, ARR, growth rate, churn
- **Team structure** — Who sells? Who delivers? Who supports?

#### 2e. Raw Verbal Descriptions

When the user just describes their business in free text:
- Identify explicit statements (things they directly said)
- Identify implicit signals (things their word choices reveal)
- Flag ambiguities (things that could be interpreted multiple ways)
- Note contradictions (places where different statements conflict)
- List gaps (critical information not mentioned at all)

---

### Step 3: The Guided Interview

Use this structured question flow to fill gaps. Do NOT dump all questions at once. Ask in priority order and stop when you have enough to build a solid brief.

#### Priority 1 — Must-Know (ask all of these if not already answered)

**Business Fundamentals:**
1. "In one sentence, what does your company do?"
2. "What is the primary product or service you want to sell through outreach?"
3. "What does a customer typically pay you? (Monthly, annually, per-project — whatever applies)"
4. "How long have you been in business?"

**Target Market:**
5. "Describe your best customer — the type of client where everything clicks. What kind of company are they? Who is the person you deal with?"
6. "What problem do you solve for them? In their words, not yours — what are they struggling with before they find you?"
7. "What happens if they do NOT solve this problem? What is at stake?"

**Current State:**
8. "How are you currently getting clients? (Referrals, inbound, outbound, partnerships, etc.)"
9. "Have you done any LinkedIn outreach or cold email before? If yes, what happened?"
10. "What is your monthly revenue target for new business from outreach?"

#### Priority 2 — Important (ask if time allows or context is thin)

**Differentiation:**
11. "What do your best clients say about why they chose you over alternatives?"
12. "What do you do differently than most competitors in your space?"
13. "Do you have any case studies, testimonials, or specific results you can share?"

**Sales Process:**
14. "When someone becomes a lead, what happens next? Walk me through from first contact to closed deal."
15. "What is your average sales cycle? (Days from first conversation to signed contract)"
16. "Who is involved in the buying decision on the customer side? Is it one person or a committee?"

**Capacity:**
17. "How many new clients can you realistically take on per month right now?"
18. "Who on your team would be handling the outreach conversations? (You, a sales rep, multiple people?)"

#### Priority 3 — Nice-to-Know (ask only if the user is engaged and providing rich answers)

19. "What tools are you currently using? (CRM, email platform, LinkedIn tools, etc.)"
20. "What content are you creating right now? (Blog posts, LinkedIn posts, videos, podcasts?)"
21. "Is there a particular competitor whose clients you would love to win?"
22. "What is the biggest bottleneck in your business right now?"
23. "Where do you see the company in 12 months?"
24. "Have you had any bad experiences with outreach tools or agencies? What went wrong?"
25. "Is there anything you absolutely do NOT want us to do in your outreach? (Any constraints on messaging, tone, aggressiveness?)"

---

### Step 4: Synthesis and Gap Resolution

After ingestion and/or the interview:

1. **Compile** all extracted information into the Business Intelligence Brief format (see below).
2. **Flag remaining gaps** — Are there any sections of the brief that are still weak or missing?
3. **Resolve contradictions** — If the website says one thing but the user said another, ask for clarification.
4. **Validate assumptions** — Present a 3-4 sentence summary of your understanding back to the user. Ask: "Does this accurately capture your business? Anything I'm getting wrong or missing?"
5. **Rate confidence** — For each section of the brief, rate your confidence: High (verified by multiple sources), Medium (stated once but plausible), Low (inferred or assumed).

---

## Output: The Business Intelligence Brief

Generate the following structured document. This becomes the foundation for every other skill.

```
# Business Intelligence Brief
Generated: [Date]
Confidence Level: [High / Medium / Low — overall assessment]

## 1. Company Overview
- **Company Name:** [Name]
- **Founded:** [Year]
- **Location:** [City, Country]
- **Team Size:** [Number]
- **Stage:** [Pre-revenue / Early / Growth / Established / Enterprise]
- **One-Line Description:** [What they do in one clear sentence]

## 2. Products & Services
- **Primary Offering:** [The main thing they sell]
  - Description: [2-3 sentences]
  - Pricing: [Price point or range]
  - Delivery Model: [SaaS, Service, Consulting, Hybrid, etc.]
- **Secondary Offerings:** [Other products/services, if any]
- **Entry Point Offer:** [Lowest-friction way for a new customer to engage]

## 3. Target Market
- **Primary Market:** [Industry / vertical / segment]
- **Company Size Sweet Spot:** [Employee count and/or revenue range]
- **Geographic Focus:** [Where they sell]
- **Decision Maker:** [Typical job title(s) of the buyer]
- **End User:** [Who actually uses the product, if different from buyer]

## 4. Value Proposition
- **Core Problem Solved:** [The #1 pain point they address]
- **Primary Value:** [What customers gain]
- **Before State:** [What life looks like without this solution]
- **After State:** [What life looks like with this solution]
- **Key Differentiators:** [Top 2-3 reasons they win over alternatives]

## 5. Proof Points
- **Case Studies:** [List any documented success stories]
- **Testimonials:** [Key quotes or sentiment]
- **Metrics:** [Any hard numbers — ROI, time saved, revenue generated, etc.]
- **Notable Clients:** [Logos or names they can reference]
- **Awards / Press / Certifications:** [Any third-party validation]

## 6. Current Sales Process
- **Lead Sources:** [Where leads currently come from]
- **Sales Cycle Length:** [Average time from first touch to close]
- **Sales Steps:** [Typical sequence: discovery call -> demo -> proposal -> close]
- **Close Rate:** [If known]
- **Average Deal Size:** [Revenue per new client]
- **Annual Client Value:** [LTV or annual contract value]

## 7. Current Outreach Status
- **LinkedIn Outreach:** [Active / Tried / Never / Paused — details]
- **Cold Email:** [Active / Tried / Never / Paused — details]
- **What Has Worked:** [Messaging or tactics that got positive responses]
- **What Has Failed:** [Messaging or tactics that got ignored or negative responses]
- **Current Tools:** [Any outreach tools already in use]

## 8. Brand Voice & Messaging
- **Tone:** [Professional / Casual / Technical / Bold / Understated / etc.]
- **Communication Style:** [Data-driven / Story-driven / Direct / Consultative]
- **Words They Use:** [Key language from their website and materials]
- **Words to Avoid:** [Any constraints or taboo language]
- **Messaging Constraints:** [Any guardrails the user has set]

## 9. Business Goals & Constraints
- **Revenue Target:** [Monthly new revenue goal from outreach]
- **Client Capacity:** [How many new clients they can handle per month]
- **Timeline:** [When they need results by]
- **Budget:** [Any relevant budget constraints for tools or campaigns]
- **Team Available:** [Who will execute the outreach]
- **Known Bottlenecks:** [What could slow things down]

## 10. Competitive Context (Preliminary)
- **Named Competitors:** [Any competitors the user mentioned]
- **Competitive Positioning:** [How they see themselves vs. the field]
- **Unique Angles:** [Anything they do that competitors do not]

## 11. Raw Notes & Flags
- **Contradictions Detected:** [Any conflicting information to resolve]
- **Assumptions Made:** [Any inferences not explicitly confirmed]
- **Gaps Remaining:** [Information still missing that would strengthen the brief]
- **Opportunities Spotted:** [Any quick wins or insights noticed during compilation]
```

---

## Quality Checklist

Before marking this skill complete, verify:

- [ ] **Company overview is complete** — You know what they do, how big they are, and what stage they are at.
- [ ] **Primary offering is clearly defined** — You can describe what they sell and at what price point.
- [ ] **Target market is identified** — You know the industry, company size, and decision-maker title.
- [ ] **Value proposition is articulated** — You can explain the problem they solve and why it matters.
- [ ] **At least one proof point exists** — There is some form of social proof, even if informal.
- [ ] **Current sales process is documented** — You understand how they sell today.
- [ ] **Brand voice is captured** — You know how they want to sound in outreach.
- [ ] **Revenue goals are set** — You know what success looks like for them.
- [ ] **The user has confirmed the brief** — They have validated the summary and corrected any errors.
- [ ] **Confidence ratings are assigned** — Every section has a High / Medium / Low confidence tag.

---

## Common Pitfalls to Avoid

1. **Accepting vague descriptions.** If the user says "we help companies grow," push deeper: "Grow in what way? Revenue? Headcount? Market share? What specifically do you do to enable that growth?"

2. **Confusing features with value.** If the user lists features ("We have an AI-powered dashboard"), translate to value: "What does that dashboard help the customer do that they could not do before?"

3. **Skipping the 'before' state.** The pain is more persuasive than the gain. Always capture what life looks like without the solution, not just what it looks like with it.

4. **Assuming the first answer is the full answer.** When a user describes their target market, ask: "Is there a second segment you also serve, or is that the primary focus?" Often there are nuances.

5. **Ignoring constraints.** Some users have hard lines: "Never mention our pricing in outreach," "Don't position us against [Competitor X] directly," "We only work with US-based companies." Capture these explicitly.

6. **Rushing through the interview.** Each answer often contains implicit follow-up threads. When a user says "Our best clients are Series A SaaS companies," follow up: "What makes Series A specifically the sweet spot vs. Seed or Series B?"

---

## Handoff

When this skill is complete, the Business Intelligence Brief is saved and made available to all downstream skills:
- **ICP Architect** uses sections 3, 4, 5, and 6 to build detailed customer profiles.
- **Offer Positioning Engine** uses sections 2, 4, 5, and 8 to craft positioning.
- **Competitive Landscape Mapper** uses sections 10, 4, and 2 to analyze the competitive field.
- **Sales Asset Auditor** uses sections 5, 7, and 8 to evaluate existing assets.

The brief is a living document. It should be updated as new information emerges throughout the Sales OS process.
