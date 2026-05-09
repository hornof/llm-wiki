---
title: How to improve AI energy efficiency by 1000x
type: source
medium: article
url: https://unconv.ai/blog/how-to-improve-ai-energy-efficiency-by-1000x/
ingested: 2026-05-08
---

## Summary

Peter McMahon (Research Fellow at [[unconventional-ai]]) lays out the company's mission to achieve a **1000× energy-efficiency advantage** for GenAI inference over state-of-the-art conventional hardware (GPUs/TPUs), measured end-to-end in **Joules per token** (text) or **Joules per image** (image), iso-quality. The thesis: efficiency wins are bounded not by arithmetic but by data movement, so the path to 1000× requires hardware-software co-design from the ground up.

## Key Claims / Takeaways

- **Baseline**: largest models today use ~10 J/token (text) and >10,000 J/image (image). Throughput on an 8-GPU B200 system tops out around 1000 tokens/sec/user at ~14 kW.
- **TOPS / TOPS-per-Watt are the wrong metrics** — they invite apples-to-oranges comparisons. The end-to-end-system metric is Joules-per-token at constant quality.
- **Challenge #1: data movement dominates energy.** Off-chip HBM reads cost >>1000× more energy than 8-bit integer multiplications (Horowitz 2014; Google 2021 7nm CMOS update). Off-chip memory consumes 20%+ of GPU power in current GenAI inference datacenters.
- **Back-of-envelope for a 100B-active-parameter model** (per token): arithmetic-only ~0.007 J; SRAM-resident model parameters ~0.2 J; HBM-resident model parameters ~3.9 J. KV cache for long contexts (32k → ~50 GB; 1M → >1 TB) adds another large term that can dominate at long context.
- **Going from off-chip HBM to on-chip SRAM only buys ~10× in theory, ~1.5× measured** (Cerebras CS-3 vs. Nvidia DGX-B200 on Transformers). The 1000× win **cannot come from "better memory placement" alone**.
- **Challenge #2: Amdahl's Law in energy.** If 99% of energy is optimized to zero, the system-level cap is 100×. To clear 1000×, **everything must be optimized** — no overhead component above 0.1% of the original budget can remain unoptimized.
- **Approaches at hand** (none alone is sufficient; aggregate them — "10 factors of 2× or 3 factors of 10×"):
  1. Specialization to a model architecture (dataflow architectures, spatial CMOS layout)
  2. Specialization to a specific trained model (hard-wired parameters — [Taalas](https://taalas.com/) approach)
  3. Parameter efficiency (deep equilibrium models, recursive models)
  4. Sparsity (sparse recurrent systems can match dense feedforward accuracy)
  5. Avoid Attention via dynamics (state-space models like Mamba — sidesteps KV cache)
  6. Allow non-mathematical-isomorphism to NNs (CMOS circuits as physical neural networks — coupled oscillators, trained lookup tables)
  7. Analog circuits where they help, digital elsewhere
  8. Tolerate noise (don't over-engineer SNR; train with noise in the loop)
- **Wind tunnel test for candidate physical-neural-network circuits**: must be expressive, parameter-rich, *expensive to simulate digitally* (otherwise just simulate it), and trainable by gradient descent.
- **Goal is end-to-end inference at the limit of what's physically possible with current CMOS**, not a single magic primitive.
- Anchor against **2030 conventional-hardware projections**, not 2026 state-of-the-art — the relevant comparison is "where the ball is going."

## Pages Updated

- [[unconventional-ai]] (new)
- [[peter-mcmahon]] (new)
- [[naveen-rao]] (new — author of the LinkedIn amplification)
- [[ai-energy-efficiency]] (new)
