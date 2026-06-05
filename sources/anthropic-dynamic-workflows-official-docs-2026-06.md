---
title: "Anthropic Dynamic Workflows — official Claude Code docs (Orchestrate subagents at scale, 2026-06)"
type: source
medium: article
url: https://code.claude.com/docs/en/workflows
ingested: 2026-06-05
---

## Summary

[[anthropic|Anthropic]]'s **canonical Claude Code documentation for Dynamic Workflows** — *"Orchestrate subagents at scale with dynamic workflows"*. **First wiki-captured Anthropic-canonical primary docs page for Dynamic Workflows** (prior wiki coverage was via the [[anthropic-dynamic-workflows-primary-2026-05-28|May 28 preview-ship announcement]] + [[nateherk-dynamic-workflows-2026-05-30|Nate Herk's 41-Haiku case study]] + [[claude-opus-4-8-dynamic-workflows-2026-05-28|Opus 4.8 launch positioning]]). Captures the **runtime constraints** (16 concurrent agents / 1,000 agents total per run), the **`ultracode` keyword + `/effort ultracode` mode**, the **bundled `/deep-research` workflow**, the **`.claude/workflows/` + `~/.claude/workflows/` save-location convention** (paralleling the `.claude/agents/` schema), and the **subagents-vs-skills-vs-agent-teams-vs-workflows comparison table** that resolves the ongoing practitioner-content terminology question.

## Key Claims / Takeaways

### Definition (from the docs)

> *"A dynamic workflow is a JavaScript script that orchestrates subagents at scale. Claude writes the script for the task you describe, and a runtime executes it in the background while your session stays responsive."*

**Use when**: a task needs more agents than one conversation can coordinate, OR you want the orchestration codified as a script you can read and rerun. Examples: codebase-wide bug sweep, 500-file migration, cross-checked research question, multi-angle plan-drafting.

### The 4-way comparison table — first wiki-captured Anthropic-canonical disambiguation

| | Subagents | Skills | Agent teams | **Workflows** |
|---|---|---|---|---|
| What it is | A worker Claude spawns | Instructions Claude follows | A lead agent supervising peer sessions | **A script the runtime executes** |
| Who decides what runs next | Claude, turn by turn | Claude, following the prompt | The lead agent, turn by turn | **The script** |
| Where intermediate results live | Claude's context window | Claude's context window | A shared task list | **Script variables** |
| What's repeatable | The worker definition | The instructions | The team definition | **The orchestration itself** |
| Scale | A few delegated tasks per turn | Same as subagents | A handful of long-running peers | **Dozens to hundreds of agents per run** |
| Interruption | Restarts the turn | Restarts the turn | Teammates keep running | **Resumable in the same session** |

