---
name: Agentic AI
type: topic
last_updated: 2026-05-01
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

## Resources
- [[github-hornof-profile]] — wiki owner is actively tracking crewAI, learn-agentic-ai, OpenAI Agents SDK
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy at AI Ascent 2026; sensors/actuators framing, agent-native infrastructure, agentic engineering as discipline
- [[ashwingop-company-brain-part-1]] — Company Brain thesis Part 1 (memory substrate underneath agentic AI)
- [[ashwingop-company-brain-part-2]] — Company Brain Part 2 (factual memory ≠ RAG; semantic file system; memory participates)
- [[seelffff-personal-ai-agent]] — personal-scale agent stack on Claude Desktop + MCP
