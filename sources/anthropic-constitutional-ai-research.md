---
title: "Constitutional AI: Harmlessness from AI Feedback"
type: source
medium: article
url: https://www.anthropic.com/research/constitutional-ai-harmlessness-from-ai-feedback
ingested: 2026-04-24
published: 2022-12-15
---

## Summary

Anthropic's December 2022 research page introducing Constitutional AI (CAI) — a methodology for training AI systems to be helpful and harmless using a written "constitution" of principles and AI-generated feedback, requiring significantly fewer human labels than traditional RLHF.

## Key Claims / Takeaways

- Constitutional AI replaces human harmlessness labels with AI-generated critiques and revisions (RLAIF — Reinforcement Learning from AI Feedback)
- Two-phase training: (1) SL phase — model samples outputs, self-critiques against the constitution, and revises; (2) RL phase — AI evaluations train a reward model used for RL
- Produces a "harmless but non-evasive" assistant that explains objections to harmful queries rather than refusing outright
- Chain-of-thought reasoning incorporated for transparency
- Accompanies the original paper (arXiv 2212.08073)

## Pages Updated

- [[constitutional-ai]] (new)
- [[anthropic]] (new)
