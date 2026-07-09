---
title: "Praveen Neppalli — Uber's agentic-AI adoption + Agentic Pods (2026-07-07)"
type: source
medium: twitter-thread
url: https://x.com/praveenTweets/status/2074605343439810922
ingested: 2026-07-09
---

## Summary

Praveen Neppalli (Uber engineering leader) publishes a first-party account (2026-07-07, clipped 2026-07-09) of **agentic-AI adoption at [[uber|Uber]]** and a concrete org pattern — **Agentic Pods** — for taking it beyond engineering into the whole company. A strong, verifiable AI-native-organization receipt to pair with [[block-builderbot-launch-2026-06-17|Block's Builderbot]].

## Key Claims / Takeaways

- **Engineering adoption stats** (first-party): **99% of engineers use AI tools**; **>70% of pull requests attributed to local or cloud agents**; **2,500+ agent skills** built across the SDLC.
- **Agentic Pods** — the scaling pattern beyond engineering: handpick ~30 of the most AI-proficient engineers (deep Uber-systems knowledge), pair each with a **domain expert** from a business function, give each pod a **2-week sprint**:
  - Days 1–2: **shadow the expert**, document the real workflow.
  - Day 3: prioritize by scale / repetition / business impact / data availability.
  - Days 4–5: **build a working agent alongside** the person doing the job.
  - Days 6–9: validate with several others doing the same work — does it generalize?
  - Day 10: **ship**.
- **16 pods across 16 business functions in 2 months.** Concrete wins: capital allocation across 150 cities **15h → 30min**; financial pacing reports **2 days → 10min**; marketing web QA **2 weeks → 50min**; support **9,000 manual workflows → self-service automation**.
- **Core lessons**:
  - *"The workflow becomes the unit of automation — not the individual task."* (directly echoes [[loop-engineering]]'s "the loop is the unit of work" and Sydney Runkle's event-driven-loop layer).
  - *"The most impactful agent skills cut across teams, orgs, functions, tools, and systems."*
  - *"Build with them, not for them"* — the best opportunities are invisible from outside; you find them by sitting next to the work.
- **Skeptic replies**: *"day 1-2 'shadow the expert' — bro rediscovered apprenticeship and called it an agentic pod"*; recurring "this is just internal **FDE**" framing (pairs with [[andrewng-ai-fde-vs-ai-engineer-2026-06-01|Ng's Forward-Deployed-Engineer thesis]]).

## Why it matters

A first-party, quantified AI-native-org datapoint from a tier-1 company — and one that sits in **tension with Uber's own earlier posture**: the [[uber-ai-tool-cap-1500-2026-06-03|$1,500/mo per-employee AI-spend cap]] (cost-control skepticism) vs this aggressive internal-adoption showcase. Both can be true — spend discipline *and* deep adoption — but the pairing is worth tracking. The Agentic Pods pattern is a concrete, replicable FDE-style operating model for pushing agents past engineering into finance/legal/ops/marketing/support.

## Pages Updated

- [[uber]] — adoption stats + Agentic Pods (tension with the $1,500 cap noted)
- [[ai-native-organizations]] — Agentic Pods as a scaling pattern
- [[loop-engineering]] — "workflow is the unit of automation" production receipt
