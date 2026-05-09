---
title: "LLMs Corrupt Your Documents When You Delegate"
type: source
medium: paper
url: https://arxiv.org/abs/2604.15597
ingested: 2026-05-09
---

## Summary

arXiv preprint (May 2026) by **Philippe Laban, Tobias Schnabel, Jennifer Neville**. Central claim: current frontier LLMs corrupt approximately **25% of document content** during extended delegated workflows. Evaluated 19 models including Gemini 3.1 Pro, Claude 4.6 Opus, and GPT 5.4 against the **DELEGATE-52 benchmark** spanning 52 professional domains. Practitioner-relevant warning: **agentic tool use does not improve performance** — the corruption is structural to the delegation paradigm, not a tooling failure.

## Key Claims / Takeaways

### Setup

- **Benchmark**: DELEGATE-52, spanning 52 professional domains including coding, crystallography, music notation, and others
- **Models tested**: 19 including frontier (Gemini 3.1 Pro, Claude 4.6 Opus, GPT 5.4)
- **Methodology**: long-duration delegated workflows requiring "in-depth document editing"

### Findings

- **Frontier models corrupt ~25% of document content** by workflow end
- Other (non-frontier) models show more severe degradation
- Degradation **worsens with**: larger documents, longer interactions, distractor files
- **Agentic tool use does not improve performance** — i.e., giving the model more capability primitives does not fix the corruption

### Failure-mode framing

The abstract describes "sparse but severe errors that silently corrupt documents." The errors are not random noise — they are infrequent enough to evade casual inspection but severe enough to invalidate downstream use. The paper positions current LLMs as **"unreliable delegates"** for delegated work paradigms.

## Why This Matters for the Wiki

- **Practitioner-grade warning** for any workflow that delegates document editing to an LLM in a fire-and-forget shape (long-running [[claude-cowork]] tasks, scheduled tasks that touch financial / legal / compliance documents, etc.).
- **Verifiability counterpart to [[anthropic-teaching-claude-why-2026-05-08|Teaching Claude Why]]**: where Anthropic argues alignment-by-reasoning is the path to trustworthy agentic behavior, this paper documents the *current* failure rate on a different axis — fidelity-to-source-document, not safety-of-action.
- **Connects to [[verifiability-and-jagged-intelligence]]**: the 25% corruption rate is exactly the kind of "jagged" failure mode Karpathy's framing predicts — frontier models look reliable on benchmarks but fail in extended-context delegation in non-obvious ways.
- **Connects to [[claude-cowork]]'s self-verification pattern**: the cheat sheet calls out *"the single biggest quality improvement you can make"* as asking Claude to verify its own work. This paper is empirical support for why that pattern matters: 25% corruption on long workflows is the failure mode the verification pattern is trying to catch.

## Pages Updated

- [[verifiability-and-jagged-intelligence]] (updated — 25% document-corruption rate as a concrete current-frontier-model jagged-failure datapoint)
- [[claude-cowork]] (updated — self-verification pattern justification strengthened with the DELEGATE-52 finding)
- [[agentic-engineering]] (updated — "agentic tool use does not improve performance" finding — control flow alone doesn't fix delegation-corruption; reasoning fidelity is a separate axis)

## Caveats

- arXiv preprint, not peer-reviewed.
- 25% is a benchmark-specific number on DELEGATE-52; the failure rate on shorter workflows or simpler domains is presumably lower.
- Frontier models (Gemini 3.1 Pro, Claude 4.6 Opus, GPT 5.4) all evaluated on the *same* benchmark; the paper reports a frontier ceiling, not a ranking — i.e., this is not a claim that one of the three is materially worse.
- "Document content" definition not yet captured here — the paper presumably defines this in the body. Verify before citing the 25% figure as a precise claim.
