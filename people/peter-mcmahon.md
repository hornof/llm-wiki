---
name: Peter McMahon
type: person
affiliation: Unconventional AI (Research Fellow)
signal_sources: [blog]
last_updated: 2026-05-08
---

## Who They Are

Research Fellow at [[unconventional-ai]]. Author of the technical essay [[mcmahon-1000x-energy-efficiency-2026-05|How to improve AI energy efficiency by 1000x]] (May 7, 2026), which lays out the hardware-side framing for Unconventional AI's mission.

Background details (academic affiliation, prior work) not present in the ingested source. Flag for verification before citing further.

## Their Current Focus

Hardware-software co-design for inference energy efficiency. Specific concerns in the May 2026 essay:
- Joules-per-token / Joules-per-image as the metric that matters
- Memory access (HBM, SRAM, KV cache) as the dominant energy term
- Amdahl's-Law-in-energy as the design constraint that forces full-stack optimization

## Notable Takes

- **"Going from off-chip HBM to on-chip SRAM only buys ~10× in theory, ~1.5× measured."** (May 2026) — important calibration: "just put it on-chip" is not the path to 1000×. — [[mcmahon-1000x-energy-efficiency-2026-05]]
- **"If we kept MAC arithmetic the same and eliminated all energy costs from memory, we would likely immediately get a ~1000x energy advantage."** (May 2026) — sharpens the diagnosis: the 1000× target is *almost entirely* a memory problem. — [[mcmahon-1000x-energy-efficiency-2026-05]]
- **Wind-tunnel test for physical neural networks** (May 2026): a candidate physical-NN circuit must be expressive, parameter-rich, expensive to simulate digitally, and trainable by gradient descent — formal criteria for distinguishing "real co-design" from "interesting but useless" analog circuits. — [[mcmahon-1000x-energy-efficiency-2026-05]]
- **Build for 2030 baselines, not 2026** (May 2026): "the relevant baseline for us is not the 2026 state-of-the-art; it is what we anticipate will be possible using conventional approaches in ~2030." Disciplined framing for a multi-year hardware bet. — [[mcmahon-1000x-energy-efficiency-2026-05]]

## Where to Follow

- Unconventional AI blog: https://unconv.ai/blog/
