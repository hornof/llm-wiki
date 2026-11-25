---
title: "Finding faster quantum algorithms with agents and formal verification"
type: source
medium: article
url: https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/
ingested: 2026-11-24
local_source: "_raw/deepmind-quantum-algorithms-lean-2026-11-24.txt"
---

## Summary

Google DeepMind and Google Quantum AI used teams of Gemini 4 agents to make known quantum algorithms cheaper, and proved every improvement correct in Lean, since circuits this large can't be tested on classical computers or today's quantum hardware. Gains range from 2.5× to 290×. The circuits still need more than the first error-corrected quantum computers will offer. The Lean library, problem specs and verified solutions are open-sourced.

## Key Claims / Takeaways

- **Why Lean** (DeepMind): *"Because we cannot test resource-intensive quantum circuits on classical computers or today's small quantum processors, we have to prove that they work mathematically."*
- **How the agents worked** (DeepMind): separate teams per problem; ideas were verified in Lean before entering a shared notebook, and *"Every four hours, agents from each team met at a virtual conference to trade, debate and compare ideas."*
- **Fusion** (DeepMind): cost *"by 11.8×"*, and memory *"from 5,650 to 4,338 error-corrected qubits"* for an inertial-confinement-fusion calculation.
- **Chemistry** (DeepMind): a light-sensitive molecule's simulation *"8× cheaper"*; for Cytochrome P450, *"a 2.5× improvement and lowered memory from 481 to 333 qubits"*.
- **Building blocks** (DeepMind): *"a 2.57x speedup for a specific implementation of Grover's algorithm"* and *"a 290x speedup for arcsin"*.
- **Still not runnable** (DeepMind): these simulations *"would still demand more computational resources than the first error-corrected quantum computers are likely to provide"*.

## Pages Updated

- [[ai-for-science]]
