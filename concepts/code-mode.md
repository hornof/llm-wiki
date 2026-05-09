---
name: Code Mode
type: concept
maturity: emerging
last_updated: 2026-05-09
---

## Definition

**Code Mode** is a runtime pattern in which an LLM agent **writes code that calls tools** rather than calling tools directly through its prompt context. Tool definitions live in code modules (TypeScript files, bash binaries) and are loaded only when the agent imports them — the model never sees the schemas of tools it doesn't use.

Coined and published by [[anthropic]] on November 4, 2025 in [Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp). Extended by [[cloudflare]] in their Code Mode MCP server.

## Why It Matters

Resolves the year-long [[mcp]]-vs-CLI debate by making it the wrong framing. Both sides had real arguments:

- **MCP camp**: typed contracts mean the agent doesn't guess at outputs.
- **CLI / shell camp**: loading every tool schema upfront balloons context — a 5-server MCP setup burns **55K tokens before any work** is done; a single workflow can hit **150K tokens** when tool schemas plus tool outputs route through the model on every step.

Code Mode keeps the typed contracts of MCP and the lazy loading of CLI, inside a single runtime. The model only loads the tool files it imports.

## How It Works

Two primitives composed inside one runtime:

1. **Bash** — for anything with a binary already installed (git, curl, grep, etc.). The model has seen these in training data and knows how to compose them. No tool definition required.
2. **Typed module imports** — for proprietary APIs (Salesforce, Stripe, internal services). Each tool is a small TypeScript file with inputs/outputs spelled out. **Type signatures travel with the import.** The agent loads only the files it uses.

```typescript
// The agent writes this. Types load only on these import lines.
import { searchFiles } from "@tools/github";
import { sendMessage } from "@tools/slack";

const files = await searchFiles({ pattern: "*.py", path: "./src" });
const summary = files.map(f => f.path).join("\n");

await sendMessage({
  channel: "#engineering",
  text: `Found ${files.length} Python files:\n${summary}`,
});
```

Three structural wins:
- **Tool definitions enter context only on import lines.** Every other tool the runtime offers stays out.
- **Data is processed in code, not piped through the model on every step.** The model never sees the raw file list above; it only sees the summary the code constructed.
- **Loops and transforms live in actual code.** No round-tripping through the model for each step.

## Concrete Token-Compression Examples

| Source | Workflow | Old | New | Reduction |
|---|---|---|---|---|
| Anthropic ([Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp)) | Google Drive transcript → Salesforce CRM update | full schemas + transcript piped twice | 2K tokens | **98.7%** |
| [Cloudflare](https://blog.cloudflare.com/code-mode-mcp/) | 2,500-endpoint API exposed to agents | 1.17M tokens of schemas | 1K tokens (`search` + `execute`) | **>99.9%** |

## Token Cost of Conventional MCP Servers (skeptic data)

From [[akshay-pachaar-mcp-vs-cli-2026-05-09]]:

- [[playwright-mcp]]: **13.7K tokens**
- Chrome DevTools MCP: **18K tokens**
- 5-server MCP setup: **55K tokens before any work**
- A single workflow with schemas + tool outputs piped through the model on every step: can hit **150K tokens**

These numbers explain why "load every tool upfront" was always a bad idea — and why Code Mode reframes the runtime.

## Current State

- **Anthropic published the pattern** on Nov 4 2025 — primary source.
- **Cloudflare extended it** to a 2,500-endpoint API compression case study (May 2026, [[cloudflare-stripe-projects-agents-2026-05]] surfaces Cloudflare's Code Mode MCP server in the Stripe Projects launch).
- **MCP is not dying** despite the reframe: 300M MCP SDK downloads as of May 2026, **up from 100M at the start of the year** — 3× in 5 months. MCP is a primitive Code Mode composes, not a competitor.
- Practitioner-side framing now widely circulating ([[akshay-pachaar-mcp-vs-cli-2026-05-09]], May 9 2026) — the rule is *"tool definitions belong in code, not in context."*

## Why This Matters for the Wiki

- **Reframes [[mcp]]**: not a runtime, a primitive. The 13.7K-tokens-for-Playwright cost is real, but Code Mode hides it behind imports the agent writes on demand.
- **Aligns with [[claude-cowork]]'s Tool Priority Ladder** (MCP → Chrome Extension → Computer Use): Cowork's "10× faster, 10× fewer tokens" preference for MCP is the same direction as Code Mode — minimize the context burned on tool plumbing.
- **Strengthens [[claude-code]]'s positioning** as a Code-Mode-native harness — terminal-native, bash-first, with TypeScript import support.
- **Implication for [[agentic-engineering]]**: the discipline shift is "treat tool plumbing as code, not as prompt scaffolding."

## Related Concepts

- [[mcp]] — typed contracts as a primitive Code Mode composes
- [[claude-cowork]] — Cowork's MCP-first priority ladder is downstream of the same insight
- [[claude-code]] — bash + TypeScript-native harness; Code-Mode-native by default
- [[agentic-engineering]] — Code Mode is the runtime-level expression of "agent reliability through control flow rather than prompt elaboration"
- [[control-flow-agents]] — Brian/bsuh's "agents need control flow, not more prompts" framing — Code Mode is the same direction at the runtime level

## Key Posts

- [Anthropic — Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp) (Nov 4 2025) — primary source for the pattern
- [Cloudflare — Code Mode MCP](https://blog.cloudflare.com/code-mode-mcp/) — 2,500-endpoint compression case study
- [[akshay-pachaar-mcp-vs-cli-2026-05-09]] — practitioner reframing of the MCP-vs-CLI debate (May 9 2026)
- [[cloudflare-stripe-projects-agents-2026-05]] — Cloudflare Code Mode MCP referenced in the Stripe Projects launch
