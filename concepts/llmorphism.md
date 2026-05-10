---
name: LLMorphism
type: concept
maturity: emerging
last_updated: 2026-05-10
---

## Definition

**LLMorphism** — coined by Valerio Capraro in [[capraro-llmorphism-2026-05]] (May 2026) — is *"the biased belief that human cognition works like a large language model."* The inverse of anthropomorphism: anthropomorphism attributes human qualities to non-humans; LLMorphism attributes LLM qualities to humans (memory-as-context-window, thinking-as-token-generation, understanding-as-next-token-prediction).

## Why It Matters

For AI engineers specifically, the conceptual hygiene cuts in two directions:

1. **The metaphors we work with are operationally useful but ontologically dangerous.** Treating "the LLM is the programmer; the wiki is the codebase" ([[llm-wiki-pattern]]) is a productive scaffolding for *building things* — but if it slides into a literal claim about human cognition, you've smuggled in a category error.
2. **Output similarity ≠ mechanism identity.** A useful pre-commitment for evaluating any "LLMs are like X" or "X is just an LLM" claim — the question is what mechanism is actually at work, not what behavior looks similar at the surface.

Capraro's most load-bearing line:
> "The issue is not only whether we are attributing too much mind to machines, but also whether we are beginning to attribute too little mind to humans."

## Current State

- **Coined**: May 6 2026, single-author preprint ([[capraro-llmorphism-2026-05]]).
- **Adoption**: not yet observed in mainstream ML or HCI discourse as of this ingest. Track for whether the term survives or gets absorbed.
- **Driver mechanisms named** in the paper: *analogical transfer* (LLM behavior → LLM mechanism imputed to humans) and *metaphorical availability* (LLM vocabulary becomes default cognition vocabulary).
- **Domains the paper claims are affected**: work, education, accountability, healthcare, interpersonal communication, creative process, human dignity.

## Key Papers / Posts

- [[capraro-llmorphism-2026-05]] — Capraro's coinage paper; sociological/conceptual.

## Related Concepts

- [[verifiability-and-jagged-intelligence]] — adjacent angle on output-vs-mechanism gap, but at the LLM-capability level; LLMorphism is about how observing what LLMs *can* do reshapes self-perception of human cognition.
- [[llm-wiki-pattern]] — metaphor-as-tool example; the "LLM as programmer / wiki as codebase" framing is exactly the kind of working metaphor LLMorphism warns can drift into ontological claim.
