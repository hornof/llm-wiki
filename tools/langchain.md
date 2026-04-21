---
name: LangChain
type: tool
category: framework
status: mainstream
last_updated: 2026-04-21
---

## What It Is
A Python (and JavaScript) framework for building LLM-powered applications. Provides abstractions for chains, agents, RAG pipelines, memory, and tool use. Described as "the agent engineering platform."

## Traction Signals
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- One of the earliest and most widely adopted LLM frameworks; large ecosystem [unsourced]

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
