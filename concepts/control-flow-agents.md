---
name: Control Flow for Agents
type: concept
maturity: emerging
last_updated: 2026-05-07
---

## Definition

A counter-position to **prompt-engineering-as-panacea**: the claim that reliable agents tackling complex tasks need **deterministic control flow encoded in software** — explicit state transitions, validation checkpoints, modular composition — rather than increasingly elaborate prompt chains. The LLM is treated as a *component* of a larger software system, not as the system itself.

> "Reliable agents tackling complex tasks need deterministic control flow encoded in software, not increasingly elaborate prompt chains." — Brian (bsuh.bearblog.dev), May 2026 — [[bsuh-agents-need-control-flow-2026-05]]

## Why It Matters

The dominant practitioner pattern in May 2026 is **better prompts and better skills**: the [[zodchiii-anatomy-perfect-skill]] 6-pattern framework, the eight-senior-prompts pattern in [[aina-ai2-eight-senior-prompts]], the CLAUDE.md voice-context patterns in [[alfiejcarter-linkedin-claude-stack]]. The control-flow position pushes back: prompts are "non-deterministic, weakly specified, and difficult to verify" — adding more imperative language ("MANDATORY", "DO NOT SKIP") doesn't change those properties, only obscures them.

The diagnostic signal: when your prompts include capitalized imperatives, you've hit prompting's limit. The fact that this works at all is fragile and degrades silently as agents take on more state.

## Current State

Counter-positioning voice in the practitioner conversation; not yet a dominant pattern. Relevant adjacent positions:

- **Zohar Einy's organizational harness** ([[benln-x-karpathy-agentic-engineering-2026-05]]) — agents need governance/orchestration/measurement layers around them. The control-flow argument extends this from organizational scale to per-agent architectural scale.
- **Karpathy's spec-first framing** ([[agentic-engineering]]) — the spec is what enables deterministic structure; prompts implement details inside it. Spec-first is upstream of control-flow-first.
- **Cheng & Zhang's localization gap** ([[cheng-zhang-distributed-icl-2026-05]]) — if model behavior cannot be cleanly localized, building reliability via prompt-tuning becomes harder still; control flow side-steps the problem by not relying on the model to enforce structure.

## What This Argument Does Not Provide

The Brian / bsuh post is conceptual — no code patterns or framework recommendations. The argument is a stake-in-the-ground rather than an implementation guide. Watch for follow-up posts and any framework consolidation around this idea.

## Related Concepts

- [[agentic-engineering]] — the broader engineering discipline; control flow is one (under-emphasized) tool inside it
- [[verifiability-and-jagged-intelligence]] — control flow improves verifiability by making agent behavior observable in code-flow terms
- [[mcp]] — MCP is one place control flow naturally lives; the protocol gates what an agent can touch

## Key Papers / Posts

- [[bsuh-agents-need-control-flow-2026-05]] — primary source: Brian's "Agents need control flow, not more prompts" (May 2026)
