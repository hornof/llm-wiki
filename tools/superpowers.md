---
name: Superpowers
type: tool
category: framework
status: gaining-traction
last_updated: 2026-07-12
---

## What It Is

**Superpowers** (by **Jesse Vincent** / `obra`, at Prime Radiant) is *"an agentic skills framework & software development methodology that works"* — a [[claude-code|Claude Code]] plugin that bundles a pack of [[skill-md|skills]] enforcing a disciplined dev workflow: the agent asks clarifying questions, brainstorms and refines a spec, presents a design for validation, writes a detailed plan, then executes via **subagent-driven development** with code-review checkpoints. It is the "Skill Forge / 14-skill power pack" tile (Developers dept) in [[charliejhills-claude-whole-company-42-skills-2026-07-12|Charlie Hills' "Claude as a company" chart]].

## Traction Signals

- **~253k GitHub stars / ~22.6k forks** (per [github.com/obra/superpowers](https://github.com/obra/superpowers), 2026-07-12) — among the highest-starred agent-skills repos captured in this wiki; at mainstream-adoption scale, though this is a conservative first capture.
- **Official-marketplace distribution**: installable via Anthropic's official plugin marketplace (`/plugin install superpowers@claude-plugins-official`) — first-party channel, not just a raw repo.
- **Cross-agent reach**: install paths documented for Claude Code, [[antigravity|Antigravity]], Cursor, GitHub Copilot CLI, Kimi Code, [[codex|Codex]], Factory Droid, and Pi — a portability signal beyond a single harness.
- Active release cadence (v6.1.1 latest as of 2026-07); MIT-licensed.

## How to Use It

- **Claude Code**: `/plugin install superpowers@claude-plugins-official`
- Skills trigger **automatically** based on the task — no manual invocation. Bundles 7+ core skills: `test-driven-development`, `systematic-debugging`, `brainstorming`, `writing-plans`, `subagent-driven-development`, `requesting-code-review`, `using-git-worktrees`.

## Key Concepts

- **Subagent-driven development** — dispatch a fresh agent per task with two-stage review (the maker-checker discipline from [[loop-engineering]]).
- **RED-GREEN-REFACTOR** — test-first cycle enforced before implementation.
- **YAGNI** — minimal-code / no-speculative-features principle (echoes the [[claude-md-pattern|CLAUDE.md]] "Simplicity First" rule).
- **Skill** — composable workflow module that triggers automatically.

## Compared To

- **[[skill-md|SKILL.md]] generally** — Superpowers is a curated, opinionated *bundle* of skills + a methodology, versus a single hand-rolled skill.
- **[[claude-mem]] / [[context7]]** — sibling third-party Claude-skill packs in the same emerging OSS ecosystem, but Superpowers is workflow/methodology-focused (how to build), where claude-mem is memory and context7 is docs-retrieval.

## Resources
- [github.com/obra/superpowers](https://github.com/obra/superpowers) — MIT; Jesse Vincent / Prime Radiant
- [[charliejhills-claude-whole-company-42-skills-2026-07-12]] — surfaced as the Developers "Skill Forge" tile
