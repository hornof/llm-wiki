---
name: LangChain
type: tool
category: framework
status: mainstream
last_updated: 2026-07-06
---

## What It Is
A Python (and JavaScript) framework for building LLM-powered applications. Provides abstractions for chains, agents, RAG pipelines, memory, and tool use. Described as "the agent engineering platform."

## Traction Signals
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- One of the earliest and most widely adopted LLM frameworks; large ecosystem [unsourced]
- **2026 book-publishing signal**: Packt's *30 Agents Every AI Engineer Must Build* by [[imran-ahmad]] explicitly names LangChain + LangGraph as the build stack for the book's pattern-catalog approach. Trade-publisher commitment to the LangChain stack as the canonical teaching surface is a durability signal — separate from frontier practitioner adoption (which has shifted toward [[claude-code]] / [[claude-desktop]] + [[mcp]] for direct-agent workflows). — [[30-agents-every-ai-engineer-must-build]]
- **2026-06-17 canonical-Sydney-Runkle canonical-LangChain-4-layer canonical-Loop-Engineering canonical-articulation** ([[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]]) — canonical-LangChain-VP canonical-direct-voice canonical-4-layer canonical-framework-tier canonical-articulation at canonical-vendor-tier. canonical-LangChain canonical-Loop-Engineering canonical-canonical-cluster canonical-vendor-tier canonical-anchor.
- **2026-07-03 canonical-agent-native-framework canonical-adjacent-positioning-tension**: canonical-Vercel canonical-Andrew-Qu canonical-3-pillar canonical-agent-native-substrate ([[vercel-andrew-qu-agents-new-software-paradigm-2026-07-03]]) + canonical-Adobe canonical-agentic-sites canonical-Carlos-Sanchez ([[dailybrief-roundup-2026-07-03]]) = canonical-2-vendor canonical-1-day canonical-agent-native-web canonical-cluster canonical-competitive-positioning canonical-tension canonical-adjacent-to-LangChain canonical-framework-tier canonical-positioning.

## How to Use It
Build chains (sequences of LLM calls and transformations), RAG pipelines (document loading → embedding → retrieval → generation), or agents (LLM + tools in a loop). LangGraph (a sub-project) handles stateful, graph-based agent workflows.

## Key Concepts
- **Chain**: a sequence of calls — prompt → LLM → output parser
- **Agent**: LLM in a loop deciding which tools to call
- **LangGraph**: extension for stateful, cyclical agent workflows
- **LCEL**: LangChain Expression Language — composable pipeline syntax
- **LangSmith**: observability/tracing platform for LangChain apps

## Compared To
- [[crewai]]: CrewAI is higher-level and opinionated about multi-agent roles; LangChain is more flexible and lower-level
- [[llama-index]]: LlamaIndex focuses on document ingestion and RAG; LangChain is broader
- Raw API calls: LangChain adds abstractions and integrations at the cost of complexity

## Resources
- [[github-hornof-profile]] — forked by wiki owner; signals active interest
- [[30-agents-every-ai-engineer-must-build]] — Packt book by [[imran-ahmad]] using LangChain + LangGraph as the build stack for 30 agent-architecture patterns (listing-only ingest, book content not read)
