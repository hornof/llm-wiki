---
title: "GPT-6 models demonstrate intrinsic protein-design capabilities"
type: source
medium: article
url: https://openai.com/index/gpt-6-models-demonstrate-intrinsic-protein-design-capabilities/
ingested: 2026-11-24
local_source: "_raw/openai-gpt-6-protein-design-2026-11-24.txt"
---

## Summary

OpenAI reports (with a preprint) that GPT-6 models can design protein structures and sequences using only reasoning and general-purpose code, without calling specialized biology models. Lab tests with Onava found binders for all five targets, though specialized models still supplied sequences and picked candidates for the first experiment. The brief asked for the denominator; it's in the post: 35 of 322 minibinders bound, a lower hit rate than the original RFdiffusion study, which OpenAI says depends on filtering.

## Key Claims / Takeaways

- **The claim** (OpenAI): the models *"can design new protein structures and sequences without relying on specialized biology models, using only reasoning and general-purpose coding tools."* Computationally they did *"comparably to or better than specialized models on most tasks, although predicting a complete protein structure remained a clear weakness."*
- **Lab experiment 1, the denominator** (OpenAI): *"We tested 322 minibinders against 5 targets in the lab. Of those, 35 (10.9%) tested positive for binding to their intended target."* GPT-6.2 drew the 3D shapes; SolubleMPNN, a specialized model, supplied the sequences. The original RFdiffusion study *"reported higher hit rates"* (a link marker sits inside the sentence on OpenAI's page).
- **Lab experiment 2, sequences from GPT-6.2** (OpenAI): binding in *"75 of 88 designs for MDM2 (85%), 26 of 42 for VEGF-A (62%), and 8 of 59 for PD-1 (14%)"*. For unpublished shapes, *"Of the 107 proteins made from GPT‑6.2’s new sequences, 14 (13.1%) showed binding."* OpenAI reads the unpublished structures and divergent sequences as evidence against memorization.
- **Antibodies** (OpenAI): redesigned loops kept binding in *"128 (70%)"* of 182 designs, and *"179 (66%)"* of 272 therapeutic-antibody fragments bound the original target.
- **Motif scaffolding, computational only** (OpenAI, preliminary): *"43.7% of the designs we evaluated from our latest internal model met both criteria, compared with 27.8% for RFdiffusion."*

## Pages Updated

- [[ai-for-science]]
- [[gpt-6-2]]
