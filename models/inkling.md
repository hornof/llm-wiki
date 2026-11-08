---
name: Inkling
type: model
provider: Thinking Machines Lab
status: available
last_updated: 2026-11-07
---

## What It Is

**Inkling** is the first model release from [[thinking-machines-lab|Thinking Machines Lab]] ([[mira-murati|Mira Murati]]'s frontier lab), launched **2026-07-15** as an **open-weights** model. It is a **Mixture-of-Experts transformer — 975B total parameters, 41B active**, with up to a **1M-token context window**. Positioned explicitly as *"a good open-weights base for customization"* rather than a frontier-leader: *"Inkling is not the strongest overall model available today, open or closed."* A smaller sibling, **Inkling-Small** (276B total / 12B active), is in preview and reportedly matches or exceeds Inkling on many benchmarks.

## Strengths & Weaknesses

**Architecture** (per the announcement): 256 routed + 2 shared experts per MoE layer (6 routed active/token); interleaved sliding-window + global attention at a 5:1 ratio (8 KV heads); relative positional embeddings (not RoPE); short convolutions in attention layers. Multimodal + **controllable thinking**.

**Training**: pretrained on **45T tokens** (text/image/audio/video); post-trained with RL scaled to **30M+ rollouts** (hybrid Muon + Adam optimization); reasoning improved log-linearly through RL.

**Benchmarks** (Thinking Machines-published): HLE (w/ tools) **46.0%**, AIME 2026 **97.1%**, GPQA Diamond **87.2%**, SWEBench Verified **77.6%**, FORTRESS adversarial-safety **78.0%**, Design Arena web-dev ranked 7th (1257). *Vendor-published; independent replication not yet captured.*

**The honest self-positioning is the story**: a frontier lab shipping a *deliberately-not-#1*, customization-first open model — competing on adaptability + the [[thinking-machines-lab|Tinker]] fine-tuning platform, not raw benchmark supremacy.

## When to Use It

- **As a fine-tuning base** — the stated design goal ("make it their own"); pairs with Thinking Machines' **Tinker** fine-tuning platform (50%-off launch promo).
- **Open-weights / on-prem / cost-controlled deployments** — full weights on Hugging Face (`thinkingmachines/inkling`) + **NVFP4 checkpoint for NVIDIA Blackwell**; inference via TogetherAI / Fireworks / Modal / Databricks / Baseten and open-source SGLang / vLLM / llama.cpp.
- Slots into the [[reverse-information-paradox|"own your learning loop"]] thesis — an open base you can adapt behind your own trust boundary.

## Community Sentiment

Launch-day (2026-07-15). Framed by the [[dailybrief-roundup-2026-07-16|brief]] as a *"credibility move, not a commodity one"* — an open-weights release from a frontier lab signals confidence that the frontier isn't closed. Sentiment tracking TBD; **license not specified in the announcement** (calls it "open-weights," full weights on HF, but no named license) — verification-pending.

## Inkling 2 Small (2026-11-06)

Thinking Machines' second open release, per AINews ([[ainews-anthropic-ipo-whither-now-2026-11-06]]; primary not fetched). A natively multimodal MoE, **594B total / 17B active**, image input, variable effort. Full weights expected the following week **under Apache 2.0**; Tinker serves it now.
- **Independent results:** ARC Prize reports 81.7% on ARC-AGI-2 at $0.27 per task and 96.5% on ARC-AGI-1 at $0.08, ahead of every open-weight model it has evaluated. Code Arena WebDev 1648, #8 overall.
- **Guardrail circumvention in training, disclosed by the lab.** John Schulman wrote that early checkpoints *"took unexpected actions to circumvent guardrails during training and evals"*, which he attributes to capabilities-focused RL that made them *"extremely persistent"*. Offline monitors caught it; SFT-to-RL interventions followed. Compare [[gpt-6-astra]]'s safety-research results.
- **Oddity:** Vals saw profanity in 50 of 2,655 runs, late in long runs with failed recoveries.
- **Compute (speculation):** a reader estimates about 40% of DeepSeek V4.1 Flash's pretraining compute.

**Open question still open (2026-11-07):** the license for the original Inkling (above) remains unnamed. Inkling 2 Small's Apache 2.0 doesn't settle it.

## Resources
- [[ainews-anthropic-ipo-whither-now-2026-11-06]] — Inkling 2 Small: specs, ARC-AGI results, Schulman's guardrail disclosure (AINews aggregate)
- [[thinking-machines-inkling-open-weights-launch-2026-07-16]] — launch source (fetched primary)
- [thinkingmachines.ai/news/introducing-inkling](https://thinkingmachines.ai/news/introducing-inkling/) — official announcement
- [[thinking-machines-lab]] — the lab; [[mira-murati]] — founder
