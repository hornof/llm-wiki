---
name: Context Engineering
type: concept
maturity: emerging
last_updated: 2026-07-13
---

## Definition

**Context engineering** is the discipline of assembling the full **information environment** an LLM agent sees *before* it acts — not the wording of a single prompt. The framing that names it: *"Context is the operating system for AI"* — the model sees only what is inside the context window; everything outside it does not exist, so the agent's quality is set by what you load into that window, not by clever phrasing. It is positioned as the successor to **prompt engineering** the way prompt engineering succeeded manual scripting.

This concept page is the umbrella over several disciplines the wiki already tracks as sub-parts: [[claude-md-pattern|CLAUDE.md / AGENTS.md]] (project rules), [[skill-md|SKILL.md]] (per-capability procedure + verifier), [[okf|OKF]] (portable knowledge), [[mcp|MCP]] (cross-system context), memory files ([[claude-mem]], [[mem0]]), and the evolving-context loop of [[loop-engineering]].

## Why It Matters

The load-bearing claim: **an agent's quality is determined more by its context than by its model.** Most agent failures — wrong file edited, wrong assumption, an "obvious" mistake — are missing-context failures, not model failures; the common but wrong fix is to rewrite the prompt, when the real fix is to build the context correctly.

> *"An agent with perfect prompts and poor context makes intelligent mistakes. An agent with average prompts and complete context makes correct decisions. The model is the same. The information environment is not."* — [[noisyb0y1-context-engineering-8x-2026-07-04]]

Directly restates the wiki's recurring thesis: [[trq-dynamic-workflows-harness-2026-06-02|"reliability comes from the harness, not the model"]], [[addy-osmani-agent-harness-engineering-2026-04-19|Addy Osmani's `Agent = Model + Harness`]], and the [[loop-engineering|loop-engineering]] "the loop, not the model, is the expensive/important part." Context engineering names the *input* side of that same shift.

## Current State

### The seven context components
A properly engineered context is more than pasted text — it is seven layers working together: **memory** (what the agent knows from past sessions) · **instructions** (rules, constraints, style) · **examples** (what good output looks like) · **files** (relevant code/docs/architecture) · **previous actions** (what it already tried) · **tool results** (what searches/functions returned) · **state** (where the task stands). Every action grows the context; the agent sees the new context and picks the next action — *that cycle, not the prompt, is the actual mechanism of an agent* (i.e., the [[loop-engineering|loop]]).

### The three-layer context stack
| Layer | Loaded | Contains |
|---|---|---|
| **Global** | every session, always present | agent identity/role, coding standards, security constraints, never-touch rules, how to handle uncertainty |
| **Project** | at project start | README/architecture, **AGENTS.md**, folder/naming conventions, testing patterns, key dependencies + why |
| **Task** | for the specific task | current + related files, the session goal, recent changes/outcomes, current test results, task-specific constraints |

*"Most developers only give Claude task context"* — the agent then starts every session without global or project context and guesses the rest, which is where mistakes come from. The prescribed **context stack** loads in order: global → project (AGENTS.md) → search memory → task files → current state → define goal + success criteria → *then* act.

### AGENTS.md / CLAUDE.md as the permanent project layer
The [[claude-md-pattern|AGENTS.md/CLAUDE.md]] file is where project context lives permanently and is read automatically at session start — *"every rule in this file is one mistake Claude will never make again,"* the same ratchet principle as [[addy-osmani-agent-harness-engineering-2026-04-19|Addy Osmani's harness taxonomy]].

### Memory as context that survives sessions
Three memory tiers feed context: **long-term** (learned across all past sessions), **short-term** (earlier in this conversation), **working** (what's in the window now). Long-term memory is what makes an agent *compound in value* — implemented as a markdown memory file read at session start and updated at session end (*"architecture decisions / what worked / what didn't / recurring patterns"*), the [[skill-md|outer-loop-memory]] discipline. Tooling: [[claude-mem]], [[mem0]].

### MCP as context from everywhere
[[mcp|Model Context Protocol]] pulls context from the systems the work already lives in (GitHub, Linear/Jira, Slack, Postgres, Drive, Sentry) so the agent sees not just the code but the ticket that motivated it, the decision thread, the live error, and the schema the fix must respect — "complete context" without per-system integrations.

### The "8x" claim (caveat)
The framing source ([[noisyb0y1-context-engineering-8x-2026-07-04]]) asserts *"Anthropic engineers merge 8x more code per day than a year ago… the model didn't change; what changed is what Claude sees before it starts."* **This 8x figure and the "Anthropic's own research says so" attribution are author-asserted in a promotional practitioner thread, not traced to a specific Anthropic publication here** — treat the number as illustrative, not a verified benchmark. The *underlying discipline* (7 components, 3-layer stack, AGENTS.md, memory files, MCP) is well-grounded in ideas the wiki already tracks; the 8x is the hook.

## Key Papers / Posts
- [[noisyb0y1-context-engineering-8x-2026-07-04]] — practitioner synthesis: "context is the operating system for AI"; 7 components + 3-layer stack + AGENTS.md + memory + MCP (8x claim caveated)

## Related Concepts
- [[claude-md-pattern]] — the project-context layer (AGENTS.md/CLAUDE.md) as behavioral contract
- [[skill-md]] — per-capability procedure + verifier; outer-loop memory
- [[loop-engineering]] — context that evolves each step *is* the agent loop; context engineering is its input side
- [[okf]] — portable knowledge-file layer
- [[mcp]] — cross-system context retrieval
- [[llm-wiki-pattern]] — context engineering applied to a personal knowledge base
