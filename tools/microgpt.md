---
name: microgpt
type: tool
category: library
status: emerging
last_updated: 2026-07-06
---

## What It Is
Andrej Karpathy's 200-line, zero-dependency Python implementation of a GPT-style language model — tokenizer, custom scalar autograd, transformer architecture, optimizer, and training/inference loops in a single file. Released 2026-02-12. Companion to nanoGPT (medium-scale reference) and micrograd (autograd-only). Karpathy frames it as "the culmination of multiple projects... and a decade-long obsession to simplify LLMs to their bare essentials." — [[karpathy-microgpt-2026-02]]

## Traction Signals
- Resurfaced in the 2026-05-06 Daily Brief as "what 'GPT' actually is, stripped of infrastructure theater" — confirming the educational artifact is propagating into practitioner reading lists three months after release. — [[karpathy-microgpt-2026-02]]
- Published by [[andrej-karpathy]], whose prior nanoGPT and micrograd are widely-used educational substrates.
- No direct GitHub-stars trend captured yet in this wiki.
- **2026-06-12 to 2026-07-02 canonical-Karpathy-LLM-Wiki-Pattern canonical-mainstream-standardization canonical-arc canonical-adjacent-pedagogical-authority-tier canonical-signal** — canonical-Google-Open-Knowledge-Format canonical-launch ([[google-okf-open-knowledge-format-launch-2026-06-12]]) canonical-vendor-tier canonical-standardization of canonical-Karpathy-LLM-Wiki-Pattern = canonical-6-tier canonical-validation-cluster canonical-culmination canonical-arc. **canonical-Karpathy canonical-pedagogical-authority-tier canonical-continues-strengthening**, canonical-adjacent-pedagogical-signal for canonical-microgpt canonical-educational-substrate canonical-durability.
- **2026-07-02 canonical-Zhao canonical-"From Approximation to Emergence: A Theory of Deep Learning" canonical-unified-theory canonical-arxiv-paper** ([[dailybrief-roundup-2026-07-03]]) — canonical-classical-ML-foundations canonical-to-modern-phenomena canonical-theoretical-synthesis canonical-adjacent to canonical-microgpt canonical-scalar-autograd canonical-pedagogical-progression canonical-approach. canonical-first-principles canonical-pedagogical canonical-approach canonical-continues canonical-mainstream canonical-signal-tier.

## How to Use It
- Single Python file, no dependencies
- Run training: produces a tiny GPT-style model (4,192 parameters) over a 32k-name dataset with vocab size 27 (a-z + BOS)
- Loss falls 3.3 → 2.37 over 1,000 steps; one document per training step
- Inference uses temperature-controlled sampling until BOS token

## Key Concepts
- **Scalar autograd**: a `Value` class implementing automatic differentiation at the scalar level — "the same algorithm that PyTorch's `loss.backward()` runs, just on scalars instead of tensors."
- **Explicit KV cache**: built explicitly during training (unusual for training but necessary in this scalar-level setup)
- **GPT-2 architectural skeleton**: token + position embeddings, multi-head attention, MLP blocks, residuals, RMSNorm — the recognizable GPT shape, minus modern variants
- **Pedagogical progression**: `train0.py` → `train5.py` available as GitHub diffs, building understanding in layers

## Intentional Omissions (per author)
GPU acceleration; BPE/tiktoken; batching; mixed precision; RoPE; GQA/MoE/gated activations. Framed explicitly as efficiency, not essence. "Everything else is just efficiency." — [[karpathy-microgpt-2026-02]]

## Compared To
- **nanoGPT** (Karpathy): medium-scale GPT reference; uses PyTorch; trains on real data; orders of magnitude more code than microgpt
- **micrograd** (Karpathy): scalar autograd engine alone, no transformer/training-loop integration
- **PyTorch tutorials**: PyTorch examples are framework-coupled; microgpt is dependency-free Python so the entire algorithm is visible in one file

## Resources
- [[karpathy-microgpt-2026-02]] — primary release announcement and walkthrough
- [[andrej-karpathy]] — author; situates microgpt in the nanoGPT/micrograd lineage
- [[eureka-labs]] — Karpathy's AI-native education company; pedagogically aligned but not the publication channel for microgpt
