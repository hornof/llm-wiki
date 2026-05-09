---
name: Unconventional AI
type: company
status: early-stage
last_updated: 2026-05-08
---

## What It Is

Unconventional AI ([unconv.ai](https://unconv.ai/)) is an AI hardware-software co-design company pursuing a **1000× energy-efficiency advantage for GenAI inference** over state-of-the-art conventional hardware (GPUs/TPUs), measured end-to-end as **Joules per token** (text) or **Joules per image** (image), iso-quality. Founded by [[naveen-rao]]; [[peter-mcmahon]] is a Research Fellow.

The company is building **AI models and AI hardware from the ground up together** ("neural co-evolution") — designing CMOS circuits to match model architectures rather than mapping a model onto general-purpose silicon. The bet is that aggressive co-design buys you "10 factors of 2× or 3 factors of 10×" that compound to 1000×.

## Technical Thesis

Two design constraints frame the entire approach ([[mcmahon-1000x-energy-efficiency-2026-05]]):

1. **Data movement, not arithmetic, dominates inference energy.** Off-chip HBM reads cost >>1000× the energy of an 8-bit integer multiply. Modern frontier models (>1T parameters, >100B active) cannot fit on a single chip, so HBM access is the dominant cost. Off-chip memory consumes 20%+ of GPU power in current GenAI inference datacenters.
2. **Amdahl's Law in energy.** If 99% of energy is optimized to zero, the system-level cap is 100×. To clear 1000×, **everything must be optimized** — no overhead component above 0.1% of the original budget can remain unoptimized. This is what forces full-stack co-design rather than point optimizations.

## Approach

A combinable toolkit (no single approach is sufficient):
- Specialization to model architectures (dataflow, spatial CMOS layout)
- Specialization to specific trained models via hard-wired parameters (cf. [Taalas](https://taalas.com/))
- Parameter efficiency (deep equilibrium, recursive models)
- Sparsity (sparse recurrent ≈ dense feedforward in accuracy at lower power)
- Avoid Attention (state-space / Mamba — sidesteps KV cache)
- Allow non-mathematical-isomorphism (CMOS as physical neural networks: coupled oscillators, trained lookup tables)
- Analog circuits where they help, digital elsewhere
- Tolerate noise (don't over-engineer SNR; train with noise in the loop)

**Wind tunnel test** for candidate physical-NN circuits: must be expressive, parameter-rich, *expensive to simulate digitally* (otherwise just simulate it), and trainable by gradient descent.

## Traction Signals

- **Public technical thesis** (May 7, 2026) — full-length blog post with explicit metrics, baselines, and approach taxonomy. Unusual transparency for an early-stage AI hardware company.
- **Naveen Rao LinkedIn amplification** (May 8, 2026) — "we're building in the open" stance, with substantive technical comments from practitioners (Boy Kester on coordination physics, Sidney Scott on heterogeneous-fleet traverse, Duane Schwingel on data-movement-dominated optimization). — [[nrao-linkedin-1000x-2026-05]]
- Funding, headcount, customers, silicon timelines: not disclosed in ingested sources. Stub page; promote beyond `early-stage` only on stronger primary evidence.

## Caveats

- 1000× is a multi-year R&D bet, not a near-term shipping product. Anchored against **2030 conventional-hardware projections**, not 2026 SOTA — disciplined framing, but means commercial validation is far out.
- Direct competitive landscape (Cerebras, Groq, SambaNova, Lightmatter, Etched, Taalas, etc.) not enumerated in ingested sources — this page should be expanded as comparative pieces are ingested.

## Resources

- [[mcmahon-1000x-energy-efficiency-2026-05]] — primary technical thesis (May 7, 2026)
- [[nrao-linkedin-1000x-2026-05]] — Naveen Rao's amplification + practitioner comments (May 8, 2026)
- [[naveen-rao]] — founder
- [[peter-mcmahon]] — Research Fellow / essay author
- [[ai-energy-efficiency]] — concept page
- Site: https://unconv.ai/
