---
name: Agentic AI
type: topic
last_updated: 2026-05-15
---

## What It Is
The paradigm of LLMs that take actions autonomously — calling tools, making decisions, executing multi-step plans — rather than just generating text responses. An "agent" is an LLM in a loop: perceive → think → act → observe → repeat.

Karpathy's framing (AI Ascent 2026): agents are "sensors and actuators over the world" — decompose workloads into sensing the environment and acting on it. Everything must be "decomposed into fundamentally sensors over the world, actuators over the world" to become agent-native. — [[karpathy-vibe-coding-agentic-engineering]]

## Why It Matters for AI Engineering
Agents are the current frontier of applied AI engineering. Moving from "LLM as a smart autocomplete" to "LLM as an autonomous worker" unlocks entirely new application categories but introduces new engineering challenges around reliability, observability, and safety.

## Key Patterns
- **Tool use**: LLM calls external functions (search, code execution, APIs)
- **ReAct**: Reasoning + Acting — LLM interleaves thinking steps with tool calls
- **Multi-agent**: multiple specialized agents collaborate, delegate, or check each other's work
- **Human-in-the-loop**: agent pauses for human approval at key decision points

## Recurring Cognitive Decomposition

Across academic surveys, framework documentation, and Packt's *30 Agents* book ([[30-agents-every-ai-engineer-must-build]] by [[imran-ahmad]]), the same five-capability decomposition shows up as the foundational core of any production agent:

| Capability | What it does |
| --- | --- |
| Perception | Reads inputs from the environment (user prompt, tool output, retrieved docs, sensor data) |
| Memory | Holds short-term working state and longer-term context across runs ([[mem0]], [[company-brain]] at organizational scale, CLAUDE.md at personal scale — [[seelffff-personal-ai-agent]]) |
| Reasoning | Plans, evaluates, decides next action |
| Planning | Decomposes goals into action sequences; backtracks on failure |
| Learning | Updates from feedback loops (rare in current production; mostly research) |

This decomposition is the lens to use when reading any new agent-architecture proposal — most "novel" patterns are recombinations of these five capabilities with different scaffolding around memory, planning, or tool integration.

## Key Protocols
- **MCP (Model Context Protocol)**: Anthropic's open standard for connecting LLMs to tools and data sources — [[mcp]] (see also [[claude-code]] for practical gotchas)
- **A2A (Agent-to-Agent)**: protocol for agents to communicate with each other [unsourced — needs ingestion]
- **OpenAI Agents SDK**: OpenAI's framework for building agents [unsourced — needs ingestion]

## Tools in This Space
- [[crewai]] — multi-agent role-playing framework
- [[langchain]] — agent engineering platform (LangGraph for stateful agents)
- [[llama-index]] — document agents and RAG
- [[claude-code]] — agentic coding tool

## Concepts in This Space
- [[agentic-engineering]] — Karpathy's term for the professional discipline of coordinating agents for production-quality software; >10x speedup; engineers remain responsible for taste, design, and oversight
- [[vibe-coding]] — Karpathy's term for the floor-raising counterpart; anyone can build anything; quality bar is lower
- [[software-3-0]] — the paradigm shift from writing code to prompting agents; agents are intelligent interpreters of context
- [[company-brain]] — the **memory substrate** layer beneath agentic systems at organizational scale; per [[ashwingop]], agents fail not because companies lack data but because they lack memory of *why* the data means what it means
- [[ai-native-organizations]] — org-design counterpart to the company-brain memory substrate (Block / Jack Dorsey)

## Two Scales of the Same Pattern (April 2026)

A recurring observation across recent ingests: the same **factual-memory + reasoning + action** structure shows up at two scales.

| Scale | Source | Memory layer | Action layer |
| --- | --- | --- | --- |
| Organizational | [[company-brain]] / [[sentra]] / [[ashwingop]] | Communication channels, KBs, agent traces; semantic file system | Drafts follow-ups, creates tickets, warns of cross-team drift, governs agent action |
| Personal | [[seelffff-personal-ai-agent]] / [[personal-ai-agent-claude-desktop-mcp]] | `CLAUDE.md` + `context.md` + `tasks.md` + `notes.md` | Browses real sites, updates files, pushes Telegram notifications |

Both insist that the agent must *read context before acting* and that **memory must participate** rather than wait to be queried.

## Agent-as-Customer Pattern (May 2026)

A new primitive surfaced May 6 2026: [[cloudflare]] and Stripe co-launched **Stripe Projects**, a protocol that lets agents *autonomously create accounts, purchase domains, and deploy apps* under Stripe-attested identity and pre-set spending budgets. Agents can now be economic actors, not just labor: discover services via `stripe projects catalog`, authenticate via Stripe-orchestrated OAuth, and pay via tokenized cards with default $100/month per-provider caps.

