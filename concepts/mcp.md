---
name: Model Context Protocol (MCP)
type: concept
maturity: active-research
last_updated: 2026-05-20
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
- **38+ first-party MCP connectors named in Cowork** (May 2026): [[claude-cowork]] ships built-in MCP connectors covering Google Workspace (Gmail, Calendar, Drive), Slack, Notion / Linear / Asana / Jira, HubSpot / Salesforce / Apollo / Clay / Outreach, GitHub, Canva, DocuSign, Microsoft 365, Snowflake, Similarweb, FactSet — and Team/Enterprise plans can register custom remote MCP servers. The internal routing prefers MCP over Chrome Extension over Computer Use because **MCP is roughly 10× faster and uses 10× fewer tokens** than browser/computer-use. First time MCP performance characteristics are made user-facing in product copy. — [[claude-cowork-cheatsheet-2026-05-07]]
- **Token cost of MCP servers — concrete practitioner numbers** (May 2026, [[akshay-pachaar-mcp-vs-cli-2026-05-09]]): [[playwright-mcp]] = 13.7K tokens, Chrome DevTools MCP = 18K, a **5-server MCP setup burns 55K tokens before any work**. Single workflows with schemas + tool outputs piped through the model on every step can hit **150K tokens**. These numbers explain why "load every tool upfront" was always a bad idea — and why Anthropic's [[code-mode]] reframe shipped.
- **MCP-vs-CLI debate resolved by [[code-mode]]** (Nov 2025 publication, May 2026 practitioner reframing): both sides survived; they stopped being the runtime and became the primitives the runtime composes. Code Mode keeps MCP's typed contracts and CLI's lazy loading inside one runtime. Tool definitions enter context only on the import lines the agent writes. Anthropic's published example dropped a Google-Drive→Salesforce workflow from full schemas to **2K tokens (98.7% reduction)**; Cloudflare collapsed a 2,500-endpoint API from 1.17M tokens of schemas to **1K tokens** via `search` + `execute`. — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]
- **MCP traction — 300M SDK downloads, up from 100M at start of 2026** (Anthropic-stated, May 2026): 3× growth in 5 months. *"What died was loading every tool upfront. The protocol is not dying. It is the fastest growing piece of agent infrastructure right now."* — [[akshay-pachaar-mcp-vs-cli-2026-05-09]]
- **MCP tunnels (public beta, 2026-05-19)** — named network-primitive for connecting Claude to MCP servers behind customer firewalls. Shipped alongside [[anthropic|Anthropic's self-hosted sandboxes]] (Claude running inside customer infrastructure) as part of the May 2026 enterprise-deployment expansion. First wiki capture of MCP tunnels as a distinct named primitive; prior MCP framing was protocol-only without specific network-tunneling tooling. — [[dailybrief-roundup-2026-05-19]]

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
- [[claude-cowork]] — Anthropic's autonomous-execution surface; MCP is the top tier of its tool priority ladder
- [[code-mode]] — runtime pattern that uses MCP as a primitive (not a runtime); lazy-loads tool schemas via code imports; resolves the year-long MCP-vs-CLI debate
- [[playwright-mcp]] — most-used MCP server in this wiki's practitioner content
- [[rag]] — RAG retrieves from a vector store at query time; MCP connects the model to live tools and data sources at runtime
