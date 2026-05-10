---
name: Constitutional AI
type: concept
maturity: foundational
last_updated: 2026-05-09
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

## Evolution: Teaching Claude Why (May 2026)

[[anthropic-teaching-claude-why-2026-05-08]] documents an evolution of the constitutional-training methodology: training on examples where the assistant *reasons through* the aligned choice, not just demonstrates the aligned action. Three sub-methods extending the 2022 CAI base:

- **Difficult Advice dataset** — 3M tokens, highly out-of-distribution scenarios where the assistant provides principled guidance with reasoning shown. **28× more sample-efficient** than in-distribution honeypot training; generalizes better.
- **Constitutional-document training plus fictional aligned-AI stories** — drove honeypot misalignment from **65% → 19%**.
- **Diverse environment mixing** — varied system prompts and tool definitions inside safety training so the alignment signal isn't tied to one environment shape.

Result: all Claude models from **Haiku 4.5 onward score 0–<1%** on honeypot self-preservation evaluations (vs. up to 96% for Claude 4). **Improvements persisted through subsequent RL phases** — i.e., reasoning-based alignment didn't get scrubbed by next-stage training, which is the typical failure mode for alignment interventions.

Pairs with [[anthropic-natural-language-autoencoders-2026-05]]: Teaching Claude Why trains reasoning *in*; NLAs read it *out* for audit. Two halves of "make model reasoning explicit and inspectable."

## Key Papers / Posts

- [[anthropic-constitutional-ai-research]] — original research page (Dec 2022); arXiv 2212.08073
- [[anthropic-claudes-constitution]] — the actual constitution document (CC0, public)
- [[anthropic-teaching-claude-why-2026-05-08]] — alignment-by-reasoning evolution of the CAI methodology (May 2026)

## Related Concepts

- [[agi]] — what CAI-trained models are ultimately meant to be safe predecessors of
- [[world-models]] — LeCun's alternative alignment philosophy (very different approach)
- [[training-data-quality]] — orthogonal lever: CAI addresses values, data quality addresses capability
