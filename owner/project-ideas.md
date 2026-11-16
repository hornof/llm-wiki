---
name: Project Ideas
type: owner-notes
last_updated: 2026-11-16
---

## How this page works

One line per project idea, wherever it was first written down. The long write-ups stay where they are; this page points to them. Paths starting `Cowork/` are under `Claude-Cowork/projects/` in the vault.

**Statuses:** *built* · *active* · *failed* (tried, didn't work, lesson recorded) · *candidate* (not started) · *rejected* (keep the reason so it isn't suggested again).

**Adding to it:** an ingest that turns up a build worth trying adds a *candidate* line here (CLAUDE.md, ingest step 5b). An idea from a Cowork chat gets a line too. When an idea moves, change its status and date; don't delete it.

Compiled 2026-11-16 from six Cowork pages and the wiki's source pages. Statuses come from `Cowork/fable-5/agent-status.md` and GitHub, checked that day.

## Built, active or tried

| Idea | Status | What happened | Write-up |
|---|---|---|---|
| hornof.org rebuild | built 2026-07-09 | Agent-built Astro site on Cloudflare, three days from old host to domain flip | `Cowork/fable-5/loop/prd-hornof-org.md` |
| Loop drill | built 2026-07-03 | First unattended `/goal` run: 6 PRs, all merged by hand, 57 tests | `Cowork/fable-5/loop/product-backlog.md` |
| eclipse-sim (orrery that predicts eclipses) | built 2026-07-07 | Overnight run, 47 minutes from brief to working. Hand-testing found 4 bugs the green test suite missed, which is where property-based and mutation testing came from | repo `hornof/eclipse-sim` |
| mont-fort motion clone | failed 2026-07-10 to 07-15 | 26 iterations, ~320M tokens. The loop optimized the motion statistics its checker measured and produced visual garbage. Relaunch-or-kill still undecided | `~/src/claude/mont-fort-study/report/WRITEUP.md` |
| Mountain rebuild | failed 2026-07-15 | Passed gate 0, failed gate 1. The builder rated its own work too kindly | `Cowork/fable-5/loop/prd-mountain-rebuild.md` |
| ai-pulse daily brief | active | Runs daily; feeds this wiki | repo `hornof/ai-pulse` |
| apb (build-process plugin) | active | Shipped 2026-10-25 as a public plugin; fixes since from the sketch-gallery trial | repo `hornof/apb`, `Cowork/ai-build-lab/sketch-gallery-apb-notes.md` |
| inktober-gallery (with Sam) | started 2026-10-25 | Repo, board and first ticket set up; last push 2026-10-26 | repo `hornof/inktober-gallery` |
| sketch-gallery | active | Solo trial of apb before handing the process to Sam; 9 apb issues logged | repo `hornof/sketch-gallery` |
| Vandenberg launch tracker | built | A launch table refreshed from the Launch Library API on request, not an app | `Claude-Cowork/personal/rocket-launches/vandenberg-launches.md` |

## Candidates

### Big builds (the 2026-07-17 bar: "wait, an AI built THAT?" with a public recipe)

From `Cowork/fable-5/next-build-candidates.md`. The 2026-10-02 refresh kept the ranking and called these project 2–3 material, not a first project.

| Idea | Note |
|---|---|
| Game Boy emulator that passes the accuracy test ROMs, run unattended for weeks | **Ranked first.** The test ROMs are a ready-made checker, the lesson mont-fort taught |
| Scoped C compiler by a small agent team (Carlini reproduction) | Ranked second, paired with a reduced Gas Town |
| Fable plays Pokémon on the public harness, scored against Anthropic's claim | Ranked third, as a fast public win |
| Self-hosting programming language in a Ralph loop | |
| Multiplayer browser world built in public (the fly.pieter.com pattern) | |
| Browser CAD editor with its own AI copilot | Also #7 on the showcase list |
| Gas Town at 5–10 agents on a real build | |
| Large migration on an open-source repo, PRs sent upstream | The only one where strangers certify the result |
| Weeks-long unattended run with public proof | No one has published one; wraps one of the first three |

