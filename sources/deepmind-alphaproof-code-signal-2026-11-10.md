---
title: "Introducing AlphaProof Code: a breakthrough in verifying complex software at depth"
type: source
medium: article
url: https://deepmind.google/blog/introducing-alphaproof-code/
ingested: 2026-11-10
---

## Summary

[[google-deepmind|Google DeepMind]] post (2026-11-10) on AlphaProof Code, a multi-agent system for formal verification. Humans and models write the specification, and Gemini Carbon agents write the Lean proofs. DeepMind used it to prove security properties of the Signal protocol's compiled code, not just its design, in four weeks. The same week, Anthropic reported 1,000 Fable 5.2 agents formalizing Fermat's Last Theorem in Lean ([[anthropic-claude-fable-mythos-5-2-2026-11-09]]). Both labs are now pointing agent swarms at machine-checked proof.

## Key Claims / Takeaways

- **The division of labour.** *"human experts work with AI to decide what to prove, and a group of AI agents does it."* Humans reviewed every specification.
- **Scale.** Agents *"generating over six million lines of Lean"*. Agents then flagged parts for human review, *"just one percent of the codebase"*.
- **Down to the code that runs.** *"proving that the compiled code fulfills the key security properties"*, including protection before and after a temporary device compromise. *"most protocol verification stops at the design level."*
- **Time.** *"our verification process took just four weeks"*, against years for expert teams (DeepMind's comparison).
- **Bug check.** Two real, previously fixed bugs were put back into an isolated copy, and *"In both cases, the system produced a machine-checked proof that the buggy version was insecure."*
- **Signal's CTO, Ehren Kret:** *"Using AI agents to translate live code into valid Lean theorems is a major breakthrough."*
- **Brief error.** The 2026-11-10 Daily Brief said "three million lines of formal proofs". DeepMind's figure is over six million lines of Lean.
- Related: [[verifiability-and-jagged-intelligence]]. Proof is the case where the checker is fully automatic, so output volume isn't capped by human review.

## Pages Updated

- [[google-deepmind]] — Traction Signals
