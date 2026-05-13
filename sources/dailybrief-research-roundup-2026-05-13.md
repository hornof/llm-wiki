---
title: Daily Brief research roundup — 2026-05-13
type: source
medium: article
url: https://www.arxiv.org/
ingested: 2026-05-13
---

## Summary

Aggregator entry for the three arXiv papers surfaced in the **Research** block of `Daily Briefs/2026-05-13.md`. None individually merits a dedicated source page on the brief's own framing ("incremental but solid" or "niche"), but the cluster is worth capturing for cross-reference. No primary-source fetches performed in this batch — titles, abstracts and framing are from the brief; arXiv IDs taken verbatim.

## Papers

### Rotation-Preserving Supervised Fine-Tuning ([arXiv:2605.10973](https://arxiv.org/abs/2605.10973))

- **Problem**: standard SFT degrades pretrained representations by rotating subspaces away from their pretrained alignment, hurting OOD generalization.
- **Approach**: SFT regularizer that *preserves rotation* of pretrained subspaces while still adapting task-specific directions.
- **Wiki relevance**: low if [[end-of-finetuning]] thesis holds — but **non-zero** for the "top 1% who still finetune" (Cognition, Cursor RLFT). Worth a note in [[end-of-finetuning]] under "What's keeping finetuning research alive."

### LEAP — Enabling dLLM Parallelism via Lookahead Early-Convergence Token Detection ([arXiv:2605.10980](https://arxiv.org/abs/2605.10980))

- **Problem**: diffusion LLMs (dLLMs) generate via iterative denoising; tokens converge at different speeds and naive parallelism wastes compute.
- **Approach**: early-convergence detection lets parallel inference move past finished tokens without waiting for the full batch.
- **Wiki relevance**: diffusion LMs remain nascent; tag as **watch-only** until a frontier-scale dLLM ships. Related to [[ai-energy-efficiency]] (data-movement-dominates-arithmetic — this is the arithmetic side, not the binding constraint per [[mcmahon-1000x-energy-efficiency-2026-05]]).

### Structural Interpretations of Protein Language Model Representations via Differentiable Graph Partitioning ([arXiv:2605.10985](https://arxiv.org/abs/2605.10985))

- **Problem**: ESM-2 and similar protein language models produce embeddings whose internal structure is opaque.
- **Approach**: differentiable graph-partitioning on attention/representation graphs surfaces interpretable substructures.
- **Wiki relevance**: outside wiki's current AI-engineering-career focus, but slot under [[ai-for-science]] and [[mechanistic-interpretability]] for biotech-adjacent role surfacing.

## Cross-References

- [[end-of-finetuning]] — rotation-preserving SFT is a counterweight datapoint
- [[ai-energy-efficiency]] — LEAP is an arithmetic-side optimization, distinct from the memory-bandwidth bottleneck
- [[ai-for-science]] — protein-LM interpretability paper
- [[mechanistic-interpretability]] — protein-LM interpretability paper

## Pages Updated

- (aggregator only; no entity pages updated from this source)
