---
name: Kimi K3 (2.8T-A50B)
type: model
provider: Moonshot AI
status: available
last_updated: 2026-07-17
---

## What It Is

**Kimi K3** is [[moonshot-ai|Moonshot AI]]'s new flagship — a **2.8-trillion-parameter Mixture-of-Experts model (≈50B active, "2.8T-A50B")**, billed as **the largest open model ever released**. Successor to the K2 line ([[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|K2.6]]). The headline framing ([[dailybrief-roundup-2026-07-17|brief]]): *"Opus-class capability at Sonnet pricing"* — the open-model inflection where open weights compete on **capability *and* cost in the same tier**.

> ⚠️ **Not actually open-weights yet (as of 2026-07-16).** Per [[simon-willison|Simon Willison]], the **open-weight release is *promised* by 2026-07-27**; K3 is currently available only via **Moonshot's website, API, and OpenRouter**. The "largest open model ever released" headline is ahead of the weights drop.

## Strengths & Weaknesses

- **Capability (self-benchmarks, caveat)**: Moonshot's numbers show K3 *"mostly beating Claude Opus 4.8 max and GPT-5.5 high"* but **losing to [[claude-fable-5|Claude Fable 5]] and GPT-5.6 Sol** — i.e. upper-tier, not frontier-leading. Independent: **Artificial Analysis Elo 1547**; **leading model on Arena.ai's Frontend Code arena**.
- **Pricing**: **$3 / M input, $15 / M output** — matching [[claude-sonnet-5|Claude Sonnet]] tier, and a **large step up from K2.6's $0.95 / $4**. So "Sonnet pricing" is a *price increase* for Moonshot, framed against the capability jump — not a discount.
- **"3T-class" marketing tell**: they round **2.8T up to 3T** for marketing — Willison's flag that *"parameter count [no longer] signals capability."*
- **Pelican-on-a-bicycle benchmark**: generated a valid SVG for **~25¢** (95 input + 16,658 output tokens, **13,241 of them reasoning tokens**). Willison's point: even a joke benchmark still surfaces *"interesting model characteristics"* (tokenization quirks, reasoning-token efficiency, vision) — though it *"doesn't touch at all on… agentic tool calling."*

## When to Use It

- **Cost/capability-sensitive upper-tier work** where Sonnet-class pricing is acceptable and you want an open-weights option (once weights land 2026-07-27) — fine-tuning / on-prem / [[reverse-information-paradox|own-your-boundary]] deployments.
- Frontend/code generation (leads the Frontend Code arena). For the outright strongest model, Fable 5 / GPT-5.6 Sol still edge it.

## Community Sentiment

Launch (2026-07-16). Read as an **open-weight scaling inflection** feeding the [[ai-margin-collapse]] thesis — *"expect margin compression across the mid-market LLM API stack"* ([[dailybrief-roundup-2026-07-17|brief]]). Willison's grounding note: past the point where parameter count alone signals capability; benchmark *design* matters more as hype peaks.

## Resources
- [[kimi-k3-largest-open-model-2026-07-16]] — launch + Willison analysis (fetched primary)
- [Willison — "Kimi K3, and what we can still learn from the pelican benchmark"](https://simonwillison.net/2026/Jul/16/kimi-k3/)
- [[moonshot-ai]] — maker; [[ai-margin-collapse]] — the open-weights-cost thesis
