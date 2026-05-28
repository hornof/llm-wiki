---
title: "Heeki Park: Using spec-driven development with Claude Code"
type: source
medium: article
url: https://heeki.medium.com/using-spec-driven-development-with-claude-code-4a1ebe5d9f29
ingested: 2026-05-28
---

## Summary

[[heeki-park|Heeki Park]] (AWS solutions architect, Medium / heeki.medium.com, published Feb 28 2026, captured 2026-05-27) — substantive practitioner walkthrough of **spec-driven development with [[claude-code|Claude Code]]**. Anchors on **Birgitta Böckeler's three-level taxonomy** (spec-first → spec-anchored → spec-as-source). Builds a real AWS Bedrock AgentCore project: MCP server + Gateway + interceptor. **7th+ independent practitioner-validation surface for the [[claude-md-pattern|CLAUDE.md pattern]]**: Park reports *"frequently took learnings from the project and integrated them into my CLAUDE.md steering document and even ended up creating a SKILL.md at the end of the project."* Also surfaces **selectable-input clarifying-question pattern** (already captured in [[hassid-cowork-setup-2026-04-07|Hassid's setup]]) and **Bedrock-vs-Pro context-window tradeoffs**.

## Key Claims / Takeaways

### Birgitta Böckeler's three-level spec-driven taxonomy

- **Spec-first**: well-thought-out spec written first, then used in AI-assisted dev workflow
- **Spec-anchored**: spec kept after task completion, for evolution + maintenance
- **Spec-as-source**: spec is the *main source file* over time; only the spec is edited by the human, human never touches the code

Park's self-classification: *"my general inclination is mostly toward spec-first… though it's equally easy to go off and start implementing, leaving that one specification in the dust… that's not even spec-first but instead *spec-once* development."* Coins **spec-once** as the failure mode: spec launches the project, then gets forgotten.

**Source**: Böckeler, [Levels of Spec-Driven Development with AI](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html) (Martin Fowler blog).

### The build flow (real-world walkthrough)

1. **Read AWS CloudFormation + AgentCore docs first**; direct Claude Code to ingest the same docs so they share context.
2. **Decompose into modular sub-projects + phases** (red blocks / yellow phases in diagrams). Park's project: 2 sub-projects (interceptor stack + gateway stack), each with explicit phases.
3. **Heavy upfront planning**, writing all plans as a specification, then review the spec against design intent.
4. **Build stepwise in small testable chunks** — each stack independently testable.

### CLAUDE.md as continuously-updated steering artifact (7th+ practitioner surface)

- *"I frequently took learnings from the project and integrated them into my `CLAUDE.md` steering document and even ended up creating a `SKILL.md` at the end of the project."*
- *"I think custom skills creation will likely be a significant accelerator for future projects."*
- **Why this matters for [[claude-md-pattern]]**: Park's framing is **CLAUDE.md as a *living* artifact** — not authored once and forgotten, but updated as project learnings accrue. Pairs structurally with Park's spec-anchored vs spec-once framing (the same dynamic at the project-config level). **First wiki-captured practitioner surface that explicitly frames CLAUDE.md as continuously evolved during a single project rather than authored at startup.**
- **Adds SKILL.md as the project-emergent artifact** — surfaces alongside [[dac|bruin-data/dac's SKILL.md]] (which ships for both Claude Code and Codex) and [[writing-claude-code-skills|writing-claude-code-skills tutorial]]. Park's framing is that SKILL.md *emerges from* a finished project rather than being authored upfront.

### Practitioner techniques worth replicating

- **Instruct Claude Code to ask clarifying questions with selectable inputs** — pairs with [[hassid-cowork-setup-2026-04-07|Hassid's AskUserQuestion-based about-me.md interview]] pattern. *"It presents a set of options that I can then navigate via a menu of choices. It leaves the last option for open user input if needed."* **Same pattern named by two independent practitioner surfaces in 2026 (Hassid + Park) — practitioner-canonicalization signal for the selectable-input clarifying-question convention.**
- **Context-window tradeoffs**: 200K default on Pro / 1M on Max-20x (Park: *"womp womp"*). Bedrock direct (CLAUDE_CODE_USE_BEDROCK=1) supports 1M context on Opus 4.6 / Sonnet 4.6 / Sonnet 4.5 / Sonnet 4 *via beta header* `anthropic-beta: context-1m-2025-08-07` — but **Claude Code doesn't expose the beta-header flag**, so Bedrock users also stuck at 200K in practice.
- **Opus hits subscription usage limits faster than Sonnet** — Park hit Opus 4.6 sliding-window limits in 45-60 minutes of heavy use on Pro; Sonnet 4.6 lasted hours. Practical migration pattern: bounce between subscription Pro and Bedrock direct via `claude --resume <session_id>`.
- **Multiple parallel Claude Code sessions via tmux** (`tmux -CC` in iTerm2). Park: *"useful when experimenting with agent teams."*
- **Compaction observed at 3-5 min on the low end, 10-12 min on the high end** for 200K context fills.

### Architectural lessons

- **Time spent in upfront planning pays dividends for implementation efficiency.** Park's pre-AI shape: *"a few quick sentences as part of the initial prompt and get generating as soon as possible"* — produced course-correction churn. Post-spec-driven: *"most follow-up interactions were small tweaks rather than wholesale changes."*
- **Build security in sooner than later.** Park added OAuth2 Gateway authorization at the end, triggering full stack redeploy (Gateway `AuthorizerType` can't be changed in place; credential provider had to be `boto3`-created since CloudFormation didn't support it at the time). *"Fortunately, Claude Code handled this with relative ease."*
- **Stacked PRs reference** ([cjroth.com elite engineering culture](https://www.cjroth.com/blog/2026-02-18-building-an-elite-engineering-culture)): small reviewable PRs with explicit dependencies — pairs with the [[claude-md-pattern|CLAUDE.md pattern]] discipline thread.

### What's notably absent / verification-pending

- **Park's CLAUDE.md content**: not transcribed (would be valuable for the practitioner-validation surface cohort).
- **The exact spec content** that drove the project: linked to the project repo but specifics not in the article.
- **Whether the SKILL.md was committed to the project repo**: not specified.
- **Cross-vendor portability test** of Park's spec pattern (does it work as well on Codex / Cursor?): not tested.

## Pages Updated

- [[claude-md-pattern]] — Heeki Park added as **7th+ practitioner-validation surface** (Stulberg + Zephyr + Capone + ShilpaMitra + Hassid + arps18 + Park); new framing: **CLAUDE.md as continuously-evolved-during-project artifact** (not authored-once); SKILL.md as project-emergent artifact added
- [[claude-code]] — Bedrock-vs-Pro context-window tradeoffs (1M beta-header) captured; selectable-input clarifying-question pattern reinforced; tmux parallel-session technique referenced
- [[writing-claude-code-skills]] — SKILL.md emergence pattern (post-project rather than upfront) added if relevant section exists

Verification-pending: Park's CLAUDE.md content; whether SKILL.md was committed to the repo; cross-vendor portability of the spec pattern; whether spec-as-source level adoption is observable in practitioner-content surfaces yet.

## Adjacent sources

- [[hassid-cowork-setup-2026-04-07]] — selectable-input clarifying-question pattern co-validation
- [[dac]] — SKILL.md as the productized cross-vendor artifact (vs Park's project-emergent SKILL.md)
- [[forrest-chang]] — original CLAUDE.md 4-rule template; the floor of the practitioner cohort
- [[anthropic-founders-playbook-2026-05]] — frontier-lab-canonical builder enablement; Park's practitioner-content is the bottom-up complement to Anthropic's top-down playbook
