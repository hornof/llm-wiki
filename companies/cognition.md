---
name: Cognition
type: company
status: active
last_updated: 2026-05-29
---

## What It Is

Cognition is the AI company behind **Devin**, an autonomous-coding agent positioned as a *"software-engineer-as-a-service"* product. Founded 2023. As of late May 2026, **$1B+ raised at $26B post-money valuation** with **$492M ARR run-rate** and **10× usage growth this year** — first wiki-captured operational-scale data point for an autonomous-coding-agent vendor at this magnitude. The **53× ARR multiple** is well above typical SaaS (5-15× mature, 20-30× high-growth); investor framing is *"capability franchise"* pricing.

First wiki appearance: 2026-05-27 via [[cognition-26b-valuation-492m-arr-2026-05-27]]; referenced across [[dailybrief-roundup-2026-05-27]], [[dailybrief-roundup-2026-05-28]], [[latentspace-end-of-finetuning-2026-05-13]] (RLFT top-1% practitioner), [[willison-anthropic-openai-pmf-2026-05-27]] (end-user-product-PMF data point).

## Product: Devin

Devin is Cognition's flagship product — an autonomous software-engineering agent that runs end-to-end coding tasks (read codebase, propose changes, write code, test, commit, open PRs). Positioned competitively against [[claude-code]] + Codex at the *vendor-provided autonomous-agent* surface (vs the *infra-provider-runs-your-agent* surface).

Pricing pattern: per-seat enterprise contracts; *"capability franchise"* multiplier per the investor framing.

## Traction Signals (May 2026)

- **$492M ARR run-rate** (May 2026) — operational scale that crosses the *"autonomous-coding-agent vendors are commercially real"* threshold
- **10× usage growth this year** (Anthropic-framed; verification-pending)
- **$1B raise at $26B valuation** — 53× ARR multiple
- **80% commit rate** (Walden Yan via [[latentspace-walden-yan-async-agents-2026-05-29|Latent Space Async Agents pod, 2026-05-29]]) — first wiki-captured Cognition-side success-rate metric. **Methodology open**: 80% of *what* (all attempts vs completed attempts vs human-invoked attempts)? Reconciliation question vs [[sankar-token-spend-roi-gap-2026-05-25|Sankar's $100K → $18K practitioner-side funnel]] remains the central empirical puzzle.
- **Top-1% RLFT practitioner** per [[latentspace-end-of-finetuning-2026-05-13|swyx's End-of-Finetuning thesis]] — Cognition is one of two named labs (with Cursor) that continue to run fine-tuning at production scale despite the broader practitioner shift to long-context + constitutional-spec
- **Pairs with [[willison-anthropic-openai-pmf-2026-05-27|Willison's PMF thesis]]**: Cognition is one *concrete data point* in favor of end-user-product PMF existing for AI-coding products sitting on top of frontier models — though Willison frames it as *one company-level proof point, not category-level resolution*

## Operational Shape (Walden Yan, Latent Space May 2026)

[[latentspace-walden-yan-async-agents-2026-05-29|Latent Space "The Age of Async Agents"]] pod (with co-guest Cole Murray of OpenInspect) maps Cognition's operational shape:

- **Spec-to-PR pipeline** — human writes spec → agent produces PR → human reviews & commits. *Vendor-provided* analogue to [[heeki-spec-driven-development-2026-02-28|Heeki Park's practitioner-assembled spec-driven Claude Code workflow]].
- **Memory** — long-running agent context across sessions/tasks. Pairs with [[company-brain]] and [[mem0]].
- **Async execution** — agents working autonomously over hours/days without continuous supervision. Pairs with [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows persistence-across-interruption]].
- **Strategic positioning: "dev productivity SaaS" rather than "coding tool"** — unit of value is *engineering output velocity per dollar* rather than *LOC per minute*. Cognition occupies the *AI-native challenger* tier in [[saas-disruption-thesis|the three-tier survival framework]] directly under the [[anthropic|frontier-lab utility tier]]; the canonical exemplar of [[gustaf-alstromer|YC's AI-Native Service Companies RFS]] framing at material scale.

## Why It's Worth Tracking

- **Operational-scale anchor for the autonomous-coding-agent category** — until Cognition's $492M ARR, the wiki had capability claims and practitioner-content but no concrete revenue magnitude for an autonomous-coding-agent vendor
- **Gross-margin question is open** — brief framing flags whether the 53× multiple is *capability-franchise* (Cognition captures gross margin via its own value-add) or *revenue-pass-through* (Cognition passes the frontier-lab inference costs through to customers, taking thin margin); verification-pending
- **Pairs structurally with [[saas-disruption-thesis]]**: Cognition is the high-water-mark exemplar of *"AI-native challenger eating mid-market SaaS"* — if the 12-month revenue retention holds, it's the strongest single company-level proof of the thesis; if it doesn't, it's a counter-example
- **Pairs with [[claude-code]]**: same competitive surface (autonomous coding) at the *vendor-provided* layer vs Claude Code's *infra-provider* layer
- **Cross-vendor pattern**: [[dailybrief-roundup-2026-05-27|PolyArch/humanize plugin]] runs *Claude implements + Codex reviews* — practitioner-stack mixing labs at the agent layer; competitively relevant to Cognition's all-in-one positioning

## Resources

- [[cognition-26b-valuation-492m-arr-2026-05-27]] — primary source for the $1B/$26B/$492M ARR signals
- [[dailybrief-roundup-2026-05-27]] — daily-brief context with cross-cuts
- [[latentspace-end-of-finetuning-2026-05-13]] — Cognition as top-1% RLFT practitioner
- [[willison-anthropic-openai-pmf-2026-05-27]] — Cognition as PMF data point
- [[forbes-ai-50-2026]] — Forbes 2026 AI 50 ranking context
