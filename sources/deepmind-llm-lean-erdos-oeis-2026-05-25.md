---
title: "DeepMind LLM-Lean agent loop: 9 open Erdős problems + 44 OEIS conjectures"
type: source
medium: article
url: https://digg.com/ai/f9bq87j9
ingested: 2026-05-25
---

## Summary

Digg-surfaced report (2026-05-25 Daily Brief) that **Google DeepMind's LLM-Lean agent loop has resolved 9 open Erdős problems and proved 44 OEIS conjectures**, at *"a few hundred dollars per proof"*. First wiki capture of **LLM-Lean** as a named DeepMind tool — a Lean-validator-in-the-loop architecture where an LLM generates proof sketches, Lean type-checks them, errors feed back into the next iteration, and a formal proof emerges. Primary article not deeply fetched; brief-tier capture pending follow-up. **Pairs structurally with [[openai-disproves-discrete-geometry-conjecture-2026-05-21|OpenAI GPT-next disproving Erdős planar unit distance]] (May 21)** as **two frontier-lab competing math results in five days** — DeepMind on proof generation (Lean-validated), OpenAI on counterexample finding (single disproof). Same problem family (Erdős conjectures), different methodologies.

## Key Claims / Takeaways

### The headline numbers

- **9 open Erdős problems** resolved.
- **44 OEIS (On-Line Encyclopedia of Integer Sequences) conjectures** proved.
- **Cost: "a few hundred dollars per proof."** Compare with [[openai-disproves-discrete-geometry-conjecture-2026-05-21|OpenAI's <$1K compute cost]] for the single Erdős unit-distance disproof — **same order of magnitude per result**.
- **Total cost-scale** for the DeepMind batch: 53 results × few hundred dollars each = **low five figures** for the full set. Order-of-magnitude cheaper than a single graduate-student-year of conventional formal-math research.

### The LLM-Lean loop architecture (brief-tier capture)

Per Draft 1 framing:
1. **LLM generates proof sketches** in natural language / Lean-adjacent pseudocode.
2. **Lean validator type-checks every step**.
3. **Errors feed back** into the next iteration.
4. **Formal proof emerges** when the validator accepts the entire chain.

Key structural property: *"feedback at the logical level, not the surface level."* — distinguishes LLM-Lean from text-only proof-attempt loops (where the feedback is "did the model produce something that looks like a proof?") versus formal-validator-in-the-loop (where the feedback is "did Lean type-check this?").

### What's notably absent from the brief

- **Identity of the 9 Erdős problems** not specified. Erdős posed hundreds of conjectures across number theory, combinatorics, graph theory, discrete geometry; identity matters for capability evaluation.
- **OEIS conjecture identities** not specified. OEIS contains thousands of integer-sequence conjectures of varying difficulty; 44 is large but the difficulty distribution matters.
- **Model identity** (which DeepMind model is the LLM-generator? Gemini 3.5? Co-Scientist-class? A specialized reasoning model?).
- **Independent verification** — has any working mathematician confirmed the Lean proofs are correct? Lean type-checking *is* verification, but proofs can still be vacuously true or trivially trivial; mathematical-community acceptance is the next layer.
- **Compute-to-difficulty mapping** — the "few hundred per proof" is the average; the variance matters (was it $100 for easy ones and $5K for hard ones?).

## Why It Matters

- **DeepMind + OpenAI competing math results in five days** is structurally significant. May 21 OpenAI GPT-next disproves Erdős planar unit distance (1 result, <$1K, counterexample-finding); May 25 DeepMind LLM-Lean resolves 9 Erdős + 44 OEIS (53 results, low-five-figures total, proof generation). **Pattern**: math is the verifiable domain where both labs are landing autonomous-discovery results simultaneously, but with different architectures (OpenAI's general-frontier-model + search vs DeepMind's tool-augmented LLM-Lean loop).
- **First wiki capture of LLM-Lean as a named tool** in the DeepMind applied-AI-for-science portfolio alongside [[alphafold]] (structural biology), [[deepmind-co-scientist-aging-reversal-2026-05-19|Co-Scientist]] (functional biology / hypothesis generation), and now LLM-Lean (formal-math proof generation). **DeepMind is operationalizing the [[ai-for-science]] thesis across three substantively different domains simultaneously** — biology structure, biology function, mathematics.
- **Few-hundred-dollars-per-proof economics** make formal-verified mathematics newly tractable. Compares with conventional graduate-student-year-per-conjecture-resolution math research; if the LLM-Lean approach generalizes, the **cost-per-mathematical-result is dropping by orders of magnitude**.
- **OEIS conjectures specifically** are practitioner-relevant — OEIS is the standard reference for integer-sequence research; proving 44 conjectures clears named open questions across number theory, combinatorics, and adjacent fields. The community will absorb these into the encyclopedia and use them as building blocks for further work.
- **Pairs with [[verifiability-and-jagged-intelligence|verifiability thesis]]** — Lean type-checking provides exactly the verifiable-domain feedback Karpathy's framing names as the load-bearing condition for capability landing. Pure-math is more verifiable than physics (no experiment needed) and biology (no replication needed) — capability lands there *first* because the feedback loop is tightest.

## Caveats

- **Primary not deeply fetched.** Digg pointer captured; underlying primary source (DeepMind blog post or paper?) not surfaced in the brief. Worth deep-fetch on follow-up.
- **Lean type-checking ≠ mathematical-community acceptance.** A Lean proof is mechanically valid; mathematical significance still requires human evaluation. Worth tracking which of the 9 Erdős and 44 OEIS results are considered substantive vs trivial by working mathematicians.
- **Compute-cost averages can hide variance.** The "few hundred dollars per proof" framing is the average; if there's a long tail where some proofs cost $50K+, the economic story is different.
- **"Open" varies by community.** Some Erdős conjectures have been folklore-open for decades but considered tractable; others are deep. Without identity disclosure, can't tell which kind these are.
- **Methodological-critique cross-reference**: same-day brief item flags [[dailybrief-roundup-2026-05-25|Leonardo.AI co-founder Ethan Smith warning that 10× training-speedup claims in recent diffusion papers may rely on flawed metrics]]. Worth applying the same skepticism to "few hundred dollars per proof" until cost methodology is disclosed.

## Cross-references

- [[openai-disproves-discrete-geometry-conjecture-2026-05-21]] — competing/complementary May 2026 frontier-lab math result; counterexample-finding vs proof-generation methodological contrast.
- [[google-deepmind]] — entity page; LLM-Lean added as third applied-AI-for-science tool alongside Co-Scientist and AlphaFold.
- [[ai-for-science]] — concept thread; formal-math proof generation as third applied domain alongside structural and functional biology.
- [[deepmind-co-scientist-aging-reversal-2026-05-19]] — DeepMind's same-month functional-biology result; LLM-Lean is the pure-math counterpart.
- [[verifiability-and-jagged-intelligence]] — math + physics + biology are the verifiable domains where frontier-discovery capability lands first; Lean validator is the tightest-feedback example.
- [[latent-space-lupsasca-vibe-physics-2026-05]] — physics-side companion; same general pattern of frontier-models generating verifiable-domain results.
- [[dailybrief-research-roundup-2026-05-25]] — same-day Latent Cache Flow + Tensor Cache memory-bottleneck research items.

## Pages Updated

- [[google-deepmind]] (updated — LLM-Lean named as third DeepMind applied-AI-for-science tool with 9 Erdős + 44 OEIS results + "few hundred dollars per proof" cost framing; date bumped to 2026-05-25)
- [[ai-for-science]] (updated — formal-math proof generation via LLM-Lean added as third applied domain alongside structural and functional biology; date bumped to 2026-05-25)
- [[openai-disproves-discrete-geometry-conjecture-2026-05-21]] (updated in-place — DeepMind LLM-Lean parallel/competing result added as methodological contrast: counterexample-finding vs proof-generation)
