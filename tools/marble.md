---
name: Marble
type: tool
category: platform
status: emerging
last_updated: 2026-06-03
---

## What It Is

[[world-labs|World Labs]]' first product — a **multimodal-input, dual-output 3D world-generation system** positioned as "World Labs' first move into simulator territory" in the [[feifei-li-world-models-functional-taxonomy-2026-06-03|3-category functional taxonomy of world models]] (renderer / simulator / planner).

## Input / Output

- **Inputs (multimodal)**: text + image + video + spatial-sketch prompts
- **Outputs (dual)**: 
  - **Gaussian splats** — for visual exploration (renderer-side)
  - **Collision meshes** — for physics engines to operate on (simulator-side)

**Pattern**: Marble *"dissolves the boundary between the renderer and the simulator"* (Fei-Fei Li, 2026-06-03). First wiki-captured concrete instance of *category-blending* in the 3-category world-models taxonomy — outputs both pixels (for human visual exploration) and geometry-with-physics (for downstream physics-engine + simulator-side consumption) from a single model.

## Traction Signals

- **2026-06-03**: First wiki-captured concrete product description with input/output schema, in Fei-Fei Li's *A Functional Taxonomy of World Models* essay ([[feifei-li-world-models-functional-taxonomy-2026-06-03]]). **Primary not deeply fetched**; user-facing product surface not yet wiki-captured.
- **Deployment metrics unknown**: number of users / customers / revenue all undisclosed in the essay.

## Where It Sits in the World-Models Stack

Per [[feifei-li-world-models-functional-taxonomy-2026-06-03|the 3-category taxonomy]]:

| Category | Output | Marble's position |
|---|---|---|
| Renderer | pixels (visual fidelity) | partially — outputs Gaussian splats |
| **Simulator** | **state (geometry + physics + dynamics)** | **primary — outputs collision meshes for physics engines** |
| Planner | actions | not directly addressed |

**Positioning**: World Labs is betting on the **simulator category** as the structurally-most-consequential. Marble is *the first chapter of a much longer arc*; the explicit endpoint is the **unified world model** that can render + simulate + plan from a single foundation model.

## Compared To

- **Google Genie 3** (DeepMind) — *renderer-side* world model; interactive system generating frames in real time conditioned on user input. Doesn't output physics-engine-consumable geometry.
- **World Labs RTFM** — *renderer-side* internal World Labs product (cited in the essay); separate from Marble.
- **NVIDIA Omniverse** — *simulator-side* incumbent; ">$1T addressable market" per NVIDIA's framing per [[feifei-li-world-models-functional-taxonomy-2026-06-03|the essay]]. **Marble is positioned to compete in the simulator-side that Omniverse dominates** but with AI-generative-from-multimodal-prompt as the differentiation rather than hand-authored 3D pipeline.
- **xAI Grok Imagine** ([[latentspace-video-agents-xai-grok-imagine-2026-06-02]]) — *renderer-side action-conditioned* video-agent; pattern-watch on whether xAI extends into the simulator category or stays in renderer-becoming-interactive.

## Open Questions

- **Sim-to-real fidelity**: how does Marble's collision-mesh output compare to hand-authored physics-engine assets when fed to robot-control or autonomous-vehicle training loops?
- **Multi-physics scope**: does Marble handle rigid bodies + deformable objects + fluids + cloth, or single-domain rigid-only?
- **Generative-simulator-risk** (per the essay): *"AI-generated geometry can look correct while containing self-intersections or wrong scale that produce nonsensical physics"* — how does Marble validate or constrain output geometry?
- **Pricing / availability**: is Marble in private preview, public preview, or GA? Pricing band?
- **Integration partners**: does Marble plug into NVIDIA Omniverse / Unity / Unreal / Blender as a content-generation primitive, or remain a self-contained World Labs surface?

## Resources

- [[feifei-li-world-models-functional-taxonomy-2026-06-03]] — primary source describing Marble's input/output schema and positioning
- [[world-labs]] — parent company
- [[world-models]] — concept page; Marble is the first World Labs product in the simulator category
- [[fei-fei-li]] — founder
