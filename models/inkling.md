---
name: Inkling
type: model
provider: Thinking Machines Lab
status: available
last_updated: 2026-07-16
---

## What It Is

**Inkling** is the first model release from [[thinking-machines|Thinking Machines Lab]] ([[mira-murati|Mira Murati]]'s frontier lab), launched **2026-07-15** as an **open-weights** model. It is a **Mixture-of-Experts transformer — 975B total parameters, 41B active**, with up to a **1M-token context window**. Positioned explicitly as *"a good open-weights base for customization"* rather than a frontier-leader: *"Inkling is not the strongest overall model available today, open or closed."* A smaller sibling, **Inkling-Small** (276B total / 12B active), is in preview and reportedly matches or exceeds Inkling on many benchmarks.

## Strengths & Weaknesses

**Architecture** (per the announcement): 256 routed + 2 shared experts per MoE layer (6 routed active/token); interleaved sliding-window + global attention at a 5:1 ratio (8 KV heads); relative positional embeddings (not RoPE); short convolutions in attention layers. Multimodal + **controllable thinking**.

**Training**: pretrained on **45T tokens** (text/image/audio/video); post-trained with RL scaled to **30M+ rollouts** (hybrid Muon + Adam optimization); reasoning improved log-linearly through RL.

**Benchmarks** (Thinking Machines-published): HLE (w/ tools) **46.0%**, AIME 2026 **97.1%**, GPQA Diamond **87.2%**, SWEBench Verified **77.6%**, FORTRESS adversarial-safety **78.0%**, Design Arena web-dev ranked 7th (1257). *Vendor-published; independent replication not yet captured.*

**The honest self-positioning is the story**: a frontier lab shipping a *deliberately-not-#1*, customization-first open model — competing on adaptability + the [[thinking-machines|Tinker]] fine-tuning platform, not raw benchmark supremacy.

## When to Use It

- **As a fine-tuning base** — the stated design goal ("make it their own"); pairs with Thinking Machines' **Tinker** fine-tuning platform (50%-off launch promo).
- **Open-weights / on-prem / cost-controlled deployments** — full weights on Hugging Face (`thinkingmachines/inkling`) + **NVFP4 checkpoint for NVIDIA Blackwell**; inference via TogetherAI / Fireworks / Modal / Databricks / Baseten and open-source SGLang / vLLM / llama.cpp.
- Slots into the [[reverse-information-paradox|"own your learning loop"]] thesis — an open base you can adapt behind your own trust boundary.

## Community Sentiment

Launch-day (2026-07-15). Framed by the [[dailybrief-roundup-2026-07-16|brief]] as a *"credibility move, not a commodity one"* — an open-weights release from a frontier lab signals confidence that the frontier isn't closed. Sentiment tracking TBD; **license not specified in the announcement** (calls it "open-weights," full weights on HF, but no named license) — verification-pending.

## Resources
- [[thinking-machines-inkling-open-weights-launch-2026-07-16]] — launch source (fetched primary)
- [thinkingmachines.ai/news/introducing-inkling](https://thinkingmachines.ai/news/introducing-inkling/) — official announcement
- [[thinking-machines]] — the lab; [[mira-murati]] — founder
