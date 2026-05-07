---
title: "microgpt: Distilling GPT to Its Algorithmic Essence"
type: source
medium: article
url: http://karpathy.github.io/2026/02/12/microgpt/
ingested: 2026-05-06
---

## Summary
Andrej Karpathy releases microgpt: a single 200-line, zero-dependency Python file that trains and runs a GPT-like language model from scratch. Companion to nanoGPT and micrograd. The point is pedagogical: strip GPT to its bare algorithmic essentials so the implementation is mechanically transparent and "Everything else is just efficiency."

## Key Claims / Takeaways
- **Scope**: tokenizer, autograd engine (`Value` class implementing scalar autodiff), GPT-2-style transformer (token+pos embeddings, MHA, MLP, residuals, RMSNorm, explicit KV cache), Adam optimizer with linear LR decay, training loop, inference loop — all in 200 lines, no deps.
- **Dataset**: 32,000 names; 27-token vocab (a-z + BOS); one document per training step.
- **Model size**: 4,192 parameters (vs GPT-2's 1.6B). Loss falls 3.3 → 2.37 over 1,000 steps.
- **Autograd framing**: "This is the same algorithm that PyTorch's `loss.backward()` runs, just on scalars instead of tensors." Anchor for understanding modern frameworks.
- **Intentional omissions**: GPU acceleration, BPE/tiktoken, batching, mixed precision, RoPE, GQA/MoE, modern variants. These are explicitly framed as efficiency, not essence.
- **Pedagogical scaffolding**: progression `train0.py` → `train5.py` available as GitHub diffs, building understanding in layers. Companion FAQ on whether the model "understands" — answer is mechanically transparent.
- **Pithy line**: "Everything else is just efficiency."
- **Provenance line**: "the culmination of multiple projects... and a decade-long obsession to simplify LLMs to their bare essentials."

## Pages Updated
- [[microgpt]] — new tools/ page (Karpathy educational artifact)
- [[andrej-karpathy]] — added microgpt to the pedagogical lineage (nanoGPT, micrograd, microgpt)
- [[eureka-labs]] — implicit pedagogical-mission alignment (no edit warranted)
- [[index]] — added microgpt under Tools & Frameworks; source under Recent ingests
