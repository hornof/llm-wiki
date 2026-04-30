---
name: Agentic Engineering
type: concept
maturity: emerging
last_updated: 2026-04-29

---

## Definition
Karpathy's term for the professional engineering discipline of coordinating AI agents to ship production-quality software without sacrificing the quality bar that existed before AI coding tools.

> "Agentic engineering is about preserving the quality bar of what existed before in professional software. You're not allowed to introduce vulnerabilities due to vibe coding. You are still responsible for your software just as before, but can you go faster?" — Andrej Karpathy, AI Ascent 2026

> "You have these agents which are these like spiky entities. They're a bit fallible, a little bit stochastic, but they are extremely powerful. [Agentic engineering is] how do you coordinate them to go faster without sacrificing your quality bar." — Andrej Karpathy, AI Ascent 2026

## Why It Matters
Karpathy asserts the speedup from skilled agentic engineering is well beyond 10x — "people who are very good at this peak a lot more than 10x from my perspective right now." This is not a marginal productivity improvement; it is a capability transformation for engineers who master it.

## Core Responsibilities of the Agentic Engineer
1. **Spec and design authority**: the engineer owns the system design, not the agent. Example: insisting on a persistent unique user ID rather than letting the agent cross-correlate by email address.
2. **Taste and aesthetics**: agent-generated code is often "bloaty," with copy-paste and brittle abstractions. The engineer identifies and demands better.
3. **Oversight**: agents are "intern entities" — remarkable capability, but still require a human who understands what correct looks like.
4. **Conceptual understanding**: knowing *what* the code is supposed to do — e.g., understanding that a tensor has an underlying view and separate storage — even if you've forgotten the exact API details (dim vs. axis, reshape vs. permute).

## What the Agent Handles
- API-level details (exact library signatures, parameter names)
- Boilerplate and fill-in-the-blanks implementation
- Multi-step execution within a well-specified plan

## Agents as Interns
Karpathy uses the "intern" metaphor: agents have exceptional recall and can execute at high speed, but they make category errors on common sense (e.g., cross-correlating user identity via email across systems). The engineer must maintain the big picture.

## Hiring Implications
Traditional interview formats (puzzles, leetcode) are the old paradigm. Karpathy's proposed new interview format:
- Give a large project (e.g., "build a Twitter clone")
- Make it really good, really secure
- Simulate real traffic with agents
- Use an adversarial agent (e.g., "10 Codex 5.4x agents try to break your deployment")
- Evaluate: did the system hold?

## Relationship to Vibe Coding
See [[vibe-coding]]. Vibe coding raises the floor; agentic engineering raises the ceiling. Both are legitimate — they serve different purposes and audiences.

## Tools in This Space
- [[claude-code]] — Karpathy specifically cites "Claude Code or Codex" as the layer where agentic engineering happens
- Codex (OpenAI) — mentioned alongside Claude Code as a primary agentic engineering interface

## Related Concepts
- [[vibe-coding]] — the floor-raising complement; entry-level
- [[software-3-0]] — the broader paradigm; agentic engineering is the professional manifestation
- [[verifiability-and-jagged-intelligence]] — explains which domains benefit most from agentic approaches
- [[agentic-ai]] — the broader topic page covering multi-agent patterns, protocols, and tools

## Solo Operator Vision (Naval's Reinforcement)

Naval Ravikant (April 2026) articulates the same capability from an investor/founder perspective: a 1-person company operating at the velocity of a 50-person team via agents. Users report bugs → agent reviews → agent writes fixes, opens PRs, runs tests → founder reviews and ships. No coordination overhead, no political compromise, no vision diluted by committee. This is the market-facing consequence of agentic engineering applied to product companies. See [[saas-disruption-thesis]] and [[naval-ravikant-saas-is-next]].

## The Missing "Why" Layer (Chamath, April 2026)

Chamath Palihapitiya identifies a team-level gap that individual agent speed gains don't solve: architectural reasoning (the "why" behind decisions) typically lives in Slack threads, Linear tickets, or individual heads. Individual engineers can go faster with AI, but team collective knowledge doesn't compound — so the team goes the same speed or slower. The implication for agentic engineering: agents need access to decision context, not just code. A good multiplayer AI dev experience must capture the reasoning layer, not only accelerate the execution layer. — [[chamath-decision-context-agents]]

## Resources
- [[karpathy-vibe-coding-agentic-engineering]] — PRIMARY SOURCE: Karpathy introduces and distinguishes this framing at AI Ascent 2026
- [[naval-ravikant-saas-is-next]] — Naval's investor framing of the solo-operator outcome; "pure software is uninvestable"
- [[chamath-decision-context-agents]] — Chamath on decision-context capture as the missing layer for team AI leverage
