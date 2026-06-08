---
title: "Mike Van Horn — WTF Is a Loop? Peter Steinberger vs. Boris Cherny (2026-06-07)"
type: source
medium: article
url: https://x.com/mvanhorn/status/2063865685558903149
ingested: 2026-06-08
---

## Summary

**Mike Van Horn (@mvanhorn)** publishes (2026-06-07) **WTF Is a Loop? Peter Steinberger vs. Boris Cherny** — the first wiki-captured comprehensive synthesis-layer essay on the Loop Engineering discourse, framed as `/last30days` background research on *"the most repeated sentence in AI coding this week"*. Van Horn surfaces: (a) **first wiki-captured Cherny-direct-voice "I have loops that are running... my job is to write loops" framing** from the [[boris-cherny|Boris Cherny]] WorkOS Acquired Unplugged talk (2026-06-02); (b) **first wiki-captured 5-stage Loop Engineering lineage** (ReAct 2022 → AutoGPT 2023 → ralph 2025 → /goal spring-2026 → orchestration-loops mid-2026); (c) **first wiki-captured Cherny IDE-deletion-November-2025 receipt** + 259-PRs-in-30-days self-citation; (d) **first wiki-captured ~4% Claude-Code-share-of-public-GitHub-commits framing**; (e) **first wiki-captured Steve Yegge Gas Town surface** (Jan 2026 — Mayor + Patrol agent multi-agent orchestration with git-backed state); (f) **first wiki-captured Uber $1500/person/tool/month Claude-Code-and-Cursor cap** after burning annual AI budget in 4 months; (g) **first wiki-captured Geoffrey Huntley ralph entire-programming-language-for-$297 receipt**. Pairs with [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny's same-week 5-tip X post]] as the **practitioner-narrative companion** to the operator checklist.

## Key Claims / Takeaways

### Van Horn's punchline

> *"The most repeated sentence in AI coding this week is six words long, and almost nobody saying it can define it. One tweet had the entire timeline in a chokehold this week, so I ran /last30days on the word everyone was fighting about. The answer is real, it has a five-year lineage, and the punchline is that the loop, not the model, is now the expensive part."*

**First wiki-captured framing: "the loop, not the model, is now the expensive part"** — extends [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "reliability comes from the harness"]] framing from reliability-locus to cost-locus.

### Cherny's "I write loops now" framing — WorkOS Acquired Unplugged (2026-06-02)

