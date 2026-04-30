---
name: Verifiability and Jagged Intelligence
type: concept
maturity: active-research
last_updated: 2026-04-29
---

## Definition
Karpathy's framework for understanding why LLMs have uneven ("jagged") capability profiles: models excel at tasks where outputs can be automatically verified (enabling RL training with verification rewards) and stagnate in domains that are harder to verify or that labs haven't prioritized for their training data.

> "Traditional computers can easily automate what you can specify in code. The latest round of LLMs can easily automate what you can verify." — Andrej Karpathy, AI Ascent 2026

## Why It Matters
The verifiability thesis predicts which domains will improve fastest, helps engineers calibrate trust in specific model capabilities, and suggests a strategy for founders: build RL environments in verifiable domains that frontier labs haven't yet targeted.

## The Core Mechanism
Frontier labs train LLMs as giant reinforcement learning environments. Tasks with clear verification signals (did the code pass the test? is this proof correct?) get dense RL reward signals. This creates capability peaks in verifiable domains (math, code) and rough capability in unverifiable domains.

Two factors determine capability level:
1. **Verifiability**: can the output be automatically checked?
2. **Lab prioritization**: did the lab actually add this verifiable domain to their RL training?

Both matter. Chess improved dramatically from GPT-3.5 to GPT-4 not just from general scaling — Karpathy believes a large dataset of chess games was added to the pre-training set specifically. The capability peak came from a human decision at OpenAI, not from emergent generalization.

## The Jagged Intelligence Phenomenon
Models are "jagged entities" — capability peaks dramatically in RL-trained circuits and falls off sharply outside them.

**Canonical Karpathy example (2026)**:
> "How is it possible that state-of-the-art Opus 4.7 will simultaneously refactor a 100,000 line codebase or find zero day vulnerabilities and yet tells me to walk to this car wash [50 meters away]?"

The "walk to the car wash" failure is not stupidity — it is a domain that was not part of the RL circuits. The model lacks the common-sense grounding that would tell a human "you need a wet car to reach a car wash on foot, that's not the purpose."

The classic earlier example: counting letters in "strawberry." Models have since patched this specific case, but the jaggedness pattern persists in new forms.

## Implications for Builders

**Trust calibration**: Agents remain jagged. Being in the loop matters. Treat them as powerful but fallible tools, not reliable reasoners.

**Founder strategy**: If you find a valuable, verifiable domain that frontier labs haven't trained on, you can fine-tune using your own RL environments. This is real leverage — "you can pull a lever if you have a huge amount of diverse datasets of RL environments."

**Hiring/evaluation**: Test in the actual domain you care about. Don't assume a model that's great at code is great at your specific verifiable problem.

## Everything Is Eventually Automatable
Karpathy's view: "I do think that ultimately almost everything can be made verifiable to some extent." Even subjective domains like writing quality can use a council of LLM judges as approximate verification. The question is not whether something is automatable but how easy or hard verification is to construct.

## Relationship to AGI Definition
See [[agi]]. Hassabis uses similar language — "jagged intelligence" — to describe why current systems are not AGI. Karpathy's verifiability framework gives a mechanistic explanation for why the jaggedness exists: RL training shapes peaks around verified domains. This complements Hassabis's phenomenological observation with a causal theory.

## Ghosts vs. Animals (Related Framing)
Karpathy also uses a "ghosts vs. animals" framing to resist anthropomorphizing LLMs. LLMs are "summoned ghosts" — statistical simulation circuits shaped by data and reward, not by intrinsic motivation, curiosity, or embodied experience. This matters because:
- Yelling at them has no effect.
- They don't have preferences that make them want to do better.
- The substrate is pre-training statistics + RL bolted on top.

The practical implication is the same as the verifiability thesis: be suspicious, explore the capability landscape empirically, don't assume human-like cognition.

## Related Concepts
- [[agi]] — Hassabis uses "jagged intelligence" to describe why current systems aren't AGI; Karpathy's verifiability thesis is a mechanistic complement
- [[agentic-engineering]] — one response to jaggedness: keep engineers in the loop to catch edge cases
- [[vibe-coding]] — works best in the high-verifiability zones (code); struggles in unverifiable aesthetic domains
- [[software-3-0]] — verifiability determines which parts of Software 3.0 are currently ready

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — PRIMARY SOURCE: AI Ascent 2026; Karpathy elaborates verifiability thesis, jagged intelligence, ghosts vs. animals, chess data example
