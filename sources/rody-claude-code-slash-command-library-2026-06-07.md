---
title: "0x_rody — How to Build a Claude Code Slash Command Library (Exact Template Inside) + Anthropic 'main manager' 26-min talk X amplification (2026-06-07)"
type: source
medium: article
url: https://x.com/0x_rody/status/2063549084695158936
ingested: 2026-06-08
---

## Summary

**rody (@0x_rody)** publishes (2026-06-07) **How to Build a Claude Code Slash Command Library (Exact Template Inside)** + companion same-day X post (`x.com/0x_rody/status/2063722061126651935`) framing the article around an Anthropic *"main manager"* 26-minute talk. **First wiki-captured comprehensive operator-side canonical practitioner-content guide on Claude Code slash-command libraries**. **Exact YAML + body template** + **7 ready-to-ship slash commands** (review / test / migrate / audit / doc / triage / refactor) + **15-minute on-ramp** + **5 common-mistakes-that-kill-your-slash-commands taxonomy**. Companion X post quotes Anthropic-internal voice: *"Nobody types prompts from scratch. The commands should be live in the project."* **2nd substantive 0x_rody wiki surface** (extends [[rody-5-subagent-templates-2026-05-31|May 31 5-template subagent guide]]) — confirms 0x_rody as wiki-tracked Claude Code-side practitioner-content register voice. Shares Telegram channel `t.me/zodchixquant` with [[zodchii]] (verification-pending whether same person or co-collaborators).

## Key Claims / Takeaways

### The pain-point framing

> *"You type the same 30-second instruction to Claude Code 20 times a week. That's roughly 10 hours a month spent re-typing context that should be a single command."*

**First wiki-captured concrete 10-hours/month productivity-loss-from-prompt-retyping figure**. Pairs with [[mit-ai-coding-elasticity-substitution-rohanpaul-2026-06-07|MIT verification-tax framing]]: re-typing prompts is the *practitioner-side analogue* of the verification-tax — paying the same cost-per-iteration when the cost should compound to zero with discipline.

### The Anthropic-internal voice receipt (companion X post)

> *"Anthropic's main manager: 'Nobody types prompts from scratch. The commands should be live in the project.' In 26 minutes, she walks through how Anthropic runs Claude Code, including the command library every new dev inherits on day one."*

