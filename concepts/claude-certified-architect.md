---
name: Claude Certified Architect
type: concept
maturity: emerging
last_updated: 2026-04-30
---

## Definition

**Claude Certified Architect, Foundations** is Anthropic's first official technical certification, launched March 12, 2026 alongside the [[anthropic|Claude Partner Network]]. It is a proctored exam targeting solution architects building production applications with Claude. Access is gated through `anthropic.skilljar.com/claude-certified-architect-foundations-access-request`. Anthropic announced additional certifications for "sellers, architects, and developers" coming later in 2026 — Foundations is the entry point of a multi-track program.

## Why It Matters

The Foundations cert codifies what Anthropic considers the production-grade competencies for building Claude applications. The published domain weights are a leading indicator of where Anthropic believes the practitioner skill gap is — and a forcing function for organizations building on Claude to standardize on patterns Anthropic endorses. For an AI engineer, the exam blueprint doubles as a curriculum for the technical surface Anthropic is committing to long-term: agentic orchestration, MCP-based tool design, [[claude-code]] workflows, structured-output prompt engineering, and context/reliability discipline.

## Current State

### Anthropic-confirmed (primary source)
- Launched 2026-03-12 — [[anthropic-claude-partner-network]]
- Anthropic's *first* technical certification
- Target audience: solution architects building production Claude applications
- Proctored exam (format details not in primary source)
- Available immediately to members of the Claude Partner Network (free to join)

### Third-party-reported (secondary, circulating widely March–April 2026)
- 60-question exam, proctored
- Five weighted domains:
  - **Agentic Architecture & Orchestration** — 27%
  - **Claude Code Configuration & Workflows** — 20%
  - **Prompt Engineering & Structured Output** — 20%
  - **Tool Design & MCP Integration** — 18%
  - **Context Management & Reliability** — 15%
- Reported by multiple independent third-party guides (Medium "Reliable Data Engineering" March 2026; lowcode.agency; FlashGenius; dev.to community; the-ai-corner.com; claudecertifications.com). The structural numbers were *not* extracted from the Anthropic news page; treat them as well-corroborated practitioner consensus rather than primary-source-confirmed.
- Practitioner study roadmaps appearing on X within ~6 weeks of launch — [[elora-khatun-claude-certified-architect-roadmap]]

### Implications by domain weight (if the third-party numbers are accurate)
- **Agentic Architecture & Orchestration at 27%** is the largest single domain — confirms Anthropic's positioning around [[agentic-engineering]] (Karpathy's framing) and [[agentic-ai]] as the central skill.
- **Claude Code at 20%** elevates the CLI from "one of several tools" to a core competency for production engineers — consistent with Karpathy citing Claude Code as the LLM agent layer for the [[llm-wiki-pattern]].
- **MCP at 18%** confirms [[mcp]] as production infrastructure, not just an experiment.
- **Context Management at 15%** as a *named domain* is notable — the field has converged on context discipline (token budgets, hot caches, progressive disclosure) as a first-class engineering concern.

## Key Papers / Posts

- [[anthropic-claude-partner-network]] — primary Anthropic source (announcement, March 2026)
- [[elora-khatun-claude-certified-architect-roadmap]] — secondary practitioner X post (April 2026); 6-week study roadmap

## Related Concepts

- [[mcp]] — domain of the exam (Tool Design & MCP Integration, 18% per third-party reports)
- [[claude-code]] — domain of the exam (Claude Code Configuration & Workflows, 20%)
- [[agentic-ai]] — broader topic; cert's largest domain (Agentic Architecture & Orchestration, 27%) sits within
- [[agentic-engineering]] — Karpathy's framing of the production-quality discipline the cert is essentially codifying
- [[anthropic]] — issuing organization
