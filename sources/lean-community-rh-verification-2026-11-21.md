---
title: "Lean verification of the Riemann Hypothesis"
type: source
medium: article
url: https://leanprover-community.github.io/blog/posts/riemann-hypothesis/
ingested: 2026-11-22
local_source: "_raw/lean-community-rh-verification-2026-11-21.txt"
---

## Summary

A joint statement by the Lean and Mathlib communities (2026-11-21), endorsed by the Lean FRO and the Mathlib Initiative. It certifies that Levent Alpöge's Lean proof of the Riemann hypothesis, released the day before, is correct: the statement is Mathlib's, the code proves exactly that statement, and several independent proof checkers accept it. This settles what [[alpoge-riemann-claude-lean-2026-11-20]] left open as "it compiles". Read with it: Alpöge's own note (`alpo.ge/remark.pdf`), Andrew Sutherland's verification page (math.mit.edu/~drew/grh/, checks run with Claude Code), Willison's quotes of Alpöge and Ravi Vakil, and AINews. All of these are saved in `_raw/riemann-followups-2026-11-20-22.txt`.

## Key Claims / Takeaways

- **Certified:** *"We have full confidence that Alpöge's proof of the Riemann Hypothesis is correct"* and *"We hereby certify that both the statement and the proof of the Riemann Hypothesis are correct."*
- **Size:** released *"as a Lean library comprising 17 million lines of code"*. AINews describes the Lean code as *"1.3GB worth, ~250,000 page equivalent"*.
- **How it was checked** (Lean blog): the statement *"is part of Mathlib"*; *"dozens of people have reported correct compilation"*; two independent tools confirmed *"the theorem proved in Alpöge’s library is exactly Mathlib’s statement of the Riemann Hypothesis"*; and the exported proof passed Lean's kernel and several independent checkers. Two of them, con-leche and con-ron, *"come with a formal proof, relative to set theory, that they cannot accept a false proof"*. The checks ran on an inert export, *"out of reach of hypothetical malicious code"*.
- **Sutherland's page** (as of 2026-11-22 16:20 UTC): *"All 175,187 modules compile"*; the five headline theorems use only the three standard axioms; an independent sandboxed rebuild reproduces the export byte for byte. Lean's own kernel was still re-checking the full export (*"running"*). The five theorems go beyond the classical hypothesis: one covers *"every Dirichlet L-function"*, with no zeros to the right of the critical line.
- **Alpöge's note:** *"I believe I have, working with Claude, discovered a proof of the Riemann Hypothesis. In fact, the method easily extends much further, resolving the so-called Generalized Riemann Hypothesis"*. On Claude's part: *"this time Claude far outpaced me near the finish line."* On why he released only Lean: *"It being obviously inappropriate to attempt to post some massive unreadable travesty of "slop""*. He intends *"to understand and impart understanding of this argument"*.
- **Still missing:** a human-readable proof. The Lean blog looks forward to work *"that will help explain the new ideas in this proof."* Alpöge expects the argument *"will be massively simplified, likely immediately."*
- **The human proof:** Vakil, via Willison: Brian Conrad *"has been looking closely at it for months"*, and *"it is so far looking good. It is all human, with no AI."* AINews: Masullo's draft is *"940 page"*, the work of 12 years. It isn't in Lean, so it can't yet be checked the same way.
- **Before certification** (AINews, 2026-11-20): Elliot Glazer *"puts the chance of a Lean bug well under 1%"*.

## Pages Updated

- [[ai-for-science]]
- [[anthropic]]
- [[verifiability-and-jagged-intelligence]]
- [[alpoge-riemann-claude-lean-2026-11-20]]
