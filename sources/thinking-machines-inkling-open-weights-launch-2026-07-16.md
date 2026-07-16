---
title: "Thinking Machines Lab launches Inkling — a 975B-MoE open-weights model + Tinker fine-tuning platform (2026-07-15)"
type: source
medium: article
url: https://thinkingmachines.ai/news/introducing-inkling/
ingested: 2026-07-16
---

## Summary

[[thinking-machines|Thinking Machines Lab]] ([[mira-murati|Mira Murati]]'s lab) publishes its **first model, [[inkling|Inkling]]** (2026-07-15) — an **open-weights** Mixture-of-Experts transformer (**975B total / 41B active**, 1M context), released with full weights on Hugging Face plus the **Tinker** fine-tuning platform. Notably self-positioned as *"not the strongest overall model available today, open or closed,"* but *"a good open-weights base for customization."* A US frontier lab shipping an open model is the structural event; anchor source for [[thinking-machines]], [[inkling]], and [[mira-murati]]. *(Primary fetched for accuracy.)*

## Key Claims / Takeaways

- **Model**: MoE transformer, 975B total / 41B active, up to 1M context. 256 routed + 2 shared experts (6 routed active/token); interleaved sliding-window + global attention (5:1, 8 KV heads); relative positional embeddings (not RoPE); short convolutions; multimodal + **controllable thinking**. **Inkling-Small** (276B/12B active) in preview.
- **Training**: pretrained on **45T tokens** (text/image/audio/video); post-trained with RL scaled to **30M+ rollouts** (Muon + Adam); reasoning reward improved log-linearly (0.264 → 0.356).
- **Benchmarks** (vendor-published): HLE w/ tools **46.0%**, AIME 2026 **97.1%**, GPQA Diamond **87.2%**, SWEBench Verified **77.6%**, FORTRESS adversarial **78.0%**.
- **Distribution**: full weights + **NVFP4 (Blackwell)** checkpoint on HF (`thinkingmachines/inkling`); **Tinker** fine-tuning (50%-off launch promo); inference via TogetherAI / Fireworks / Modal / Databricks / Baseten + SGLang / vLLM / llama.cpp; free playground.
- **Rationale**: *"build AI that extends human will and judgment"*; open *"so that people can make it their own."*

## Why it matters

- **First frontier-lab (US) open-weights release of this cycle** — the [[dailybrief-roundup-2026-07-16|brief]]'s read: *"a credibility move, not a commodity one… means they're confident enough in safety or convinced enough that the frontier isn't closed."* Enters the arena led by [[deepseek|DeepSeek]] / [[moonshot-ai|Moonshot]] / [[qwen|Qwen]].
- **Strategy = adaptation infrastructure over model rank** — Inkling + Tinker sells *customizability* (fine-tune it behind your own boundary), aligning with the [[reverse-information-paradox|"own your learning loop"]] thesis.

## Pages Updated
- [[thinking-machines]] (new), [[inkling]] (new), [[mira-murati]] (new)

## Verification-pending
- **License** — the announcement says "open-weights"/"full weights available" but names no license; confirm terms before relying (redistribution / commercial use).
- Independent benchmark replication (all figures are Thinking Machines-published).
- Whether Inkling-Small's "matches or exceeds" claim holds on release.
