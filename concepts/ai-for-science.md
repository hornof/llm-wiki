---
name: AI for Science
type: concept
maturity: active-research
last_updated: 2026-09-30
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

**AI-assisted cryptanalysis as a research *methodology* (2026-07-28/30)** ([[dailybrief-roundup-2026-07-30]], via [[simon-willison|Willison]]): Anthropic researchers prompted **Claude to discover mathematical weaknesses** in the post-quantum signature scheme **HAWK** and in **weakened AES variants**, then **published the prompts**. The load-bearing signal is *methodological, not the flaws themselves* (**practical impact ≈ zero** — real-world crypto isn't broken): it demonstrates a new mode of **AI-as-research-accelerant** — prompt-engineering a model to hunt for attack surfaces in a formal domain, with the prompt chain as the reproducible artifact. Extends the vibe-physics pattern (novel research-grade findings) from theoretical physics to **cryptanalysis/security**; a datapoint for Jack Clark's *"automation reaching too-hard-to-automate work"* thread ([[jack-clark]]).

## The gap in the dominant formulation — intrinsically disordered proteins (2026-09-30)

[[alphafold|AlphaFold]] and its successors predict **a** structure. **Intrinsically disordered proteins do not have one**, and they are a large and largely undrugged fraction of the proteome. **Topos Bio** ([[topos-bio-redefining-druggable-space-2026-09-30]]) is building for that gap: modelling a protein's **conformational ensemble** — *"the collection of structures it can adopt"* — rather than its fold, plus small-molecule binding **inside the same framework**.

Their framing of what a drug does is the useful sentence: *"since protein shape gives rise to function, drug design can be thought of as **reshaping the landscape of shapes accessible to the protein**."* Their one novelty claim is self-hedged — *"to our knowledge, this is the first generative model that produces ensembles of disordered proteins bound to small molecules."*

**Recorded for the shape of the bet, not the company.** Seed-stage ($10.5M, Axios, 2026-01), one surface, **no `companies/` page created**. **Nothing on the page is evidence** — no benchmark, no molecular-dynamics baseline, no validated binder. What makes it worth a line here is that **the row above this one in the table treats structure prediction as solved**, and the fraction of the proteome where the formulation itself doesn't apply is exactly where the remaining commercial and scientific room is.

### The pharma-side structure is the more interesting item

Topos joined **Eli Lilly's TuneLab** (2026-06-30): federated access to models trained on *"decades of Eli Lilly proprietary ADMET data"*, **while contributing its own data to train them further**.

**An incumbent operating a federated platform where seed-stage startups both consume and feed its proprietary-data models is a structure the wiki has not recorded anywhere.** It answers the [[company-brain|proprietary-data-as-moat]] question by **pooling rather than hoarding** — the data stays the moat, but access is traded for more data. **Whether regulated-industry incumbents elsewhere copy that shape is a better question than anything about this particular startup**, and it is the thing to watch. *(Per Topos's own site; TuneLab's terms, participant list and what "federated" means operationally are all uncaptured.)*

**Context, same week**: [[anthropic|Anthropic's]] AI-discovered enzyme system, DeepMind's **SynthID Bio** protein watermarking ([[frontier-ai-governance]]), and the [[fda-accelerated-ai-pathway-pilot-2026-05-26|FDA AI-evidence pathway]]. **Tooling, provenance and a regulatory route are accumulating around generative biology at roughly the same time** — which is the pattern, rather than any single entrant.

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
- [[topos-bio-redefining-druggable-space-2026-09-30]] — Topos Bio; conformational-ensemble modelling for intrinsically disordered proteins; Eli Lilly TuneLab federated-data membership (Sept 2026)
- [[isomorphic-labs-series-b-2026-05-16]] — Isomorphic Labs $2.1B Series B; IsoDDE drug-design engine; pairs with Co-Scientist as DeepMind applied-AI-for-science commercial-and-research portfolio (May 2026)
- [[deepmind-llm-lean-erdos-oeis-2026-05-25]] — DeepMind LLM-Lean agent loop resolves 9 open Erdős problems + 44 OEIS conjectures via Lean-validator-in-the-loop; formal-math proof generation as third applied AI-for-science domain alongside structural biology (AlphaFold) and functional biology (Co-Scientist); few-hundred-dollars-per-proof economics (May 25 2026)
- [[openai-disproves-discrete-geometry-conjecture-2026-05-21]] — OpenAI GPT-next disproves Erdős planar unit distance problem for <$1K compute; counterexample-finding methodology complement to DeepMind's proof-generation methodology (May 2026)
- [[fda-accelerated-ai-pathway-pilot-2026-05-26]] — FDA 2026 Accelerated AI Pathway Pilot for AI-generated evidence in drug submissions; first regulatory framework legitimizing AI-evidence-as-data not just AI-as-tool; regulatory-infrastructure unlock for the IsoDDE / Co-Scientist / LLM-Lean pharma applied stack (May 26 2026)
- [[dailybrief-roundup-2026-05-26]] — LLM-AutoSciLab closed-loop active-experimentation + Bérczi-Fehér AlphaEvolve-+-GPT-5.5-Pro geometry-conjecture-generation; three same-month frontier-lab loop-closing AI-for-science tools (May 26 2026)
- [[dailybrief-roundup-2026-05-27]] — **AirCast-SR** kilometer-scale atmospheric super-resolution foundation model (latent consistency diffusion; climate/agriculture/disaster-management applied-AI signal) + **ESMFold2** (Alex Rives) claims to beat [[alphafold|AlphaFold3]] on protein-protein interaction benchmarks with lab-validated binders targeting five therapeutic proteins (first competitor signal vs AlphaFold3; verification-pending on benchmark specifics) (May 27 2026)
