---
name: World Models
type: concept
maturity: active-research
last_updated: 2026-04-22
---

## Definition
AI systems that build internal representations of how the world works — learning to predict future states, reason about causality, and plan across time horizons — rather than systems that simply predict the next token in a sequence. The leading alternative architecture to LLMs for achieving general intelligence.

## Why It Matters
LeCun's core thesis: current LLMs are "a dead end when it comes to superintelligence" because they predict in token space rather than building world representations. World models could enable machines to learn as efficiently as humans and animals — who learn vast background knowledge through observation, not supervision.

## JEPA: Joint Embedding Predictive Architecture

The specific architecture LeCun proposes. Key insight: predict in abstract representation space, not in pixel/token space.

**How it works:**
1. Two inputs (e.g., consecutive video segments) pass through encoders → abstract representations sx and sy
2. A predictor module predicts sy from sx
3. Latent variable z represents unpredictable information
4. Uncertainty handled by either discarding hard-to-predict details or generating multiple plausible predictions

**Training**: VICReg (Variance, Invariance, Covariance Regularization) — avoids expensive contrastive learning

**Hierarchical JEPA**: stack multiple JEPAs — lower levels handle short-term, concrete predictions; higher levels handle long-term, abstract planning. Mirrors how humans reason at multiple timescales.

## Why Not Generative Models?
The world is not fully predictable. Generating in pixel/token space forces the model to predict everything — including irreducible noise. JEPA abstracts away the unpredictable and focuses on what can be learned. More efficient, more robust.

## The Six-Module Architecture (LeCun 2022)
LeCun proposes six differentiable modules working together:
- **Configurator**: sets the goal and parameters for the other modules
- **Perception**: encodes the current state of the world
- **World model**: predicts future states
- **Cost**: evaluates outcomes against goals
- **Actor**: generates actions
- **Short-term memory**: holds current state and recent context

## Relationship to AGI Debate
LeCun's world-model thesis is a direct challenge to scaling LLMs as a path to AGI. Compare with:
- [[demis-hassabis]]: agrees current systems are insufficient (jagged intelligence); believes continual learning and creativity are missing; building Gemini at Google DeepMind
- [[andrej-karpathy]]: focused on data quality and cognitive core + retrieval; less specific on world models vs. LLMs

## Current State
Theoretical and early-experimental stage. AMI Labs ([[ami-labs]]) is LeCun's vehicle for building this out. JEPA variants (I-JEPA for images, V-JEPA for video) have been released by Meta FAIR. Not yet demonstrated at general intelligence scale.

## Resources
- [[lecun-path-autonomous-machine-intelligence]] — PRIMARY SOURCE: the 2022 paper
- [[yann-lecun]] — architect of this approach
- [[ami-labs]] — the lab building it out
