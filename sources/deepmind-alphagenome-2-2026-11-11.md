---
title: "AlphaGenome 2: Deciphering how cells read DNA to better understand disease"
type: source
medium: article
url: https://deepmind.google/blog/alphagenome-2-deciphering-how-cells-read-dna-to-better-understand-disease/
ingested: 2026-11-11
---

## Summary

[[google-deepmind|Google DeepMind]] (2026-11-11) announces AlphaGenome 2, which predicts how DNA variants change gene activity in specific cell types, not tissue averages as AlphaGenome 1 did. It is a conditional model: it takes the cell type or state as an input alongside the DNA sequence. All results are DeepMind's own.

## Key Claims / Takeaways

- **What changed:** *"AlphaGenome 2 is a conditional model that predicts DNA effects for one condition - defined as a tissue, cell type or state - at a time."* It also predicts DNA methylation.
- **Training data:** *"over 107 million individual cell profiles"*. The summary line says *"more than 100 million individual cell profiles across 68 tissues"*.
- **Headline result (vendor):** on TenK10K it *"identified nearly twice as many causal variants (30% vs. 16%) and directional gene effects (43% vs. 23%)"* as AlphaGenome 1 fine-tuned on single-cell data and other tools.
- **New cell states without retraining:** from *"just a few dozen cells"*, it can condition on cell states it hasn't seen, such as vaccine-activated T cells.
- **Access:** *"available today for non-commercial research via the AlphaGenome API, and in private preview for commercial research."* Predictions for trait-associated variants are precomputed.

## Pages Updated

- [[google-deepmind]] — Traction Signals
