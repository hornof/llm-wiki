---
name: Claude Agent SDK
type: tool
category: api
status: emerging
last_updated: 2026-05-07
---

## What It Is

The **Claude Agent SDK** is [[anthropic]]'s developer-accessible SDK powering both the IDE and Desktop hosts of Claude. Announced at **Code w/ Claude 2026** (May 6 2026) — [[willison-code-w-claude-2026]]. Consolidates the developer surface previously split across product-specific harnesses ([[claude-code]] CLI, [[claude-desktop]] MCP host, in-product harnesses inside Claude.ai). Externally documented as a single SDK developers can build against.

## Traction Signals

- 2026-05-06: announced at Code w/ Claude 2026 alongside the Claude Code Desktop App, Claude Code Routines, Multi-agent Orchestration, and Claude Opus 4.7 — all framed as a unified developer + production stack.
- First-party SDK positioning is novel for Anthropic at this surface — previous developer access was via the [[anthropic]] API plus product-specific harnesses; the Agent SDK is positioned as the layer underneath all of them.

## How to Use It

Documentation/deep details not in the live-blog coverage. Expected to be the sanctioned path for embedding Anthropic agent capability in third-party applications, parallel to OpenAI's Agents SDK ([[openai]]).

## Compared To

- **OpenAI Agents SDK** ([[agentic-ai]]): the closest direct analog at the labs-providing-agent-frameworks layer.
- **MCP** ([[mcp]]): MCP is the *protocol* — Agent SDK is the *developer toolkit*. Distinct layers of the same stack.
- **Claude Code** ([[claude-code]]): Claude Code is one *consumer* of the Agent SDK (per the Code w/ Claude 2026 framing — "Claude Agent SDK powering IDE and Desktop app").

## Resources

- [[willison-code-w-claude-2026]] — Code w/ Claude 2026 event announcement
