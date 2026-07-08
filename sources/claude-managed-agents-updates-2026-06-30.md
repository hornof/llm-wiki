---
title: "Claude Managed Agents — June 2026 platform updates (ClaudeDevs)"
type: source
medium: twitter-thread
url: https://x.com/ClaudeDevs/status/2072058428424589412
ingested: 2026-07-08
---

## Summary

`@ClaudeDevs` announces a batch of platform updates to **Claude Managed Agents** — Anthropic's hosted agent-session API surface under the [[claude-agent-sdk|Claude Agent SDK]] (2026-06-30). A thin changelog, but a concrete capability signal: the managed-agent surface is being hardened for production multi-session/observability use, not just launched-and-left.

## Key Claims / Takeaways

- **Streaming session event deltas** — incremental event streaming for live session state, rather than polling for full snapshots.
- **Per-session agent overrides** — start a session from a *stored* agent and override parts of its config for that one session: swap the **model, system prompt, tools, `mcp_servers`, or skills**. Lets one stored agent definition be reused across sessions with per-invocation variation (the hosted analog of Claude Code's per-run overrides).
- **New webhook event types** — more granular event hooks for external integrations.
- **Reverse pagination** — page backward through session history.
- **Credential injection scoping** — tighter control over which credentials are injected into which sessions (a security/isolation improvement for multi-tenant agent hosting).
- **New Managed Agents Observability tab in Console** — session-level metrics: input/output token use and tool usage.
- Discoverability note: Anthropic points users to the built-in **`claude-api` skill** in Claude Code plus the cookbook for learning these features.

## Why it matters

Reinforces the [[claude-agent-sdk|Claude Agent SDK]] as the layer beneath Anthropic's agent products, with **Managed Agents** as the hosted/production execution surface (stored agents + sessions + webhooks + observability). The per-session override + credential-scoping + observability additions are production-hardening signals — the same eval/observability discipline the [[loop-engineering]] and [[agentic-engineering]] discourse keeps flagging, arriving as first-party platform features. Cross-vendor contrast: Google's [[google-agents-cli|Agents CLI]] pushes the *build/deploy/observe* lifecycle from the coding-agent side; Anthropic ships it as *hosted-session* platform features.

## Pages Updated

- [[claude-agent-sdk]] — added Managed Agents as a documented surface + this update under Traction Signals
