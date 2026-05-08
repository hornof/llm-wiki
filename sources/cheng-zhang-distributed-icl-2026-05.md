---
title: "Single-Position Intervention Fails: Distributed Output Templates Drive In-Context Learning"
type: source
medium: paper
url: https://arxiv.org/abs/2605.04061
ingested: 2026-05-07
---

## Summary

Bryan Cheng and Jasper Zhang preprint (May 2026) showing that **probing accuracy and causal importance are decoupled in in-context learning**. Linear probes hit 100% task-identity accuracy at certain layers/positions of Llama-3.2-3B, but **single-position activation intervention transfers 0% of the task across all 28 layers**. Multi-position intervention (replacing all demonstration-output-token activations simultaneously) reaches **96% task transfer at layer 8**. Generalizes across LLaMA, Qwen, and Gemma — universal intervention window at ~30% network depth. Authors propose "distributed output templates" — task identity is encoded across multiple demonstration tokens, not concentrated at a single position.

## Key Claims / Takeaways

- **The headline gap**: **100% probing accuracy ↔ 0% causal effect at the same positions**. Probes detect signal that the model doesn't actually use to drive behavior. Probing as a standalone interpretability tool is structurally limited.
- **Distributed output templates**: ICL task identity is an **output-format template distributed across demonstration tokens**, not a localized feature. Coordinated multi-position changes are required to transfer a task.
- **Cross-architecture universality**: ~30% network depth as the "intervention window" across three different model families is a strong universality claim — suggests this is about ICL itself, not architectural quirks.
- **Methodological warning for the field**: mechanistic interpretability papers built on linear-probe localization claims should be re-examined. The probing-accuracy → causal-importance inference is broken for ICL.
- **Authors / affiliation**: Bryan Cheng and Jasper Zhang. arXiv page lists no institutional affiliation; treat as unverified provenance until institutional confirmation surfaces.

## Why This Matters for the Wiki

Pairs with [[anthropic-natural-language-autoencoders-2026-05]] in the same week as **two methodologically distinct interpretability claims arriving simultaneously**:

1. **Cheng & Zhang**: prior localization-based interpretability work likely overstates how cleanly task representations can be pinned down — probing alone is misleading.
2. **Anthropic NLAs**: a new self-explanatory primitive that bypasses the "trained researchers must interpret complex artifacts" bottleneck entirely.

Both belong on a [[mechanistic-interpretability]] concept page. Worth tracking whether the Cheng & Zhang result is reproduced and which interpretability papers cite it as a methodological correction.

## Pages Updated

- [[mechanistic-interpretability]] — new concept page; Cheng & Zhang result captured as a methodological correction to localization-based work
