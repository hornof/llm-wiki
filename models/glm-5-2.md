---
name: GLM 5.2
type: model
provider: Z.ai / Zhipu
status: available
last_updated: 2026-07-06
---

> [!update] Successor announced — GLM 5.3 (2026-08-20)
> Z.ai CEO **Jie Tang** surfaced **GLM 5.3** alongside a *"death of params"* post-training-scaling thesis ([[dailybrief-roundup-2026-08-20]], Latent Space AINews) — param-count is no longer the frontier; **post-training** is the new scaling axis. Continues Z.ai's rapid cadence and keeps the [[ai-margin-collapse|open-weight-parity]] pressure on. *(Summary "too vague to confirm depth"; no dedicated GLM-5.3 page yet — fold on a 2nd substantive surface.)*

## What It Is

**GLM 5.2** is an open-weights frontier-class model from [[zhipu-ai|Z.ai / Zhipu]], served through providers such as Fireworks. Per Martin Alderson it is "the first model that reaches the bar of a genuine open weights competitor to Opus and GPT" — the first open-weights release credible enough to be a drop-in replacement for closed frontier models on many tasks. See [[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]].

## Strengths & Weaknesses

**Strengths**
- Near-Opus quality on many tasks — "genuinely very good and hard to tell the difference from Opus" (Alderson's hands-on impression).
- **Price**: ~**$4.40 / MTok**, under 20% of Opus's ~$25/MTok reference. Open weights → trivial switching cost.

**Weaknesses**
- No vision support.
- Weaker web search.
- Slower, due to extended reasoning.
- Quality claim is one practitioner's impression, not third-party benchmarked (as of 2026-07-06).

## When to Use It

Cost-sensitive, text-only workloads where "good enough vs Opus" holds and latency isn't critical — the canonical example behind the [[ai-margin-collapse]] thesis. Not yet the pick for vision or search-heavy agentic work.

## Community Sentiment

- Framed by Alderson (2026-07-06) as the trigger for a coming collapse in LLM inference margins — see [[ai-margin-collapse]].
- Independent GLM-5.2-vs-Opus evals not yet captured — **verification-pending**.

## Resources

- [[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]] — pricing, quality impression, margin-collapse thesis.
- [[zhipu-ai]] — the maker.
- [[ai-margin-collapse]] — the economic thesis GLM 5.2 anchors.
