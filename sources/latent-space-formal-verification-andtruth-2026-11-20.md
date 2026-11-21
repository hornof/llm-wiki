---
title: "The War Against Slop and an Emerging Weapon to Fight it: Formal Verification"
type: source
medium: article
url: https://latent.space/p/formal-verification/
ingested: 2026-11-20
local_source: "_raw/latent-space-formal-verification-andtruth-2026-11-20.txt"
---

## Summary

Latent Space (Richard MacManus, 2026-11-20). A short survey of companies selling formal verification of code with AI and Lean: Harmonic, Theorem, Axiom Math and a new one, &Truth. Most of it is an interview with &Truth's co-founder Clark Barrett, a Stanford professor and co-creator of the cvc5 solver. The brief called the summary thin; the article is a survey, not a result.

## Key Claims / Takeaways

- **Tests versus proofs:** Barrett on what agents mean by "verifying": testing and scanning *"find a ton of problems"*, but *"you're never quite sure, did I find all of them [the issues] or is there one more lurking there that my tool can't find?"*
- **Solvers already in production:** cvc5 is used for specification analysis and test generation in Amazon's Kiro. Barrett: *"cvc5 is now called billions of times a day in production pipelines at Amazon"*.
- **&Truth's plan:** a *"verification machine"* on Lean, aiming to read code *"in any language, proving whether it satisfies precisely stated requirements, and enabling humans to trust it without having to understand every line."* Its first tool, &Atlas, maps open-source C code.
- **Lean as the common checker:** Barrett: *"What Lean does is it just checks that you didn't make a mistake"*. The article cites GPT-6.2 Astra's Lean proof of Smoktunowicz's Gap Theorem (per Vals), Anthropic's Lean formalization of Fermat's Last Theorem (*"a project of 13 million lines"*, per Vals), and the Alpöge Riemann claim ([[alpoge-riemann-claude-lean-2026-11-20]]).
- **For training too:** Axiom Math uses formal verification as correctness feedback when training its reasoning models.

## Pages Updated

- [[verifiability-and-jagged-intelligence]]
