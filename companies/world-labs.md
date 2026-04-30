---
name: World Labs
type: company
status: active
last_updated: 2026-04-29
---

## What It Is

World Labs is a spatial intelligence AI startup founded by [[fei-fei-li]] and based in San Francisco. It develops AI models that reason about and generate three-dimensional environments — described by Li as "the next frontier of AI," explicitly complementary to (not replacing) LLMs. Founded 2023; "little more than a year old" as of the November 2025 Bloomberg interview.

## Founding Story

Li co-founded World Labs after going on partial leave from Stanford in January 2024. The founding thesis: spatial intelligence is the major missing capability in current AI — current multimodal LLMs "rarely perform better than chance on estimating distance, orientation, and size." World Labs aims to build models that can perceive, reason about, and generate 3D environments, grounding AI in the physical world.

In Li's words: "I am co-founder and CEO of World Labs. We are building the next frontier of AI — spatial intelligence — which people don't hear too much about today because we're all about large language models. I believe spatial intelligence is as critical [as] — and complementary to — language intelligence." — [[bloomberg-feifei-li-2025]]

## Funding

- **$230M** raised ahead of public launch in 2024 — [[bloomberg-feifei-li-2025]]
- NEA led a $100M round; valuation exceeded $1B at that point (TechCrunch, August 2024) — [[bloomberg-feifei-li-2025]]
- **$1B total raised** as of 2026 — [[forbes-ai-50-2026]]
- Listed on **Forbes 2026 AI 50** — [[forbes-ai-50-2026]]

## Key Product: Marble

**Marble** (November 2025) is World Labs' flagship frontier model. It generates interactive 3D worlds from a text prompt or image.

- **Input**: text prompt (e.g., "Give me a modern-looking kitchen") or an image of a space
- **Output**: a full navigable 3D world based on the input
- **What makes it a "frontier model"**: Li's term — not a visualization tool but a world-generating model with geometric and physical consistency

### Marble Use Cases (from Li, Nov 2025)
- **Design and architecture**: ideate and prototype spaces in 3D before physical construction
- **Game development**: generate 3D environments for use in games
- **Robotics simulation**: generate training and evaluation data for robot learning (physically consistent worlds for sim-to-real transfer)
- **AR/VR education**: immersive learning environments — Li's example: "walk into a cell" to understand nucleus, enzymes, membranes

Li on Marble's broader vision: "The ability to create a 3D world is fundamental to humans. I hope one day it's fundamental to AI." — [[bloomberg-feifei-li-2025]]

## Technical Thesis

### Spatial Intelligence as AI's Missing Layer
Li argues the first half of AI research focused on passive perception: "This is a cup. This is a beautiful lady. This is a microphone." But intelligence evolved in service of action — the action-perception loop: "We see, because we move. We move, therefore we need to see better."

Spatial intelligence is the active layer: understanding 3D geometry, depth, orientation, object relationships, and physical dynamics — enabling AI to act in the world, not just describe it.

### Three Required Capabilities (Li's World Model Architecture)
1. **Generative**: creates geometrically and physically consistent simulated worlds
2. **Multimodal**: processes images, text, depth maps, and other input types
3. **Interactive**: predicts next world states based on actions

### Position in the AGI Debate
Li's framing is explicitly additive — spatial intelligence *complements* LLMs, it does not replace them. This distinguishes her from [[yann-lecun]] (who rejects LLMs entirely as a path to superintelligence and builds the JEPA architecture from scratch) and from [[demis-hassabis]] (who focuses on continual learning and creativity as what's missing).

Compare the world-model approaches:
- **LeCun / AMI Labs / JEPA**: abstract representation space; rejects generative models; no next-token prediction
- **Li / World Labs / Marble**: 3D spatial geometry; generative; builds on top of current AI
- **Luma AI / Uni-1**: unified latent space across all modalities; also generative

See [[world-models]] for the full comparison.

## Competitive Landscape

Google DeepMind is building in adjacent territory — **Genie 3** is noted in the Bloomberg article as "a new frontier for world models" (footnote 13). World Labs distinguishes itself by deep 3D spatial grounding (not just video generation) and Li's foundational research lineage (ImageNet, Stanford Vision and Learning Lab's iGibson simulation environment).

## Key People

- **[[fei-fei-li]]** — co-founder and CEO; created ImageNet (2006); Stanford HAI co-director; CS231n; AI4ALL; 25 years in the field

## Intellectual Lineage

World Labs sits at the intersection of two research traditions Li drew on for ImageNet:
1. **Cognitive psychology** (James J. Gibson's ecological approach to visual perception — "We perceive in order to move, and we move in order to perceive"; Stanford's iGibson simulation platform is named after him)
2. **Linguistic taxonomy** (WordNet — the semantic network that inspired organizing visual concepts into a large-scale taxonomy, leading to ImageNet's 22,000-class structure)

## Resources

- [[bloomberg-feifei-li-2025]] — PRIMARY SOURCE: full Bloomberg Weekend Interview (Nov 2025); founding story, Marble, spatial intelligence thesis, AGI stance
- [[forbes-ai-50-2026]] — AI 50 list inclusion; $1B total funding
- [[fei-fei-li]] — founder profile with full context
- [[spatial-intelligence]] — deep dive on the spatial intelligence concept
- [[world-models]] — comparative analysis of world-model architectures (LeCun vs. Li vs. Luma)