**Resolves the ongoing practitioner-content terminology question** ([[lennysan-shipper-10-takeaways-2026-05-24|Shipper takeaway 9]] *"build software for humans and agents together"* + [[trq-suzanne-learn-quiz-2026-06-01|Suzanne's Learn Quiz]] context-management vs orchestration distinction). **First wiki-captured authoritative 4-primitive Claude Code agent-architecture decomposition** with the key differentiator: *who holds the plan* (Claude turn-by-turn vs lead agent vs the script).

### Runtime constraints — first wiki-captured concrete numerical caps

| Constraint | Value | Why |
|---|---|---|
| Mid-run user input | Not allowed | Only agent permission prompts can pause a run |
| Direct filesystem / shell access from workflow itself | Not allowed | Agents read/write/run; the script coordinates |
| **Concurrent agents** | **Up to 16** (fewer on machines with limited CPU cores) | Bounds local resource use |
| **Total agents per run** | **1,000** | Prevents runaway loops |

**First wiki-captured authoritative confirmation of the 1,000-agent-cap** ([[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's "up to 1,000 per Dynamic Workflows run"]] framing is now Anthropic-canonical) + **the 16-concurrent-cap** (new wiki signal).

### `ultracode` keyword + `/effort ultracode` mode

Two trigger mechanisms:
- **Keyword in prompt**: include `ultracode` literal in a prompt to trigger a single-task workflow run (natural-language *"use a workflow" / "run a workflow"* also works as opt-in).
- **`/effort ultracode` mode**: session-level setting that *plans a workflow for every substantive task* until session ends; resets on new session. Combines `xhigh` reasoning effort with automatic workflow orchestration. Available only on models that support `xhigh` effort.

**First wiki-captured `ultracode` keyword + `/effort ultracode` mode primitives**. Resolves the [[dailybrief-roundup-2026-06-01|effort-menu contradiction]] — `xhigh` effort is real and `ultracode` is a new session-level mode on top of it.

**Historical note from docs**: *"Before v2.1.160 the literal trigger keyword was `workflow`; natural-language requests work in both versions."* — first wiki-captured Claude Code version-specific keyword-history note.

### Bundled `/deep-research` workflow

Built-in workflow for cross-source research investigation:

> *"Fans out web searches on a question across several angles, fetches and cross-checks the sources it finds, votes on each claim, and returns a cited report with claims that didn't survive cross-checking filtered out. Requires the WebSearch tool to be available."*

**First wiki-captured authoritative `/deep-research` command spec** — *fan-out + cross-check + vote-on-each-claim + cited-report-with-filtered-claims*. The wiki's `/autoresearch` pattern is structurally parallel; pattern-watch is whether `/deep-research` becomes the canonical naming or whether practitioner-content sticks with autoresearch / similar conventions.

### `/workflows` management interface — first wiki-captured TUI key-binding catalog

| Key | Action |
|---|---|
| `↑` / `↓` | Select a phase or agent |
| `Enter` or `→` | Drill into phase, then into agent (read prompt, recent tool calls, result) |
| `Esc` | Back out one level |
| `j` / `k` | Scroll within agent detail when it overflows |
| `p` | Pause or resume the run |
| `x` | Stop selected agent, or stop whole workflow when focus is on the run |
| `r` | Restart selected running agent |
| **`s`** | **Save the run's script as a command** |

**First wiki-captured concrete `/workflows` TUI binding catalog**. The `s` binding is structurally significant — it's the operationalization of *codifying-the-orchestration* (the workflow's load-bearing property per the comparison table).

### Save semantics — `.claude/workflows/` schema

Two save locations:
- **`.claude/workflows/` in project** — shared with everyone who clones the repo
- **`~/.claude/workflows/` in home directory** — available in every project, visible only to you

If both share a name, **project workflow wins**.

**Pairs structurally with the `.claude/agents/<role>.md` schema** ([[zodchii-4-agent-pipeline-2026-05-30|zodchii pipeline]] + [[rody-5-subagent-templates-2026-05-31|@0x_rody's 5 templates]]) — **`.claude/workflows/` is the parallel orchestration-side primitive to `.claude/agents/` worker-side primitive**. **First wiki-captured complete dual-primitive Claude Code project-shared agent-architecture convention** (`.claude/agents/<role>.md` for workers + `.claude/workflows/<name>.js` for orchestration).

### `args` parameter for parameterized workflows

> *"A saved workflow can accept input through the `args` parameter. The script reads it as a global named `args`. Use this to supply a research question, a list of target paths, or a configuration object at invocation time instead of editing the script for each run."*

Example: `Run /triage-issues on issues 1024, 1025, and 1030` — Claude passes the list as structured data; script calls array/object methods on `args` directly without parsing. **First wiki-captured Claude Code structured-args invocation primitive** for saved workflows.

### Permission-mode behavior — operationally significant for Auto mode

| Permission mode | When prompted |
|---|---|
| Default, accept edits | Every run, unless you've selected *"Yes, and don't ask again"* for this workflow in this project |
| **Auto** | **First launch only.** Any *Yes* records consent in user settings; later launches start without prompting. **Skipped entirely when ultracode is on** |
| Bypass permissions, `claude -p`, Agent SDK | Never. Run starts immediately |

**Subagents always run in `acceptEdits` mode regardless of session mode**. File edits are auto-approved. Shell commands / web fetches / MCP tools not in allowlist can still prompt mid-run. **First wiki-captured concrete Auto-mode + ultracode-mode interaction model** — Auto + ultracode means *zero prompts*, which is the most-permissive practitioner-tier configuration.

### Cost / token framing

> *"A workflow spawns many agents, so a single run can use meaningfully more tokens than working through the same task in conversation. Runs count toward your plan's usage and rate limits like any other session."*

Cost-management guidance:
- Run on a small slice first (one directory; narrow question)
- `/workflows` view shows per-agent token usage as run progresses
- Stop the run at any time without losing completed work
- Agent caps bound the runaway-cost ceiling
- Every agent uses session's model unless script routes a stage to a different one
- Check `/model` before large runs; ask Claude to use smaller model for stages that don't need the strongest one

**Pairs with [[uber-ai-tool-cap-1500-2026-06-03|Uber $1,500/mo per-employee cap]]** — Dynamic Workflows are *the most token-intensive Claude Code primitive*, and the cost-management framing in the docs explicitly recommends running-on-small-slice-first. **First wiki-captured Anthropic-canonical guidance for managing the token-amplification effect** that drives operator-side spend ceilings.

### Disable mechanisms (organizational + individual)

- Individual: toggle in `/config`, set `"disableWorkflows": true` in `~/.claude/settings.json`, or set `CLAUDE_CODE_DISABLE_WORKFLOWS=1` env var
- Organizational: set `"disableWorkflows": true` in managed settings, or use Claude Code admin settings toggle

When disabled: bundled workflow commands unavailable, `ultracode` keyword no longer triggers, `ultracode` removed from `/effort` menu.

**First wiki-captured admin-settings-page reference for Claude Code organizational controls** (`claude.ai/admin-settings/claude-code`).

### Availability matrix

- **Plans**: all paid plans (Pro requires turning on in `/config`)
- **APIs**: Anthropic API access, **Amazon Bedrock**, **Google Cloud Vertex AI**, **Microsoft Foundry**
- **Surfaces**: CLI, Desktop app, IDE extensions, non-interactive mode (`claude -p`), Agent SDK
- **Minimum version**: **Claude Code v2.1.154+**

**First wiki-captured concrete 3-cloud-provider availability for Anthropic frontier-product** (Bedrock + Vertex + Foundry). Pairs with [[anthropic-spacex-higher-limits-2026-05-06|substrate-tier compute lock-in]] framing — Anthropic is operationally distribution-multi-cloud at the Dynamic Workflows tier.

## Pages Updated

- [[claude-code]] — Dynamic Workflows section expanded with full docs reference; `ultracode` keyword + `/effort ultracode` mode added; runtime constraints (16/1000) added; `/workflows` TUI key-binding catalog added; `.claude/workflows/` save-location convention added
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — back-link to canonical docs added
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — "up to 1,000 per Dynamic Workflows run" framing now Anthropic-canonical confirmed
- [[claude-md-pattern]] — `.claude/workflows/` parallel-primitive to `.claude/agents/<role>.md` schema noted
- [[autoresearch]] — `/deep-research` bundled workflow as Anthropic-canonical naming; pattern-watch on convention convergence

## Adjacent sources

- [[anthropic-dynamic-workflows-primary-2026-05-28]] — May 28 preview-ship announcement
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — Opus 4.8 launch-positioning context
- [[nateherk-dynamic-workflows-2026-05-30]] — Nate Herk 41-Haiku case study with up-to-1,000 framing
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq Shihipar's harness practitioner blog (companion to canonical docs)
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — practitioner-side setup-guide framing
- [[rody-5-subagent-templates-2026-05-31]] — `.claude/agents/<role>.md` schema (paired primitive to `.claude/workflows/<name>.js`)

## Verification-pending

- Whether the v2.1.154 minimum-version requirement is the official ship-version or post-ship-stabilization version
- Whether `xhigh` effort is the only `/effort` level supporting `ultracode`, or whether other levels can be configured
- Specific Pro-tier `/config` toggle text for Dynamic Workflows
- Whether Bedrock + Vertex + Foundry distribution implies Anthropic API parity, or whether some constraints (like 1,000-agent cap) vary by cloud
- Whether `args` accepts non-JSON-serializable types (functions, classes, etc.)
- Specific structure of the `disableWorkflows` managed-settings JSON
