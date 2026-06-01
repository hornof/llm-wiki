---
name: Autoresearch
type: concept
maturity: emerging
last_updated: 2026-06-01
---

## Definition

**Autoresearch** is an autonomous iterative research-loop pattern: an agent (or coordinated agents) takes a topic, runs web searches, fetches and reads sources, synthesizes findings, and files structured outputs into a knowledge base — running until a depth-criterion or budget is reached, with minimal per-iteration human steering. Named and popularized by [[andrej-karpathy|Andrej Karpathy]] as an operator-facing application of the [[llm-wiki-pattern|LLM Wiki pattern]] — *"program.md configures objectives and constraints, the loop runs until depth is reached, output goes directly into the knowledge base."*

## Why It Matters

- **Productizes the iterative-research workflow** that practitioners had been hand-running across many tabs / many prompts. Autoresearch collapses the multi-step manual loop into a single configured invocation.
- **Pairs structurally with the [[llm-wiki-pattern|LLM Wiki pattern]]** as the *automated-ingestion* arm — the wiki is the *compilation-time knowledge base*; autoresearch is the *agent-driven population mechanism* for it.
- **Cross-cuts with [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows]]**: a Dynamic Workflow with `/deep-research` is the vendor-side productization of the autoresearch pattern. See [[nateherk-dynamic-workflows-2026-05-30|Nate Herk's framing]] of `/deep-research` as *"a workflow + agent-vote-on-each-claim + cited-research-report"* — same shape as Karpathy's autoresearch program.md.

## Current State (May-June 2026)

### Wiki implementation

This wiki ships an **`autoresearch` skill** in the `claude-obsidian` plugin (`autoresearch.md`) that implements the pattern:

- `program.md` configures objectives + depth + constraints
- The skill iterates: search → fetch → defuddle → synthesize → file
- Each iteration yields wiki pages (sources + entity updates + concept extractions)
- Termination on depth-reached or budget-reached

### Vendor-side productization

- **[[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows + `/deep-research`]]** (May 28-30 2026) — the wiki-canonical vendor-side equivalent. *"Automatically kicks off a workflow, spins up agents to research in parallel, has them vote on each claim, and hands back a cited research report"* (Nate Herk framing).
- **`mims-harvard/AutoScientists`** (GitHub; surfaced via [[dailybrief-roundup-2026-05-30]]) — research-side adjacent: decentralized AI agent teams using Claude Code subagents coordinated via local ClawInstitute server for long-running scientific tasks (e.g., nanoGPT optimization).

### Adjacent patterns

- **DeepMind LLM-Lean** ([[deepmind-llm-lean-erdos-oeis-2026-05-25]]) — autoresearch loop for math: agent loop resolving open Erdős problems at *"few hundred dollars per proof."* Same shape, narrower domain.
- **DeepMind Co-Scientist + AlphaEvolve** — autoresearch for science / hypothesis generation.

## Related Concepts

- [[llm-wiki-pattern]] — the knowledge-base substrate autoresearch populates
- [[agentic-engineering]] — capability stack that makes autoresearch operationally tractable
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — vendor-side equivalent of the pattern
- [[ai-for-science]] — applied autoresearch in pure-science domains

## Resources

- [[karpathy-llm-wiki-overview]] — Karpathy's autoresearch framing as part of the broader LLM Wiki pattern
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — `/deep-research` Claude Code slash command (vendor-side)
- [[nateherk-dynamic-workflows-2026-05-30]] — practitioner walkthrough of `/deep-research` use
- [[deepmind-llm-lean-erdos-oeis-2026-05-25]] — math-domain autoresearch instantiation
