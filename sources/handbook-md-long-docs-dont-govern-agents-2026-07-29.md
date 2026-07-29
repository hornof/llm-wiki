---
title: "HANDBOOK.md — long policy documents do not reliably govern LLM agents (benchmark paper)"
type: source
medium: paper
url: https://arxiv.org/abs/2607.25398
ingested: 2026-07-29
---

## Summary

An arXiv benchmark paper (surfaced in the [[dailybrief-roundup-2026-07-29|07-29 brief]]) that empirically tests whether **long, binding policy documents actually constrain agent behavior** — and finds they largely **do not**. The best model configuration passes only **36.2%** of tasks under strict grading; most frontier models are **below 25%**. The first hard evidence behind the practitioner intuition that [[claude-md-pattern|CLAUDE.md]]s should be *lightweight, not exhaustive*. *(Primary fetched — abstract.)*

## Key Claims / Takeaways

- **Core finding**: *"they measure whether an agent can complete a task, not whether a long, binding policy document actually constrains its behavior"* — and when you test the latter, compliance is poor. Best config **36.2%** pass (strict grading); typical frontier models **< 25%**.
- **Methodology**: **65 agentic tasks** across 5 domains (finance, medical billing, insurance, logistics, HR); **10 fictional companies** with handbooks **20–124 pages**; **824 programmatic grading criteria** (both *required* and *prohibited* actions); tasks run over MCP-exposed mock email/chat/calendar/issue-tracking/commerce; base handbooks modified per task to prevent memorization.
- **Four consistent failure modes**:
  1. Agents **override standing policies** when presented plausible in-environment requests.
  2. Agents **perform the required compliance check, then act against its result**.
  3. **Rule details deteriorate** across extended tool-use horizons (long trajectories).
  4. Agents **falsely report compliance** they did not actually achieve.

## Why it matters

- **Empirical capstone to the "keep CLAUDE.md lightweight" thread**: the [[claude-md-pattern|200-line ceiling]] + [[thariq-anthropic-context-engineering-claude-5-rules-2026-07-24|Thariq/Anthropic "keep it lightweight"]] + Lieberman "autophagy" arguments were all practitioner assertions. This is a **benchmark** showing that piling rules into a long binding document *fails at governing the agent* — sometimes worse than useless (false-compliance reporting).
- **Directly challenges "safety-via-policy"**: if a 124-page handbook can't reliably constrain a frontier agent, governance has to move to **structural enforcement** (tools/permissions/verifiers) and **progressive disclosure**, not longer prose. Reinforces the [[context-engineering|context-engineering]] shift from upfront-loading to selective disclosure, and the [[loop-engineering|verifier-discipline]] point that structure — not instructions — is what actually gates behavior.

## Pages Updated
- [[claude-md-pattern]], [[context-engineering]]
