---
name: End of Finetuning
type: concept
maturity: emerging
last_updated: 2026-05-27
---

## Definition

A practitioner-side framing — coined explicitly in **swyx**'s May 13 2026 Latent Space essay [[latentspace-end-of-finetuning-2026-05-13]] — that the **default tool stack for AI engineering has moved past finetuning** for the overwhelming majority of use cases. Two trends collapse into one: (a) **base-model capability** improved enough that finetuning's marginal lift shrank to noise for most domains, and (b) **long-context prompting + constitutional-style behavioral specification** absorbed the use cases finetuning used to occupy. OpenAI's May 2026 deprecation of its finetuning APIs is the named trigger, but the practitioner shift predates it by years.

## Why It Matters

If the default abstraction layer for "make the model behave the way I want" moves from **weight updates** to **in-context prompting + behavioral spec**, the AI-engineering job shape changes accordingly:

- **Domain adaptation** stops being a training problem and becomes a **prompting / retrieval / behavioral-spec** problem.
- The discipline shifts from MLOps (training loops, eval pipelines, weight management) to **context engineering** (long context, retrieval, [[code-mode]], [[claude-md-pattern]]).
- The remaining valid finetuning lanes harden into **economics** (custom-ASIC inference cost), **legal/IP** (weight ownership), and **frontier RLFT** (a top-1% lab capability — see Cognition, Cursor).

## Current State

- **Trigger**: OpenAI deprecating finetuning APIs (announced May 2026 per swyx).
- **Replacement pattern (swyx's framing)**: "**Just Very Long Prompts**" — extended-context base models + structured behavioral specifications. **Claude's Constitution** ([[anthropic-claudes-constitution]]) is named as the canonical example.
- **Lab positioning**:
  - **Stopped (mainstream)**: OpenAI (API deprecation).
  - **Still doing — and increasing**: **Cognition** ($25B valuation), **Cursor** are named in the essay as *increasing* RLFT on open models.
  - **Constitutional-spec as replacement**: Anthropic's training methodology ([[constitutional-ai]]) reframed by swyx as the *in-context* replacement strategy, not just an alignment technique.
- **Tier split (per swyx)**: "the top 1% of AI applications are building completely differently than the bottom 99%."
  - **Top 1%**: RLFT on open models, custom-ASIC strategies.
  - **Bottom 99%**: long-context + retrieval + behavioral spec.
- **Counterweight**: research is still active — see [[dailybrief-research-roundup-2026-05-13]] (rotation-preserving SFT, arXiv:2605.10973). The research frontier hasn't stopped; the *default practitioner stack* has.

## Opposing-Direction Signal: Continual Learning at the Agent Layer (May 2026)

[[dailybrief-roundup-2026-05-27|Trajectory]] launches with $15M (co-founded by Ronak Malde) to build a **continual learning platform for agentic AI models**. Post-deployment model improvement via user feedback — keeping agents aligned after launch. This is the **inverse-direction bet** to the End-of-Finetuning thesis: where swyx names long-context + behavioral-spec as the default replacement for finetuning, Trajectory bets that **agents specifically need continuous weight updates** to stay aligned to operational drift in production.

**Why both can be true**: End-of-Finetuning is a *default-stack* claim (the bottom 99% don't finetune anymore). Continual-learning-at-the-agent-layer is a *top-1%* + *agent-specific* claim — once you're running an autonomous agent in production with user feedback at volume, the economics of small continuous weight adjustments may dominate the long-context-only approach. Worth tracking whether Trajectory's product shape lands closer to the swyx "top 1% RLFT" lane or genuinely opens a new agent-runtime-adjacent finetuning niche.

## Open Questions / Caveats

- **Survivorship of the "1% / 99%" split**: swyx's tier framing is rhetorical and not based on a survey. Treat as a working hypothesis until practitioner surveys (e.g., next State of AI Engineering, future Ramp/OpenRouter data cuts) corroborate.
- **Long-context economics**: if long-context throughput costs stay non-trivial vs. inference on a finetuned smaller model, the "JVLP" replacement weakens in the high-volume / latency-sensitive lane. Pair with [[ai-energy-efficiency]].
- **Constitutional-spec generalization**: most teams don't have the writing discipline or eval rigor to author a constitutional spec — see practitioner-side [[claude-md-pattern]] evolution (Forrest Chang's 4 rules → Mnilax's 12) for the on-ramp that produces working behavioral contracts at smaller scope.

## Key Papers / Posts

- [[latentspace-end-of-finetuning-2026-05-13]] — primary essay (swyx, Latent Space)
- [[anthropic-claudes-constitution]] — Claude's constitutional spec
- [[constitutional-ai]] — Anthropic's training methodology (now also the in-context replacement story)
- [[anthropic-claude-cookbook-2026-05]] — Anthropic's named in-context primitives: Programmatic Tool Calling, Tool Search with Embeddings, Automatic Context Compaction

## Related Concepts

- [[constitutional-ai]] — behavioral-spec methodology, now also the JVLP replacement story
- [[claude-md-pattern]] — small-scope behavioral contracts in prose
- [[code-mode]] — search-and-execute tool runtime that makes in-context tool use cheap
- [[interaction-models]] — companion direction: capability absorbed into base model, scaffolding shrinks
- [[rag]] — retrieval is the other half of the long-context / JVLP replacement story