**First wiki-captured "Anthropic main manager" 26-min talk-surface reference** with *"command library every new dev inherits on day one"* framing. Pairs with [[boris-cherny|Cherny's IDE-deleted-in-November + 259 PRs receipt]] at the **Anthropic-internal Claude Code operational-discipline articulation layer**. *"Main manager"* identity verification-pending — likely [[cat-wu|Cat Wu]] (Anthropic Head of Product, Claude Code) but not confirmed. **First wiki-captured "new-dev-inherits-command-library-on-day-1" onboarding-pattern framing for Claude Code-shop engineering orgs**.

### The 2-location slash-command file-system convention

> *"Two locations matter:*
> *`~/.claude/commands/` ← global, available in every project*
> *`.claude/commands/` ← per-project, commit to git for the team*
> *Filename becomes the command name. **review.md** becomes /review. Subfolders become namespaces: **.claude/commands/team/review.md** becomes /team:review."*

**First wiki-captured canonical 2-location slash-command file-system convention** + **first wiki-captured namespacing-via-subfolder convention** (`/team:review` ↔ `.claude/commands/team/review.md`). Pairs structurally with the canonical [[claude-md-pattern|CLAUDE.md project-rules tier]] + [[claude-cowork|.claude/agents/<role>.md schema]] (from [[zodchii-4-agent-pipeline-2026-05-30|zodchii's pipeline]]) at the **project-shared-vs-global-personal Claude-Code-config 2-location pattern** layer.

### The exact YAML + body template

```yaml
---
description: One-line summary that shows up in /help
argument-hint: <what-arguments-look-like>
allowed-tools: Read, Grep, Glob, Bash
model: sonnet
---

The prompt body goes here. Use $ARGUMENTS to insert whatever the user
typed after the command name. Use $1, $2, $3 for positional args.
```

**First wiki-captured exact-template canonical YAML frontmatter** for slash commands:
- **`description`**: load-bearing field — what Claude reads to pick the right command (parallels [[rody-5-subagent-templates-2026-05-31|0x_rody's description-as-trigger-condition discipline]] for subagents — *"For auto-delegation to work, make the description field specific"*)
- **`argument-hint`**: what arguments look like
- **`allowed-tools`**: scopes what the command can do (tighter scope = faster + safer)
- **`model`**: optional — haiku / sonnet / opus per task complexity (parallels [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's routing-matrix]])
- **`$ARGUMENTS`**: full argument string
- **`$1`, `$2`, `$3`**: positional args

### The 7 ready-to-ship commands

**First wiki-captured 7-command canonical Claude Code slash-command starter library**:

| Command | Model | Allowed-tools | Use-case |
|---|---|---|---|
| `/review` | sonnet | Read, Grep, Glob, Bash(git diff:*, git log:*) | Senior-code-reviewer for current diff; output Critical/Important/Nitpicks with file:line |
| `/test` | sonnet | Read, Write, Edit, Bash | Tests with edge-case / error-path / happy-path priorities; tests-that-fail-when-impl-is-wrong |
| `/migrate` | sonnet | Read, Edit, Grep, Glob, Bash | Pattern/library/version migration with grep-find-then-plan-then-edit-one-file-at-a-time discipline |
| `/audit` | **opus** | Read, Grep, Glob, Bash | Security audit — *"Be paranoid. Assume the input is hostile."* (only command using opus) |
| `/doc` | **haiku** | Read, Edit, Grep, Glob, Bash(git diff:*) | Update docs to match code; only fix sections that are wrong (not rewrite) |
| `/triage` | sonnet | Read, Grep, Glob, Bash | Bug-triage with reproduce-extract-locate-severity-fix-approach 5-step structure |
| `/refactor` | sonnet | Read, Edit, Bash | Plan-mode-first refactor with tests-before-and-after-each-change discipline |

**Pattern**: model-tier varies per task (haiku for routine doc updates / sonnet for most things / opus for security and complex reasoning). Pairs with [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii's 5-level effort menu]] at the **slash-command-layer model-routing discipline**. **First wiki-captured concrete per-slash-command model-routing rule-set** (1 haiku + 5 sonnet + 1 opus across 7 commands).

### The 15-minute on-ramp

**First wiki-captured 5-step canonical 15-minute Claude Code slash-command on-ramp**:

1. **3 min**: pick the one task you do 5+ times a week. Copy the matching template
2. **3 min**: tweak the prompt for your stack (test framework / linter / conventions)
3. **2 min**: save to `.claude/commands/{name}.md`
4. **2 min**: run it on a real task to confirm it works
5. **5 min**: build the next one

> *"Build one a day for a week and you'll have 7 commands handling 80% of your routine work, and the long instructions you used to retype every session become a single keystroke."*

**Pattern**: same 7-of-7 / 80%-of-work framing as [[khairallah-claude-projects-6-part-blueprint-2026-06-06|Khairallah's 5-projects-everyone-needs framing]] — *7 commands per practitioner / 5 projects per knowledge-worker / 6-part blueprint per project*. **First wiki-captured 3-surface practitioner-content-register convergence on 5-to-7-canonical-artifacts-per-domain framing** (Khairallah Projects + 0x_rody slash-commands + the implicit Cherny 5-tip recipe).

### 5-mistake taxonomy (kill-your-slash-commands)

**First wiki-captured 5-mistake taxonomy for slash-command failure modes**:

1. **Description too vague** — *"Review code" tells Claude nothing about when to use it. "Review the current diff for bugs, security, and style issues" is what you want.* (mirrors 0x_rody's prior [[rody-5-subagent-templates-2026-05-31|description-as-trigger-condition]] discipline for subagents)
2. **`allowed-tools` too loose** — defaults to inheriting everything; scope tight for sensitive paths
3. **`$1` confusion** — `$1` is only the first space-separated token; use `$ARGUMENTS` for whole string
4. **Wrong location** — project commands in `.claude/commands/`; global commands in `~/.claude/commands/`
5. **Not committing project commands to git** — `.claude/commands/` should be in repo so teammates inherit shortcuts on clone

### Comment-thread practitioner reactions

- **Kekko D'Amato**: *"'Nobody types prompts from scratch' should be a poster on every dev team's wall. The command library idea is basically productizing your own workflow — the people who do this once save hundreds of hours over time."* **First wiki-captured "productize your own workflow" framing for slash-command discipline.**
- **Nagarjuna Creates**: *"This setup with reusable commands makes a lot of sense. It turns AI into a real team member instead of just a helper you keep explaining things to. Smart way to scale."* **AI-as-team-member-not-helper framing.**
- **Moysha**: *"future is not prompts, it's command systems"* **First wiki-captured "command systems > prompts" register-evolution coinage** at the practitioner-content layer. Pairs with [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger Loop Engineering register coinage]] + [[loop-engineering|loop-engineering concept]] at the **4-stage practitioner-content-register evolution** (prompts → harnesses → loops → command-systems / fleets).
- **Rufus.eth**: *"Now main skill is prompt writing to be successful, right?"* (genuine question, suggests register-confusion at practitioner level)

## Cross-cutting framings

- **First wiki-captured comprehensive operator-side canonical guide on Claude Code slash-command libraries**
- **First wiki-captured exact YAML + body template** for slash commands
- **First wiki-captured 7-command canonical starter library** (review / test / migrate / audit / doc / triage / refactor)
- **First wiki-captured canonical 2-location slash-command file-system convention** (`~/.claude/commands/` + `.claude/commands/`) + **namespacing-via-subfolder convention**
- **First wiki-captured concrete per-slash-command model-routing rule-set** (1 haiku + 5 sonnet + 1 opus across 7 commands)
- **First wiki-captured 5-step canonical 15-minute Claude Code slash-command on-ramp**
- **First wiki-captured 5-mistake taxonomy for slash-command failure modes**
- **First wiki-captured "Anthropic main manager" 26-min talk-surface reference** with *"command library every new dev inherits on day one"* framing (likely Cat Wu; verification-pending)
- **First wiki-captured 10-hours/month productivity-loss-from-prompt-retyping figure**
- **2nd substantive 0x_rody wiki surface** — extends [[rody-5-subagent-templates-2026-05-31|May 31 5-template subagent guide]]; confirms 0x_rody as wiki-tracked Claude Code-side practitioner-content register voice
- **First wiki-captured "command systems > prompts" register-evolution coinage** (Moysha comment) — adds to the [[loop-engineering|Loop Engineering practitioner-content-register evolution]] (prompts → harnesses → loops → command-systems / fleets)
- **First wiki-captured "productize your own workflow" framing** for slash-command discipline (Kekko D'Amato)
- **6-surface 6-day Anthropic-product-tier canonical practitioner-content register cluster now articulated** (extends 5-surface cluster from pt4): Cherny + Steinberger + Van Horn + 0xchromium (Cowork) + Khairallah (Projects) + **0x_rody (Claude Code slash commands)** — **first wiki-captured 6-surface practitioner-content register cluster across all 3 Anthropic product surfaces** (Claude Code × 4 + Cowork × 1 + Projects × 1)
- **Pairs with [[zodchii-opus-4-8-setup-guide-2026-05-29|zodchii model-routing matrix]] + [[zodchii-4-agent-pipeline-2026-05-30|zodchii 4-agent pipeline]]**: same Telegram channel `t.me/zodchixquant`; verification-pending whether 0x_rody = zodchii (one person two handles) or co-collaborators
- **Adds Claude Code 3-location project-config canonical convention**: CLAUDE.md (project-rules) + `.claude/agents/<role>.md` (role) + `.claude/commands/<name>.md` (slash-command) — all 3 git-committable + git-shared; pairs with `~/.claude/` global-personal variants for each

## Pages Updated

- [[0x-rody]] — new entity page; 2nd substantive surface confirmed (rody-5-subagent-templates-2026-05-31 + this slash-command-library guide)
- [[claude-code]] — slash-command-library 2-location convention + namespacing + 7-command starter library + 5-mistake taxonomy + "command library on day 1" framing added
- [[zodchii]] — cross-reference to 0x_rody same-Telegram-channel; verification-pending whether same person
- [[cat-wu]] — flagged as likely "Anthropic main manager" referenced in the 26-min talk; verification-pending
- [[claude-md-pattern]] — 3-location canonical project-config convention (CLAUDE.md + .claude/agents/<role>.md + .claude/commands/<name>.md)
- [[loop-engineering]] — Moysha "command systems > prompts" coinage added as 4-stage practitioner-content-register evolution extension

## Adjacent sources

- [[rody-5-subagent-templates-2026-05-31]] — 1st substantive 0x_rody surface; 5-template subagent guide
- [[zodchii-4-agent-pipeline-2026-05-30]] — zodchii's 4-agent pipeline with `.claude/agents/<role>.md` canonical schema
- [[zodchii-opus-4-8-setup-guide-2026-05-29]] — zodchii's Opus 4.8 routing-matrix
- [[khairallah-claude-projects-6-part-blueprint-2026-06-06]] — Khairallah 6-part blueprint at Claude Projects layer
- [[0xchromium-claude-cowork-workflows-guide-2026-06-04]] — 0xchromium 4-component workflow primitive at Claude Cowork layer
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — Cherny 5-tip recipe at Claude Code layer
- [[steipete-loops-engineering-vision-md-2026-06-07]] — Steinberger Loops Engineering coinage + VISION.md primitive
- [[mvanhorn-wtf-is-a-loop-2026-06-07]] — Van Horn Loop Engineering synthesis

## Verification-pending

- 0x_rody full identity / X-bio context / prior work
- Whether 0x_rody = zodchii (same person two handles) or co-collaborators (verification-pending given shared Telegram channel `t.me/zodchixquant`)
- "Anthropic main manager" identity in the referenced 26-min talk — likely Cat Wu but not confirmed
- Specific 26-min talk venue and date — verification-pending
- Whether the 7 commands (review / test / migrate / audit / doc / triage / refactor) are 0x_rody's own framing or sourced from the Anthropic talk
- Whether `description`-as-trigger-condition discipline is canonical Anthropic-side or 0x_rody-side framing
- Specific cat-wu-side primary verification of the *"Nobody types prompts from scratch. The commands should be live in the project."* quote
