---
title: "Hyper Optimizing Kimi K3 in vLLM"
type: source
medium: article
url: https://vllm.ai/blog/2026-10-16-kimi-k3-megakernel
ingested: 2026-10-18
---

## Summary

vLLM blog post (2026-10-16) by Benjamin Chislett of [[nvidia|NVIDIA]] describing a specialised decode path for [[kimi-k3|Kimi K3]] on GB300 GPUs. Most per-layer operations are fused into custom CuTe DSL kernels, cutting a layer from 23 kernels and about 130 µs to 13 kernels and about 69 µs. Reported decode speedups are 1.6–1.9× at TP16 and 1.3–1.6× at TP8 against stock vLLM.

## Key Claims / Takeaways

- **Hardware scope:** GB300, 8 or 16 GPUs in one NVLink domain, decode batches 1–64.
- **Techniques:** fused custom kernels; the attention output projection fused with its all-reduce; MoE router work split across tensor-parallel ranks, with the shared expert on its own stream; weight prefetch during communication; optional decode context parallelism for long contexts.
- **Numbers, no speculative decoding:** TP16 1.62–1.88× (batch 1: 256.4 tok/s); TP8 1.31–1.58× (batch 1: 193.3 tok/s).
- **Numbers, with speculative decoding:** 842 vs 488 tok/s at batch 1, TP16 (1.73×), using a synthetic acceptance length of 6. A per-user interactivity comparison (403 vs 224 tok/s) compares 16 GPUs against an earlier 8-GPU result, so it is not like-for-like.
- **Availability:** vLLM PR #61867. The post does not say whether the path is on by default. A follow-up PR for DeepSeek-V4.1-Flash makes the same idea opt-in (`decode_backend: latency_specialized`).
- The post adds no new architecture facts beyond KDA and attention layers, tensor-parallel experts and a shared expert.

## Pages Updated

- [[kimi-k3]] — new section on serving cost
