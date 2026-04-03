# Sales OS

**Your AI-powered sales operating system.** Feed Claude your business context — it builds, audits, and optimizes your entire LinkedIn + email outreach pipeline.

Built from 18,000+ real LinkedIn DMs, 6 years of email marketing data, and $20M+ in generated pipeline.

---

## What This Does

Sales OS turns Claude into your personal sales team lead. Drop these skills into your Claude environment, connect your business knowledge base, and Claude will:

- **Audit** your LinkedIn profile, email campaigns, and outreach scripts
- **Rewrite** everything that's underperforming — DMs, emails, subject lines, CTAs
- **Build** complete outreach sequences across LinkedIn and email
- **Optimize** reply rates, open rates, and booking rates with data-driven fixes
- **Automate** the repeatable parts of your sales process

**37 skills. 6 phases. One system.**

---

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/SendoraAI/sales-os.git

# 2. Run setup
chmod +x scripts/setup.sh && ./scripts/setup.sh

# 3. Add your business context
#    Drop your docs into /knowledge-base/

# 4. Open Claude and say:
#    "Go through the Sales OS and tell me what's the next step."
```

---

## Structure

```
sales-os/
├── .claude/                        # Claude environment config
├── skills/                         # 37 AI skills across 6 phases
│   ├── 01-foundation/              # Business intelligence layer
│   ├── 02-linkedin-profile/        # Profile optimization
│   ├── 03-linkedin-outreach/       # DM & engagement engine
│   ├── 04-email-outreach/          # Cold email system
│   ├── 05-cross-channel/           # LinkedIn + email unified
│   └── 06-optimization/            # Analytics & automation
├── frontend/                       # Sales OS dashboard & visualizer
├── knowledge-base/                 # Your business docs go here
├── guides/                         # Setup & usage guides
├── scripts/                        # Shell utilities
└── CLAUDE.md                       # Master instruction file
```

---

## The 6 Phases

| Phase | Skills | What It Covers |
|-------|--------|----------------|
| **Foundation** | 5 | Business context, ICP, positioning, competitive intel, asset audit |
| **LinkedIn Profile** | 6 | Profile audit, headline, about, featured, experience, social proof |
| **LinkedIn Outreach** | 9 | Prospecting, DMs, follow-ups, objections, voice notes, engagement |
| **Email Outreach** | 10 | Deliverability, campaigns, copy, sequences, replies, segmentation |
| **Cross-Channel** | 5 | Omnichannel sequences, lead scoring, pipeline, reviews |
| **Optimization** | 4 | Performance analysis, automation planning, voice training |

---

## How It Works

1. **You provide context** — business docs, website, current campaigns, scripts
2. **Claude ingests everything** — builds a complete picture of your business
3. **Claude audits your current state** — finds what's broken and what's missing
4. **Claude rebuilds your outreach** — personalized to your offer, ICP, and voice
5. **You execute** — Claude keeps optimizing as you feed it performance data

**First 30 minutes:** You'll have a rewritten LinkedIn profile, a diagnosis of your email outreach, and a prioritized roadmap for your entire sales pipeline.

---

## Knowledge Base

Drop any of these into `/knowledge-base/`:

- Company overview / pitch deck
- Current email campaigns and templates
- LinkedIn DM scripts
- Website copy or landing pages
- Case studies and testimonials
- Sales call recordings or transcripts
- Performance metrics (reply rates, open rates, etc.)

The more context you provide, the more personalized your Sales OS becomes.

---

## Requirements

- [Claude Code](https://claude.ai/code) or Claude with Projects
- Your business knowledge base (docs, scripts, campaigns)
- 30 minutes for initial setup

---

Built by [Sendora](https://sendora.ai) — AI Transformation Partners

