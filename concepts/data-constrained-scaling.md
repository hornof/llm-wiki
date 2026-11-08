---
name: Data-Constrained Scaling
type: concept
maturity: active-research
last_updated: 2026-11-08
---

## Definition

Scaling laws for the case where the amount of unique training data is fixed and the only way to use more compute is to train bigger models for more epochs over the same data. Chinchilla-style laws assume fresh data grows with compute (about 20 tokens per parameter). Data-constrained laws add terms for repeating data, such as an overfitting penalty, and ask how model size, epochs and regularization should change when data runs out.

## Why It Matters

Compute is growing faster than the supply of high-quality text, so frontier pretraining is moving into multi-epoch training. If the right recipe there differs from Chinchilla, the cost and shape of future models changes with it: bigger models, more passes, more regularization.

## Current State

One measured claim in the wiki so far ([[qlabs-quadrillion-parameter-transformers-2026-11]], Q Labs, November 2026):
- With weight decay scaled up for model size and epochs, and with checkpoint ensembling, loss keeps falling as compute grows on a fixed dataset. Fixed-hyperparameter recipes get worse.
- Their fitted law stays near-optimal at 16× the fitted compute. Extrapolated to 5T tokens at 10^29 FLOPs, it prescribes about 7,000× Chinchilla's parameter count.
- The headline numbers are extrapolations from small runs (the shown curve is on 100M tokens). No large model trained this way is reported. Treat the "quadrillion-parameter" title as a prescription, not a result.

## Key Papers / Posts

- Baron et al., *Improving Data-Constrained Scaling with Hyperparameter Transfer and Ensembling* (arXiv:2610.37842), via [[qlabs-quadrillion-parameter-transformers-2026-11]]. It builds on Muennighoff et al. 2023 (*Scaling Data-Constrained Language Models*) and Lovelace et al. 2026; both are cited in the post, not ingested.

## Related Concepts

- [[simulation-scaling]] — another proposed scaling axis beyond more fresh data