The 2026-09-03 review of the Fable 5.1 thread (`Cowork/fable-5/fable-51-thread-candidates-2026-09-03.md`) points the same way. Of its ten, only an engine-checked build was worth doing (a Doom or Game Boy emulator), or a $50 train-yard probe. It's still waiting on "probe" or "doom".

### Single-page visual builds

From the 50-idea ranking (`Cowork/fable-5/burn/idea-factory.md`, 2026-07-06) and the showcase top 10 (`Cowork/fable-5/loop/fable-showcase-ideas.md`, 2026-07-04). The two lists agree on the top four.

| Idea | Note |
|---|---|
| Fluid sim set to music it composes itself | Top of both lists |
| Black-hole lensing visualizer | |
| Watch escapement with a screenshot-checked correctness loop | |
| Abyssal Garden-style scene from one prompt, with a blind visual critic and a frame-time budget | From the wiki, 2026-11-14: [[abyssal-garden-fable-5-2-2026-11-14]]. Has a checker, unlike most of this class; see the 09-03 note under Rejected |
| True-scale universe atlas | From the wiki, 2026-07-16: [[chrisjz-universe-atlas-fable-verification-2026-07-16]]. Worth reading for its checking setup more than as a build |

The orrery from both lists is built (eclipse-sim, above).

### Process and tooling

| Idea | Source | Note |
|---|---|---|
| Always-on build loop that waits out usage limits and resumes | `Cowork/fable-5/build-ideas.md` (A) | Partly built: loop design, auto-resume wrapper, then the mont-fort lane |
| Self-driving site cloner that diffs clone against original | `Cowork/fable-5/build-ideas.md` (B) | Folded into the hornof.org rebuild |
| Loop dashboard (lanes, usage, what needs you) | `Cowork/fable-5/loop/product-backlog.md` #6 | Draft spec in `Cowork/fable-5/burn/specs/06-dashboard-v1.md` |
| "Ask my site": cited answers over resume, talks and this wiki | `Cowork/fable-5/loop/product-backlog.md` #10 | |
| Compare other build systems and agent memory (Superpowers, gstack, gbrain) | `Cowork/ai-build-lab/restart-2026-10/joint-projects.md` P2 | |
| Open model plus a gateway, Claude for hard work, local model for bulk | `Cowork/ai-build-lab/restart-2026-10/joint-projects.md` P3 | First project that pays per token |

### The April list

From `Cowork/ai-build-lab/brainstorm.md` (2026-04-27). The website builder became the hornof.org rebuild and the launch tracker exists (both above). The rest haven't been picked up:

- X/Twitter manager: daily AI news summaries, then posting, then running on its own
- Social media money maker
- Agentic business, with you as the only human
- Resume builder
- Slide deck builder (`Claude-Cowork/playbooks/slide-deck-playbook.md` exists)
- Cowork how-to primer
- Startup-evaluation framework (continued in `Cowork/founder-thesis/`)

Startup ideas with Vlad are in `Cowork/founder-thesis/brainstorm.md`. They're company ideas rather than builds, so they aren't copied here.

## Rejected

| Idea | When | Why |
|---|---|---|
| The first 2026-07-17 list (Taskify, a tools collection, transcript tooling, harness-comparison write-ups) | 2026-07-17 | "small, embarrassing little apps"; the process came first and the artifact last |
| Seven of the ten Fable 5.1 thread builds | 2026-09-03 | Single HTML files from public prompts; one was reproduced by a cheaper model in six minutes. They're judged by looking at them, so nothing automatic can check them |
| Compress the ai-pulse roadmap | 2026-07-01 | You rarely change ai-pulse code |
| Wiki autoresearch loop | 2026-07-01 | Demoted. The manual ingest chain doesn't hurt, and the review steps are deliberate |
| Standalone memory cockpit | 2026-07-01 | Folded into the loop and the cloner |
| Rebuild from screenshots by hand | 2026-07-01 | Replaced by the self-driving cloner |
| Solo motion piece | 2026-07-16 | PR #41 closed unmerged |

**A tension to decide:** Abyssal Garden is a single HTML file from one prompt, which is the class rejected on 09-03. The difference is that its prompt carries two checks, a critic that sees only the renders and a frame-time target. Whether that's enough to clear the bar is your call.
