---
name: Moonshot AI
type: company
status: active
last_updated: 2026-10-29
---

## What It Is

Chinese AI lab, maker of the **Kimi** model family (the wiki's canonical anchor is **Kimi K2.6**), one of the Chinese open-weights frontier vendors tracked alongside [[z-ai|Z.ai]] ([[glm-5-2|GLM-5.2]]), [[deepseek|DeepSeek]], and [[qwen|Qwen]] ([[alibaba|Alibaba]]).

## Recent Activity

- **2026-10-28 (reported) — Kimi K3.1 Pro trained heavily on GPT-6 Astra outputs** ([[deepseek-moonshot-astra-distillation-2026-10-28]], The Information via Reuters). Moonshot didn't respond. → [[kimi-k3]]

- **2026-10-23 — Kimi K3.1 Pro and Highspeed** ([[kimi-k3-1-pro-launch-2026-10-23]]): 2.8T total / 104B active, 1M context, live on the API; open weights planned by 11-04. Moonshot removed cybersecurity data from post-training. Benchmarks are mostly social-sourced. → [[kimi-k3]]
- **2026-10-21 (reported) — Kimi in an attack harness** ([[claude-grok-latam-financial-attacks-2026-10-21]]): steps Claude refused were rerouted to Kimi. → [[ai-vulnerability-discovery]]
- **2026-07-16 — [[kimi-k3|Kimi K3]] (2.8T-A50B), "largest open model ever released"** ([[kimi-k3-largest-open-model-2026-07-16]]): 2.8T-param MoE (~50B active); self-benchmarks *"mostly beating Opus 4.8 max + GPT-5.5 high"* but losing to Fable 5 / GPT-5.6 Sol; Artificial Analysis Elo 1547; #1 on Arena.ai Frontend Code. **Priced at Sonnet tier ($3/$15) — a step *up* from K2.6's $0.95/$4.** Open-weight drop **promised by 2026-07-27** (API/website/OpenRouter now). An open-weight scaling inflection for the [[ai-margin-collapse]] thesis.
- **Kimi K2.6 as a loop-engineering workhorse**: surfaced most substantively via [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|0xMovez's 10-step playbook]], which pairs **Kimi K2.6 (300 parallel agents × 4,000 coordinated steps)** as the cheap generator with [[claude-opus-4-8|Opus 4.8]] as the verify-gate — a concrete 2-model split-architecture. Cited pricing there: ~$0.95/M in + $4.00/M out + $0.16 cache hits. *(Specifics per that source; primary not independently fetched.)*
- Referenced across the June 2026 Chinese-open-weights clusters ([[chinese-openweights-political-ai-jun-18-cluster-2026-06-18]], [[jun-19-open-source-research-origin-cluster-2026-06-19]]).

## Compared To

- [[z-ai|Z.ai]] ([[glm-5-2|GLM-5.2]]), [[deepseek|DeepSeek]], [[qwen|Qwen]] — peer Chinese-open-weights vendor cluster.

## Resources

- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — Kimi K2.6 + Opus 4.8 split-architecture playbook.
- [[ai-margin-collapse]] — the economics thesis Kimi-class open weights help drive.
- [[loop-engineering]] — Kimi K2.6 as the cheap-generator half of a generator/verifier loop.
