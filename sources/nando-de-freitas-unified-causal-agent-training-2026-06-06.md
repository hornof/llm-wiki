---
title: "Nando de Freitas — Unified causal agent training to replace SFT+RLHF pipelines (Microsoft VP of AI, 2026-06-06)"
type: source
medium: article
url: https://digg.com/ai/8yq4fo0z
ingested: 2026-06-07
---

## Summary

**[[nando-de-freitas|Nando de Freitas]], Microsoft VP of AI**, proposes (2026-06-06 via Digg-surfaced framing) **replacing the standard SFT + RLHF post-training pipeline with a unified, continual interactive causal agent training paradigm**. **First wiki-captured Nando de Freitas surface** + **first wiki-captured Microsoft-AI-VP-side post-training-methodology proposal**. Adds a senior-vendor-side voice to the post-training-methodology debate alongside [[nvidia-nemotron-3-ultra-550b-2026-06-04|NVIDIA Nemotron 3 Ultra (multi-teacher distillation)]] + [[anthropic-self-service-data-analytics-2026-06-03|Anthropic data-analytics (skill-discipline)]]. Primary not deeply fetched; Digg framing is the load-bearing surface.

## Key Claims / Takeaways

### The proposal shape

> *"Microsoft VP of AI Nando de Freitas proposes replacing complex training pipelines with unified, continual interactive causal agents"* (Digg framing)

**Pattern**: collapse the **SFT (supervised fine-tuning) + RLHF (reinforcement learning from human feedback)** post-training pipeline into a **single learning loop** centered on a continual interactive causal agent.

### Brief framings

- *hot_take*: *"Nando's right that SFT + RLHF is a Frankenstein stack. But unified training only wins if the causal agent actually learns from interaction — which means solving credit assignment at scale. We're not there yet."*
- *insightful*: *"If this works, it collapses the post-training stack from 'two separate objectives fighting each other' to 'one learning loop.' The real test: does a single agent trained on causality + feedback beat today's pipeline on reasoning tasks? That would reframe what 'reasoning' means — less final-answer-polish, more decision-making-under-uncertainty."*

### Microsoft VP-of-AI senior-vendor signal

- **Nando de Freitas** is Microsoft VP of AI; previously at Google DeepMind (DeepMind research scientist + reinforcement-learning lead pre-Microsoft). **First wiki-captured Nando de Freitas surface** establishes him as a senior-vendor-side voice
- **First wiki-captured Microsoft-AI-side post-training-methodology proposal** — Microsoft has been wiki-tracked at the Satya-Nadella-Scout-rejection level ([[dailybrief-roundup-2026-06-05]]) but not at the AI-research-leadership-methodology-proposal level
- **Microsoft is positioned as a 3rd-vendor entrant** in the post-training-methodology debate alongside NVIDIA (multi-teacher distillation) + Anthropic (skill-discipline)

### Pairs structurally with the post-training-methodology debate

The wiki now tracks **3 distinct vendor-side post-training-methodology framings in 4 days**:

| Date | Vendor | Methodology | Source |
|---|---|---|---|
| 2026-06-03 | Anthropic | Skill-discipline + canonical skill-file skeleton + provenance footer + pairwise-skill pattern | [[anthropic-self-service-data-analytics-2026-06-03]] |
| 2026-06-04 | NVIDIA (via Nathan Lambert) | Multi-teacher on-policy distillation pipeline (10+ specialized teachers) | [[nvidia-nemotron-3-ultra-550b-2026-06-04]] |
| **2026-06-06** | **Microsoft** | **Unified continual interactive causal agent training** | **(this)** |

**First wiki-captured 3-vendor 4-day post-training-methodology debate cluster**. **Pattern**: post-training methodology is now load-bearing competitive surface — each vendor stakes out a distinct framing. Pattern-watch: do OpenAI / Google DeepMind / xAI publish counter-positions?

### Pairs with [[end-of-finetuning|the end-of-finetuning thesis]]

