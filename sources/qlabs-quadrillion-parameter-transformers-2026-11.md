---
title: "Quadrillion-parameter transformers and how to train them"
type: source
medium: article
url: https://qlabs.sh/research/parameters
ingested: 2026-11-08
---

## Summary

Q Labs research post (Vegesna, Baron, Satheesh, Dahal; November 2026) summarizing their paper *Improving Data-Constrained Scaling with Hyperparameter Transfer and Ensembling* (Baron et al., arXiv:2610.37842). They fit a scaling law for training on a fixed dataset for many epochs, with terms for overfitting and ensembling. Their claim: when data is the limit, compute-optimal models are far larger than Chinchilla prescribes, provided weight decay scales up and checkpoints are ensembled. The headline numbers are extrapolations, not trained models.

## Key Claims / Takeaways

- **Headline (extrapolated).** *"Extrapolated to 5T tokens, our law prescribes ~7,000× Chinchilla's parameter count at 10 29 FLOPs, and the count keeps growing with compute."* (The "10 29" is 10^29 with the superscript lost in extraction.) No quadrillion-parameter model was trained; the title describes a prescription.
- **The motivation.** *"The 1,000,000x sample efficiency gap between AI and humans is one of the central mysteries of the field"*. Counting synapses as weights, they argue current networks are too small *"by seven orders of magnitude"*.
- **Weight decay has to scale.** *"We find that optimal weight decay grows steeply with epochs and with model size."* Prior data-constrained laws held it fixed and so predict loss rising with compute.
- **The law extrapolates, within their tests.** *"it is near-optimal at 16x of the fitted compute, and within 0.01 nats of the optimal loss on every axis we test"*.
- **Ensembling as a scaling axis.** Snapshot ensembling (averaging checkpoints from one run under a cyclic learning rate) *"costs no extra training compute"*. Deep ensembling becomes compute-optimal when compute is large relative to data, after which *"the optimal number of members grows roughly linearly with compute"*.
- **Result at small scale.** On 100M tokens, *"The prior recipe gets worse with compute"*, while scaled hyperparameters plus ensembling keep loss falling.
- **Their own limit.** Going further *"will require new algorithms, hardware and more"*.
- Same lab as the backprop-free pretraining post noted in [[dailybrief-roundup-2026-10-06]].

## Pages Updated

- [[data-constrained-scaling]] — new page
