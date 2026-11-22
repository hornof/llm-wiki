---
title: "Perplexity and Intelligence"
type: source
medium: article
url: https://openai.com/index/perplexity-and-intelligence
ingested: 2026-11-22
local_source: "_raw/pachocki-perplexity-and-intelligence-2026-11.txt"
---

## Summary

Essay by Jakub Pachocki, OpenAI's chief scientist (dated 2026-11-22 on the page). He proposes that labs compare pretraining progress by perplexity (cross-entropy loss), publishes OpenAI's internal numbers, and calls for shared limits that labs commit not to cross until monitoring reaches a concrete milestone. A Digg write-up (in the same raw file) notes what it doesn't include: no named labs, no enforcement and no timetable.

## Key Claims / Takeaways

- **The proposal:** *"I further propose common limits, based on perplexity and other measurements, that developers are committed to not crossing until our ability to understand and monitor AI behavior achieves a certain concrete milestone (such as the development of a successor to CoT monitors)."*
- **OpenAI's internal numbers:** *"GPT‑3.5, at a log-perplexity of ~0.99 on our current main evaluation dataset"*; *"GPT‑4, at ~0.91"*; *"as we have reached losses below 0.8, we have seen the emergence of transformative capabilities in fields like cybersecurity and mathematics."* He adds *"it was not at all clear a priori"* that those capabilities would appear at those thresholds.
- **Why now:** *"as soon as 2027 we could conceivably see a similar avalanche of fundamental pretraining advancements"*, and alignment and monitoring progress *"is unlikely to be fast enough to allow the full potential acceleration in pretraining."*
- **Cost of publishing:** the numbers give *"competitors a clearer picture of where we stand"*, which he says the urgency outweighs.
- **Limits of the metric** (Digg's reading of the essay): the numbers come from OpenAI's own evaluation set and aren't comparable across labs yet, and chain-of-thought reasoning can raise capability without lowering perplexity. *"This is a proposal, not an agreed pause."*

## Pages Updated

- [[openai]]
- [[frontier-ai-governance]]
- [[recursive-self-improvement]]