[[end-of-finetuning|swyx's May 2026 end-of-finetuning thesis]]: OpenAI deprecating finetuning APIs is the trigger for a multi-year practitioner shift to long-context + constitutional-spec; top 1% still RLFT (Cognition, Cursor). **Nando's unified-causal-agent proposal extends this thesis structurally** — if SFT+RLHF collapses into single causal-agent learning loop, the *"top 1% still RLFT"* exception narrows further. **First wiki-captured senior-vendor proposal that operationally extends the end-of-finetuning thesis**.

### Pairs with [[recursive-self-improvement|the RSI concept]]

Continual interactive causal agent training **is structurally adjacent to RSI** — if the agent learns continually from interaction, the boundary between *"pre-training + post-training + deployment"* (3 phases) and *"deployment-as-continual-training"* (1 phase) dissolves. **First wiki-captured concrete vendor-side proposal at the RSI-adjacent methodology layer** (alongside [[anthropic-institute-when-ai-builds-itself-2026-06-04|Anthropic Institute RSI publication]]).

### Cross-cutting framings

- **First wiki-captured Microsoft-side AI-research-leadership-methodology-proposal**
- **Pairs with [[dailybrief-roundup-2026-06-05|Satya Nadella's rejection of the Scout addictive-AI-agent proposal]]**: Microsoft-side AI-leadership is publicly articulating positions across both **product-discipline** (Nadella, no-addictive-design) + **research-methodology** (de Freitas, unified-causal-agent). **First wiki-captured 2-vector Microsoft-AI-leadership public-positioning** in 2 days.
- **Pairs with [[dan-jeffries-rsi-time-multiplicity-critique-2026-06-04|Jeffries Time-Multiplicity critique]]**: Jeffries argues feedback-loop-and-ground-truth constraints limit RSI; de Freitas's proposal *centers* on solving the credit-assignment problem (the technical heart of feedback-loop-design). **First wiki-captured methodology-proposal that directly addresses the Jeffries-LeCun bottleneck framing**.
- **Pairs with [[andrewng-ai-fde-vs-ai-engineer-2026-06-01|Ng's 5 future-specialist-role predictions]]**: if SFT+RLHF collapses to unified-causal-agent, the specialist-roles (LLMOps + Evals + AI Data + Harness + FDE) reorganize. Pattern-watch: does de Freitas's framing imply specific specialist-role implications?
- **First wiki-captured "credit assignment at scale" framing** as the bottleneck for unified-causal-agent training — pairs with [[verifiability-and-jagged-intelligence|verifiability concept]] at the *what-can-be-credit-assigned* layer

### Notably-absent

- **Primary source not fetched** — Digg framing is the load-bearing surface; no original Nando blog post / X thread / paper captured
- **Specific implementation details** — no architectural diagrams, training objectives, or pseudocode
- **Specific timeline** — when would Microsoft ship this? Internal R&D vs production pipeline?
- **Specific Microsoft-internal team** working on this (Microsoft AI Research? Phi team? Microsoft AI vs Microsoft Research distinction)
- **Specific OpenAI / Google DeepMind / xAI / Meta response** — pattern-watch
- **Specific Nando de Freitas role articulation** — entity-page-candidate needs full role + background capture
- **Specific causal-inference methodology cited** (Pearl-style? Contrast with predictive-model framing?)

## Pages Updated

- [[nando-de-freitas]] — entity-page candidate flagged; first wiki surface; Microsoft VP of AI structurally load-bearing role justifies entity page at single-source threshold
- [[end-of-finetuning]] — Nando proposal noted as senior-vendor extension of the thesis
- [[recursive-self-improvement]] — Nando proposal noted at the RSI-adjacent methodology layer
- [[anthropic-self-service-data-analytics-2026-06-03]] — back-link as 1st in 3-vendor 4-day post-training-methodology debate cluster
- [[nvidia-nemotron-3-ultra-550b-2026-06-04]] — back-link as 2nd in cluster

## Adjacent sources

- [[anthropic-self-service-data-analytics-2026-06-03]] — 1st of 3-vendor 4-day post-training-methodology debate cluster
- [[nvidia-nemotron-3-ultra-550b-2026-06-04]] — 2nd of cluster (Lambert post-AI2 "post-training industry standard" framing)
- [[end-of-finetuning]] — swyx's end-of-finetuning thesis Nando's proposal extends
- [[dailybrief-roundup-2026-06-05]] — Satya Nadella's Scout-rejection (Microsoft-AI-leadership product-discipline parallel)
- [[dan-jeffries-rsi-time-multiplicity-critique-2026-06-04]] — Time-Multiplicity critique Nando's proposal addresses at the credit-assignment layer
- [[anthropic-institute-when-ai-builds-itself-2026-06-04]] — RSI publication context
- [[verifiability-and-jagged-intelligence]] — verifiability framing adjacent to credit-assignment bottleneck

## Verification-pending

- Primary Nando de Freitas source (blog post / paper / X thread)
- Specific implementation details + architectural diagrams + training objectives
- Specific timeline for Microsoft adoption
- Specific Microsoft-internal team
- OpenAI / Google DeepMind / xAI / Meta response
- Specific Nando de Freitas full background + DeepMind → Microsoft transition timeline
- Specific causal-inference methodology cited (Pearl-style? Other?)
- Whether the proposal includes concrete evaluation benchmarks vs current SFT+RLHF pipeline
