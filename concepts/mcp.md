---
name: Model Context Protocol (MCP)
type: concept
maturity: active-research
last_updated: 2026-04-24
---

## Definition
MCP (Model Context Protocol) is Anthropic's open standard for connecting LLMs to external tools and data sources. It defines a client-server protocol: an LLM host (e.g., Claude Code, Claude Desktop) acts as a client, and MCP servers expose tools, resources, and prompts that the model can invoke. The model doesn't access files or APIs directly — it calls MCP servers, which do the work and return results.

## Why It Matters
MCP is the connective tissue for agentic AI systems. Instead of hard-coding tool access into each LLM application, MCP lets you plug any data source or capability into any MCP-compatible model. This is the practical infrastructure layer under the "agents that take autonomous actions" vision.

## Current State
- Launched by Anthropic as an open standard (not proprietary)
- Supported natively in Claude Code, Claude Desktop, and growing third-party tools
- Community building MCP servers for: filesystem access, web search, GitHub, Slack, databases, browser control
- **Gotcha**: unconstrained MCP can ingest enormous amounts of context — e.g., pulling an entire `node_modules` tree when looking for one dependency. `context-mode` is a server-side setting that constrains file ingestion scope — [[claude-code]]
- **A2A** (Agent-to-Agent protocol, Google): a complementary standard at a different layer — MCP connects models to tools; A2A connects agents to other agents — [[agentic-ai]]

## Key Papers / Posts
- [[github-hornof-profile]] — `learn-agentic-ai` repo (forked by owner) covers MCP alongside OpenAI Agents SDK, A2A, Knowledge Graphs, Dapr
- [[reddit-3-things-claude-output-quality]] — community tip: use `context-mode` to prevent MCP token bloat

## Related Concepts
- [[agentic-ai]] — MCP is the tool-connection layer for agentic systems
- [[claude-code]] — primary CLI that uses MCP servers for extended capabilities
- [[rag]] — RAG retrieves from a vector store at query time; MCP connects the model to live tools and data sources at runtime
