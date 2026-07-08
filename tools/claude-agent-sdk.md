---
name: Claude Agent SDK
type: tool
category: api
status: emerging
last_updated: 2026-07-08
---

## What It Is

The **Claude Agent SDK** is [[anthropic]]'s developer-accessible SDK powering both the IDE and Desktop hosts of Claude. Announced at **Code w/ Claude 2026** (May 6 2026) — [[willison-code-w-claude-2026]]. Consolidates the developer surface previously split across product-specific harnesses ([[claude-code]] CLI, [[claude-desktop]] MCP host, in-product harnesses inside Claude.ai). Externally documented as a single SDK developers can build against.

## Traction Signals

- 2026-05-06: announced at Code w/ Claude 2026 alongside the Claude Code Desktop App, Claude Code Routines, Multi-agent Orchestration, and Claude Opus 4.7 — all framed as a unified developer + production stack.
- First-party SDK positioning is novel for Anthropic at this surface — previous developer access was via the [[anthropic]] API plus product-specific harnesses; the Agent SDK is positioned as the layer underneath all of them.
- 2026-06-30: **Managed Agents platform updates** ([[claude-managed-agents-updates-2026-06-30]]) — a production-hardening batch on the hosted agent-session surface: streaming session event deltas, **per-session agent overrides** (start from a stored agent, override model / system prompt / tools / `mcp_servers` / skills for one session), new webhook event types, reverse pagination, **credential injection scoping**, and a new **Managed Agents Observability** tab in Console (session-level input/output token + tool-usage metrics). Signals the managed surface is being built out for multi-session, multi-tenant production use, not just launched.

## Managed Agents

**Claude Managed Agents** is the SDK's hosted agent-session surface: developers define *stored agents* (model + system prompt + tools + `mcp_servers` + skills) and run *sessions* against them via the [[anthropic]] API, with webhooks, observability, and credential scoping handled by Anthropic rather than self-hosted. It is the production/hosted counterpart to the local [[claude-code]] harness. Capabilities are evolving quickly — see the [[claude-managed-agents-updates-2026-06-30|June 2026 update batch]].

## How to Use It

Documentation/deep details not in the live-blog coverage. Expected to be the sanctioned path for embedding Anthropic agent capability in third-party applications, parallel to OpenAI's Agents SDK ([[openai]]).

## Compared To

- **OpenAI Agents SDK** ([[agentic-ai]]): the closest direct analog at the labs-providing-agent-frameworks layer.
- **MCP** ([[mcp]]): MCP is the *protocol* — Agent SDK is the *developer toolkit*. Distinct layers of the same stack.
- **Claude Code** ([[claude-code]]): Claude Code is one *consumer* of the Agent SDK (per the Code w/ Claude 2026 framing — "Claude Agent SDK powering IDE and Desktop app").

## Resources

- [[willison-code-w-claude-2026]] — Code w/ Claude 2026 event announcement
- [[claude-managed-agents-updates-2026-06-30]] — June 2026 Managed Agents platform updates (per-session overrides, observability tab, credential scoping)
