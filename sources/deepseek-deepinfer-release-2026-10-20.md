---
title: "deepseek-ai/DeepInfer — DeepSeek's production inference framework, open-sourced in part"
type: source
medium: github-repo
url: https://github.com/deepseek-ai/DeepInfer
ingested: 2026-10-20
---

## Summary

[[deepseek|DeepSeek]] released **DeepInfer**, described as "the high-performance inference framework that powers DeepSeek's large-scale production services," under Apache 2.0. It supports only DeepSeek-V4.1-Flash, for offline inference, on **NVIDIA SM100 GPUs and Huawei Ascend 950 NPUs.** Three parts the README says a complete service needs are not included.

## Key Claims / Takeaways

- **Features:** asynchronous scheduling, structured outputs, deterministic sampling.
- **Hardware:** NVIDIA SM100 (CUDA 13) and Huawei Ascend 950 (CANN 9.2). The benchmarks used 4 GPUs for prefill and 64 for decode, each within one scale-up domain. The performance figures are only in chart images, not in the text.
- **Not released:** the KV cache system; prefill/decode disaggregation (the README says most of the engine work for it is already in); load balancing across data-parallel replicas.
- **Repo at capture:** about 10.7k stars (the brief said 8.4k), 943 forks, no releases.
- The Digg item relays a Latent Space translation saying some components of the production system are not yet fully open.

## Pages Updated

- [[deepseek]] — recent activity
