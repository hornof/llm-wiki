---
title: "Noisy (@noisyb0y1) — \"Anthropic engineers 8x output. Here's the context engineering system behind it\" (7 components + 3-layer stack + AGENTS.md + memory + MCP)"
type: source
medium: twitter-thread
url: https://x.com/noisyb0y1/status/2073335736271618072
ingested: 2026-07-13
---

## Summary

@noisyb0y1 ("Noisy") publishes a practitioner synthesis (2026-07-04) arguing that **context engineering is replacing prompt engineering**, framed around the claim that *"Anthropic engineers merge 8x more code per day than a year ago… the model didn't change; what changed is what Claude sees before it starts working."* The thread is the anchor source for the new [[context-engineering]] concept page: it lays out the 7 context components, the 3-layer Global/Project/Task stack, AGENTS.md as the permanent project layer, memory files, and MCP. Substantive and well-grounded in ideas the wiki already tracks — with one promotional caveat (the 8x number).

## Key Claims / Takeaways

- **"Context is the operating system for AI"** — the model sees only what's in the context window; agent quality is set by context, not phrasing. *"The prompt is the last 1% of the work. The context is the other 99%."*
- **Seven context components**: memory · instructions · examples · files · previous actions · tool results · state. Every action grows the context → agent sees new context → picks next action. *"That cycle is the actual mechanism of an agent — not the prompt, not the model."*
- **Three-layer context stack**: **Global** (identity, rules, style, never-touch — every session) → **Project** (README, **AGENTS.md**, conventions, testing, deps — at project start) → **Task** (current files, goal, recent changes, test state — per task). *"Most developers only give Claude task context"* and the agent guesses the rest.
- **AGENTS.md** = the permanent project-context layer, read automatically at session start; *"every rule in this file is one mistake Claude will never make again"* — the ratchet principle (cf. [[addy-osmani-agent-harness-engineering-2026-04-19]]).
- **Memory tiers**: long-term (across sessions) / short-term (this conversation) / working (the window). Long-term = a markdown memory file read at session start, updated at session end → the agent *compounds*.
- **MCP** pulls context from GitHub / Linear / Slack / Postgres / Drive / Sentry so the agent sees the ticket, the decision thread, the live error, and the schema — not just the code.
- **Weekend setup**: Day 1 build the 3-layer stack (global file + AGENTS.md + memory file); Day 2 connect MCP (GitHub, filesystem, Slack/Linear); Day 3 A/B the same task prompt-only vs full-stack — *"the output gap is where the 8x comes from."*

## Caveat

The **8x figure and the "Anthropic's own research" attribution are author-asserted** in a promotional thread ("Bookmark this and follow"), not traced to a specific Anthropic publication here. Treat the number as illustrative. The underlying discipline is sound and maps onto [[claude-md-pattern]] / [[skill-md]] / [[mcp]] / [[loop-engineering]]; the 8x is the engagement hook.

## Pages Updated
- [[context-engineering]] (new — anchor source)
