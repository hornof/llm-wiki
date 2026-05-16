---
title: "Miles Deutscher: 'I fired my financial advisor and replaced him with Claude' + full CFO setup"
type: source
medium: twitter-thread
url: https://x.com/milesdeutscher/status/2055109926213816682
ingested: 2026-05-16
---

## Summary

Miles Deutscher (@milesdeutscher) — crypto/markets content creator — published two-layer content May 14 2026: (1) an X post claiming **"I fired my financial advisor and replaced him with Claude. Claude literally does a BETTER job than him (and it's completely free)"**, layered on (2) a long-form step-by-step CFO-setup tutorial. The substantive payload is the tutorial's **folder architecture**: an `instructions.md` system prompt + a perpetually-updated `memory.md` change log + an `investor-one-pager.md` mindset document + a `/financials/` reference folder, all loaded into a Claude Cowork project. Pairs with [[claude-md-pattern]] (behavioral contract at the file level) and the broader [[company-brain]] thesis applied to personal finance.

## Key Claims / Takeaways

### The folder architecture (the load-bearing technical contribution)

Four files at the root of an Investment Folder:

1. **`instructions.md`** — system prompt: "You are [name]'s investment strategist. Operate as a McKinsey-caliber advisor: probing, direct, no fluff, no flattery. You are *not* a licensed financial advisor; your job is to frame decisions, never to make them." Includes seven explicit rules including *"Read 'investor-one-pager.md' and 'memory.md' before every response. Treat both as canonical."*
2. **`memory.md`** — running change log; appended to (never overwritten); dated entries in reverse chronological order. Captures life changes, jurisdiction/tax shifts, income changes, new positions, behavioural patterns observed.
3. **`investor-one-pager.md`** — mindset-state document (not numerical-target document) produced through a seven-phase discovery interview with Claude. Output specification is explicit: North Star (2–4 sentences) / Core Philosophy (5–7 bullets) / Time Horizon / Mindset Rules (6–9 imperative rules) / Personal Nuances / Anti-Portfolio.
4. **`/financials/`** — reference subfolder: `pnl-summary.md` rolling 6-month P&L, monthly bank statements, cash position.

### The seven-phase discovery interview prompt (worth quoting)

Deutscher provides a substantial system prompt for an "Investor Strategy Architect" agent that runs a structured 7-phase interview:
1. Situation & Constraints
2. Capital & Horizon
3. Philosophy & Mindset
4. Behavioural Nuance
5. Preferences & Anti-Preferences
6. Goals (mindset form, not numerical)
7. Stress Tests (concrete hypotheticals e.g. *"Your highest-conviction position drops 70% in a week. Walk me through what you do, hour by hour."*)

Operating principles: *"Probing over polite. Constraints first, ambitions second. Mindset > mechanics. One sharp question at a time. Push back on contradictions. No fluff, no flattery."* — this is a structured-discovery template adaptable beyond finance.

### Mobile-access pattern

Telegram BotFather → Claude bot OR Claude Cowork → Dispatch. Surface for "24/7 CFO in your pocket."

### Comment-thread skepticism

- **Lucy Taylor (@aurumfinancial)**: *"As someone with common sense, uploading your extremely personal info to Anthropic's server is a privacy nightmare."*
- **Mark Pommrehn**: *"How do you manage data leakage, address privacy, etc. This sounds like a disaster waiting to happen, with potential wrench attacks, etc."*
- **Sathish Harry (@SathishAiHype)**: *"How do you handle the memory.md curation problem? Auto-append means it bloats and degrades over time. Manual curation means it's only as good as your discipline."* — Names the **memory-curation failure mode** that the entire system is built around.

## Why It Matters

- **First wiki capture of [[company-brain]] applied to personal finance**. The instructions.md + memory.md + one-pager + financials architecture is a per-person version of the three-layer memory substrate captured in [[ashwingop-company-brain-year-lessons-2026-05]] — factual layer (financials), context graph (one-pager + memory), action coordination (Cowork dashboard).
- **The seven-phase Investor Strategy Architect prompt is structurally novel**. Most Claude-personal-assistant content is "here is a system prompt"; Deutscher provides a *structured-interview template* with hard rules (*"never produce the final document until all seven phases are genuinely complete; refuse generic answers; name contradictions directly"*). This is the [[claude-md-pattern]] discipline extended to behavioral-discovery agents.
- **Memory-curation problem is named and unsolved**: Sathish Harry's comment is the most useful framing — auto-append → bloat/degradation; manual curation → discipline-bound. The Deutscher template doesn't actually solve this; it just makes the failure mode the user's responsibility. Worth flagging as the **load-bearing unsolved problem** for Claude-as-personal-OS applications.
- **Privacy framing matters for context**: Deutscher's audience is crypto/markets; the privacy comments name the tradeoff that the AI-as-CFO framing elides. Treat as cultural-adoption data point rather than security analysis.

## Caveats

- **Promotional structure** at the end: gated assets behind newsletter signup. Deutscher is in the content-marketing register, not the engineering register. The technical content (folder architecture, system prompts) is substantive and reusable; the framing is influencer-tier.
- **"Claude literally does a BETTER job than [my advisor]" is unverified** — no comparison methodology, no portfolio-performance numbers, no time horizon.
- **No quantitative benchmark** for whether memory.md curation degrades over 6+ months of daily use.

## Cross-references

- [[claude-md-pattern]] — behavioral-contract-at-the-file-level pattern; Deutscher's instructions.md is a domain-specific instantiation.
- [[company-brain]] — per-person company-brain architecture; first wiki capture of the personal-finance instantiation.
- [[claude-cowork]] — Cowork is the surface Deutscher recommends for the dashboard layer.
- [[ashwingop-company-brain-year-lessons-2026-05]] — three-layer memory substrate at organizational scale; Deutscher's setup is the same pattern at individual scale.
- [[agent-memory]] / [[claude-managed-agent-memory]] — memory.md as the persistent-state surface; the curation-problem-named-by-Sathish is the unsolved boundary.

## Pages Updated

- [[claude-md-pattern]] (updated — Deutscher Investor Strategy Architect prompt added as a Notable Variant: structured-interview-template extension of the behavioral-contract pattern beyond code-task contexts; date bumped to 2026-05-16)
- [[company-brain]] (updated — "Personal-Finance Instantiation (Deutscher, May 2026)" section added with the four-file folder architecture; date bumped to 2026-05-16)
