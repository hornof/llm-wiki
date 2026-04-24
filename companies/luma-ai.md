---
name: Luma AI
type: company
status: active
last_updated: 2026-04-24
---

## What It Is
AI lab building multimodal general intelligence — systems that jointly model language, audio, video, images, and spatial reasoning in a single unified architecture. Based in San Francisco. Founded by [[amit-jain]] and Jiaming Song (diffusion models researcher).

## Mission
"Build multimodal AGI that can generate, understand, and operate in the physical world." Rejects the model of LLMs fine-tuned to handle images/audio — argues all modalities should be jointly trained from scratch in one coherent latent space.

## Key Products
- **Dream Machine**: video generation platform; 1M users in 4 days at launch (2024); trained on 1.2 quintillion tokens
- **Ray2 / Ray3**: video models; Ray3 is the "world's first reasoning video model"
- **Uni-1**: first "Unified Intelligence" model (March 2026); autoregressive transformer jointly trained on audio, video, image, language, and spatial reasoning; "think in language, imagine in pixels"
- **Luma Agents**: creative workflow agents powered by Uni-1; maintain persistent context across assets and iterations; self-critique and refine outputs

## Technical Approach
- **Unified latent space**: all modalities — language, audio, video, image — operate in one shared representation space, not separate pipelines
- **Joint training**: backprop flows through all modalities simultaneously; Jain argues this is essential for the sum to exceed the parts
- **Generative world model**: diffusion-based and autoregressive (Uni-1); contrasts with LeCun's JEPA which explicitly rejects generative approaches
- **Concepts framework**: teach models new capabilities from minimal examples without degrading base model; later internalize into next-gen model
- **Training dynamics**: studies pathway formation in first 20-30K iterations; aggressive dataset filtering over scale

## Traction Signals
- $900M Series C (November 2025) led by HUMAIN (Saudi PIF), with a16z, AMD Ventures; valuation ~$4B — [[techcrunch-luma-uni1]]
- Dream Machine: 1M users in 4 days at launch
- Uni-1 outscores Google and OpenAI image models on reasoning benchmarks at 30% lower cost (March 2026)
- Grown from ~30 to 160+ employees in 2025
- Project Halo: 2-gigawatt AI supercluster in Saudi Arabia (completion 2028)

## Relationship to the AGI Debate
Luma sits in a distinct position relative to the key players:
- vs. **LeCun/JEPA**: direct philosophical opposition — LeCun rejects generative models; Luma builds them. Both target world models as the path forward but diverge sharply on whether to generate in pixel/token space.
- vs. **Fei-Fei Li/World Labs**: both emphasize physical world understanding; Fei-Fei focuses on 3D spatial geometry specifically; Luma is broader (all modalities unified)
- vs. **Hassabis/Gemini**: both believe current LLMs are insufficient for AGI; differ on architecture

## Resources
- [[amit-jain]] — co-founder and CEO
- [[cognitive-revolution-luma-worldsim]] — deepest technical discussion of architecture
- [[techcrunch-luma-uni1]] — Uni-1 and Luma Agents launch
- [[amplify-amit-jain-interview]] — Jain's philosophy on unified models and scale
