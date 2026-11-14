---
name: LangChain
type: tool
category: framework
status: mainstream
last_updated: 2026-11-14
dormant_since: 2026-09-20
---

## What It Is
A Python (and JavaScript) framework for building LLM-powered applications. Provides abstractions for chains, agents, RAG pipelines, memory, and tool use. Described as "the agent engineering platform."

## Traction Signals
- **2026-11-13: $300M Series C at a $3B valuation, led by CapitalG** ([[ainews-no-ai-slop-llamacpp-langchain-2026-11-13]], AINews). New LangSmith features are due on 2026-11-20. The primary announcement wasn't fetched.
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- One of the earliest and most widely adopted LLM frameworks; large ecosystem [unsourced]
- **2026 book-publishing signal**: Packt's *30 Agents Every AI Engineer Must Build* by [[imran-ahmad]] explicitly names LangChain + LangGraph as the build stack for the book's pattern-catalog approach. A trade publisher teaching on the LangChain stack is a durability signal — separate from frontier practitioner adoption (which has shifted toward [[claude-code]] / [[claude-desktop]] + [[mcp]] for direct-agent workflows). — [[30-agents-every-ai-engineer-must-build]]
- **2026-06-17: LangChain maps its products onto four agent loops** ([[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]]). Sydney Runkle's "The Art of Loop Engineering" describes four nested loops: the agent loop (`create_agent`), a verification loop that grades output against a rubric and retries (`RubricMiddleware`), an event-driven loop triggered by crons and webhooks (LangSmith Deployment and Fleet), and a hill-climbing loop where an analysis agent reads production traces and rewrites the harness config (LangSmith Engine). It's a vendor post, but it's the clearest statement of how LangChain now positions itself: as a stack for running agents in production, not only a chaining library. See [[loop-engineering]].

*(Filler rewritten 2026-11-12. A 2026-07-03 bullet about Vercel's and Adobe's agent-native web work was removed: neither source mentions LangChain, so the "tension" with LangChain was the wiki's own inference.)*

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
