---
title: "Fei-Fei Li + World Labs team — A Functional Taxonomy of World Models (2026-06-03)"
type: source
medium: blog-post
url: https://x.com/drfeifei/status/2062247238143996275
ingested: 2026-06-03
---

## Summary

[[fei-fei-li|Fei-Fei Li]] and the [[world-labs|World Labs]] team publish *"A Functional Taxonomy of World Models"* (2026-06-03 via X + Substack) — **first wiki-captured load-bearing taxonomy of what "world model" actually means**, decomposing the heavily-overloaded term into **three functional projections**: **renderer** (outputs pixels), **simulator** (outputs state), and **planner** (outputs actions). The essay positions **simulation as the linchpin** ("the bridge between rendering and planning"), and frames World Labs' [[marble|Marble]] as the company's first move into the simulator territory. Pairs structurally with the May 2026 [[lecun-path-autonomous-machine-intelligence|LeCun JEPA / autonomous-machine-intelligence paper]] (architectural priors for world-models) and with the same-week [[latentspace-video-agents-xai-grok-imagine-2026-06-02|Latent Space xAI Grok Imagine video-agent breakdown]] (xAI side of the *renderer-as-frontier-product* layer).

## Key Claims / Takeaways

### The 3-category functional taxonomy

The thesis is that the canonical RL "agent ↔ world" loop (Sutton & Barto's POMDP picture) has three projections, each producing a different output:

| Category | Output | Contract | Example products |
|---|---|---|---|
| **Renderer** | observations (pixels) | visual fidelity | text-to-video models; Google **Genie 3**; World Labs **RTFM**; Google **Nano Banana** image-gen |
| **Simulator** | state (geometry + physics + dynamics) | structural accuracy | NVIDIA **Omniverse**; World Labs **Marble**; physics engines |
| **Planner** | actions | task-completion under partial observation | **Vision-Language-Action models**; model-based RL; **World Action Models** |

**Pattern**: each of the three is *"a different projection of the same loop"* — same underlying geometry/physics/dynamics knowledge sits beneath all three; the differences are which face is consumed by the downstream user.

### Why simulation is the linchpin

> *"Of the three categories, the simulator gets the least public attention, and is the most consequential of the three."*

- **Renderer** is *commercially mature* — Nano Banana and adjacent text-to-image/video products are now consumer-scale. Ceiling: optimizes for plausibility, not accuracy → *"cannot be trusted to design a building or train a robot."*
- **Planner** is *the most intriguing and the most nascent* — robotic demos look impressive but are *"confined to heavily constrained laboratory setups, with narrow object sets and short task horizons. None have been validated at the complexity, variability, or duration that real-world deployment demands."*
- **Simulator** is the bridge: *"the structural backbone from which both visual appearance (for renderers) and action consequences (for planners) can be derived. A model that masters simulation can project its understanding into pixels for human consumption, and into action predictions for embodied agents."*

**NVIDIA Omniverse total-addressable-market framing**: NVIDIA estimates *"more than a trillion dollars of addressable market in factories, warehouses, supply chains, and digital twins."* **First wiki-captured concrete-TAM framing for the simulator category** as distinct from the renderer category.

### The hard open problems live in simulation

- **3D data scarcity**: *"three-dimensional data with explicit geometry, material properties, and physical annotations is orders of magnitude scarcer than the internet video that renderers train on."*
- **Sim-to-real gap** persists.
- **Generative-simulator-specific risk**: *"AI-generated geometry can look correct while containing self-intersections or wrong scale that produce nonsensical physics."*
- **Multi-physics at scale**: rigid + deformable + fluids + cloth interacting is *"orders of magnitude more expensive than single-domain simulation."*

### Marble = World Labs' first move into simulator territory

> *"Marble is our first move into this territory. It takes multimodal prompts (text, image, video, or spatial sketch) and generates explorable 3D environments, outputting Gaussian splats for visual exploration alongside collision meshes a physics engine can operate on."*

**First wiki-captured concrete World Labs Marble product description with input/output schema**:

- **Inputs**: text + image + video + spatial-sketch (multimodal)
- **Outputs (dual)**: Gaussian splats (for visual exploration; renderer-side) + collision meshes (for physics engines; simulator-side)

**Pattern**: Marble *"dissolves the boundary between the renderer and the simulator"* — first concrete instance of category-blending in the 3-category taxonomy.

### The endpoint: unified world model

> *"The logical endpoint is a unified world model: one foundation model that can render photorealistic views, produce physically accurate structure, and plan action sequences, switching between output modalities depending on what the downstream consumer needs."*

Open problem: *"Reconciling these tensions inside a single architecture is the defining open problem in world model research today."*

### Pattern: every level moving from passive output to interactive system

> *"Every level is moving from passive output to interactive system, with renderers becoming action-conditioned, simulators generating worlds that are more controllable and editable, and planners deliberating rather than just reacting."*

**First wiki-captured cross-category convergence framing** — pairs structurally with the [[latentspace-video-agents-xai-grok-imagine-2026-06-02|Latent Space "reasoning over raw frames"]] framing on Grok Imagine: *xAI is making the renderer action-conditioned* at the same time World Labs is *dissolving the renderer-simulator boundary*. **First wiki-captured same-week 2-vendor convergence on the renderer-becomes-interactive direction**.

### Historical anchoring

- **Kenneth Craik (1943)**: original "small-scale models of reality" — the term "world model" predates modern neural networks.
- **Sutton & Barto (RL textbook)**: canonical POMDP picture; original technical meaning of "world model" lives there.
- **Late 1980s / early 1990s**: neural-network adoption of the "world model" terminology.
- **Bet since the late 1980s**: *"a sufficiently rich model of the world is all that any agent needs to see worlds, build them, and act in them."*

### Cross-cutting framings

- **Words vs world**: the essay opens with Wittgenstein (*"The world is everything that is the case"*) and frames world-models as *"the substrate language models can't reach"*: *"Where language models learn the statistical structure of text, world models learn the statistical structure of space and time."*
- **NVIDIA Omniverse + a trillion-dollar simulation TAM** — first wiki-captured concrete-TAM framing pairs with [[nvidia|NVIDIA]]'s broader infrastructure-backbone positioning.
- **Three commercially-real research programs converging into one**: *"three threads, each already driving and shaping multi-billion-dollar industries on its own, that began as separate research programs are starting to behave like one."*
- **Pairs structurally with [[xai|xAI Grok Imagine]] modality-divergence move** ([[latentspace-video-agents-xai-grok-imagine-2026-06-02|Latent Space breakdown]] from 2026-06-02): xAI is competing in the *renderer-becoming-action-conditioned* surface; World Labs is competing in the *renderer + simulator unification* surface. **First wiki-captured same-week 2-vendor world-model-category-divergence in the renderer-extension direction**.
- **Pairs with [[ami-labs|Yann LeCun's AMI]] and [[lecun-path-autonomous-machine-intelligence|JEPA path-paper]]**: LeCun's JEPA framing is *world-model-as-autonomous-architecture-prior*; Fei-Fei's framing is *world-model-as-product-taxonomy*. The two are largely complementary — LeCun's frame addresses *what the architectural priors should be*; Fei-Fei's frame addresses *what the consumer-facing categories should be*.
- **Pairs with [[ineffable-intelligence|David Silver's RL-from-self-play lab]] and [[physical-intelligence|Physical Intelligence's robot-foundation-model]]**: both are planner-side bets in Fei-Fei's taxonomy; the essay candidly notes *"the gap between a compelling demo reel and a robot that reliably works in a kitchen, a warehouse, or an operating room remains vast."*

### Notably absent from the essay

- **No mention of [[anthropic]] / [[openai]] / [[google-deepmind]]** as world-model vendors — though Genie 3 (DeepMind) and Nano Banana (Google) are cited as renderer examples. **Fei-Fei is framing World Labs as the simulator-side player** without engaging with frontier-lab branding.
- **No reference to [[xai]] Grok Imagine** (2026-06-02 ship, 1 day prior) — possible timing overlap or deliberate omission; pattern-watch is whether World Labs responds to the xAI move in subsequent communications.
- **No specific deployment metrics for Marble** — number of users, customers, revenue all undisclosed.

## Bloomberg Tech 2nd surface (a16z X amplification, 2026-06-08-clipped)

Fei-Fei Li re-articulates the 3-category framework at **Bloomberg Tech live with @emilychangtv** (same date 2026-06-03; clipped + amplified by @a16z 2026-06-08 — `x.com/a16z/status/2064075116867469550`):

> *"Right now there are three ways of calling world models when it comes to spatial intelligence."*
>
> *"One is what I call a renderer, when the model puts beautiful pixels on the screen."*
>
> *"Another kind of world model is what we call a planner. That is more for machines, more for robots."*
>
> *"The third kind, which I think is the linchpin of the three, is a simulator."*
>
> *"A simulator could become a renderer. The simulator could become a planner. But this layer is a huge critical path to unlock spatial intelligence. And that's what World Labs is working on."*

**First wiki-captured Fei-Fei-direct-voice articulation of "simulator could become a renderer / simulator could become a planner" projection-mechanic framing** — the Substack version stated *"a model that masters simulation can project its understanding into pixels for human consumption, and into action predictions for embodied agents"*; the Bloomberg Tech version is the **shorter, more-memetable practitioner-quote version**. **First wiki-captured "linchpin of the three" canonical Fei-Fei-voice phrasing**. 2nd substantive Fei-Fei surface of the taxonomy within the same week (Substack + Bloomberg Tech) confirms the framework as Fei-Fei-canonical-talking-point.

### Practitioner comment-thread reactions (a16z X amplification, 2026-06-08)

- **Sanket Datta (@sanketdattta)**: *"Useful distinction. My only hesitation is that these labels get blurry fast once a system starts doing more than one thing, so the taxonomy helps until people mistake it for fixed boundaries. Curious which overlap creates the most confusion in practice."* **First wiki-captured practitioner-side caveat: taxonomy-helps-until-mistaken-for-fixed-boundaries.**
- **Roshan (@meta_x_ai)**: *"There is only one world and there should be only one definition of a world model. A model that can simulate both the physical and intelligent world that an average human can't tell the difference...using any of their senses."* **First wiki-captured practitioner-side reductionist counter-framing**: collapse 3-category framing to single Turing-test-style world-model definition. **Counter-position to Fei-Fei's functional-projection framing.**
- **Ilman Shazhaev (@shzhv13)**: *"The simulator is the interesting part because it turns world models from generate something plausible into reason about what happens next. That's the difference between a visual toy and a real intelligence layer."* **First wiki-captured "visual-toy-vs-real-intelligence-layer" framing** at the renderer-vs-simulator distinction layer. Pairs with Fei-Fei's *"cannot be trusted to design a building or train a robot"* renderer-ceiling framing.
- **Isabelle E-Z (@IsabelleRLabs)**: *"The renderer-planner-simulator framework is elegant. But building simulators requires R&D investment Canada isn't making. We'll keep losing our talent to places that actually fund this work."* **First wiki-captured Canada-AI-R&D-investment-gap framing** at the simulator-category geographic-talent-flow layer. Pairs with [[junyang-lin|Junyang Lin departure from Alibaba Qwen]] at the **geographic-AI-talent-flow** layer (different direction: Lin China→TBD; Isabelle Canada→TBD).

**Pattern**: the a16z X amplification surfaces **4-distinct practitioner-comment-thread reactions** (caveat / reductionist-counter / visual-toy-vs-intelligence-layer / Canada-talent-flow-gap) — adds practitioner-content register validation + counter-positioning to the Fei-Fei framework.

## Pages Updated

- [[fei-fei-li]] — latest essay added as Notable Take; the 3-category functional taxonomy framing
- [[world-labs]] — first wiki-captured Marble product description added; renderer-simulator boundary-dissolving framing
- [[world-models]] — Three-category functional taxonomy section added (renderer / simulator / planner) as the load-bearing organizing frame
- [[marble]] — new entity page created for World Labs Marble
- [[nvidia]] — Omniverse "more than a trillion dollar" simulator TAM framing noted

## Adjacent sources

- [[bloomberg-feifei-li-2025]] — prior Fei-Fei Li primary source
- [[lecun-path-autonomous-machine-intelligence]] — LeCun's JEPA / autonomous-machine-intelligence architectural-prior framing
- [[latentspace-video-agents-xai-grok-imagine-2026-06-02]] — same-week xAI Grok Imagine renderer-becomes-action-conditioned move
- [[wikipedia-fei-fei-li]] — biographical baseline
- ["From Words to Worlds: Spatial Intelligence"](https://drfeifei.substack.com/p/from-words-to-worlds-spatial-intelligence) — referenced earlier Fei-Fei essay (not yet wiki-captured; flagged for follow-up ingest)

## Verification-pending

- Marble specific user / customer / revenue metrics
- Marble model architecture / training data composition
- Whether World Labs publishes a paper or remains at essay-level positioning
- Co-authors on the essay (essay credits "World Labs team" without names; verification-pending which team members co-wrote)
- Specific NVIDIA Omniverse TAM source (is the >$1T number from NVIDIA's own filings, an analyst report, or an internal estimate?)
- Whether World Labs has signed any of NVIDIA's Omniverse partner programs
