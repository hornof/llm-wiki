---
title: "A Path Towards Autonomous Machine Intelligence — Yann LeCun (2022)"
type: source
medium: paper
url: https://openreview.net/forum?id=BZ5a1r-kVsf
ingested: 2026-04-22
---

## Summary
LeCun's 2022 technical paper proposing an alternative architecture to LLMs for reaching general intelligence. Core thesis: machines need configurable predictive world models, intrinsic motivation, and hierarchical joint embedding architectures trained with self-supervised learning — not next-token prediction. This paper is the technical foundation for JEPA and AMI Labs.

## Key Claims / Takeaways
- Central question: "How could machines learn as efficiently as humans and animals? How could machines learn to reason and plan?"
- **World models are key**: "The ability to learn world models — internal models of how the world works — may be the key" to human-level AI
- **Learning from observation**: humans and animals learn vast background knowledge through observation with minimal interaction; current AI doesn't do this
- **JEPA (Joint Embedding Predictive Architecture)**: captures dependencies between two inputs (x and y) by learning abstract representations, not by predicting pixels/tokens
  - Two encoders extract abstract representations sx and sy
  - A predictor module predicts sy from sx
  - Latent variable z represents unpredictable information
  - Manages uncertainty by either discarding hard-to-predict details or generating multiple plausible predictions
- **VICReg training**: Variance, Invariance, Covariance Regularization — avoids expensive contrastive learning
- **Hierarchical JEPA**: stacked JEPAs enable short-term predictions at low abstraction and long-term predictions at high abstraction — analogous to human multi-timescale planning
- **Six modular components**: configurator, perception, world model, cost, actor, short-term memory — all differentiable
- **Why not generative models**: predicting in representation space (JEPA) is more efficient than predicting in pixel/token space (generative models); world is not fully predictable, so abstract representations handle uncertainty better

## Pages Updated
- [[world-models]]
- [[yann-lecun]]
- [[ami-labs]]
