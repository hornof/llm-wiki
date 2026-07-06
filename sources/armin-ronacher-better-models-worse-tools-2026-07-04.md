---
title: "Better Models: Worse Tools"
type: source
medium: article
url: https://simonwillison.net/2026/Jul/4/better-models-worse-tools/
ingested: 2026-07-06
---

## Summary

[[armin-ronacher|Armin Ronacher]] documents a counterintuitive regression: newer Claude models ([[claude-opus-4-8|Opus 4.8]], [[claude-sonnet-5|Sonnet 5]]) are *worse* than their predecessors at calling a specific third-party edit-tool schema — they invent fields that don't exist in the schema, which causes the harness to reject the tool call even though the underlying edit is correct. Surfaced (via [[simon-willison|Willison]]) in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]].

## Key Claims / Takeaways

- **The failure**: calling Pi's edit tool, the models add fabricated fields to the `edits[]` array that don't match the schema. The edits themselves are often right, but the invented parameters make the harness reject the whole call.
- **The paradox**: it gets *worse* with newer models — "the SOTA models of the family are worse at this specific tool schema than their older siblings."
- **Proposed mechanism**: Anthropic likely used RL to make recent models excel at [[claude-code|Claude Code]]'s *built-in* search-and-replace edit tool. That specialization made them worse at *alternative* schemas from third-party harnesses. A capability-alignment gap — the model knows the edit it wants, but not the interface contract of a non-native tool.
- **Infrastructure dilemma**: should harnesses like Pi ship multiple edit-tool variants and route each model to whichever schema it handles best? Tension between per-vendor model optimization and cross-tool interoperability.

## Owner's angle (from brief)

> "Opus hallucinates schema fields it's never seen — invents args, then executes anyway because the edit itself is right. Classic capability-alignment gap: the model knows what it wants to do, but not the interface contract. Matters for tool-use at scale."

## Why it matters

Concrete, reproducible friction for anyone building agent/tool-use infrastructure on top of Anthropic models: training a model hard on one native tool schema can *degrade* generalization to others. A caution against assuming "newer model = strictly better integration." Feeds [[claude-opus-4-8]] weaknesses and the broader tool-use reliability theme.

## Pages Updated

- [[armin-ronacher]] (new)
- [[claude-opus-4-8]] (updated — tool-schema hallucination friction)
- [[dailybrief-roundup-2026-07-06]]
