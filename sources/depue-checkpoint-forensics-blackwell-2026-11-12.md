---
title: "Top Chinese Frontier AI Models Carry the Fingerprint of Export-Controlled NVIDIA Blackwell GPUs"
type: source
medium: article
url: https://unemploymentlabs.com/checkpoint-forensics
ingested: 2026-11-15
---

## Summary

Will DePue's report at Unemployment Labs (2026-11-12), the primary source behind the fingerprint claim the wiki had recorded second-hand from AINews ([[ainews-jensen-huang-resigns-hydrogen-2026-11-12]]) and TechCrunch ([[nvidia-after-huang-techcrunch-2026-11-13]]). Fetched from the 2026-11-15 brief ([[dailybrief-roundup-2026-11-15]]). It reads the GPU type out of published open weights. PyTorch fills a model's starting weights from a seeded random generator, and how the numbers are laid out depends on how many processor cores the GPU has. Enough of that layout survives training to identify the hardware class. The report finds six Chinese models from four labs initialized on Blackwell GPUs, which need a US license to ship to China. **Correction:** the report was revised on 11-12 and roughly doubled its GPU estimate. The "2–3K Blackwells" figure on the AINews page is the pre-revision number.

## Key Claims / Takeaways

- **Finding:** *"Six models released by these companies since April 2026 contain numerical patterns matching Blackwell hardware, whereas earlier models from the same companies match NVIDIA’s older Hopper generation."* The six are DeepSeek-V4-Flash, DeepSeek-V4-Pro, Kimi K3, Kimi K3.1-Pro, MiniMax-M3 and Ant Group's Ling-3.1-flash.
- **What it doesn't show:** the findings *"do not establish where the chips were located, how access was obtained, or whether export controls were violated."* The fingerprint shows how the weights were initialized and *"supports, without proving, the inference that Blackwell also performed the training."*
- **Validation:** *"For 24 specific models, the developer has publicly said what hardware was used. In every case, our method agrees with the public announcement."* For DeepSeek-V4-Flash and Kimi K3 the match was also confirmed on physical Blackwell chips.
- **Strength of evidence:** the best chance match across the search would be *"about 8 sigma"*, while *"The strongest evidence for each of the six models ranges from 49 to 1,385 sigma."*
- **Not everyone switched:** *"The newest models we could read from Alibaba (Qwen), Zhipu (GLM), Tencent, Xiaomi and StepFun all read as Hopper-trained."*
- **Scale, revised:** for Kimi K3 and DeepSeek-V4-Pro, *"Our best estimates are about 4,500 and 3,000"* Blackwell GPUs for two to three months, and *"about 12,000 Blackwell GPUs across the five runs"*. The revision note: *"The first version of this report gave 2,000 to 3,000 Blackwell GPUs for the largest runs"*, which assumed Nvidia-benchmark efficiency. The author says *"We are not confident in these estimates"*, mainly because run lengths aren't known.
- **Limits:** the method *"needs published weights, so closed models cannot be checked"*, and it doesn't work for every framework (Baidu's PaddlePaddle) or for weights initialized on a CPU (several Qwen3 models).
- **For the owner:** a clean example of a verifiable claim built from public artifacts alone, with a stated method, a validation set and an error model. The wiki's earlier "critics say export controls are mostly holding" point was made against the smaller, superseded estimate. [Judgment.]

## Pages Updated

- [[nvidia]] — Traction Signals
- [[deepseek]] — Recent Activity
- [[kimi-k3]] — Community Sentiment
- [[ainews-jensen-huang-resigns-hydrogen-2026-11-12]] — correction note on the GPU estimate
