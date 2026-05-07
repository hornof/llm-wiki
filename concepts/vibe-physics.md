---
name: Vibe Physics
type: concept
maturity: emerging
last_updated: 2026-05-06
---

## Definition
Term coined by Alex Lupsasca (OpenAI Science team) by direct analogy with [[vibe-coding]]: the practice of using iterative dialogue with a frontier AI model to derive *novel theoretical physics results* — not to retrieve existing literature, not to interpolate within known regimes, but to extend the frontier of human knowledge in mathematical physics.

> "Actually extending the frontier of human knowledge." — Alex Lupsasca, framing what distinguishes vibe physics from prior AI-for-science work — [[latent-space-lupsasca-vibe-physics-2026-05]]

## Why It Matters
If validated by independent groups, vibe physics is a categorically different milestone than [[alphafold]]-style applications. AlphaFold applies deep learning to a *well-defined existing problem* (protein structure given sequence). Vibe physics is the model generating *new theoretical conjectures and derivations* in domains where expert humans have been stuck for years. This is the strongest published demonstration to date that frontier LLMs can contribute to the [[ai-for-science]] thesis at the *theoretical-derivation* level, not just at the prediction or simulation level.

## Concrete Results Cited
- **Gluon amplitudes (GPT-5.2)**: derived results showing certain "single-minus gluon tree amplitudes" can be non-zero under specific conditions, contradicting prior assumptions. Lupsasca's team had been stuck on this for over a year; GPT solved it in one week using a "half-collinear regime" limit. — [[latent-space-lupsasca-vibe-physics-2026-05]]
- **Graviton extension**: 110 pages of novel quantum gravity calculations extending the gluon work to gravitons. The model adapted techniques specifically for gravitons' unique mathematical properties rather than transposing the gluon approach. Three weeks of human verification before publishing. — [[latent-space-lupsasca-vibe-physics-2026-05]]

## Workflow Pattern
1. Warmup priming problems set up systematic approach
2. Core unsolved problem presented in natural language
3. Iterative refinement of GPT's derivation
4. Extension prompts for related cases (e.g., "Perform the same research... but instead for gravitons")
5. Multi-week human verification before publishing

## Current State
- One documented practitioner (Lupsasca), one frontier domain (theoretical physics / quantum gravity), one institutional context (OpenAI Science).
- Independent reproduction by other research groups not yet documented in this wiki.
- Verification still requires expert humans (3 weeks for the 110-page graviton paper).
- Specific to mathematical-derivation domains where the validation step (re-checking the math) is tractable; not yet extended to empirical sciences requiring physical experiment.

## Distinction From Adjacent Concepts
- **vs. [[vibe-coding]]**: same coined-by-analogy pattern (iterative dialogue, model carries the heavy lifting). But the *output* is theoretical physics derivations rather than software, and the verification cost is much higher (3 weeks of expert review per major result).
- **vs. [[agentic-engineering]]**: agentic engineering preserves a quality bar through human spec/review at the *engineering* level. Vibe physics has the analogue at the *theoretical proof* level — the human is still the verifier, but the model is the conjecturer + first-pass deriver.
- **vs. [[ai-for-science]]**: vibe physics is a *technique* under the broader AI-for-science thesis — specifically, the technique of using frontier LLMs in dialogue at the theory-derivation step rather than only at the prediction/simulation step.
- **vs. [[alphafold]]**: AlphaFold is well-defined-problem deep learning. Vibe physics is open-ended theoretical conjecture using a general-purpose chat interface.

## Why The Term Matters
The "vibe X" pattern (after Karpathy's [[vibe-coding]]) is becoming a working vocabulary across domains. Vibe physics is the second "vibe X" the wiki captures as a *separate practitioner-coined concept* — not a Karpathy coinage but an analogue from a different field. This is the pattern propagating into adjacent disciplines.

## Related Concepts
- [[vibe-coding]] — the originating analogue; Karpathy's term for floor-raising AI-assisted coding
- [[ai-for-science]] — the broader thesis vibe physics extends
- [[agentic-engineering]] — the parallel high-rigor mode (in software)
- [[verifiability-and-jagged-intelligence]] — vibe physics works because mathematical derivation is verifiable; explains the domain fit

## Key People
- [[alex-lupsasca]] — coined the term; produced the first documented results

## Resources
- [[latent-space-lupsasca-vibe-physics-2026-05]] — primary source: Latent Space interview with Lupsasca (May 2026)