> *"Now it's actually leveled up, I think, again, to the next wave of abstraction where I don't prompt Claude anymore. I have loops that are running. They're the ones that are prompting Claude and figuring out what to do. My job is to write loops."* — Boris Cherny, WorkOS [Acquired Unplugged](https://www.youtube.com/watch?v=RkQQ7WEor7w), 2026-06-02

**First wiki-captured Cherny-direct-voice articulation of loop-engineering as primary job-description at the Claude Code creator layer**. Pairs structurally with [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger's "you should be designing loops that prompt your agents"]] — both surfaces same-week, same framing, distinct voices (Cherny = Anthropic-internal-creator; Steinberger = practitioner-content-register).

### Cherny's 3-stage personal-ladder (Van Horn framing)

> *"A year ago he wrote code by hand with autocomplete. Then he ran five to ten Claude sessions in parallel and prompted each one. Now he does not prompt at all. He writes the loops that prompt Claude, and a couple hundred agents read his GitHub, Slack, and Twitter and decide what to build next."*

**First wiki-captured 3-stage Cherny-personal-ladder**:
1. **Autocomplete coding** (pre-2025)
2. **5-10 parallel Claude sessions, human-prompted** (~2025)
3. **Loop-authored, ~couple-hundred agents reading GitHub/Slack/Twitter** (now)

### Cherny's "259 PRs in 30 days" receipt

> *"In the last 30 days, 100% of my contributions to Claude Code were written by Claude Code. I landed 259 PRs."* — Boris Cherny, via Simon Willison, [2025-12-27](https://simonwillison.net/2025/Dec/27/boris-cherny/)

**First wiki-captured 259-PRs-in-30-days Cherny self-citation** (originally Dec 27 2025 via Willison; surfaced in Van Horn essay as load-bearing receipt for the loop-engineering thesis).

> *"He deleted his IDE in November and has not opened it since."*

**First wiki-captured Cherny IDE-deletion-November-2025 receipt** — concrete behavioral marker of the loop-engineering transition at the Anthropic-creator layer.

### ~4% Claude-Code-share-of-public-GitHub-commits

> *"It now reportedly sits behind close to four percent of all public commits on GitHub."*

**First wiki-captured ~4%-of-public-GitHub-commits framing for Claude Code adoption**. Verification-pending: primary source for this figure (Van Horn does not link). Pairs with [[aakashgupta-anthropic-growth-acceleration-2026-05-09|Aakash Gupta's $2.5B run-rate / 1000 enterprise customers]] aggregate signals at the Claude-Code-adoption scale.

### 5-stage Loop Engineering lineage (Van Horn synthesis)

**First wiki-captured 5-stage Loop Engineering lineage**:

| Stage | Year | Surface | Description |
|---|---|---|---|
| 1 | 2022 | **ReAct paper** ([arXiv:2210.03629](https://arxiv.org/abs/2210.03629)) | Academic while-loop: model reasons, calls tool, reads result, repeats. One model, one loop, human watching. |
| 2 | 2023 | **AutoGPT** | Goal-driven self-prompting loop; famously *"spinning forever doing nothing."* Seeded *"agents are a toy"* discourse. |
| 3 | 2025-07 | **ralph loop** ([[geoffrey-huntley|Geoffrey Huntley]]) | Bash one-liner piping same prompt file into agent repeatedly. Resets context to anchor files each iteration. Huntley built *"an entire programming language with it for about $297."* |
| 4 | 2026 spring | **`/goal` command** ([[claude-code|Claude Code]] + Codex) | Productized ralph: runs until validator model confirms task done. *"The ralph loop, built into Claude Code."* |
| 5 | 2026 mid | **Orchestration loops** (Cherny / Steinberger / [[steve-yegge|Yegge]] Gas Town) | Loops supervising loops, concurrent + scheduled. Durability via git-backed state + crash recovery. Loop = unit of work, not task. |

**Stage-5 four innovations** (Van Horn synthesis):
1. **Loop became the unit of work, not the task**
2. **Loops started supervising other loops, concurrently and on a schedule**
3. **Scheduling replaced the human kickoff** (infrastructure-time replaces attention-time)
4. **Durability became explicit** — git-backed state + crash recovery

Stage-3 ralph assumed terminal stayed open; stage-5 assumes it does not. **Trash Panda's right-twice framing**: single-agent ralph is *"old hat"*; multi-agent supervision is *"the new thing."*

### Van Horn's "cron plus a decision-maker" definition

> *"A cron job runs a fixed script. A loop runs a model that looks at the current state, decides what to do next, does it, checks whether it worked, and decides whether to keep going. The decision is the agent's, not yours, and not a hardcoded branch. Stack those, let one loop dispatch and supervise others, give them durable shared state, and you have something cron cannot express. The honest framing is not that loops are new magic and not that loops are just cron. It is that loops are cron plus a decision-maker in the body, and the interesting engineering is everything you wrap around that decision so it does not run off a cliff."*

**First wiki-captured "loops = cron + decision-maker in the body" framing**. Pairs structurally with [[steipete-loops-engineering-vision-md-2026-06-07|Mo's "loop needs something that can say no"]] framing — the *push-back primitive* is the *"decision-maker in the body"*; the loop is the *"cron"* shell. Van Horn confirms: *"The /loop command in Claude Code uses cron under the hood."*

### Boris's canonical /loop starter

> */loop babysit all my PRs. Auto-fix build issues, and when comments come in, use a worktree agent to fix them.*

**First wiki-captured Cherny-canonical-starter `/loop` instantiation** — pairs structurally with `/goal` recipe layer in [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's `/goal` guide]] at the *on-ramp* layer.

### Steve Yegge's Gas Town (the orchestration-loop-shipped-and-open-source)

> *"The deep end is Steve Yegge's [Gas Town](https://github.com/gastownhall/gastown), launched in January: twenty to thirty Claude Code instances coordinated by a Mayor agent, with patrol agents that run continuous loops and state stored in git so work survives a crash. That is the continuous orchestration loop that oversees other threads Trash Panda was reaching for, shipped and open source."*

**First wiki-captured [[steve-yegge|Steve Yegge]] Gas Town surface**:
- **20-30 Claude Code instances** coordinated by a **Mayor agent**
- **Patrol agents** running continuous loops
- **State stored in git** so work survives a crash
- **Launched January 2026**
- **Open source** at github.com/gastownhall/gastown

**First wiki-captured concrete multi-agent-orchestration-loop with named roles (Mayor + Patrol)** — pairs with [[zodchii-4-agent-pipeline-2026-05-30|zodchii's 4-agent pipeline]] (Planner/Coder/Tester/Reviewer) at the multi-agent-architecture pattern layer; Yegge's pattern is **continuous + git-durable** vs zodchii's **handoff-file-discrete**.

### roborev (Dan Kornas) — continuous review primitive

> *"Kornas is shipping roborev, a tool that reviews every commit in the background and feeds the findings back into the agent while the context is still fresh. An open loop that writes code with no feedback is a machine for generating confident mistakes. A loop that writes, runs, reads the result, and corrects is the thing that actually works. The loop is not the magic. The feedback inside it is."*

**First wiki-captured roborev surface** (Dan Kornas / @DanKornas) — continuous-review-feedback-into-loop primitive. Pairs structurally with [[dailybrief-roundup-2026-05-27|PolyArch/humanize RLCR loop]] (Claude implements + Codex reviews) at the cross-loop-review-feedback pattern layer. **Pattern: "the loop is not the magic; the feedback inside it is"** — first wiki-captured explicit articulation that **loop-quality reduces to feedback-quality**.

### Uber $1500/person/tool/month cap (cost-locus receipt)

> *"The receipt of the month: Uber capped its engineers at 1,500 dollars per person per tool per month for Claude Code and Cursor after burning its annual AI budget in four months."*

**First wiki-captured Uber Claude-Code-and-Cursor $1500/person/tool/month cap** — *"after burning its annual AI budget in four months."* Verification-pending: primary source (Van Horn does not link). Pairs structurally with [[anthropic-dynamic-workflows-primary-2026-05-28|Bun rewrite hundreds-of-agents]] at the **cost-explosion-from-loop-scaling** failure mode layer.

### Gartner agentic-AI-deployment-gap (~17%)

> *"Gartner puts agentic AI at the peak of inflated expectations, with only about seventeen percent of organizations actually deploying agents."*

**First wiki-captured Gartner agentic-AI Peak-of-Inflated-Expectations placement + ~17% organization deployment figure**. Pairs structurally with [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn's "gap between the timeline and the receipts is the real state of play"]] framing at the hype-vs-deployment-reality layer.

### 3 production hard stops for loops

**First wiki-captured 3-element production-loop hard-stop framework** (Van Horn synthesis):

> *"Which is why every serious 2026 write-up on loops converges on the same three hard stops: a maximum iteration count, no-progress detection, and a token or dollar budget ceiling."*

1. **Maximum iteration count** — explicit halt at N ticks
2. **No-progress detection** — halt when state stops advancing
3. **Token or dollar budget ceiling** — halt at spend threshold

Pairs structurally with [[anthropic-dynamic-workflows-official-docs-2026-06|Dynamic Workflows]] *"16 concurrent / 1000 total"* runtime constraints at the production-safety-rail layer. **Pattern: production-grade loops are halt-condition-engineered, not iteration-count-optimized.**

### "Cronjobs have funny re-branding rn" — the skeptic line

> X reply, loops discourse: *"Cronjobs have funny re-branding rn."*

**First wiki-captured loops-as-rebranded-cron skeptic critique**. Van Horn: *"This deserves a straight answer, not a dodge, because it is half right. Yes, the scheduling layer is cron. Boris literally runs his on cron. The /loop command in Claude Code uses cron under the hood... What cron never had is the part in the middle."* **First wiki-captured Cherny-runs-his-loops-on-cron disclosure** + **first wiki-captured `/loop` uses-cron-under-the-hood disclosure**.

### Steinberger's secondary thesis — skills (Van Horn closing framing)

> *"The loop is plumbing. The asset is the skill it calls."*
> *"Steinberger's other recurring point pairs with the loops one and is the more durable half: if you do something more than once, turn it into an automated skill, and if you do something hard, turn it into a skill afterward so next time is free."*

**First wiki-captured Steinberger turn-into-a-skill secondary thesis** as *"more durable half"* of the loops framing — *"do something more than once, turn it into an automated skill; do something hard, turn it into a skill afterward."* Pairs structurally with [[zodchiii-anatomy-perfect-skill|zodchii's 6-pattern skill anatomy]] + [[anthropic-academy-courses-catalog-2026-05|Anthropic Academy "Introduction to agent skills" course]] at the **skills-as-the-asset-loops-call-on** layer. **First wiki-captured 2-axis skill-creation rule**: (1) *do twice → skill* + (2) *do hard once → skill-afterward*.

### Van Horn's research-volume disclosure (`/last30days` receipt)

> *"Reddit: 17 voices (r/ClaudeAI, r/AI_Agents, r/ExperiencedDevs), 47 threads, 34k upvotes*
> *X: 21 voices (steipete, bcherny, runes_leo), 56 posts, 175 reposts*
> *YouTube: 4 voices (WorkOS, Lenny's Podcast, Y Combinator), talk transcripts*
> *TikTok: 6 voices (ai.native.founder, nikpolale), 34 clips*
> *Instagram: 4 voices (sequenzy_com, ai.builders), 14 reels*
> *Hacker News: 12 voices, 54 stories, 1k comments*
> *GitHub: 6 repos (gastownhall/gastown, NousResearch/hermes), steipete 259+ PRs*
> *Top voices: steipete, bcherny, runes_leo, rohit_jsfreaky, MatthewBerman"*

**First wiki-captured `/last30days`-style research-tool concrete-volume receipt**: 6+ surfaces × ~70 voices × ~150 sources. Pairs with [[anthropic-dynamic-workflows-official-docs-2026-06|Dynamic Workflows `/deep-research`]] as the **operator-side research-loop instantiation** of the fan-out / cross-check / cite pattern.

## Cross-cutting framings

- **First wiki-captured 5-stage Loop Engineering lineage** (ReAct → AutoGPT → ralph → /goal → orchestration loops)
- **First wiki-captured Cherny-voice "I write loops now" job-description framing** (WorkOS Acquired Unplugged 2026-06-02)
- **First wiki-captured Cherny IDE-deletion-November-2025 receipt** + 259-PRs-in-30-days self-citation
- **First wiki-captured ~4%-of-public-GitHub-commits Claude Code adoption framing**
- **First wiki-captured "loops = cron + decision-maker in the body" framing**
- **First wiki-captured Steve Yegge Gas Town surface** (Mayor + Patrol + git-durable; 2026-01; open source)
- **First wiki-captured roborev surface** (Dan Kornas continuous-review-feedback)
- **First wiki-captured Geoffrey Huntley ralph $297-programming-language receipt**
- **First wiki-captured Uber $1500/person/tool/month Claude-Code-and-Cursor cap** (annual-budget-burned-in-4-months)
- **First wiki-captured Gartner agentic-AI ~17% deployment / Peak-of-Inflated-Expectations placement**
- **First wiki-captured 3-element production-loop hard-stop framework** (max-iteration + no-progress + budget-ceiling)
- **First wiki-captured "the loop is not the magic; the feedback inside it is" framing**
- **First wiki-captured Cherny-runs-his-loops-on-cron disclosure** + `/loop` uses cron under the hood
- **First wiki-captured Steinberger turn-into-a-skill secondary thesis** as *"more durable half"* of loops framing
- **First wiki-captured `/last30days`-style research-tool concrete-volume receipt**

## Pages Updated

- [[boris-cherny]] — major update: WorkOS Acquired Unplugged + IDE-deletion + 259-PRs + ~4%-of-GitHub + 3-stage ladder + canonical `/loop` starter + cron-under-the-hood disclosure
- [[peter-steinberger]] — new entity page (2nd substantive surface confirmed via this article's quote-set)
- [[geoffrey-huntley]] — new entity page (ralph creator + $297-programming-language receipt)
- [[steve-yegge]] — new entity page (Gas Town + Mayor + Patrol + git-durable)
- [[loop-engineering]] — new concept page (5-stage lineage + 3 hard stops + cron-plus-decision-maker definition)
- [[claude-code]] — Loop Engineering layer note + Cherny 5-tip recipe + Gas Town reference + roborev reference
- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — back-link as the same-week Cherny-voice operator-checklist companion

## Adjacent sources

- [[bcherny-5-tips-opus-autonomous-2026-06-05]] — same-week Cherny X post; operator-checklist companion to this narrative
- [[steipete-loops-engineering-vision-md-2026-06-07]] — same-week Steinberger Loops Engineering surface (pt2 ingest)
- [[linas-beliunas-claude-goal-guide-2026-05-14]] — Linas's `/goal` operator-synthesis
- [[linas-beliunas-dynamic-workflows-guide-2026-06-04]] — Linas's Dynamic Workflows operator-synthesis
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's harness-for-every-task framing
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — Anthropic Dynamic Workflows canonical docs
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Bun Zig→Rust 11-day rewrite (canonical Anthropic-side long-horizon receipt)
- [[zodchii-4-agent-pipeline-2026-05-30]] — 4-agent pipeline (handoff-discrete sibling pattern to Yegge's Mayor + Patrol continuous-orchestration)

## Verification-pending

- ReAct paper full citation (arXiv:2210.03629 verifiable; ingested with confidence as named primary)
- Huntley ralph blog post (`ghuntley.com/ralph/`) — primary verification of $297 figure + entire-programming-language scope
- Yegge Gas Town GitHub repo (`github.com/gastownhall/gastown`) — verification of Mayor + Patrol agent role-names + git-durable state architecture
- Cherny WorkOS Acquired Unplugged talk video (`youtube.com/watch?v=RkQQ7WEor7w`) — verification of "I write loops" quote in primary
- Cherny 259-PRs / IDE-deletion-November Willison post (`simonwillison.net/2025/Dec/27/boris-cherny/`)
- Uber $1500/person/tool/month cap primary source
- ~4%-of-public-GitHub-commits primary source
- roborev tool / Dan Kornas primary repo and twitter handle
- SWE-Marathon benchmark primary (referenced via [[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny X post]] quote-tweet of @rishi_desai2)
- Gartner Peak-of-Inflated-Expectations agentic-AI placement primary (Gartner Hype Cycle citation)
- Van Horn's `/last30days` tool — what is it, is it a public skill / workflow, who built it
