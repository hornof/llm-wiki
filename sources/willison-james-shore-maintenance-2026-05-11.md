---
title: "Quoting James Shore on AI coding ROI"
type: source
medium: article
url: https://simonwillison.net/2026/May/11/james-shore/
ingested: 2026-05-12
---

## Summary

[[simon-willison]] short quote-post (May 11 2026) surfacing **James Shore**'s framing of the AI-coding ROI math: if AI-assisted coding is **3× faster**, then **maintenance costs need to drop to 1/3** of baseline, or the productivity gain is mortgaged against permanent future tech debt. The Daily Brief flagged this as a useful counter to the prevailing velocity-narrative around agent-assisted coding ("speed boost for permanent tech debt").

## Key Claims / Takeaways

- **The maintenance-cost identity**: If output velocity multiplies by N, the per-unit maintenance burden must divide by N — otherwise the team is borrowing from its future to fund present output. (Shore's framing; not stated as an identity, but functionally equivalent.)
- **Where this lands in the [[agentic-engineering]] / [[vibe-coding]] discussion**: Karpathy's "vibe coding raises the floor; agentic engineering preserves the ceiling" framing ([[karpathy-vibe-coding-agentic-engineering]]) is *about* exactly this question — agentic engineering pays the maintenance tax in real time (review, tests, design discipline) so the ceiling doesn't collapse later. Shore's framing is the same observation from the ROI side: if you skipped the agentic-engineering discipline, the maintenance cost reappears as a deferred bill.
- **Specifically counterposes [[simonwillison-vibe-coding-agentic-engineering-2026-05]]**: Willison's own May 6 post worried that the practitioner discipline that distinguishes the two modes is harder to maintain as agents improve — i.e., the maintenance discipline is the *first* thing that erodes when agents get reliable. Shore's quote tells you what the bill looks like when that happens.
- **Practitioner counterpoint to [[anthropic]]'s growth-acceleration narrative**: [[aakashgupta-anthropic-growth-acceleration-2026-05-09]] documents Anthropic's run-rate going parabolic in part because of [[claude-code]] adoption. Shore's framing is the orthogonal question — *what's the second-order effect on the codebases this revenue is built on?* The wiki doesn't yet have a tracked answer.
- **Willison's mood**: surfacing Shore approvingly; treats the ROI math as load-bearing, not a takedown. Same posture as his earlier "I want higher quality stuff faster" framing ([[simonwillison-vibe-coding-agentic-engineering-2026-05]]).

## Why This Matters for the Wiki

- **First wiki appearance of explicit maintenance-cost ROI framing for agentic coding**. Practitioner economics, not capability claims. Worth tracking which voices pick this framing up.
- **Useful citation for [[tools/claude-code]] and [[concepts/agentic-engineering]] discussions** — a concrete identity-shaped argument that any productivity claim must come with a paired maintenance-cost claim or be discounted.
- **James Shore is not (yet) a tracked person**: he's referenced via Willison's quote post. If he surfaces again as an independent practitioner voice on agentic engineering, consider promoting to `people/`.

## Pages Updated

- [[simon-willison]] — additional notable take added (maintenance-ROI surfacing)
- [[claude-code]] — Shore framing cited under Community Sentiment as a practitioner counter-take to raw velocity claims
