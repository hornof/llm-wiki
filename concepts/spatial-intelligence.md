---
name: Spatial Intelligence
type: concept
maturity: active-research
last_updated: 2026-04-23
---

## Definition
The ability of AI systems to perceive, reason about, and act within three-dimensional physical and virtual worlds. Goes beyond language and 2D vision to include understanding of geometry, physics, depth, orientation, object relationships, and cause-and-effect in space. Fei-Fei Li's term and thesis for AI's next major capability frontier.

## Why It Matters
LLMs excel at language but are physically blind — state-of-the-art multimodal models "rarely perform better than chance on estimating distance, orientation, and size." They cannot navigate mazes, recognize shortcuts, or predict basic physics. Li argues that without spatial intelligence, AI cannot become a "true partner" in the physical world, and AGI itself is incomplete: "AGI will not be complete without spatial intelligence."

## Key Distinction: Complementary vs. Replacement
Li's position is explicitly *additive*: "I believe spatial intelligence is as critical [as] — and complementary to — language intelligence." — [[bloomberg-feifei-li-2025]]

This separates her from LeCun, who rejects LLMs as a path to superintelligence entirely. Li builds on top of current AI; LeCun builds around it.

## The Action-Perception Loop
"We see, because we move. We move, therefore we need to see better." — [[bloomberg-feifei-li-2025]]

Intelligence evolved in service of action in a physical world. Passive perception (reading text, recognizing images) is not enough — AI needs to understand 3D space to act effectively within it. This grounds the spatial intelligence thesis in evolutionary biology, not just engineering preference.

## LeCun Connection
Both Li and [[yann-lecun]] independently arrive at "world models" as the solution to current AI's limitations — but from very different angles:
- LeCun: world models as a *replacement* for LLMs (JEPA, abstract representation space, reject next-token prediction)
- Li: world models as a *complement* to LLMs — the spatial/physical layer that language models lack

Same architecture name, fundamentally different stance on whether LLMs have a future in general intelligence.

## The World Model Architecture (Li's Version)
Three required capabilities:
1. **Generative**: creates geometrically and physically consistent simulated worlds
2. **Multimodal**: processes images, text, depth maps, gestures, and other input types
3. **Interactive**: predicts next world states based on actions

Must reconcile semantic, geometric, dynamic, and physical dimensions simultaneously — "exceeds anything AI has faced before."

## Current State
World Labs ([[fei-fei-li]]'s startup) released **Marble** (November 2025) — a world-generating model that reconstructs, generates, and simulates 3D worlds. Early-stage; $1.23B raised total ($230M in 2024, $1B in 2026).

## Relationship to AGI Debate
Li's position in the AGI debate: not skeptical of LLMs per se, but insists they are **incomplete** — a necessary but insufficient component of general intelligence. Spatial understanding is the missing layer.

Compare with:
- [[world-models]] (LeCun) — rejects LLMs as the path; builds from scratch with JEPA
- [[agi]] (Hassabis) — focuses on continual learning and creativity as what's missing
- [[training-data-quality]] (Karpathy) — focuses on data quality within the LLM paradigm

## Resources
- [[feifei-substack-spatial-intelligence]] — PRIMARY SOURCE: Li's Substack post
- [[fei-fei-li]] — architect of this approach
