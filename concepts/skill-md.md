---
name: SKILL.md
type: concept
maturity: emerging
last_updated: 2026-07-12
---

## Definition

**SKILL.md** is the file-based primitive for packaging a reusable capability — a named, described procedure (often with tools/scripts) that a coding agent loads on demand to perform a specific task end-to-end. Where [[claude-md-pattern|CLAUDE.md]] tells the agent *how to behave* in a project and OKF-style knowledge tells it *what it knows*, a SKILL.md tells it *how to do a specific job* — and crucially encodes the **verification** of that job so the agent can self-check its work.

## Why It Matters

SKILL.md is the unit of **outer-loop memory** in [[loop-engineering|loop engineering]]: the file that outlives the conversation and carries a lesson forward, so the agent isn't re-taught every run. The official [[claude-code-getting-started-loops-2026-07-06|Claude Code loops taxonomy]] makes it the hand-off for *turn-based loops* — you "hand off the check" by encoding your manual QA as a `SKILL.md` (e.g. the `verify-frontend-change` example). When a loop's output misses the bar, the durable fix is to encode it into a skill so all future iterations improve, not just the one.

## Current State

- **Packaged, branded, installable catalogs (2026-07-12)**: [[charliejhills-claude-whole-company-42-skills-2026-07-12|Charlie Hills' "Build Your Whole Team with Claude"]] lays out **42 skills as a company org chart** (`claude-code` = "the operating system"), every tile a real install from a mix of first-party (`github.com/anthropics/skills`, `claude.com/plugins/{finance,small-business,legal}`) and third-party OSS (`obra/superpowers`, `upstash/context7`, `thedotmack/claude-mem`, …). Signals SKILL.md graduating from a per-capability primitive into a **distribution ecosystem** with a long OSS tail and a consumer-legible "company-as-a-stack-of-skills" packaging. The bundled department plugins claim ~100+ skills total (Marketing 45, Small Business 31, …), of which 42 are the curated chart.
- **Plugin-level substrate**: surfaced as the Skills half of the `commands/` + `skills/` plugin structure in the wiki owner's [[hornof-knowledge-work-plugins-claude-cowork-2026-06-17|knowledge-work-plugins]] — file-based markdown + JSON, no code or build steps.
- **Operator-discipline pattern**: [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|0xMovez's playbook]] frames "save the workflow as a Skill" and "turn verify-feedback into a permanent rule" as core self-improving-loop steps — the Document-to-Skill vs Skill-captures-process distinction.
- Adjacent to vendor-neutral siblings (AGENTS.md) and project-root discipline files (CLAUDE.md, CONSTRAINTS.md).

## Related Concepts

- [[claude-md-pattern]] — project-behavior file; SKILL.md is the per-capability sibling.
- [[loop-engineering]] — SKILL.md as outer-loop persistent memory + the verifier's home.
- [[claude-code-getting-started-loops-2026-07-06]] — turn-based loops "hand off the check" via SKILL.md.
