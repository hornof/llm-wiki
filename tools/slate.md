---
name: Slate
type: tool
category: cli
status: emerging
last_updated: 2026-07-10
---

## What It Is

**Slate** (by RandomLabs; `npm i -g @randomlabs/slate`) is a terminal AI coding agent positioned specifically for **swarm orchestration** — running long, parallel, multi-step [[loop-engineering|loops]] across a codebase. Its pitch versus [[claude-code|Claude Code]] / [[codex|Codex]] / Cursor is **automatic per-step model selection** (plan with one model, search with a cheap one, execute/verify with another), **parallel isolated subagents**, and **self-managed context across multi-hour sessions**.

> ⚠️ **Signal caveat**: the only wiki source for Slate is a single promotional thread — [[how-to-build-first-ai-loop-slate-2026-07-10|@sairahul1's "How To Build Your First AI Loop"]] (theaibuilders.co), which reads as a paid/affiliate placement (*"Worth more than any $500 agentic course"*). RandomLabs and Slate have **no independent corroboration** captured here — no GitHub-star trend, no practitioner "switched to Slate" reports, no vendor-neutral coverage. Treat everything below as vendor/promoter claims until a second source appears.

## Traction Signals

- **[unsourced beyond one promotional thread]** — single engagement-optimized X thread (2026-07-10); no independent adoption evidence yet.
- Claimed differentiators: *"first agent built specifically for swarm orchestration"*; runs up to 5 parallel specialized subagents on one task.

## How to Use It

Loop-engineering scaffold as taught in the source thread:

- **`AGENTS.md`** (project root) — context read at every session start: what the codebase does, architecture, key commands (`npm test` / `build` / `lint` / `typecheck`), hard rules, `## Session start` directive to read `STATE.md` first.
- **`slate.json`** — permissions (`"*": "allow"`, `"bash": "ask"`) + per-role model map:
  ```json
  "models": {
    "main":     { "default": "anthropic/claude-opus-4.6" },
    "subagent": { "default": "anthropic/claude-sonnet-4.6" },
    "search":   { "default": "anthropic/claude-haiku-4.5" },
    "reasoning":{ "default": "openai/gpt-5.6" }
  }
  ```
  plus custom `command` slash-templates.
- **`.slate/skills/<name>/SKILL.md`** — reusable skills (frontmatter `name` + `description`); `/skills` to list, `@skill` to activate, or auto-activated.
- **`STATE.md`** — durable loop memory (last run / in-progress / completed / escalated / lessons); the maker-checker verifier subagent gets no access to the maker's reasoning.
- **Run a loop**: `slate --queue loop.md` (queue-file), `slate run "$(cat loop.md)" --output-format stream-json --dangerously-skip-permissions` (headless/CI, e.g. a GitHub Action on `workflow_run` failure), `slate --continue` (resume most recent session).
- **Interaction**: Tab to queue a message mid-run, Enter to steer immediately, `/enter-mode-next` to cycle steer/queue/interrupt; `!cmd` runs shell inline; `slate serve --port` + `slate attach` for team/remote.

## Key Concepts

- **Workspace** — `@`-mention files or `/workspace add ./src`; the set of dirs Slate reasons over.
- **Per-role model map** — cheap model for search, strong model for main reasoning, strict model as verifier.
- **Queue file (`loop.md`)** — a markdown block Slate runs as a queued message with an explicit stop condition + hard iteration cap.
- **Maker-checker isolation** — the verifier subagent sees only the requirements + test output, never the implementer's reasoning.

## Compared To

- **[[claude-code|Claude Code]]** — Slate's claimed edge is built-in multi-model routing and swarm parallelism; Claude Code delivers the same loop primitives natively (`/goal`, `/loop`, `/schedule`, [[anthropic-dynamic-workflows-official-docs-2026-06|dynamic workflows]], skills) with first-party model access and far deeper documented traction.
- **[[codex|Codex]]** / **[[openclaw|OpenClaw]]** — same practitioner niche (terminal agent, long autonomous runs); Slate uniquely markets the auto-model-selection angle.

## Resources
- [[how-to-build-first-ai-loop-slate-2026-07-10]] — the sole (promotional) source; a full loop-build tutorial built around Slate
- Claimed vendor links (unverified): `randomlabs.ai/s`, `docs.randomlabs.ai`
