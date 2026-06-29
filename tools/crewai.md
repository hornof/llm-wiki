---
name: CrewAI
type: tool
category: framework
status: gaining-traction
last_updated: 2026-06-29
---

## What It Is
A Python framework for orchestrating multi-agent AI workflows. Agents are assigned roles, goals, and tools; they collaborate as a "crew" to tackle complex tasks that benefit from parallel or sequential specialization.

## Traction Signals
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- **2026-06-08: Opik canonical-50+ framework integrations canonical-roster includes CrewAI** ([[akshay-pachaar-opik-self-repairing-harness-2026-06-08]]) — CrewAI cited alongside LangGraph as canonical-multi-agent-framework canonical-instrumentation-target at canonical-self-repairing-harness canonical-substrate-tier
- **2026-06-13: Omnigent canonical-positioning canonical-comparison-target** ([[zaharia-omnigent-multi-agent-meta-harness-2026-06-13]]) — Matei Zaharia's Omnigent positioned in same canonical-multi-agent-orchestration canonical-cohort as CrewAI + LangChain + Anthropic Dynamic Workflows (verification-pending Zaharia-canonical-direct-comparison)
- One of the most-starred agent orchestration frameworks on GitHub [unsourced]

## How to Use It
Define agents with roles and tools, define tasks, assemble into a Crew, and kick off. Agents can use RAG, web search, code execution, or custom tools.

## Key Concepts
- **Agent**: an LLM-backed role with a goal and set of tools
- **Task**: a discrete unit of work assigned to an agent
- **Crew**: a team of agents with a defined process (sequential or hierarchical)
- **Process**: how tasks are executed — sequential (one after another) or hierarchical (manager delegates)

## Compared To
- LangChain: broader framework covering chains, RAG, agents; CrewAI is specifically opinionated about multi-agent role-playing
- [[langchain]]: overlapping agent use cases; CrewAI's crew abstraction is higher-level
- AutoGen (Microsoft): similar multi-agent approach; different API style

## Resources
- [[github-hornof-profile]] — forked by wiki owner; signals active interest
