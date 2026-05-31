---
title: "@0x_rody: Build Your First Claude Code Subagent in 15 Minutes (5 ready-to-use templates)"
type: source
medium: twitter-thread
url: https://x.com/0x_rody/status/2061019244595233135
ingested: 2026-05-31
---

## Summary

@0x_rody publishes a substantive practitioner-content piece (2026-05-31) with **5 ready-to-use Claude Code subagent templates** + copy-paste-ready frontmatter + invocation syntax + cost-discipline framing. Surfaced via [[zodchii|@zodchii]]'s X amplification (zodchii's 3rd wiki surface; attributes the quote to *"Anthropic engineer"* — **verification-pending whether @0x_rody is actually Anthropic-affiliated**). **Substantially extends the [[zodchii-4-agent-pipeline-2026-05-30|zodchii 4-agent pipeline]] template surface** with standalone single-purpose subagents + new Claude Code primitives (**`@agent-name` invocation**, **`/agents` command**, **auto-delegation via description field**, **`~/.claude/agents/` global vs `.claude/agents/` project distinction**).

## Key Claims / Takeaways

### The 5 templates shipped

| # | Agent | Tools | Model | Output |
|---|---|---|---|---|
| 1 | **reviewer** | Read, Grep, Glob, Bash | Sonnet 4.5 | `git diff` → categorized CRITICAL/WARNING/INFO findings |
| 2 | **test-writer** | Read, Grep, Glob, Write, Bash | Sonnet 4.5 | Happy path + edge + error tests; runs them; fixes failures |
| 3 | **doc-writer** | Read, Grep, Glob, Write | Sonnet 4.5 | JSDoc + inline comments (WHY not WHAT) + API docs |
| 4 | **security** | Read, Grep, Glob, Bash | Sonnet 4.5 | Hardcoded-secrets scan + SQL/XSS check + npm audit; report-only, never fixes |
| 5 | **pr-writer** | Read, Grep, Glob, Bash | Sonnet 4.5 | What/Why/Changes/Testing structured PR description |

