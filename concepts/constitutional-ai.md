---
name: Constitutional AI
type: concept
maturity: foundational
last_updated: 2026-04-24
---

## Definition

Constitutional AI (CAI) is a training methodology developed by [[anthropic]] (December 2022) for producing AI assistants that are both helpful and harmless. Instead of relying on human raters to label harmful outputs, CAI gives the model a written set of principles — a "constitution" — and uses AI-generated feedback to supervise its own training. The key innovation is replacing human harmlessness labels with AI-generated critiques (RLAIF: Reinforcement Learning from AI Feedback).

## Why It Matters

CAI solves two problems simultaneously:

1. **Scalability** — human labeling of harmful content is expensive, slow, and psychologically taxing. AI feedback scales.
2. **Transparency** — the constitution is a legible, auditable document. Instead of opaque human preferences baked into a reward model, the principles guiding the model's behavior can be read and debated.

It's the foundation of how Claude is trained, and its core ideas (RLAIF, model spec documents) are now widely referenced in alignment research.

## How It Works

Training unfolds in two phases:

**Phase 1 — Supervised Learning (SL-CAI):**
1. Sample a potentially harmful response from the model
2. Ask the model to critique that response against the constitution
3. Ask the model to revise the response based on the critique
4. Fine-tune on the revised (more harmless) responses

**Phase 2 — Reinforcement Learning (RL-CAI / RLAIF):**
1. Generate pairs of responses
2. Ask an AI (not a human) to evaluate which is more aligned with the constitution
3. Use those AI preferences to train a reward model
4. Apply RL (PPO) against that reward model

The result: "a harmless but non-evasive AI assistant that engages with harmful queries by explaining its objections" — it reasons through the harm rather than refusing blindly.

## The Constitution in Practice

Anthropic has publicly released Claude's actual constitution at `anthropic.com/constitution` (CC0 license). It establishes four ordered priorities:

1. **Broad Safety** — don't undermine human oversight of AI
2. **Broad Ethics** — be honest, avoid harmful actions
3. **Anthropic Guidelines** — follow specific operator guidance
4. **Genuine Helpfulness** — benefit operators and users

The ordering matters: safety > ethics > guidelines > helpfulness. When these conflict, earlier priorities win.

## Current State

CAI (2022) → model spec / "Claude's Constitution" (public, 2024) → Constitutional Classifiers (2025, applied to jailbreak defense). The core RLAIF idea has been extended beyond harmlessness training into classifier systems that defend against universal jailbreaks.

The model spec is now a living document Anthropic explicitly calls a "perpetual work in progress."

## Key Papers / Posts

- [[anthropic-constitutional-ai-research]] — original research page (Dec 2022); arXiv 2212.08073
- [[anthropic-claudes-constitution]] — the actual constitution document (CC0, public)

## Related Concepts

- [[agi]] — what CAI-trained models are ultimately meant to be safe predecessors of
- [[world-models]] — LeCun's alternative alignment philosophy (very different approach)
- [[training-data-quality]] — orthogonal lever: CAI addresses values, data quality addresses capability
