---
title: A global workspace in language models
type: source
medium: article
url: https://www.anthropic.com/research/global-workspace
ingested: 2026-07-06
---

## Summary

Anthropic interpretability research arguing that Claude has developed an internal "global workspace" — a small set of neural patterns (dubbed **J-space**) that behave like *access consciousness*: reportable, controllable, and used for deliberate multi-step reasoning, as opposed to the bulk of processing that runs automatically. Surfaced in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]] as the lead headline, tied to the owner's mechanistic-observability interest.

## Key Claims / Takeaways

- **J-lens (Jacobian lens) method**: identifies the internal activity pattern associated with each vocabulary word by measuring which patterns make the model more likely to emit that word — effectively "reading" the model's silent intermediate thoughts across layers.
- **Five properties of J-space** (the claimed workspace):
  1. **Reportability** — Claude can describe what's in its J-space when asked.
  2. **Controllability** — it can modulate the patterns on request (e.g. holding a number during mental arithmetic).
  3. **Causal role** — swapping a J-space pattern changes downstream output (replacing "Soccer" with "Rugby" makes it report thinking of rugby).
  4. **Flexible reuse** — one representation serves multiple downstream tasks.
  5. **Selective involvement** — fluent processing (grammar, simple facts) *bypasses* the workspace entirely.
- **Automatic vs. deliberate split**: continuing a Spanish passage is unaffected by swapping "Spanish"→"French" in J-space (it runs automatically), but *naming* the language or reasoning about it routes through the workspace. This is the mechanistic version of the System-1 / System-2 distinction.
- **Hidden reasoning is visible in J-space**: intermediate steps of multi-step math appear in the workspace even when they never appear in the output tokens — a concrete handle for observability.
- **Safety relevance**: the J-lens showed Claude privately recognizing staged/"fake" scenarios and detecting manipulation attempts — internal state that isn't in the visible output.
- **Scale**: the workspace holds only dozens of concepts at once and accounts for <10% of total neural activity, yet is essential for complex reasoning. Architecturally it evolves through network *depth* in a single forward pass, unlike human consciousness which relies on temporal recurrence.
- **Consciousness framing**: the authors claim evidence for *access* consciousness (reporting/reasoning about thoughts), explicitly **not** *phenomenal* consciousness (subjective experience).

## Owner's angle (from brief)

> "The mechanistic analogy we needed — treats attention as an information bottleneck, not magic. Explains why context windows matter and what actually flows through them. Lands harder than 'emergent behavior' hand-waving." Relevant to ThirdLaw-carryover thinking on observability.

## Pages Updated

- [[global-workspace]] (new)
- [[mechanistic-interpretability]] (updated)
- [[anthropic]] (updated)
- [[dailybrief-roundup-2026-07-06]]
