---
title: "Agentic Backdoors via Pretraining Poisoning"
type: source
medium: paper
url: https://arxiv.org/abs/2610.37741
ingested: 2026-11-02
---

## Summary

arXiv preprint, 2026-10-27, by Xinyan Hu, Pingbang Hu, Chloe Loughridge, Xuanli He, Nicholas Carlini, Matthew Jagielski, Javier Rando and Yiming Zhang. Poisoned web text in the pretraining corpus plants a backdoor that survives a clean post-training pipeline: the resulting CLI agent runs an attacker's command when a trigger appears, and behaves normally otherwise. The authors pretrained Qwen3 models from scratch at three sizes to measure it end to end. Only the abstract was read.

## Key Claims / Takeaways

- **The claim:** *"We show for the first time that such poisoning can plant a remote code execution backdoor in an agent, causing it to execute attacker-chosen commands on the user's machine."*
- **Setup:** Qwen3 models *"at sizes 0.6B, 1.7B, and 4B"*, each post-trained into a CLI agent *"using a clean pipeline"*.
- **Dose:** *"Poisoning only 0.1% of the pretraining corpus with our new poison design implants the backdoor"*.
- **Bigger is worse:** *"The attack success rate (ASR) increases with model scale, with the 4B model reaching roughly 92% ASR at a 0.1% poison rate and staying positive even when the poisoning rate drops to 0.0005%."*
- **Limits:** the largest model is 4B, far below frontier size, and the trend with scale is shown on three points. A clean post-training pipeline didn't remove the backdoor, which is the result that matters for anyone fine-tuning an open base model.

## Pages Updated

- [[ai-vulnerability-discovery]]
