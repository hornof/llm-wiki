---
name: Global Workspace (in language models)
type: concept
maturity: active-research
last_updated: 2026-07-06
---

## Definition

A "global workspace" in a language model is a small set of internal neural patterns that a subset of the model's computation reads from and writes to, functioning like a shared blackboard for deliberate reasoning. In Anthropic's 2026 interpretability work the model-internal version is called **J-space**, and it exhibits *access consciousness* properties — its contents are reportable, controllable, and causally drive multi-step reasoning — while the bulk of the model's processing (grammar, simple recall) runs automatically and bypasses it. The name borrows from Global Workspace Theory in cognitive science. See [[anthropic-global-workspace-language-models-2026-07-06]].

## Why It Matters

It reframes attention as an **information bottleneck** rather than an opaque mechanism: only a few dozen concepts occupy the workspace at once (<10% of total neural activity), yet they're what complex reasoning routes through. For an AI engineer this is a practical observability handle — hidden intermediate reasoning (e.g. steps of a multi-step math problem that never appear in output tokens) shows up in the workspace, and safety-relevant internal state (the model privately flagging a scenario as "fake" or detecting manipulation) is legible there too. It gives a mechanistic story for *why context matters and what actually flows through it*.

## Current State

- **Method — J-lens (Jacobian lens)**: maps each vocabulary word to the internal activity pattern that makes the model more likely to emit it, letting researchers "read" silent intermediate thoughts across layers.
- **Five claimed properties**: reportability, controllability, causal role (swapping a pattern changes output — "Soccer"→"Rugby"), flexible reuse, and selective involvement (automatic processing bypasses it).
- **System-1 / System-2 analogue**: continuing a Spanish passage is unaffected by swapping the "Spanish" pattern (automatic), but naming or reasoning about the language routes through the workspace.
- Anthropic claims evidence for **access** consciousness, explicitly *not* **phenomenal** (subjective experience). This is a single-lab interpretability result, not yet independently replicated — treat as active research, not settled fact.

## Key Papers / Posts

- [[anthropic-global-workspace-language-models-2026-07-06]] — Anthropic, "A global workspace in language models" (the primary source; J-space, J-lens, five properties).

## Related Concepts

- [[mechanistic-interpretability]] — the parent research program this sits inside.
- [[world-models]] — adjacent internal-representation research.
