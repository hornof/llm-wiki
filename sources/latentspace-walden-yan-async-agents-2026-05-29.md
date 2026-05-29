---
title: "Latent Space: The Age of Async Agents — Cognition's Walden Yan + OpenInspect's Cole Murray"
type: source
medium: podcast-episode
url: https://www.latent.space/p/cognition
ingested: 2026-05-29
---

## Summary

[Latent Space](https://www.latent.space/) podcast episode (2026-05-29) with **Walden Yan** ([[cognition|Cognition]] co-founder / Devin) and **Cole Murray** (OpenInspect founder) on the operational shape of **async agent workflows**. Surfaced via 2026-05-29 Daily Brief; primary not deeply fetched. **Brief framing**: *"Deep pattern narrative on agent workflows: 80% commit rates, spec-to-PR pipelines, memory, async execution. Maps the dev productivity SaaS shape Cognition is building post-Devin."* First wiki-captured Cognition-side operational metric: **80% commit rates** — concrete number behind the [[cognition-26b-valuation-492m-arr-2026-05-27|$492M ARR / 10× usage growth]] surface.

## Key Claims / Takeaways

### Headline operational metrics (Cognition-side, Walden Yan)

- **80% commit rates** — implied: of the agent's PR attempts, 80% are accepted and committed. This is the *first wiki-captured success-rate metric* for an autonomous-coding-agent vendor at production scale.
- **Spec-to-PR pipelines** — Cognition's operational shape: human writes spec → agent produces PR → human reviews & commits. Pairs structurally with [[heeki-spec-driven-development-2026-02-28|Heeki Park's spec-driven Claude Code workflow]] but at a *vendor-provided* layer rather than a *practitioner-assembled* layer.
- **Memory** — long-running agent context preserved across sessions / tasks. Pairs with [[company-brain]] and [[mem0]] as part of the agent-memory infrastructure stack.
- **Async execution** — agents working autonomously over hours / days without continuous human supervision. Pairs structurally with [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows persistence-across-interruption]] but with Cognition's *vendor-side* operational stack.

### The "80% commit rate" framing — what's load-bearing and what's open

- **If accurate**: 80% PR-accept rate at $492M ARR scale = the strongest single operational anchor for *"autonomous-coding-agent vendors are commercially viable at production scale"* the wiki has captured. Pairs with [[willison-anthropic-openai-pmf-2026-05-27|Willison's PMF thesis]] — Cognition becomes the named end-user-product-PMF-exists data point.
- **Methodology open**: 80% of *what*? Of all attempts? Of attempts the human invoked? Of attempts that completed without error? The framing matters — 80% of completed attempts vs 80% of total attempts gives very different ROI profiles.
- **Pairs with [[ai-roi-gap]]**: 80% commit-rate framing is the *vendor-claimed shipped-value yield*. The [[sankar-token-spend-roi-gap-2026-05-25|Sankar $100K → $18K funnel]] is the *practitioner-observed yield* (~18%). The gap between vendor-claimed-80% and practitioner-observed-18% is the central empirical question. **Reconciliation possibilities**:
  - Different denominators (vendor counts completed attempts; practitioner counts total spend including aborted runs)
  - Different task domains (Cognition specifies; Sankar's clients prompt loosely)
  - Both true at different operational maturity levels
  - Cognition's 80% is marketing-shaped; the real production number is closer to Sankar's 18%
- **Tracking signal**: a third-party benchmark or audited Cognition customer disclosure would resolve the gap. Worth primary-fetching the Latent Space episode for methodology specifics.

### Cole Murray / OpenInspect context

- **OpenInspect** is Cole Murray's company; not yet wiki-captured. Brief doesn't surface what OpenInspect builds, but the co-billing with Walden Yan in an *"Async Agents"* episode implies operational-overlap with Cognition's surface.
- **No wiki page for OpenInspect or Cole Murray yet** — single-source today; defer entity pages.

### Strategic implication: Cognition as "dev productivity SaaS" framing

- Brief: *"Maps the dev productivity SaaS shape Cognition is building post-Devin."*
- Cognition is positioning *not* as a coding-tool company but as a **dev-productivity-SaaS company** — the unit of value is *"engineering output velocity per dollar"* rather than *"lines of code per minute"*.
- Pairs with [[saas-disruption-thesis|saas-disruption three-tier framework]]: Cognition occupies the *AI-native challenger* tier directly under the [[saas-disruption-thesis#Frontier-Lab Capital-Event Anchor (Anthropic Series H, May 28 2026)|frontier-lab utility tier]] — eating mid-market SaaS by selling the *labor output*, not the *tool*.
- Pairs with [[gustaf-alstromer|YC AI-Native Service Companies RFS]] — Cognition is the canonical exemplar of the service-not-software framing at material scale.

### What's notably absent from the brief

- **80% commit-rate methodology** (above)
- **Cognition's customer concentration** — the same gross-margin question flagged in [[cognition-26b-valuation-492m-arr-2026-05-27]] remains open
- **OpenInspect's product surface** — what does OpenInspect actually build?
- **Specific episode highlights** — primary not deeply fetched; episode runtime + key timestamps would help re-listening
- **Comparison vs Anthropic Dynamic Workflows + Opus 4.8** — both Cognition's async-agent stack and Anthropic's Dynamic Workflows shipped in the same week; the episode predates Dynamic Workflows' May 28 announcement so direct comparison may not be on it

## Pages Updated

- [[cognition]] — Walden Yan async-agents framing + 80% commit-rate operational metric added under Traction Signals
- [[claude-md-pattern]] — spec-to-PR-pipeline pattern noted as the vendor-provided analogue to Heeki Park's practitioner-assembled spec-driven Claude Code workflow
- [[ai-roi-gap]] — vendor-claimed 80% commit-rate vs practitioner-observed Sankar $100K → $18K funnel added as the central empirical-reconciliation question
- [[saas-disruption-thesis]] — Cognition's *"dev productivity SaaS"* positioning added as the canonical AI-native-challenger-tier exemplar
- [[ai-native-service-companies]] *(if exists; else cross-reference deferred)* — Cognition as canonical exemplar
- [[simon-willison]] / [[swyx]] *(Latent Space host)* — not updated this pass

Verification-pending: 80% commit-rate methodology; Cognition customer concentration; OpenInspect product surface; episode-specific operational details.

## Adjacent sources

- [[cognition-26b-valuation-492m-arr-2026-05-27]] — capital + revenue anchor for Cognition
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — same-week competitive surface from Anthropic at the orchestration layer
- [[heeki-spec-driven-development-2026-02-28]] — practitioner-assembled analogue to Cognition's spec-to-PR pipeline
- [[willison-anthropic-openai-pmf-2026-05-27]] — Willison PMF thesis; Cognition as end-user-product-PMF data point
- [[sankar-token-spend-roi-gap-2026-05-25]] — practitioner-observed yield-rate counter-anchor
