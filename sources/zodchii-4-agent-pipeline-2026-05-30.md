---
title: "zodchii: 4-agent pipeline ships features while you sleep (Planner→Coder→Tester→Reviewer + Teamly product placement)"
type: source
medium: twitter-thread
url: https://x.com/zodchiii/status/2060674246880149900
ingested: 2026-05-31
---

## Summary

[[zodchii|@zodchii]]'s 2nd substantive wiki source (2026-05-30; follow-up to the [[zodchii-opus-4-8-setup-guide-2026-05-29|prior-day Opus 4.8 setup guide]]). **zodchii crosses the single-source-defer threshold and gets an entity page.** The post is a **canonical 4-agent pipeline pattern**: **Planner (Opus) → Coder (Sonnet) → Tester (Sonnet) → Reviewer (Opus)** with **handoff-files** in `.pipeline/{spec,changes,test-results,review}.md` and an **orchestrator slash command** at `.claude/commands/ship.md`. Each agent gets its own `.claude/agents/<role>.md` definition with explicit `tools:` and `model:` frontmatter. **First wiki-captured complete 4-agent pipeline pattern with full copy-paste-ready agent definitions + orchestrator command.** The post ships with a **Teamly product placement** ($29/mo for 5 agents; managed cloud hosting for AI agents) — captured as an emerging *paid-managed-agent-hosting* surface separate from Claude Code itself.

## Key Claims / Takeaways

### The 4-agent pipeline shape (canonical)

| Stage | Agent | Model | Read-only? | Reads | Writes |
|---|---|---|---|---|---|
| 1 | **Planner** | Opus | No (writes spec) | Codebase (Read/Grep/Glob) | `.pipeline/spec.md` |
| 2 | **Coder** | Sonnet | No (writes code) | `.pipeline/spec.md` | code files + `.pipeline/changes.md` |
| 3 | **Tester** | Sonnet | No (writes tests) | `.pipeline/changes.md` + spec + changed files | tests + `.pipeline/test-results.md` |
| 4 | **Reviewer** | Opus | **Yes** (read-only tools only) | spec + changes + test-results + `git diff` | `.pipeline/review.md` with `VERDICT: SHIP / NEEDS WORK / BLOCK` |

