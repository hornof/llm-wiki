---
name: Model Context Protocol (MCP)
type: concept
maturity: active-research
last_updated: 2026-05-06
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
- **Production status confirmed**: Anthropic's first official certification ([[claude-certified-architect]], March 2026) names "Tool Design & MCP Integration" as a weighted exam domain (~18% per third-party guides), elevating MCP from emerging-protocol to required-knowledge for solution architects — [[anthropic-claude-partner-network]]
- **Consumer-grade MCP stacks** (April 2026): [[claude-desktop]] is now hosting personal-agent stacks (Filesystem MCP + [[playwright-mcp]] + custom-built MCP servers) on a $20/mo Claude Pro subscription with no API keys, no AWS, no developer accounts. Expands the practitioner population from developers-with-API-budget to anyone-with-Claude-Pro. Community shorthand crystallizing: **"MCP = USB ports for AI."** — [[seelffff-personal-ai-agent]]
- **YC partner-level validation** (April 2026): YC's Summer 2026 RFS includes a "Software for Agents" category (Aaron Epstein) explicitly calling for "machine-readable interfaces: APIs, MCPs, CLIs" — frames MCP as foundational primitive for the next-generation agent-native software stack. "While everyone else is building agents, the biggest opportunity might be building the software those agents depend on." — [[yc-summer-2026-rfs]]
- **Cloudflare Code Mode MCP server** (May 2026): [[cloudflare]]'s edge-hosted MCP server is one of the named technical surfaces in the Stripe Projects launch — agents use Code Mode MCP to provision Cloudflare infrastructure (accounts, domains, deployments) under Stripe-attested identity and budgets. First wiki appearance of an infrastructure provider co-designing a payments protocol around MCP-driven agent purchasing. — [[cloudflare-stripe-projects-agents-2026-05]]

## Key Papers / Posts
- [[github-hornof-profile]] — `learn-agentic-ai` repo (forked by owner) covers MCP alongside OpenAI Agents SDK, A2A, Knowledge Graphs, Dapr
- [[reddit-3-things-claude-output-quality]] — community tip: use `context-mode` to prevent MCP token bloat
- [[anthropic-claude-partner-network]] — Anthropic announcement (March 2026); MCP integration codified as a Claude Certified Architect exam domain
- [[seelffff-personal-ai-agent]] — April 2026 hands-on tutorial: build a personal life-management agent with Filesystem MCP + Playwright MCP + custom 25-line Telegram MCP on Claude Desktop ($0 incremental cost on Claude Pro)
- [[personal-ai-agent-claude-desktop-mcp]] — wiki-side tutorial derived from above
- [[yc-summer-2026-rfs]] — Aaron Epstein's "Software for Agents" RFS names MCPs as one of the machine-readable interfaces agents need
- [[anthropic-academy-courses-catalog-2026-05]] — official Anthropic Academy MCP courses ("Introduction to Model Context Protocol", "Model Context Protocol: Advanced Topics" — sampling, notifications, file system access, transport mechanisms, production server development)

## Related Concepts
- [[agentic-ai]] — MCP is the tool-connection layer for agentic systems
- [[claude-code]] — terminal-native MCP host
- [[claude-desktop]] — desktop MCP host; same protocol, different harness; popular for non-coding agentic stacks
- [[playwright-mcp]] — most-used MCP server in this wiki's practitioner content
- [[rag]] — RAG retrieves from a vector store at query time; MCP connects the model to live tools and data sources at runtime
