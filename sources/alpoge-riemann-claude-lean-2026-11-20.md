---
title: "AI claimed a solution to the 167-year-old Riemann hypothesis — and a human did, too"
type: source
medium: article
url: https://techcrunch.com/2026/11/20/ai-claimed-a-solution-to-the-167-year-old-riemann-hypothesis-and-a-human-did-too/
ingested: 2026-11-20
local_source: "_raw/alpoge-riemann-claude-lean-2026-11-20.txt"
---

## Summary

TechCrunch (Tim Fernholz, 2026-11-20). Levent Alpöge, a mathematician at Anthropic, posted a proof of the Riemann hypothesis in Lean, found working with Claude. Mathematicians on the Lean Zulip, including MIT's Andrew Sutherland, report that it compiles. Nobody yet has a human-readable account of why it works. The same day, Stanford's Ravi Vakil posted a human-only proof of the generalized Riemann hypothesis by postdoc Alessandro Masullo, not in Lean. Alpöge's essay and the Zulip thread weren't read here; this is TechCrunch's account.

## Key Claims / Takeaways

- **The claim:** Alpöge *"found a Lean-compilable solution to the Riemann hypothesis, which dates back to 1859 and is among the Millennium Prize math problems."* He messaged Dario Amodei the Sunday before to ask how to announce it, and wrote *"The precise timing is horrible"*, given the IPO the same week.
- **Checked by compiling, not yet understood:** *"Several participants in the Zulip chat, including MIT mathematician Andrew Sutherland, say they have successfully confirmed that Alpöge’s solution can be compiled successfully."* TechCrunch: *"for all that action to mean anything, we’ll have to wait for humans to be able to understand the result and explain it to each other"*. Alpöge has committed to writing that explanation.
- **How it was found:** Alpöge describes *"incredible confusion with Claude"* and says the model *"flew, and danced, and sparkled near that finish line."* No model version is given.
- **A second result:** Alpöge and NYU's Tristan Buckmaster also released a proof on the Navier-Stokes equations. The 11-20 brief lists the repo, [tristanbuckmaster/navier-stokes](https://github.com/tristanbuckmaster/navier-stokes), as a *"Lean 4 formalization of the finite-time blow-up theorem"*.
- **The human proof:** Vakil, quoted: *"it is all human, with no AI."* It isn't in Lean, so TechCrunch says *"it is too early to say whether the proof checks out"*. Masullo, whose proof is *"the result of 12 years of work"*: *"we are still here. We are very much alive. We are not going anywhere."*
- **Earlier:** a Jacobian-conjecture counterexample credited to Alpöge and Claude surfaced unconfirmed on 2026-07-20 ([[dailybrief-roundup-2026-07-20]]).

## Follow-up

- **Certified 2026-11-21.** The Lean and Mathlib communities certified *both the statement and the proof* as correct, using several independent proof checkers, and Andrew Sutherland published his checks. The proof is a 17-million-line Lean library and covers more than the classical hypothesis. Still open: a human explanation. See [[lean-community-rh-verification-2026-11-21]].

## Pages Updated

- [[ai-for-science]]
- [[anthropic]]
