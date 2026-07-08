---
title: "Dan Fein — show me the feature before building it (plan + low-fi artifact first)"
type: source
medium: twitter-thread
url: https://x.com/dfeinition/status/2074304545690190318
ingested: 2026-07-07
---

## Summary

Dan Fein (`@dfeinition`) shares a [[claude-code]] workflow pattern (2026-07-06): before writing any code, ask Claude Code to produce **a plan plus a low-fidelity artifact** showing how the UI will look and how the systems fit together, and **keep the two in sync as you iterate**. The stated payoff: *"This moves more of the iteration from the code to the plan."* The reply thread coined the memorable framing *"much easier to edit a blueprint than a house."* A related sub-thread surfaces the community **"Taste" skill** (tasteskill.dev) as a design-quality complement.

## Key Claims / Takeaways

- **Plan-and-artifact-first**: *"Create a plan and a low-fidelity artifact showing how the UI will look and the systems fit together. Keep them in sync as we iterate."* Iterating on a cheap visual mockup + plan is far cheaper than iterating on already-written code. Fein generates the mockup animations via [[claude-design]] ("requesting an animation/video").
- **"Edit the blueprint, not the house"** (`@nickventuri`) — the pattern's one-line thesis; front-loads design decisions into an artifact where they're cheap to change.
- **Practitioner-reported drift caveat**: `@bygregorr` — the "keep them in sync" instruction *"starts drifting around iteration 4 or 5"*; asks whether to reset the artifact periodically. Others report the pattern still "works wonders" and makes Claude "seem more confident" even applied broadly. Open question, not a solved workflow.
- **Adjacent: the "Taste" skill** (`tasteskill.dev`, surfaced by Meng To amplifying Miles Deutscher, Jul 3): a Claude skill that *"completely kills generic AI-slop and gives Fable 5 the tools & instructions needed to ship beautiful design."* Single-cluster mention, creator not yet independently confirmed — **watch-note only**, no page created.

## Pages Updated

- [[claude-design]] — added the plan-artifact-first workflow signal + Taste-skill watch-note