This is a step beyond "agent uses tools" — it is "agent buys SaaS." Distinct primitives required: identity attestation, payment tokenization, budget guardrails, MCP-driven service catalogs ([[mcp]]), human approval gates for critical actions. — [[cloudflare-stripe-projects-agents-2026-05]]

Strategic read: this is the protocol-level answer to the [[saas-disruption-thesis]] question of *how agents purchase software*. If agents become buyers, infrastructure providers either co-define the agent-purchase primitives (as Cloudflare and Stripe just did) or get disintermediated by whoever does.

## Multi-Agent Orchestration Patterns (May 2026)

Practitioner-content piece [[eng-khairallah-multi-agent-team-course-2026-05-15]] surfaces three production-validated multi-agent patterns layered on top of [[willison-code-w-claude-2026|Anthropic's May 6 Multi-agent Orchestration]] release (up to **20 specialized agents in parallel per task**):

| Pattern | Shape | Production example |
|---|---|---|
| **Pipeline** | Sequential pass-through: Agent A → Agent B → Agent C | Research → Analysis → Writing → Review |
| **Fan-Out** | Commander dispatches subtasks to parallel workers, results synthesized | Netflix analyzing hundreds of build logs simultaneously |
| **Specialist Team** | Multiple specialists collaborate on a single complex task | Harvey legal-work coordination |

**Customer convergence**: [[shopify]] and Mercado Libre have both publicly named **90% autonomous coding by Q3 2026** as their target. Two enterprise customers naming the same threshold on the same timeline is the cleanest cross-confirmation captured to date.

**Architectural / discipline contributions** from the same source:
- *"Standardize your output formats across agents. This is the most important technical decision you will make."* — data-contract framing for inter-agent handoffs.
- *Start-simple*: two-agent pipeline first; add agents incrementally; "complexity is the enemy of shipping" (moltoffer echo from [[meenakshiyacs-agentic-ai-architecture-cheat-sheet-2026-05-14]]).
- Named multi-agent **failure modes**: handoff failures, redundant work, quality degradation under pipeline length, token bloat.

**Outstanding claims pending primary verification** (from [[eng-khairallah-multi-agent-team-course-2026-05-15]], not yet in any Anthropic primary):
- *Harvey reports enabling Dreaming on legal agents increased completion rates approximately 6×.* If verified, this is the most concrete production-impact metric for a post-deployment-learning feature surfaced this year.
- *Apple announced Claude integration into iOS 27 alongside other AI services through a new Extensions system.* If true, the first frontier-lab × major-mobile-OS deep integration; do not propagate to entity pages until verified.

### Architecture cheat-sheet (Meenakshi taxonomy)

A second taxonomy circulated [[meenakshiyacs-agentic-ai-architecture-cheat-sheet-2026-05-14|the same week]] frames the agentic-AI stack as 7 layers: Orchestration → Agents → Tools → Memory → Monitoring → Reliability & Failure → Governance & Security. **Notable variant** from the comment thread: Taylor Wigton's *"Final Checkpoint at the action boundary"* as a missing 8th layer — the moment before an agent takes a high-consequence external action. Pairs with [[willison-andon-cafe-stockholm-2026-05|Willison's consent-ethics critique]] (human oversight on every outbound action with external impact).

## Resources
- [[github-hornof-profile]] — wiki owner is actively tracking crewAI, learn-agentic-ai, OpenAI Agents SDK
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy at AI Ascent 2026; sensors/actuators framing, agent-native infrastructure, agentic engineering as discipline
- [[ashwingop-company-brain-part-1]] — Company Brain thesis Part 1 (memory substrate underneath agentic AI)
- [[ashwingop-company-brain-part-2]] — Company Brain Part 2 (factual memory ≠ RAG; semantic file system; memory participates)
- [[seelffff-personal-ai-agent]] — personal-scale agent stack on Claude Desktop + MCP
- [[30-agents-every-ai-engineer-must-build]] — Packt book by [[imran-ahmad]] structuring agent engineering as a 30-pattern catalog (listing-only ingest)
- [[cloudflare-stripe-projects-agents-2026-05]] — Cloudflare + Stripe co-launch agent-as-customer protocol primitives (May 2026)
- [[eng-khairallah-multi-agent-team-course-2026-05-15]] — practitioner-content piece on Pipeline / Fan-Out / Specialist Team multi-agent patterns; Netflix / Harvey / Shopify production customers (May 15 2026)
- [[meenakshiyacs-agentic-ai-architecture-cheat-sheet-2026-05-14]] — 7-layer agentic-AI architecture cheat sheet; Wigton's "Final Checkpoint at the action boundary" variant in the comment thread (May 14 2026)