**All 5 templates ship with copy-paste-ready markdown including frontmatter (`name` / `description` / `model` / `tools`) + system prompt with explicit "When invoked" + output format**. First wiki-captured **standalone single-purpose subagent template set** (5 templates for 5 distinct daily-tasks) — complement to [[zodchii-4-agent-pipeline-2026-05-30|zodchii's pipeline-composition template]] which uses 4 agents *chained* via handoff-files.

### New Claude Code primitives surfaced

**Storage location distinction** (first wiki-captured):
- **`~/.claude/agents/`** → available in *every project* (personal, global)
- **`.claude/agents/`** → *this project only* (shared with team via git)

**Pairs with [[zodchii-4-agent-pipeline-2026-05-30|zodchii's `.claude/agents/<role>.md` schema]]** — zodchii's pipeline used project-scoped agents; @0x_rody adds the *global-vs-project* distinction.

**`@agent-name` invocation syntax** (first wiki-captured):
```
@reviewer check the last commit
@test-writer write tests for auth.ts
@security scan src/
```

**Three invocation paths**:
1. **`@`-mention** (most reliable; explicit)
2. **Auto-delegation** — Claude reads the description field and picks the appropriate agent
3. **`/agents` command** — opens the agent library; **Running tab** (active subagents) + **Library tab** (browse/create/edit)

**Auto-delegation discipline rule (load-bearing)**:
> *"For auto-delegation to work, make the description field specific. 'Use this agent when the user asks for code review' works. 'Code stuff' doesn't."*

**First wiki-captured concrete-discipline-rule for Claude Code subagent auto-delegation.** The principle: **description-as-trigger-condition** — the description field IS the auto-routing predicate. Pairs structurally with [[claude-md-pattern|CLAUDE.md pattern]] *"every rule should answer 'what specific mistake does this prevent?'"* — same operator-discipline principle (specificity → behavior) applied at the agent-routing layer.

### Subagent cost-discipline framing

**Without subagents**: one session does everything; context bloats to 200K+ tokens by message 20; every subsequent message costs more; autocompact loses context.

**With subagents**:
- Main session stays at **~30K tokens**
- Each subagent uses **~15-20K tokens in isolation**
- Summaries return to main session (**~500 tokens**)
- **Total tokens might be similar but quality is higher**
- **Route subagents to Sonnet → 5× cheaper per agent**

```bash
export CLAUDE_CODE_SUBAGENT_MODEL="claude-sonnet-4-5-20250929"
```

**Confirms zodchii's prior env-var surfacing** ([[zodchii-opus-4-8-setup-guide-2026-05-29]]); @0x_rody adds the *cost-math* framing that justifies it. **The real savings**: routing subagents to Sonnet while main session runs Opus → ~5× cost reduction per subagent invocation. Pairs with:
- [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's routing matrix]] for single-agent task-level routing
- [[nateherk-dynamic-workflows-2026-05-30|Nate Herk's 41-Haiku case study]] at the Dynamic Workflows scale

### Subagent anatomy (canonical schema confirmed)

@0x_rody's frontmatter format **matches [[zodchii-4-agent-pipeline-2026-05-30|zodchii's `.claude/agents/<role>.md` canonical schema]]**:

```yaml
---
name: agent-name
description: When to use this agent. Be specific.
model: claude-sonnet-4-5-20250929
tools:
  - Read
  - Grep
  - Glob
  - Bash
---

You are a [role]. Your job is to [specific task].

When invoked:
1. Do [step 1]
2. Do [step 2]
3. Return [specific output format]
```

**Same schema across two practitioner surfaces in 4 days**. The schema is now wiki-canonical:
- `name` — invocation identifier
- `description` — auto-delegation trigger predicate (specificity matters)
- `model` — explicit per-agent routing
- `tools` — explicit capability scoping (read-only for reviewers/scanners; full access for writers)

The body below frontmatter is the **system prompt** — *"this is where you tell the agent exactly how to behave."*

### Read-only-tools pattern recurs

3 of @0x_rody's 5 templates use **read-only tools** (reviewer, security) or **almost-read-only** (doc-writer can Write only docs; pr-writer Read+Grep+Glob+Bash for git inspection):

> Security agent: *"Do NOT fix issues, only report them."*
> Reviewer agent: *"If no issues found, say 'Code looks good'… Do NOT suggest changes that aren't improvements."*
> Doc-writer agent: *"Never change functionality, only add documentation."*

**Pairs directly with [[zodchii-4-agent-pipeline-2026-05-30|zodchii's Reviewer read-only architectural pattern]]**: *"Read-only tools mean the Reviewer can't paper over problems by editing, it can only judge."* **Same operator-side principle across two practitioner surfaces**: constrain by what the agent can do, not what you ask it not to do. Pairs structurally with [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's instructions-vs-capabilities lesson]] (the 150,000-inbox story).

### Strategic positioning vs zodchii's pipeline pattern

@0x_rody's 5-template set is **complementary, not redundant** to [[zodchii-4-agent-pipeline-2026-05-30|zodchii's 4-agent pipeline]]:

| Pattern | Composition | Use case |
|---|---|---|
| **zodchii pipeline** (May 30) | 4 agents *chained* via `.pipeline/` handoff-files + `/ship` orchestrator | End-to-end feature delivery (Planner → Coder → Tester → Reviewer) |
| **@0x_rody templates** (May 31) | 5 *standalone* agents invoked individually via `@agent` or auto-delegation | Daily-task augmentation (review, test, document, security, PR-description) |

**Both patterns use the same `.claude/agents/<role>.md` schema** — the schema is now demonstrably *load-bearing across composition styles*. Practitioner-side convergence on the schema is meaningful: a directory of `.claude/agents/*.md` files + a directory of `.claude/commands/*.md` files (per zodchii) + `~/.claude/agents/*.md` for personal-global agents (per 0x_rody) = **canonical Claude Code agent-and-skill layout** as of late May 2026.

### Comment-thread amplification (load-bearing)

Eclipse (@ECLresearch): *"The gap isn't ability—it's workflow inertia. A single 45-min demo breaking manual dev loops is more convincing than any benchmark."* — pairs with [[ai-roi-gap]] *"discipline is the hidden capability"* framing. **The blocker isn't capability, it's habit.**

@poly_enjoyer: *"most people watch demos. habit wins over time saved."* — same point at the operator-psychology level. **First wiki-captured concrete-articulation of the practitioner-content register's load-bearing-objection**: *demos don't change behavior; habits do*.

### zodchii's amplification framing

> *"Anthropic engineer: 'You can build 5 assistants in one afternoon. Each one handles a task you've been doing manually every single day.'"*

**zodchii attributes the @0x_rody post to *"Anthropic engineer"*** — verification-pending whether @0x_rody is actually Anthropic-affiliated:
- @0x_rody's article doesn't claim Anthropic affiliation
- The X handle (`0x_rody` — hacker-style `0x` prefix + "rody") could plausibly be an Anthropic engineer's personal handle
- zodchii's paraphrase *"You can build 5 assistants in one afternoon"* isn't verbatim from @0x_rody's article (which says *"build a code reviewer, a test writer… in under 15 minutes"*) — likely zodchii's framing rather than @0x_rody's direct claim

**Worth tracking**: confirm @0x_rody's affiliation. If Anthropic-internal, the templates are first wiki-captured *Anthropic-engineer-published* subagent templates outside the official [[anthropic-knowledge-work-plugins-2026-05-31|knowledge-work-plugins repo]].

### What's notably absent

- **@0x_rody's affiliation** — zodchii claims Anthropic; verification-pending
- **The 45-minute video** (per zodchii's framing) — primary not fetched
- **Performance / cost data** for the 5 templates at scale
- **Cross-vendor compatibility** — these templates use Claude Code-specific frontmatter (`tools: - Read`); whether Codex / Cursor parse the same format
- **Whether the templates ship in a public repo** vs being copy-paste-from-thread

## Pages Updated

- [[zodchii]] — 3rd wiki surface (amplification of @0x_rody); *"Anthropic engineer"* attribution flagged as verification-pending
- [[claude-code]] — **4 new primitives added**: `@agent-name` invocation syntax + `/agents` command (Library + Running tabs) + auto-delegation via description field + `~/.claude/agents/` (global) vs `.claude/agents/` (project) distinction
- [[claude-md-pattern]] — *"description-as-trigger-condition"* discipline noted as agent-routing-layer expression of the broader *"every rule should answer 'what specific mistake does this prevent?'"* principle
- [[anthropic-knowledge-work-plugins-2026-05-31]] — cross-reference: @0x_rody's standalone-single-purpose-subagent template set as complement to the Anthropic-official plugin repo
- @0x_rody himself — no entity page; defer until cross-referenced (zodchii's amplification is 1 wiki surface; @0x_rody's article is the substantive source but single-author-single-piece for now)

Verification-pending: @0x_rody's Anthropic affiliation; the 45-minute YouTube video content; whether templates ship in a public repo; cross-vendor compatibility.

## Adjacent sources

- [[zodchii-4-agent-pipeline-2026-05-30]] — paired pipeline-composition template using same `.claude/agents/<role>.md` schema
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — prior zodchii surface; first surfaced `CLAUDE_CODE_SUBAGENT_MODEL` env var
- [[nateherk-dynamic-workflows-2026-05-30]] — same-week Dynamic Workflows cost-discipline framing
- [[anthropic-knowledge-work-plugins-2026-05-31]] — Anthropic-official plugin-distribution repo (complement to practitioner-distributed templates)
- [[claude-md-pattern]] — file-based behavioral-contract discipline cluster
