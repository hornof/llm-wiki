---
title: "MCP vs CLI was the wrong debate (Akshay Pachaar on X)"
type: source
medium: twitter-thread
url: https://x.com/akshay_pachaar/status/2053166970166772052
ingested: 2026-05-09
---

## Summary

[[akshay-pachaar]] explainer post (May 9 2026) reframing the year-long MCP-vs-CLI practitioner debate. The debate was the wrong framing — both sides survived, but they stopped being *the runtime* and became the primitives the runtime composes. The new pattern, **Code Mode**, was published by Anthropic on Nov 4 2025 ("Code execution with MCP") and extended by [[cloudflare]] in their Code Mode MCP server. Concrete numbers: token costs of MCP servers, the 98.7% token-drop example, and the 300M MCP SDK download stat that puts MCP among the fastest-growing pieces of agent infrastructure.

## Key Claims / Takeaways

### Token cost of MCP servers (skeptic position)

- **Playwright MCP**: 13.7K tokens
- **Chrome DevTools MCP**: 18K tokens
- A 5-server MCP setup: **55K tokens before any work** is done
- A single workflow with tool schemas + tool outputs piped through the model on every step: can balloon to **150K tokens**

### CLI camp pushback

- CLIs break on multi-tenant apps
- No typed contracts, so the agent guesses at outputs
- On unfamiliar APIs, agents waste turns parsing text

### The reframe — Code Mode

> "The problem was never the protocol. It was the habit of loading every tool's full description into context the moment a session starts."

**The fix**: the model writes code that calls tools through a *runtime*. The model only sees what it imports.

Anthropic's published example ([Code execution with MCP](https://www.anthropic.com/engineering/code-execution-with-mcp), Nov 4 2025): Google Drive transcript flows into Salesforce CRM update. Old way loaded both tool schemas and piped the transcript through the model twice. New way: a few lines of TypeScript that import only what they need. **Same task, 2K tokens. 98.7% drop.**

[Cloudflare extended](https://blog.cloudflare.com/code-mode-mcp/) the pattern: collapsed their entire 2,500-endpoint API from **1.17M tokens of schemas down to 1K tokens** by exposing just two functions — `search` and `execute`. The agent writes code that searches the catalog, then executes only what matches.

### Code Mode as a runtime

Two primitives composed inside a single runtime:

1. **Bash** for anything with a binary already installed (git, curl, grep, etc.). The model has seen these in training data and knows how to compose them. *"No tool definition needed. The shell does the work."*
2. **Typed module imports** for proprietary APIs (Salesforce, Stripe, internal services). Each file describes one tool with inputs/outputs spelled out. The agent only loads the files it actually uses; type signatures travel with the import.

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

Three structural changes Code Mode enables that weren't previously possible:
- Tool definitions enter context only on the import lines; every other tool stays out
- Lists/data are processed in code, not piped through the model on every step
- The agent composes loops and transforms in actual code — no round-tripping through the model for every step

> "MCP's typed contracts plus CLI's lazy loading, in one runtime. The agent picks per task."

### Practical takeaway

> "The footer of the diagram is the practical takeaway. Code Mode is not a replacement for either approach. It is a runtime that uses both. Bash for anything with a binary on $PATH. Typed module imports for proprietary APIs."

> "If you are building agents in 2026, the rule is simple. **Tool definitions belong in code, not in context.** The model writes a few lines that call them. The runtime does the rest."

### Traction signal — MCP is not dying

> "Anthropic just reported **300M MCP SDK downloads, up from 100M at the start of the year.** The protocol is not dying. It is the fastest growing piece of agent infrastructure right now."

3× growth in ~5 months. *"What died was loading every tool upfront."*

## Pages Updated

- [[mcp]] (updated — token-cost-of-MCP-servers concrete numbers; Code Mode as the runtime that uses MCP as a primitive; 300M SDK downloads traction signal; Anthropic Nov 4 2025 publication referenced)
- [[code-mode]] (new — concept page for the Code-Mode runtime pattern)
- [[claude-cowork]] (updated — Cowork's MCP→Chrome→Computer Use priority ladder is consistent with Code Mode's "tool definitions belong in code, not in context" framing)
- [[cloudflare]] (updated — Cloudflare Code Mode MCP server's 1.17M → 1K token compression detail)
- [[playwright-mcp]] (updated — concrete token cost: 13.7K)
