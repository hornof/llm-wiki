---
name: SKILL.md
type: concept
maturity: emerging
last_updated: 2026-10-08
---

## Definition

- **A community plugin that ships its own evals (2026-09-27)** ([[jev-as-judge-cmu-paper-and-plugin-evals-2026-09-27]]): `aaddrick/building-with-typesafe-jev` packages best practices, **anti-patterns**, an API reference and links to **150+ community projects** for working [[jev|Jev]] into a harness — and publishes a **cross-provider eval** of itself: six tasks × 10 runs × three conditions, judged by **Claude Opus, GPT-6 Sol and Kimi K3 with majority deciding**. Scores: **no plugin 0.65 / official plugin 0.77 / this plugin 0.96**.
  **Notable for this page because the skill carries its own evidence.** Most SKILL.md-pattern artifacts assert usefulness; this one measures it, with better methodology than most vendor benchmarks — while being self-run on the author's own plugin, and beating the vendor's official plugin by 19 points, which is either a real docs gap or an overfit eval. *(Self-reported; a commenter's request for real usage examples is unanswered.)*

**SKILL.md** is the file-based primitive for packaging a reusable capability — a named, described procedure (often with tools/scripts) that a coding agent loads on demand to perform a specific task end-to-end. Where [[claude-md-pattern|CLAUDE.md]] tells the agent *how to behave* in a project and OKF-style knowledge tells it *what it knows*, a SKILL.md tells it *how to do a specific job* — and crucially encodes the **verification** of that job so the agent can self-check its work.

## Why It Matters

SKILL.md is the unit of **outer-loop memory** in [[loop-engineering|loop engineering]]: the file that outlives the conversation and carries a lesson forward, so the agent isn't re-taught every run. The official [[claude-code-getting-started-loops-2026-07-06|Claude Code loops taxonomy]] makes it the hand-off for *turn-based loops* — you "hand off the check" by encoding your manual QA as a `SKILL.md` (e.g. the `verify-frontend-change` example). When a loop's output misses the bar, the durable fix is to encode it into a skill so all future iterations improve, not just the one.

## Current State

- **Packaged, branded, installable catalogs (2026-07-12)**: [[charliejhills-claude-whole-company-42-skills-2026-07-12|Charlie Hills' "Build Your Whole Team with Claude"]] lays out **42 skills as a company org chart** (`claude-code` = "the operating system"), every tile a real install from a mix of first-party (`github.com/anthropics/skills`, `claude.com/plugins/{finance,small-business,legal}`) and third-party OSS (`obra/superpowers`, `upstash/context7`, `thedotmack/claude-mem`, …). Signals SKILL.md graduating from a per-capability primitive into a **distribution ecosystem** with a long OSS tail and a consumer-legible "company-as-a-stack-of-skills" packaging. The bundled department plugins claim ~100+ skills total (Marketing 45, Small Business 31, …), of which 42 are the curated chart.
- **Plugin-level substrate**: surfaced as the Skills half of the `commands/` + `skills/` plugin structure in the wiki owner's [[hornof-knowledge-work-plugins-claude-cowork-2026-06-17|knowledge-work-plugins]] — file-based markdown + JSON, no code or build steps.
- **Operator-discipline pattern**: [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|0xMovez's playbook]] frames "save the workflow as a Skill" and "turn verify-feedback into a permanent rule" as core self-improving-loop steps — the Document-to-Skill vs Skill-captures-process distinction.
- Adjacent to vendor-neutral siblings (AGENTS.md) and project-root discipline files (CLAUDE.md, CONSTRAINTS.md).
- **The load-bearing distinction — skills are progressive-disclosure, config is always-on (2026-08-06)** ([[raw-batch-roundup-2026-08-06]], r/AskVibecoders guide): *"A config file like CLAUDE.md or AGENTS.md pushes instructions into **every** session whether they're relevant or not. A skill sits idle until the agent reads its **description** and decides the current task fits, then loads the full body."* This is the cleanest practitioner statement of *why* skills exist as a separate primitive — they're the **selective-context / progressive-disclosure** answer to the [[handbook-md-long-docs-dont-govern-agents-2026-07-29|long-doc-doesn't-govern]] + [[context-engineering|context-engineering]] problem: don't push everything into every session; let the task pull in what it needs. Format: `SKILL.md` (required — YAML frontmatter `name` + **`description` carrying the trigger conditions**, e.g. *"Trigger when reviewing PRs… Do not use for architecture reviews, use the architecture skill instead"*) + optional `scripts/` `references/` `assets/`. The **description is the routing surface** — it's what the agent reads to decide whether to load the body.

- **Install-count leaderboards quantify the ecosystem (2026-08-15)** ([[raw-batch-roundup-2026-08-20]], r/ClaudeDesign): concrete traction behind the "distribution ecosystem" claim — the top design/UI skills by installs are `frontend-design` **776,052** (anthropics/skills), `web-design-guidelines` **541,180** (vercel-labs/agent-skills), `lark-whiteboard` 408,746 (larksuite/cli), then a **long third-party OSS tail** (design-taste-frontend, sleek-design-mobile-apps, ui-ux-pro-max, design-guide, all 300K+). The tracker's read: design is *"the least concentrated category… a new design skill competes on the work rather than against somebody's bundle"* — i.e. the ecosystem is **many-authors-deep, not first-party-locked** (only 2 of the top 7 are Anthropic/Vercel). Six-figure install counts per skill are the clearest evidence yet that SKILL.md is a real distribution market, not just a config primitive.
- **Planning/orientation skills, not just capability skills (2026-08-20)** ([[dailybrief-roundup-2026-08-21]]): [[matt-pocock|Matt Pocock]]'s **`/wayfinder`** skill cuts through the *"fog of war"* of greenfield/unclear projects — evidence that SKILL.md is being authored for **discovery/planning** (find the spec worth writing), not only for encoding a known repeatable workflow. Broadens the primitive from *"lazy repeated work"* toward *"structured thinking scaffolds."*
- **Review/readability skills — composable, single-purpose, attributed (2026-09-03)** ([[raw-batch-roundup-2026-09-03]]): a **review-layer** skill cluster surfaces — **`/show-me`** (@dexhorthy / HumanLayer, *"a toolbox of nice ways to look at code"* — a style guide for showing diffs in PR descriptions, *not* a generator), [[matt-pocock|Pocock's]] **`/wait-what`** (verbosity/readability reduction), and composition in the wild (*"/grill-with-mocks = grill-me + show-me"*). Extends the primitive past *capability* and *planning* into **presentation/review** (how a human reads the agent's output) — and models the ecosystem norm of **attributed, single-purpose skills** rather than repackaged bundles. Create-candidate: `dexter-horthy` / `humanlayer/skills`.
- **Cleanest beginner-definition (2026-08-17)** ([[raw-batch-roundup-2026-08-20]], r/claudeskills, +18): *"skills are just context and instructions… lazy ways to do repeated work so you don't have to retype everything to Claude every time."* Example given — a `/ship` skill bundling "update readme, marketing site, docs, de-vibe spot check, secrets scan" behind one word. The plain-language complement to the progressive-disclosure framing above.
- **"A markdown file is an employee" — the labor framing (Garry Tan / YC, 2026-08-13)** ([[garry-tan-new-rules-for-founders-a16z-2026-08-13]]): the crispest one-line statement of SKILL.md-as-durable-labor from a top allocator — *"an employee that will do the job perfectly every time, as many times as you want."* Tan's build loop makes the self-improvement explicit: when the agent errs, *"the actual trace turns into a skill file that's perfect… anytime it screws up in a future case it's just a bug fix, and then it's there forever"* — the outer-loop-memory ratchet (encode-the-lesson-once) stated as an HR metaphor. His own instances: **G-Stack** (engineering QA loop skills), **G-Brain** (RAG memory). Frames a few-hundred skill files as the labor pool behind a *"$15M ARR, 2-3 people"* company.

## A skill that improves itself against an eval (2026-09-28)

**The `claude-api` skill shipped `build-eval` and `hillclimb` sub-commands** ([[anthropic-automating-eval-design-hillclimbing-2026-09-28]]) — and then **was used on itself**, going from **66% to ~88%** on an eval derived from its own documentation, over 24 rounds.

**That self-application is the interesting part for this page.** The wiki's standing observation about SKILL.md artifacts is that **most carry no evidence they work** — noted on 09-27 when a community Jev plugin was folded here precisely because it was the rare one that did. **This is a vendor skill with a measured pass rate, a held-out split, and a published failure analysis**, which raises the bar for what a skill can be expected to show.

**The most transferable finding is about skills specifically, not evals.** The stall-and-reflect round discovered that **the skill's content was present and correct, but Claude was writing older API shapes from its trained priors anyway.** The fix was not more content — it was **a table near the top of the skill mapping the forms the model remembers to the current ones** (fixed-budget thinking → adaptive thinking; old web-search/fetch tools → current). **A skill competes with the model's priors, and stating the correction explicitly beats stating the truth implicitly.** That is a concrete authoring rule this page did not have.

It also found **ordering matters**: moving C# and Java warnings *above* their examples improved the score. *(Vendor's own skill, vendor's own eval, vendor's own models.)*

## A third-party skill ecosystem, at workflow depth (2026-09-29)

An r/claudeskills post shares a practitioner workflow for **`sn-motion-html`** — a skill for *"creating immersive, scroll-driven web stories"* — from **SenseNova's public skills repository** (`OpenSenseNova/SenseNova-Skills`), with prompts included.

**Recorded for the ecosystem fact, not the skill.** This page has tracked Anthropic's `anthropics/skills` and community plugins around Claude Code; **a separate vendor publishing a documented skills library that practitioners write workflow guides for is a different signal** — the format is being adopted by parties with no stake in Anthropic's distribution. Two independent skill repositories with third-party workflow content around them is the shape of a format becoming a standard rather than a product feature.

**Not evaluated.** No output inspected, no adoption figures, and a single Reddit workflow post is one person's practice. *(`_raw` drop, 2026-09-29.)*

## Anti-rationalization tables, and two packs converging on a gated lifecycle (2026-10-03)

**[[addy-osmani|Addy Osmani]] — ex-Google, now on the [[claude-code|Claude Code]] team — published 25 skills** ([[addyosmani-agent-skills-repo-2026-10-03]]) across **Meta → Define → Plan → Build → Verify → Review → Ship**. Four stated principles, and one of them is new to this page:

> **"Anti-rationalization.** Every skill includes a table of **common excuses agents use to skip steps** (e.g., 'I'll add tests later') **with documented counter-arguments.**"

**That is a sharper model of the failure than this page has had.** The implicit assumption behind most skill authoring is that the agent *forgets* a step. **An anti-rationalization table assumes the agent will argue its way around the step** — and it is the authoring-side counterpart to the finding that [[undefinedki-how-to-design-an-agent-harness-2026-08-15|a rule in prose gets skimmed where a rule in a linter does not]]. **Where you cannot make the rule mechanical, pre-refute the excuse.**

**"Process, not prose" names a distinction this page has been circling.** Its cleanest prior definition was *"skills are just context and instructions… lazy ways to do repeated work."* **That describes a macro.** Osmani's — *"workflows agents follow, not reference docs they read. Each has steps, checkpoints, and exit criteria"* — describes a different artifact, and it explains why skill quality varies so widely between packs. Joined by *"verification is non-negotiable… **'seems right' is never sufficient**"* and progressive disclosure.

**Also useful: the `definition-of-done` versus acceptance-criteria split** — a project-wide standing bar every change clears is not the same object as a per-task criterion. This page had been conflating them.

### Two independent packs, one shape

| | Skills | Lifecycle | Accretion stage |
|---|---|---|---|
| **[[gstack]]** (Tan, YC) | 23 | Think → Plan → Build → Review → Test → Ship → **Reflect** | **`/retro`** |
| **agent-skills** (Osmani, Anthropic) | 25 | Meta → Define → Plan → Build → Verify → Review → Ship | **none** |

**A YC president and an Anthropic engineer independently shipping a seven-stage gated lifecycle is the strongest evidence this page holds that the shape is real rather than one person's taste.** The divergence is the interesting part: **gstack closes the loop and this pack does not.** Given that the accretion step is what [[loop-engineering]] identifies as the thing that makes a harness compound, **the absence is a gap in the newer pack rather than a simplification.**

*(Repo README only — no skill content read, no installation, no evaluation. Adoption is a Trendshift badge. Osmani is an Anthropic employee publishing skills for Anthropic's product: not a conflict, not independent. Not tested by the owner.)*

## The dissent this page has lacked — "barely any skills" (2026-10-06)

**This page has collected skill packs, authoring principles and adoption signals, and no serious argument against the premise.** [[dhh-no-magic-sauce-harness-setup-2026-10-06]] supplies one, from a practitioner who ships:

> **DHH:** *"It's really just any harness, multiple agents concurrently, **barely any skills**, and using adversarial reviews. **There's no magic sauce.** The models are great out of the box."*

> **dax:** *"when i see people with custom workflows and setups **they're all addressing problems that don't exist anymore.**"*

**The disagreement is specific and it is with this page, not with harnesses generally.** DHH keeps a terminal substrate, concurrency and adversarial review — **he drops the skills.** [[gstack|Tan]] holds that *"a markdown file is an employee"* and that a few hundred skill files are the labor pool behind a *"$15M ARR, 2-3 people"* company. **Two practitioners with working systems, opposite conclusions about this page's subject, and no measurement on either side.**

**Record it as open, and note what would settle it.** The skill thesis predicts that **codified workflow outperforms a strong model used plainly, and that the advantage grows as skills accumulate.** dax predicts the opposite — that it **decays as models improve**, because the skills encode workarounds for problems that get fixed upstream. **The deletion condition is where the two theories diverge observably**: a skill library that needs regular pruning is evidence for dax; one whose entries keep earning their place is evidence for Tan. **Nobody in the wiki's record reports pruning.** [[gstack|gstack's]] `/retro` and [[addyosmani-agent-skills-repo-2026-10-03|Osmani's pack]] both add; neither documents removal.

## Related Concepts

- [[claude-md-pattern]] — project-behavior file; SKILL.md is the per-capability sibling.
- [[loop-engineering]] — SKILL.md as outer-loop persistent memory + the verifier's home.
- [[claude-code-getting-started-loops-2026-07-06]] — turn-based loops "hand off the check" via SKILL.md.
