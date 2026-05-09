---
name: AI Energy Efficiency
type: concept
maturity: emerging
last_updated: 2026-05-08
---

## Definition

The end-to-end-system energy cost of producing AI model output, expressed as **Joules per token** (text generation) or **Joules per image** (image generation), iso-quality with a comparable model. The metric explicitly excludes arithmetic-only proxies like TOPS or TOPS/Watt — those invite apples-to-oranges comparisons because they ignore data movement, which is the dominant energy cost in modern inference systems.

## Why It Matters

Inference energy economics shape what's actually buildable: long-context KV caches, multi-turn agent loops, and large-mixture-of-experts active parameter counts all multiply Joules-per-token, often dwarfing the cost of arithmetic. Anyone designing systems on top of frontier models — or evaluating the next generation of hardware — has to reason in this metric, not in TOPS.

This is also where the **physics of AI** meets the economics: data movement on CMOS has a hard energy floor that cannot be optimized away by software alone. Whoever finds a way to push that floor down by orders of magnitude reshapes the cost curve of the entire field.

## Current State (May 2026)

- **Baseline**: largest models use ~10 J/token (text), >10,000 J/image (image). 8-GPU B200 systems deliver ~1000 tokens/sec/user at ~14 kW max. ([[mcmahon-1000x-energy-efficiency-2026-05]])
- **Off-chip HBM access dominates**: >>1000× the energy of 8-bit integer multiplication. HBM reads consume 20%+ of GPU power in inference datacenters. (Horowitz 2014; Google 2021 7nm CMOS update.)
- **KV cache scales aggressively with context**: ~50 GB for 32k context, >1 TB for 1M context. At 1M context, KV-cache reads alone can dominate Joules-per-token.
- **On-chip SRAM doesn't save you alone**: theoretical ~10× over HBM, measured ~1.5× on Cerebras CS-3 vs. Nvidia DGX-B200 for Transformers. The 1000× win is not "put it on-chip."

## Two Design Constraints

From [[mcmahon-1000x-energy-efficiency-2026-05]]:

1. **Data movement dominates energy.** Models too large to fit on-chip force HBM access; HBM access dwarfs arithmetic. Eliminating memory cost while keeping arithmetic cost the same would give ~1000× — i.e., the 1000× problem is *almost entirely* a memory problem.
2. **Amdahl's Law in energy.** Optimizing 99% of the energy budget caps system-level gain at 100×. To clear 1000×, every component above 0.1% of the original budget must be optimized — no exceptions, no overhead.

The combination forces **hardware-software co-design**: small unoptimized components (KV cache, attention, attention-routing, control flow) prevent the system-level target even when the bulk-arithmetic path is excellent.

## Approaches Under Investigation

- **Architectural specialization**: dataflow architectures, spatial CMOS layout that mirrors NN topology
- **Hardwired parameters**: specialize to a specific trained model (Taalas, etc.)
- **Parameter efficiency**: deep equilibrium models, recursive models
- **Sparsity**: sparse recurrent systems matching dense feedforward accuracy
- **Avoid Attention**: state-space models (Mamba) sidestep the KV-cache term
- **Physical neural networks**: CMOS circuits not constrained to exact matrix-vector multiplications — coupled oscillators, trained lookup tables, analog where it helps
- **Noise tolerance**: train with noise in the loop, don't over-engineer SNR
- **Heterogeneous-fleet orchestration**: optimize across the chips you actually have, not just the chip you ship — *practitioner extension* surfaced in the [[nrao-linkedin-1000x-2026-05]] comment thread (Sidney Scott, ex-Rain AI backer)

## Wind Tunnel Test

A candidate physical-neural-network circuit must be:
1. **Expressive** — represents many complicated nonlinear functions
2. **Parameter-rich** — many trainable parameters (programmable or hard-wired)
3. **Expensive to simulate digitally** — if you can simulate it cheaper than running it physically, it's not a candidate
4. **Trainable by gradient descent** — needs a behavioral model accurate enough for backpropagation

[[mcmahon-1000x-energy-efficiency-2026-05]] uses this as the formal criterion separating "real co-design candidates" from "interesting but useless" analog-circuit proposals.

## Related Concepts

- [[mcp]] — protocol-level optimization layer; orthogonal but interacts with KV-cache cost
- [[agentic-ai]] — agent loops multiply Joules-per-token via repeated context loads; energy efficiency is a binding cost constraint on long-horizon agents

## Key Posts

- [[mcmahon-1000x-energy-efficiency-2026-05]] — primary technical thesis from [[unconventional-ai]]
- [[nrao-linkedin-1000x-2026-05]] — [[naveen-rao]] amplification with substantive practitioner comment thread
- [Horowitz, "Computing's Energy Problem"](https://doi.org/10.1109/ISSCC.2014.6757323) (2014) — foundational paper on memory-vs-compute energy gap
- [Google, "Ten lessons from three generations of TPU…"](https://doi.org/10.1109/ISCA52012.2021.00010) (2021) — updated 7nm CMOS numbers showing the gap persists
- [ML.ENERGY Leaderboard](https://ml.energy/leaderboard/) — public benchmark of Joules-per-token across models
