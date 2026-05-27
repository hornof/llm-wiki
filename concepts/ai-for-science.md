---
name: AI for Science
type: concept
maturity: active-research
last_updated: 2026-05-27
---

## Definition
The application of AI systems — particularly deep learning and reinforcement learning — to accelerate or transform scientific discovery. Distinct from general AI applications: the target is generating genuinely new scientific knowledge, not automating existing tasks.

Hassabis frames it as the "meta" approach to his mission: "build the ultimate tool and then come back when that was ready and use it to make breakthroughs in science — things like AlphaFold." — [[hassabis-deepmind-alphafold-agi]]

## Why It Matters
Hassabis's thesis is that AI is uniquely well-suited to scientific domains with high-dimensional, emergent, or data-rich systems where:
- Traditional mathematics lacks expressive power (e.g., biology, complex physical systems)
- Human analysis is bottlenecked by volume of weak signals and correlations
- Control experiments are impossible or unethical in the real world (e.g., economics)

"Machine learning is the perfect description language for biology in the same way maths is for physics." — [[hassabis-deepmind-alphafold-agi]]

## Current State
Google DeepMind is the most prominent institution pursuing AI for science at scale. Key projects:

| Project | Domain | Status |
|---|---|---|
| [[alphafold]] | Structural biology / protein folding | Shipped; Nobel Prize 2024 |
| [[isomorphic-labs]] | Drug discovery / compound design | Active spin-out |
| WeatherNext | Meteorology / climate simulation | Described as most accurate available |
| Virtual cell | Cell biology simulation | In development |

A second pattern emerged in May 2026: [[vibe-physics]], where frontier LLMs (GPT-5.x) are used in iterative dialogue to *derive novel theoretical results*. [[alex-lupsasca]] (OpenAI Science) documented GPT-5.2 deriving novel gluon-amplitude and graviton results that had stumped expert humans for over a year. This is a categorically different mode than AlphaFold-style application: model produces *frontier theoretical conjectures*, not interpolation on a well-defined problem. — [[latent-space-lupsasca-vibe-physics-2026-05]]

## Simulations as New Science
Hassabis argues AI-powered simulations could unlock entirely new sciences for emergent-system domains (economics, social science) by enabling repeatable controlled experiments that are impossible in the real world. Economics, for example, can't run "interest rates +0.5%" a thousand times; accurate simulators could change this.

A further possibility: extract explicit equations from learned simulators — potentially discovering new physical laws from implicit models. Analogous to Maxwell's equations emerging from careful empirical observation, but accelerated and applied to complex systems.

## Relationship to World Models
AI-for-science simulations (weather, virtual cell, economics) are closely related to [[world-models]] in the ML sense — the goal is the same: build accurate internal models of complex systems. But the emphasis is on scientific utility over general intelligence.

## Key People
- [[demis-hassabis]] — founding philosophy; calls this his "personal passion"
- [[pushmeet-kohli]] — head of Google DeepMind's AI for Science group
- [[alex-lupsasca]] — OpenAI Science team; coined and demonstrated [[vibe-physics]] (May 2026)

## Resources
- [[hassabis-deepmind-alphafold-agi]] — primary source; Hassabis's detailed framing
- [[google-deepmind]] — institution building this out
- [[alphafold]] — flagship success case
- [[world-models]] — related architectural concept
- [[vibe-physics]] — second-pattern derivation-mode AI-for-science from OpenAI Science (May 2026)
- [[latent-space-lupsasca-vibe-physics-2026-05]] — Lupsasca primary source documenting vibe physics
- [[deepmind-co-scientist-aging-reversal-2026-05-19]] — DeepMind Co-Scientist identifies genetic leads to reverse cellular aging in human cells; promising-but-not-validated; functional-biology counterpart to [[alphafold]] structural-biology (May 2026)
- [[isomorphic-labs-series-b-2026-05-16]] — Isomorphic Labs $2.1B Series B; IsoDDE drug-design engine; pairs with Co-Scientist as DeepMind applied-AI-for-science commercial-and-research portfolio (May 2026)
- [[deepmind-llm-lean-erdos-oeis-2026-05-25]] — DeepMind LLM-Lean agent loop resolves 9 open Erdős problems + 44 OEIS conjectures via Lean-validator-in-the-loop; formal-math proof generation as third applied AI-for-science domain alongside structural biology (AlphaFold) and functional biology (Co-Scientist); few-hundred-dollars-per-proof economics (May 25 2026)
- [[openai-disproves-discrete-geometry-conjecture-2026-05-21]] — OpenAI GPT-next disproves Erdős planar unit distance problem for <$1K compute; counterexample-finding methodology complement to DeepMind's proof-generation methodology (May 2026)
- [[fda-accelerated-ai-pathway-pilot-2026-05-26]] — FDA 2026 Accelerated AI Pathway Pilot for AI-generated evidence in drug submissions; first regulatory framework legitimizing AI-evidence-as-data not just AI-as-tool; regulatory-infrastructure unlock for the IsoDDE / Co-Scientist / LLM-Lean pharma applied stack (May 26 2026)
- [[dailybrief-roundup-2026-05-26]] — LLM-AutoSciLab closed-loop active-experimentation + Bérczi-Fehér AlphaEvolve-+-GPT-5.5-Pro geometry-conjecture-generation; three same-month frontier-lab loop-closing AI-for-science tools (May 26 2026)
- [[dailybrief-roundup-2026-05-27]] — **AirCast-SR** kilometer-scale atmospheric super-resolution foundation model (latent consistency diffusion; climate/agriculture/disaster-management applied-AI signal) + **ESMFold2** (Alex Rives) claims to beat [[alphafold|AlphaFold3]] on protein-protein interaction benchmarks with lab-validated binders targeting five therapeutic proteins (first competitor signal vs AlphaFold3; verification-pending on benchmark specifics) (May 27 2026)
