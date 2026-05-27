---
title: "cyb3rops: Four stages of AI coding hype (Amazement → Expansion → Grind → Realization)"
type: source
medium: twitter-thread
url: https://x.com/cyb3rops/status/2059531734589247991
ingested: 2026-05-27
---

## Summary

Florian Roth (cyb3rops, infosec practitioner, 2026-05-26 X post) names a **four-stage AI-coding-hype lifecycle**: Amazement → Expansion → Grind → Realization. The post is the third-surface practitioner-voice in the same week converging on the [[ai-roi-gap|AI ROI gap]] thesis, framed as a *psychological-investment ratchet* (stages 1-2 create social/professional commitment that makes stage 4 admission costly). Quote-tweets [[sankar-token-spend-roi-gap-2026-05-25|Sankar's $100K→$18K post]]. John Crickett's top comment sharpens stage 3: *"these are fiddling with knobs, not engineering."*

## Key Claims / Takeaways

### The four stages (verbatim, condensed)

| Stage | Name | Description |
|---|---|---|
| 1 | **Amazement** | *"You try it and can't believe how much code it generates from a few prompts."* |
| 2 | **Expansion** | *"You start more and more projects because shipping suddenly feels cheap and fast."* + you *"start convincing everyone around them: coworkers, management, friends in other companies"* because *"nobody wants to 'fall behind' in 6–12 months."* Creates *"a massive snowball/FOMO effect."* |
| 3 | **The grind phase** | *"You realize the generated code has architectural issues, sloppy mistakes, weird abstractions, duplicated logic, broken edge cases."* Response: *"re-prompting, switching models, increasing reasoning effort, reviewing fixes, generating fixes for previous fixes."* Result: *"suddenly you spend your days reviewing AI-generated pull requests instead of building software."* |
| 4 | **Realization** | *"AI coding increases output much faster than it increases certainty."* Code still needs *"review, testing, ownership, architectural understanding, long-term maintenance — usually by expensive senior engineers."* |

### The psychological-investment ratchet (the load-bearing insight)

- *"This whole cycle can take many months or even more than a year because people become socially and professionally invested in the narrative themselves."*
- *"Once teams, managers, and entire companies have been convinced that this is the future, it becomes psychologically and politically very hard to later say: 'Actually, the ROI is much lower than we expected.'"*
- **Why this matters**: it's the *mechanism* by which the [[ai-roi-gap]] persists. Stages 1-2 create social/professional commitments that make stage-4 admission costly — even when the data supports it. Pairs structurally with [[lennysan-shipper-10-takeaways-2026-05-24|Shipper's "ride the models" framing]] (which is the stage-4-aligned recovery posture) and [[levie-ceo-ai-psychosis-2026-05-23|Levie's CEO-distance framing]] (which is the executive variant of the same dynamic).

### John Crickett's top-comment sharpening

- *"I think 3 is a mistake. All these are fiddling with knobs, not engineering: re-prompting, switching models, increasing reasoning effort. Instead, the lesson here is to apply good engineering practices. Ensure the context is clear. Ensure the requirements are clear."*
- **Reframes stage 3** as a *practitioner-discipline failure*, not an inevitable phase. Aligns with [[claude-md-pattern|CLAUDE.md pattern]] practitioner-validation surfaces — the "ensure context is clear" prescription is what the CLAUDE.md / agents.md / context-engineering thread of the wiki has been tracking.

### Why a third independent surface matters

- **Sankar (2026-05-25)** = practitioner-vendor data perspective ($100K→$18K).
- **Levie (2026-05-23)** = within-AI-bull-camp executive perspective (CEOs distant from last mile).
- **cyb3rops (2026-05-26)** = infosec-practitioner outside-tech-vendor perspective (4-stage lifecycle + investment ratchet).
- The week's three surfaces span *vendor-side, executive-side, and outside-practitioner-side* — not just same-camp echo. Converges with [[techcrunch-bort-ceo-ai-psychosis-2026-05-27|the TechCrunch synthesis]] adding mainstream-press-side framing.

## Pages Updated

- [[ai-roi-gap]] — new topic page; the 4-stage lifecycle is the canonical lifecycle-framing surface
- [[ai-labor-market-impacts]] — cultural-sentiment companion: practitioner-side hype-cycle articulation
- [[claude-md-pattern]] — Crickett's *"ensure the context is clear"* counter-framing surfaced as a stage-3-avoidance prescription (not yet a 7th-validation-surface — too brief; defer)

Verification-pending: Florian Roth's broader posting cadence on AI-coding topics (is this a one-off or a recurring theme); the 4-stage framing's adoption by other practitioner voices over the next 30 days.

## Adjacent sources

- [[sankar-token-spend-roi-gap-2026-05-25]] — quote-tweeted by this post
- [[levie-ceo-ai-psychosis-2026-05-23]] — executive-side analogue of the same thesis
- [[techcrunch-bort-ceo-ai-psychosis-2026-05-27]] — mainstream-press synthesis
- [[lennysan-shipper-10-takeaways-2026-05-24]] — "ride the models" stage-4-aligned recovery posture
