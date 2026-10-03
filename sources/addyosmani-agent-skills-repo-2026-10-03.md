---
title: "addyosmani/agent-skills — production-grade engineering skills for AI coding agents"
type: source
medium: github-repo
url: https://github.com/addyosmani/agent-skills
published: 2026-10-03
ingested: 2026-10-04
---

## Summary

**[[addy-osmani|Addy Osmani]]** — ex-Google, now on the [[claude-code|Claude Code]] team — published **25 skills** encoding *"the workflows, quality gates, and best practices that senior engineers use."* Surfaced via @undefinedKi: *"an Anthropic engineer packed his whole engineering workflow into agent skills, so anyone can copy it… **his repo turns a coding agent into a senior engineer.**"*

**24 lifecycle skills plus a `using-agent-skills` meta-skill**, organised by phase: **Meta → Define → Plan → Build → Verify → Review → Ship.**

## Key Claims / Takeaways

### The four stated design principles

> - **"Process, not prose.** Skills are workflows agents follow, not reference docs they read. Each has steps, checkpoints, and exit criteria."
> - **"Anti-rationalization.** Every skill includes a table of **common excuses agents use to skip steps** (e.g., 'I'll add tests later') **with documented counter-arguments.**"
> - **"Verification is non-negotiable.** Every skill ends with evidence requirements — tests passing, build output, runtime data. **'Seems right' is never sufficient.**"
> - **"Progressive disclosure.** The `SKILL.md` is the entry point. Supporting references load only when needed."

### Four agent personas, for targeted review

| Persona | Standard it applies |
|---|---|
| **code-reviewer** (Senior Staff Engineer) | five-axis review against *"would a staff engineer approve this?"* |
| **test-engineer** (QA Specialist) | test strategy, coverage, and *"the Prove-It pattern"* |
| **security-auditor** (Security Engineer) | vulnerability detection, threat modelling, OWASP |
| **web-performance-auditor** | Core Web Vitals, Quick/Deep modes, **"a metric-honesty rule"** |

With an explicit orchestration constraint: **"personas don't invoke personas."**

### Seven reference checklists

`definition-of-done` (*"project-wide standing bar every change clears, contrasted with per-task acceptance criteria"*), `testing-patterns`, `security-checklist`, `performance-checklist`, `accessibility-checklist`, `observability-checklist` (on-call questions, RED/USE metrics, symptom-based alerting, pre-launch gate), `orchestration-patterns`.

### Two adoption paths

*"The full lifecycle from day one for a greenfield project, or an **incremental, verification-first rollout** for an established codebase."*

## Judgment

**The anti-rationalization table is the novel contribution and the wiki has nothing like it.** A table of *"common excuses agents use to skip steps, with documented counter-arguments"* treats the agent as a party that will rationalize its way around a gate — which is a sharper model of the failure than "the agent forgot." It is the authoring-side counterpart to the finding that [[undefinedki-how-to-design-an-agent-harness-2026-08-15|a rule in prose gets skimmed and a rule in a linter does not]]: **if you cannot make the rule mechanical, pre-refute the excuse.**

**"Process, not prose" names the distinction [[skill-md]] has been circling.** The wiki's cleanest prior definition was *"skills are just context and instructions… lazy ways to do repeated work."* **That describes a macro. This describes a workflow with checkpoints and exit criteria**, which is a different artifact — and it explains why skill quality varies so much between packs.

**The `definition-of-done` / acceptance-criteria split is the right structural distinction** and the wiki has been conflating them: a project-wide standing bar is not the same object as a per-task criterion, and [[undefinedki-how-to-design-an-agent-harness-2026-08-15|the "write your stopping rule in one sentence"]] advice needs both.

**Where this sits against [[gstack]].** Both are skill packs implementing a review-gated lifecycle from a named principal — gstack's 23 skills across Think → Plan → Build → Review → Test → Ship → Reflect, this one's 25 across Meta → Define → Plan → Build → Verify → Review → Ship. **Two independent packs converging on a seven-stage gated loop, by a YC president and an Anthropic engineer, is the strongest available evidence that the lifecycle shape is real rather than one person's taste.** The notable divergence: **gstack has `/retro` and this pack has no reflection stage** — the accretion step is in one and absent from the other.

**Caveats.** **Repo README only — no skill content read, no installation, no evaluation, and no independent practitioner receipts.** Adoption is a Trendshift badge. The author is an Anthropic employee publishing skills for Anthropic's product, which is not a conflict but is not independent either. **Not tested by the owner.**

## Pages Updated

- [[skill-md]]
- [[addy-osmani]]
- [[claude-code]]