**The handoff-file pattern is the load-bearing primitive**: each agent writes its output where the next one reads from. Pairs structurally with:
- [[heeki-spec-driven-development-2026-02-28|Heeki Park's spec-driven workflow]] — same shape at single-agent layer; zodchii operationalizes it as multi-agent pipeline
- [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's Four C's]] — Context-as-handoff-files-between-agents is the multi-agent analogue of Context-as-foundation
- [[claude-md-pattern|CLAUDE.md pattern]] — handoff-files are *behavioral-contracts between agents*, not just human → agent

### Model-routing within the pipeline (operational discipline)

- **Opus for Planner**: *"this stage sets the quality ceiling for everything after it. A vague spec produces vague code no matter how good the Coder is."*
- **Sonnet for Coder**: *"implementation against a clear spec is exactly the balanced cost-quality work Sonnet handles best."*
- **Sonnet for Tester**: same justification
- **Opus for Reviewer**: quality-gate at the end + read-only-tools-prevent-papering-over-problems

**Pairs with [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's prior-day routing matrix]]** — the prior post was *task → model* routing for a single agent; this post is *agent-role → model* routing for a pipeline. **Same operator-discipline principle at different altitudes.**

### Canonical `.claude/agents/` and `.claude/commands/` layout

zodchii ships **complete copy-paste-ready agent and command definitions**. First wiki-captured complete-pipeline file layout:

```
.claude/
├── agents/
│   ├── planner.md   (Opus, name+description+tools+model frontmatter)
│   ├── coder.md     (Sonnet)
│   ├── tester.md    (Sonnet)
│   └── reviewer.md  (Opus, read-only tools)
└── commands/
    └── ship.md      (orchestrator slash command)
```

The agent frontmatter format is **first wiki-captured canonical agent-definition schema**:
```markdown
---
name: planner
description: Turns a feature request into an implementation spec. Use as the first stage of the feature pipeline.
tools: Read, Grep, Glob, Write
model: opus
---
```

**Pairs with [[heeki-spec-driven-development-2026-02-28|Heeki Park's SKILL.md-as-project-emergent-artifact]]** — Heeki's SKILL.md is *workflow*; zodchii's `.claude/agents/*.md` is *agent specifications*. Two distinct file-based primitives that together compose the Claude Code agent-and-skill artifact layer.

### The Reviewer's read-only-tools discipline (load-bearing safety pattern)

> *"Read-only tools mean the Reviewer can't paper over problems by editing, it can only judge."*

**Direct cross-cut with [[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's instructions-vs-capabilities lesson]]**: tools given to an agent are *capabilities*; removing tools is the *guardrail*. zodchii's Reviewer demonstrates the same principle as architectural pattern — *constrain by what the agent can do, not what you ask it not to do.* **Same operator-side principle, two practitioner surfaces, same week.**

### The orchestrator slash command pattern

The `.claude/commands/ship.md` orchestrator is **deceptively simple** — natural-language instructions that delegate to each subagent in order, with explicit `wait for X file` gates between stages:

```text
Run the full feature pipeline for: $ARGUMENTS

Execute these stages in order. Do not skip ahead. After each stage,
confirm the handoff file exists before starting the next.

1. Delegate to the `planner` subagent...
2. If the spec has OPEN QUESTIONS, stop and show them to me...
3. Delegate to the `coder` subagent...
4. Delegate to the `tester` subagent...
5. Delegate to the `reviewer` subagent...

Report the final verdict. Do not merge anything. Leave the branch for
my morning review.
```

**Three load-bearing operator-control mechanisms in the orchestrator**:
1. **`wait for handoff file` between stages** — explicit synchronization
2. **`if OPEN QUESTIONS, stop and show them to me`** — explicit human-in-the-loop at planning ambiguity (cf. [[heeki-spec-driven-development-2026-02-28|Heeki Park's selectable-input clarifying-question pattern]])
3. **`Do not merge anything. Leave the branch for my morning review.`** — explicit no-autonomous-commit policy

**Pairs with [[nateherk-dynamic-workflows-2026-05-30|Nate Herk's Ladder framework]]**: zodchii's pipeline sits at **Rung 4 (Agent Team)** in Nate Herk's taxonomy — small crew that talks to each other through shared task list (the handoff files). **First wiki-captured concrete Rung-4 instantiation with copy-paste-ready definitions.**

### Teamly product placement (paid managed-agent-hosting surface)

zodchii's post heavily promotes **[Teamly](https://teamly.to/)** as the *managed cloud hosting* surface for the same pipeline pattern:

- **The Coordinator** = Teamly's managed equivalent of the `.claude/commands/ship.md` orchestrator + handoff files
- **My Team feature**: build a 2-4-agent team with 3-question setup; voice rules / forbidden phrases / integrations / team style (Strict / Casual / Creative)
- **Pricing**: $29/mo for 5 agents; 3-day free trial
- **Cross-domain**: *"the exact same orchestration runs a marketing team, a research team, or a support team"*

**First wiki-captured Teamly surface.** Strategic implication:
- **Pairs with [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows]] as the *vendor-managed analogue*** — Anthropic provides the orchestration primitive inside Claude Code; Teamly provides the *managed cloud hosting wrapper* on top. **Two distinct form factors at two distinct value-capture points**: capability layer (Anthropic) vs deployment layer (Teamly).
- **Cross-vendor positioning**: Teamly's *"same orchestration runs marketing / research / support"* framing is the *cross-domain* extension of the pipeline pattern. Pairs with [[mattpocock-skills-repo-2026-05-30|Pocock's npm-installable cross-vendor skills]] as evidence that **skill-and-agent infrastructure is unbundling from any single vendor.**
- **Verification-pending**: whether Teamly's underlying engine uses Claude / Codex / cross-vendor; whether the handoff-file pattern is identical or proprietary; concrete customer signals beyond zodchii's promotion.

### What's notably absent

- **Teamly's actual underlying model layer** (Claude API? Codex? routed?)
- **Whether Teamly's "Coordinator" is open-source or proprietary**
- **Performance / cost data** for the 4-agent pipeline at scale — zodchii doesn't share an actual `/ship` invocation cost
- **Cross-comparison with [[anthropic-founders-playbook-2026-05|Anthropic's Founder's Playbook product matrix]]** (Chat / Cowork / Code) — the pipeline pattern would sit primarily in Claude Code
- **Skill-vs-agent distinction** — when does a pipeline stage warrant a Skill (reusable) vs an Agent (parallel-process)?

## Pages Updated

- [[zodchii]] — new entity page; 2nd wiki source crosses single-source-defer threshold
- [[claude-md-pattern]] — 4-agent pipeline + canonical `.claude/agents/*.md` file layout added as **9th+ practitioner-validation surface** (Stulberg + Zephyr + Capone + ShilpaMitra + Hassid + arps18 + Park + Nate Herk + zodchii)
- [[claude-code]] — `.claude/agents/<role>.md` + `.claude/commands/<name>.md` file layout schema added under practitioner-content; orchestrator slash command pattern noted
- [[nate-herk]] — Ladder-framework cross-reference (zodchii's pipeline = Rung 4 instantiation)
- [[saas-disruption-thesis]] — Teamly noted as emerging *managed-agent-hosting* surface; *"same orchestration runs marketing / research / support"* framing pairs with the [[gustaf-alstromer|YC AI-Native Service Companies RFS]] cross-domain extension

Verification-pending: Teamly's underlying model layer; whether Coordinator is open-source; pipeline cost-at-scale; pipeline-vs-skill-vs-agent distinction.

## Adjacent sources

- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — prior-day zodchii setup guide; routing-matrix discipline at single-agent layer
- [[nateherk-dynamic-workflows-2026-05-30]] — same-day Nate Herk Dynamic Workflows walkthrough; Ladder framework places zodchii's pipeline at Rung 4
- [[heeki-spec-driven-development-2026-02-28]] — single-agent spec-driven workflow that the pipeline operationalizes at multi-agent layer
- [[nateherk-opus-4-8-aios-2026-05-29]] — instructions-vs-capabilities lesson; zodchii's read-only-Reviewer is the architectural-pattern instantiation
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — vendor-side orchestration primitive that Teamly wraps as managed-hosting layer
