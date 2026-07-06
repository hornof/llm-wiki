---
name: Jailbreak Severity Framework
type: concept
maturity: emerging
last_updated: 2026-07-06
---

## Definition

A **consensus, cross-vendor standard for scoring the severity of LLM jailbreaks**, so that different labs and government partners can rank and triage findings on the same scale instead of each guessing which vulnerabilities matter most. Introduced by [[anthropic|Anthropic]] with Amazon, Microsoft, Google, and other Project Glasswing participants alongside the [[claude-fable-5|Fable 5 redeployment]]. See [[anthropic-redeploying-fable-5-jailbreak-severity-framework-2026-06-30]].

## Why It Matters

Standardized severity scoring is a governance primitive: once adversarial robustness is *measured the same way across vendors*, you can actually compare models and coordinate responses, rather than arguing over whether a given jailbreak is "serious" (exactly the dispute that drove the [[claude-fable-5|Amazon/Jassy export-control saga]]). For anyone running safety evals at a startup, it's a ready-made rubric for prioritizing red-team findings.

## Current State

Four measurement criteria:

1. **Capability Gain** — does the jailbreak exceed what existing tools already enable?
2. **Breadth of Capability Gain** — how many distinct offensive tasks does it unlock?
3. **Ease of Weaponization** — human effort required to deploy it operationally.
4. **Discoverability** — how publicly accessible the technique is.

Rationale (Anthropic): "developers have no agreed-upon standard for which findings to focus on most urgently." Early-stage multi-vendor standard — adoption breadth and whether it becomes a real shared scoring surface (vs. a one-off announcement) is the thing to watch.

## Key Papers / Posts

- [[anthropic-redeploying-fable-5-jailbreak-severity-framework-2026-06-30]] — the announcement (framework + Fable 5 redeployment).

## Related Concepts

- [[mechanistic-interpretability]] — internal-state monitoring as a complementary safety surface.
- [[claude-fable-5]] — the model whose jailbreak dispute motivated the framework.
