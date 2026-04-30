---
name: World Models
type: concept
maturity: active-research
last_updated: 2026-04-29
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

## Contrasting Approaches to World Models

Three major labs are building world models, but with fundamentally different architectures and philosophies:

### LeCun / JEPA (AMI Labs)
- **Representation**: abstract latent space — explicitly NOT pixel/token space
- **Generative?**: No. Rejects generative models as inefficient and unscalable to irreducible noise
- **Temporal emphasis**: hierarchical temporal prediction; short-term concrete to long-term abstract
- **Modalities**: primarily video (V-JEPA); multi-modal via separate encoders, not joint training
- **Key claim**: "the world is not fully predictable — don't generate what can't be predicted"

### Fei-Fei Li / Spatial Intelligence (World Labs)
- **Representation**: 3D geometric structure of the physical world
- **Generative?**: Yes, but grounded in spatial geometry
- **Temporal emphasis**: action-perception loop — agent acts in space, perception updates model
- **Modalities**: vision-first; current LLMs are "wordsmiths in the dark" without spatial grounding
- **Key claim**: "intelligence lives in the physical world; language alone cannot capture it"

### Luma AI / Unified Intelligence (Uni-1)
- **Representation**: single unified latent space across all modalities
- **Generative?**: Yes — "think in language, imagine and render in pixels"
- **Temporal emphasis**: all modalities jointly; not temporal-first
- **Modalities**: audio, video, image, language, spatial reasoning — jointly trained from scratch
- **Key claim**: "nature makes no distinction between modalities — all are signals from the same physical environment"
- **Against LLM retrofitting**: "Instead of language backbones retrofitting everything, we need a unified, singular latent space" — [[amit-jain]]

**Core tension**: LeCun says generating in pixel/token space is wrong. Luma says it's the path to intelligence. Both claim world models are necessary for AGI but disagree sharply on what "world model" means.

## Silver / Ineffable Intelligence (2026): A Fourth Position

David Silver (architect of AlphaGo, AlphaZero, AlphaStar) argues that the training signal itself — not just the architecture — is the fundamental bottleneck. Even world models trained on human-generated data would face the same ceiling. The only path to exceeding the human knowledge frontier is RL from self-play (with no human data at all, only rules), the same approach that produced Move 37 in AlphaGo. Silver founded [[ineffable-intelligence]] with $1.1B to pursue this thesis. — [[sources/ric-rtp-david-silver-ineffable]]

This creates a fourth distinct position in the AGI debate:
- **LeCun/JEPA**: wrong architecture (LLMs) — fix the architecture (world models)
- **Silver/RL**: wrong training signal (human data) — fix the signal (pure self-play)
- **Hassabis**: missing capabilities (continual learning, creativity) — add them to existing LLM + RL paradigm
- **LLM scaling labs**: scale is enough

## Relationship to AGI Debate
LeCun's world-model thesis is a direct challenge to scaling LLMs as a path to AGI. Compare with:
- [[demis-hassabis]]: agrees current systems are insufficient (jagged intelligence); believes continual learning and creativity are missing; building Gemini at Google DeepMind. Also building AI-for-science simulators (WeatherNext, virtual cell) that function as learned world models for specific scientific domains — see [[ai-for-science]]
- [[andrej-karpathy]]: focused on data quality and cognitive core + retrieval; less specific on world models vs. LLMs
- [[amit-jain]]: world model is "a necessary condition, but not a sufficient condition for AGI"; the generative unified approach

## Current State
Multiple labs at active-research stage with diverging architectures:
- **LeCun/JEPA**: theoretical and early-experimental; I-JEPA and V-JEPA released by Meta FAIR; not yet at general intelligence scale
- **Fei-Fei/World Labs**: Marble prototype demonstrated; focused on 3D spatial reasoning
- **Luma/Uni-1**: Uni-1 shipped March 2026; deployed in production (Dream Machine, Luma Agents); outscores Google/OpenAI on reasoning benchmarks at 30% lower cost

## Terminology Note

"World model" is also used in organizational/business contexts to mean an AI-maintained operational picture of a company's internal state — as in [[block]]'s architecture. That usage is entirely distinct from the ML/AGI sense described on this page. See [[ai-native-organizations]] for that thread.

## Resources
- [[sources/ric-rtp-david-silver-ineffable]] — Silver's RL-from-self-play thesis; fourth position in the AGI debate
- [[ineffable-intelligence]] — Silver's lab; the pure-RL-no-human-data bet
- [[lecun-path-autonomous-machine-intelligence]] — PRIMARY SOURCE: the 2022 JEPA paper
- [[yann-lecun]] — architect of the JEPA approach
- [[ami-labs]] — LeCun's lab building JEPA out
- [[fei-fei-li]] — spatial intelligence framing
- [[amit-jain]] — Luma AI's generative unified approach
- [[luma-ai]] — Uni-1 architecture and deployment
- [[cognitive-revolution-luma-worldsim]] — deepest technical discussion of Luma's approach
- [[ai-for-science]] — Hassabis's domain-specific learned simulators (WeatherNext, virtual cell)
