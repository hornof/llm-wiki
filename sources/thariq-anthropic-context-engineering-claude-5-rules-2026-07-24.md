---
title: "Thariq Shihipar (Anthropic) — 'The new rules of context engineering for Claude 5 generation models': removed >80% of Claude Code's system prompt with no eval loss; judgment over rules (2026-07-24)"
type: source
medium: vendor-announcement
url: https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models
ingested: 2026-07-26
---

## Summary

[[thariq-shihipar|Thariq Shihipar]] (Anthropic) publishes the official **"new rules of context engineering for Claude 5 generation models"** (2026-07-24). The headline result: *"We removed over 80% of Claude Code's system prompt for models like Claude Opus 5 and Claude Fable 5 with no measurable loss on our coding evaluations."* The thesis: newer models need **less constraint, more judgment, and progressive disclosure** — a strategy shift that updates both [[context-engineering]] and the [[claude-md-pattern|CLAUDE.md]] exhaustive-rules lineage. *(Primary fetched.)*

## Key Claims / Takeaways

### The six "Then → Now" shifts
1. **Rules → Judgment**: replace explicit rules with principles; *"Claude can interpret the user's intent"* — delete constraints, trust judgment. (Conflicting/overlapping instructions make Claude *"think more carefully… before deciding what to do."*)
2. **Examples → Interface design**: stop providing usage examples — *"think more about the design of your tools, scripts and files—what parameters does Claude have and how can they be more expressive?"* (enumerations/parameters hint behavior).
3. **Upfront loading → Progressive disclosure**: selective context + **deferred tool definitions** (some tools require **ToolSearch** before use, preserving the context window).
4. **Repetition → Concise descriptions**: put tool instructions *in the tool description*, not repeated in the system prompt.
5. **CLAUDE.md memory → Auto-memory**: rely on automatic memory saving over manual documentation.
6. **Simple specs → Rich references**: use code, test suites, HTML artifacts, and rubrics as detailed references; *"write code that reads like the surrounding code."*

### Concrete guidance
- **CLAUDE.md kept lightweight** — gotchas, not obvious knowledge; progressive disclosure via skills. *"A common myth is that you want to make these a central repository for every known practice… because Claude would not find it otherwise."* (Directly tempers the exhaustive-rules framing.)
- **Skills**: lightweight guides; split long ones across files; encode team/product-specific opinions; avoid overconstraining.
- **References**: `@mention` files (specs, mockups, codebases); prefer **code over descriptions**.
- **`claude doctor`**: new command to help simplify skills + CLAUDE.md automatically.

### Prompting is NOT dead
The post explicitly does **not** say context replaces prompting — they're complementary: **prompts** are specific/task-focused; **context** (system prompt, skills, CLAUDE.md, memory, references) is general/reusable. *"Context engineering matters more than ever, but the strategy has changed."*

## Why it matters

- **Vendor-canonical update to [[context-engineering]]** — from a practitioner-synthesis concept ([[noisyb0y1-context-engineering-8x-2026-07-04]]) to Anthropic's own strategy for the new model generation.
- **Material tension with the [[claude-md-pattern|CLAUDE.md exhaustive-rules lineage]]**: the Karpathy→Mnilax arc optimized *which rules to add*; this says *delete most of them and trust judgment* on Claude 5 models — the "immune system / autophagy" framing ([[alex-lieberman-ai-engineering-best-practices-2026-07-09|Lieberman]]) now has Anthropic-official backing, plus a tool (`claude doctor`).
- **Thariq's 6th surface** — his authored (not just amplified) vendor-canonical context/harness voice.

## Pages Updated
- [[context-engineering]], [[claude-md-pattern]], [[thariq-shihipar]]
