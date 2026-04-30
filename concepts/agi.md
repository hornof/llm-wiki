---
name: AGI (Artificial General Intelligence)
type: concept
maturity: active-research
last_updated: 2026-04-29
---

## Definition
An AI system capable of performing any intellectual task that a human can. Distinct from narrow AI (which excels at specific tasks) in that it generalizes across domains, learns continuously, and can generate genuinely new knowledge — not just remix existing knowledge.

## Why It Matters
AGI is the long-term target of most major AI labs. The definition you use shapes how you measure progress, what you build, and how you assess risk. Different labs use different definitions — often ones that make their current products look closer.

## Definitions in the Field

**Demis Hassabis (Google DeepMind)**: "A system that can exhibit all the cognitive capabilities humans can." Explicitly stricter than most. Judges current systems as "jagged intelligence" — not general. — [[thread-milkroadai-hassabis-agi]]

**The Einstein Test** (Hassabis): Train a system on all human knowledge with a cutoff at 1911. Can it independently discover general relativity (as Einstein did by 1915)? Current systems cannot. — [[thread-milkroadai-hassabis-agi]]

## What's Missing (According to Hassabis)
- **Continual learning**: current systems are trained then frozen; genuine intelligence adapts from every new experience
- **True creativity**: generating paradigm-shifting ideas from first principles, not remixing training data
- **Long-term planning**: sustained goal-directed reasoning across time

## Current State
Current systems are capable of gold medal performance at the International Math Olympiad and yet "still fall apart on relatively simple math problems if you frame the question a different way." — [[thread-milkroadai-hassabis-agi]]

Hassabis describes the present as "the agent era" — a meaningful step toward AGI, but distinct from it. His framing: build an "incredibly intelligent and useful and precise tool" first; cross to questions of agency and consciousness as a second step.

## Timeline Signals
- **Hassabis**: 2030 explicitly; "I've been pretty consistent about that." DeepMind's founding in 2009 was pitched as a "20 year mission"; he says the field is "basically exactly on track." — [[hassabis-deepmind-alphafold-agi]]
  - Earlier source gave range of 5–10 years; the 2030 date is a more specific public commitment — [[thread-milkroadai-hassabis-agi]]

## Fei-Fei Li's Position (2025)

Li's stance is neither doomist nor dismissive. She disputes Hinton's extinction-risk framing: "If the human race became really in trouble, that would be the result — in my opinion — of *humans* doing wrong things, not *machines* doing wrong things." On timeline: "We don't have such a machine yet. We still have a distance, a journey to take, to that day." Her AGI thesis is **additive**: AGI will not be complete without spatial intelligence (3D world understanding) — the physical layer that LLMs lack. This distinguishes her from both LeCun (who rejects LLMs entirely) and Hassabis (who focuses on continual learning/creativity). — [[bloomberg-feifei-li-2025]]

## David Silver's Position (2026)

Silver — the architect of AlphaGo, AlphaZero, and AlphaStar — argues that LLMs trained on human-generated data have a hard ceiling: they can remix human knowledge but cannot discover genuinely new knowledge. His bet: RL from self-play (with no human training data, only rules) is the only demonstrated path to exceeding the human knowledge frontier. "Move 37" in AlphaGo vs. Lee Sedol — a move with a 1-in-10,000 probability of being played by any human — is his cited evidence. Raised $1.1B for [[ineffable-intelligence]] to pursue this thesis. — [[ric-rtp-david-silver-ineffable]]

This framing extends LeCun's critique (LLMs are wrong architecture) to a deeper claim: the training signal itself is the bottleneck, not just the architecture. Even world models trained on human data would face the same ceiling in Silver's view.

## Karpathy's Complementary View (2026)
Karpathy does not offer a crisp AGI definition, but his [[verifiability-and-jagged-intelligence]] framework provides a mechanistic explanation for why current systems are not AGI: capability is shaped by RL training circuits and data distribution choices at labs, not by general intelligence. The "jagged" capability profile Hassabis observes phenomenologically is, in Karpathy's framing, a predictable output of how these systems are trained. He also cautions against anthropomorphizing LLMs ("ghosts, not animals"), which implies skepticism of near-term AGI claims without directly commenting on timelines. — [[karpathy-vibe-coding-agentic-engineering]]

## Resources
- [[ric-rtp-david-silver-ineffable]] — Silver's RL-from-self-play thesis; Ineffable Intelligence founding
- [[ineffable-intelligence]] — Silver's lab; $1.1B seed at $5.1B; RL from self-play with zero human training data
- [[thread-milkroadai-hassabis-agi]] — Hassabis's definition and Einstein Test
- [[hassabis-deepmind-alphafold-agi]] — 2030 timeline, DeepMind founding mission, agent era framing
- [[demis-hassabis]] — primary source for the Hassabis framing
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's verifiability/jagged intelligence framing; mechanistic complement to Hassabis
- [[bloomberg-feifei-li-2025]] — Li's AGI stance: additive spatial intelligence layer; humans (not machines) bear extinction risk
- [[fei-fei-li]] — Li's spatial intelligence thesis; AGI requires 3D world understanding
- [[spatial-intelligence]] — Li's specific framing: what's missing from current AI
