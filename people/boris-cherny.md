---
name: Boris Cherny
type: person
affiliation: Anthropic (Claude Code creator)
signal_sources: [conference, twitter, podcast]
last_updated: 2026-10-15
---

## Who They Are

Boris Cherny is the creator of [[claude-code]] at [[anthropic]] — started as a side project in **September 2024**. Confirmed speaker at Sequoia's AI Ascent 2026 conference, **Code w/ Claude 2026** (May 6 2026 — closed out the event-keynote arc alongside Cat Wu), and **WorkOS Acquired Unplugged** (June 2 2026). Per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn's 2026-06-07 synthesis]]: Claude Code *"now reportedly sits behind close to four percent of all public commits on GitHub"* (verification-pending primary).

## Their Current Focus

[[claude-code]] product surface, the architectural consolidation toward the [[claude-agent-sdk]], and — as of June 2026 — **[[loop-engineering|loop-engineering]] as primary job-description**. Cherny self-describes the abstraction transition at the WorkOS Acquired Unplugged talk (2026-06-02):

> *"Now it's actually leveled up, I think, again, to the next wave of abstraction where I don't prompt Claude anymore. I have loops that are running. They're the ones that are prompting Claude and figuring out what to do. My job is to write loops."*

**3-stage personal-ladder** (Van Horn framing):
1. **Autocomplete coding** (pre-2025)
2. **5-10 parallel Claude sessions, human-prompted** (~2025)
3. **Loop-authored, ~couple-hundred agents reading GitHub/Slack/Twitter** (now)

**IDE-deletion-November-2025 receipt**: per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]], Cherny *"deleted his IDE in November and has not opened it since."* Concrete behavioral marker for the loop-engineering transition at the Anthropic-creator layer.

## Notable Takes

- Confirmed speaker at Sequoia AI Ascent 2026 — [[ai-ascent-2026]]
- **Code w/ Claude 2026** (founder-of-product reflection): *"Everything we are seeing today still feels magical to me."* — captures the from-the-creator stance on the May 2026 product expansion — [[willison-code-w-claude-2026]]
- **WorkOS Acquired Unplugged talk** (2026-06-02, [[mvanhorn-wtf-is-a-loop-2026-06-07]]): *"My job is to write loops."* First wiki-captured Cherny-direct-voice articulation of loop-engineering as primary job-description at the Claude Code creator layer.
- **2026-06-17 — "Strongly agree" validation of [[rahulgs-english-code-interpreters-10-point-thesis-2026-06-17|Rahul GS 10-point thesis]]**: *"Strongly agree with all of the above. We are entering the next era of code, where the model is able to generate correct code for an increasingly large percent of tasks. Our job is to make sure the model and our systems have the right guardrails, then to run Claude Code + an[...]"* **STRUCTURALLY CRITICAL**: first wiki-captured Cherny direct-voice validation of a framework written outside Anthropic. **First wiki-captured Cherny "next era of code" framing** + **his first "right guardrails" articulation, from the vendor-creator seat**. Pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald's verifier-first corrective]] + [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii looping-team operationalization]] = first wiki-captured 3-voice corrective + operationalization + validation same-week cluster.
- **259 PRs in 30 days self-citation** (2025-12-27 via Simon Willison, surfaced in [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]]): *"In the last 30 days, 100% of my contributions to Claude Code were written by Claude Code. I landed 259 PRs."*
- **5-tip recipe for running Opus autonomously for hours/days** (2026-06-05 X, [[bcherny-5-tips-opus-autonomous-2026-06-05]]):
  1. Auto mode for permissions
  2. Dynamic workflows (orchestrate hundreds/thousands of agents)
  3. `/goal` or `/loop` to nudge until done
  4. Claude Code in the cloud (close-laptop pattern)
  5. Self-verify end to end (Chrome extension for web, iOS/Android sim MCP for mobile, full server-startup for backend)
- **Context-rot counter-claim** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): *"Context rot isn't a thing with 4.8 imo, but curious if that's been your experience also."* Direct contradiction of [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's "context rot silently degrades long runs"]] framing — Cherny disputes for [[claude-opus-4-8|Opus 4.8]] generation.
- **5-archetype long-horizon-workload taxonomy** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): feature-building / language-migration / framework-migration / iterative-profiling-and-optimization / flaky-test-resolution.
- **2026-06-29: subagents will run in the background by default** ([[dailybrief-roundup-2026-06-29]]) — a roadmap statement in his own voice: *"next Claude Code version will run subagents in the background by default. This lets users continue chatting while tasks run independently."* **The first Claude Code roadmap anchor the wiki captured** — and notable in hindsight, since background subagents are the substrate the [[claude-code|`opusplan`]] and `/advisor` tiering patterns later assume.
- **2026-06-28: five archetypes for what engineering roles become** ([[bcherny-5-archetype-future-roles-2026-06-28]]): *"As engineering, product, design, DS, etc. melt into a new kind of role"* —

  | Archetype | Does |
  |---|---|
  | **Prototyper** | churns ideas |
  | **Builder** | takes a prototype to production |
  | **Sweeper** | cleans up, simplifies, unships |
  | **Grower** | iterates toward product-market fit |
  | **Maintainer** | stewards a mature system |

  **The archetypes are explicitly not tied to job function** — at Anthropic, designers, engineers, PMs and data scientists spread across all five. **Team composition follows product stage**: pre-PMF is Prototyper + Builder + Sweeper; growing post-PMF is Builder + Sweeper + Grower + Maintainer; strong PMF is Sweeper + Grower + Maintainer + Builder.

  > **And then the part that makes this page load-bearing — an archetype-by-archetype substitution readiness, from the person who built Claude Code:** *"**#2 can definitely be fulfilled by an AI agent today. #1 is tandem human and AI agent. #3/4/5 best performed by humans.** Will be a few years out before AI agents can do 50% or more."*
  >
  > **Builder is the one he says is already automatable, and Builder is prototype-to-production — the most common senior-engineer job description there is.** The three he reserves for humans (Sweeper, Grower, Maintainer) are all about **judgment over existing systems rather than producing new ones**, which is the same split [[loop-engineering]] records as generate-versus-verify and [[engineering-leadership-ai-era]] records as the role squeeze. **A vendor creator putting a few-years timeline on 50% substitution is the most specific such estimate the wiki holds.**

  Third direct-voice surface in three weeks (Jun 10 Tokyo, Jun 28 archetypes, Jun 29 subagents), and it pairs with [[gregisenberg-ai-native-company-context-layer-2026-06-27|Isenberg's three-pillar AI-native-company thesis]] the day before — **two voices on role evolution in one week.**
- **Canonical `/loop` starter** (via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]): */loop babysit all my PRs. Auto-fix build issues, and when comments come in, use a worktree agent to fix them.*
- **Cron-under-the-hood disclosure** (via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]): *"Boris literally runs his on cron. The /loop command in Claude Code uses cron under the hood."*
- **`/usage` slash command surfaced** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): *"Run `/usage` to see a breakdown of the specific skills, mcps, and plugins that are using your tokens."* First wiki-captured per-skill / per-MCP / per-plugin token-breakdown primitive.

## Where to Follow

- X: [@bcherny](https://x.com/bcherny)
- Wiki sources: [[bcherny-5-tips-opus-autonomous-2026-06-05]], [[mvanhorn-wtf-is-a-loop-2026-06-07]], [[willison-code-w-claude-2026]], [[ai-ascent-2026]]
- Related concept: [[loop-engineering]]
