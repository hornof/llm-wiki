---
name: Loop Engineering
type: concept
maturity: gaining-mainstream-recognition
last_updated: 2026-07-09
---

> [!key-insight] 2026-06-30 canonical-mainstream-validation-milestone
> **[[andrew-ng|Andrew Ng]] canonical-mainstream-AI-education-pedigree canonical-direct-validation** ([[andrew-ng-loop-engineering-3-loop-validation-2026-06-30|Jun 30 X-thread + canonical-The-Batch newsletter]]): Ng canonical-explicitly-cites canonical-Loop-Engineering canonical-coinage canonical-attribution to **[[boris-cherny|Boris Cherny]] + [[peter-steinberger|Peter Steinberger]]** as canonical-viral-social-media canonical-source-anchors + canonical-3-loop canonical-articulation (agentic-coding minute-scale + developer-feedback tens-of-minutes-to-hours + external-feedback hours-to-weeks) + canonical-context-advantage-vs-taste canonical-articulation. **Cluster status: 16-voice canonical-extension** (15-voice canonical-cluster + canonical-Andrew-Ng canonical-mainstream-AI-education-tier).

## Definition

**Loop Engineering** is the practitioner-content register elevated above [[trq-dynamic-workflows-harness-2026-06-02|harness-engineering]] in mid-2026 to name the discipline of **designing small programs ("loops") that prompt coding agents on the practitioner's behalf**, observe their output, decide whether the goal is met, and re-prompt until done. The model becomes the subroutine; the human becomes the author of the loop.

Coined in reply chain to [[peter-steinberger|Peter Steinberger]]'s 2026-06-07 X post (*"you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents"*) by Gautham Pai: *"Oh god, LinkedIn will now start a new fad, 'Loop Engineering'."* — see [[steipete-loops-engineering-vision-md-2026-06-07]]. **First wiki-captured Loop Engineering coinage 2026-06-07.**

## Why It Matters

- **Job-description shift at the Anthropic-creator layer**: [[boris-cherny|Boris Cherny]] (Claude Code creator) self-describes the abstraction transition at WorkOS Acquired Unplugged (2026-06-02) — *"I don't prompt Claude anymore. I have loops that are running... My job is to write loops."* See [[mvanhorn-wtf-is-a-loop-2026-06-07]].
- **Cost-locus shift**: per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]]: *"the loop, not the model, is now the expensive part."* Extends [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "reliability comes from the harness, not the model"]] framing from reliability-locus to cost-locus.
- **Receipts of scale**: [[bcherny-5-tips-opus-autonomous-2026-06-05|Ray Amjad's 19-hour `/goal` run verifying ~300 user flows]]; Cherny's *"259 PRs in last 30 days"* / *"100% of Claude Code contributions written by Claude Code"* / *"IDE deleted in November"*; [[anthropic-dynamic-workflows-primary-2026-05-28|Bun Zig→Rust 11-day rewrite]] (~750K LOC, hundreds of parallel agents).

## Current State

### 5-stage Loop Engineering lineage (Van Horn synthesis)

Per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]:

| Stage | Year | Surface | Description |
|---|---|---|---|
| 1 | 2022 | **ReAct paper** | Academic while-loop: model reasons, calls tool, reads result, repeats. One model, one loop, human watching. |
| 2 | 2023 | **AutoGPT** | Goal-driven self-prompting loop; famously *"spinning forever doing nothing."* Seeded *"agents are a toy."* |
| 3 | 2025-07 | **ralph loop** ([[geoffrey-huntley\|Geoffrey Huntley]]) | Bash one-liner piping same prompt file into agent repeatedly. Context-reset to anchor files each iteration. Huntley built *"an entire programming language with it for about $297."* |
| 4 | 2026 spring | **`/goal` command** (Claude Code + Codex) | Productized ralph: runs until validator model confirms task done. *"The ralph loop, built into Claude Code."* |
| 5 | 2026 mid | **Orchestration loops** | Loops supervising loops, concurrent + scheduled, durable via git-backed state. Loop = unit of work, not task. |

### Stage-5 four innovations

1. **The loop became the unit of work, not the task**
2. **Loops started supervising other loops, concurrently and on a schedule**
3. **Scheduling replaced the human kickoff** — loops run on infrastructure time, not attention time
4. **Durability became explicit** — git-backed state + crash recovery

Stage-3 ralph assumed your terminal stayed open. Stage-5 assumes it does not.

### "Cron plus a decision-maker in the body" (Van Horn definition)

> *"A cron job runs a fixed script. A loop runs a model that looks at the current state, decides what to do next, does it, checks whether it worked, and decides whether to keep going. The decision is the agent's, not yours, and not a hardcoded branch. Stack those, let one loop dispatch and supervise others, give them durable shared state, and you have something cron cannot express."* — [[mvanhorn-wtf-is-a-loop-2026-06-07]]

**Cherny disclosure** (via Van Horn): *"Boris literally runs his on cron. The /loop command in Claude Code uses cron under the hood."*

### 3 production hard-stops (Van Horn synthesis)

> *"Every serious 2026 write-up on loops converges on the same three hard stops..."*

1. **Maximum iteration count** — explicit halt at N ticks
2. **No-progress detection** — halt when state stops advancing
3. **Token or dollar budget ceiling** — halt at spend threshold

**Pattern**: production-grade loops are halt-condition-engineered, not iteration-count-optimized. Pairs with [[anthropic-dynamic-workflows-official-docs-2026-06|Dynamic Workflows]] runtime constraints (16 concurrent / 1000 total).

### Push-back primitive — "loop with something that can say no"

Per Mo (@mosyaseen) reply in [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger thread]]: *"designing the loop is half of it. the other half is putting something in the loop that can say no: a test, a type check, a real error. a loop with nothing to push back is the agent agreeing with itself on repeat."*

Push-back primitives: tests, type checks, real errors, **VISION.md** (per Steinberger), continuous review (e.g., [[mvanhorn-wtf-is-a-loop-2026-06-07|roborev by Dan Kornas]] reviews every commit and feeds findings back).

**Pattern**: *"The loop is not the magic. The feedback inside it is."* (Van Horn)

### 4-stage practitioner-content evolution timeline

Steinberger framing ([[steipete-loops-engineering-vision-md-2026-06-07]]):

1. **Prompts** (pre-2024) — direct LLM interaction
2. **Harnesses** (early 2026 per [[trq-dynamic-workflows-harness-2026-06-02|Thariq]]) — custom harnesses on top of Claude Code
3. **Loops** (mid-2026 current) — designing the loop that prompts the agent
4. **Fleets-that-design-loops** (Steinberger predicts ~3 months out, ~Sept 2026)

### Multi-agent orchestration receipts

- **[[steve-yegge|Steve Yegge]] Gas Town** ([github.com/gastownhall/gastown](https://github.com/gastownhall/gastown), Jan 2026): 20-30 Claude Code instances coordinated by a **Mayor agent**, **Patrol agents** running continuous loops, state stored in git for crash recovery. First wiki-captured concrete instantiation of the *"loop supervising other loops"* pattern shipped + open source. See [[mvanhorn-wtf-is-a-loop-2026-06-07]].
- **[[zodchii-4-agent-pipeline-2026-05-30|zodchii 4-agent pipeline]]**: Planner/Coder/Tester/Reviewer with discrete handoff-files in `.pipeline/{spec,changes,test-results,review}.md`. Sibling architectural pattern: **discrete handoff** vs Yegge's **continuous-supervised**.
- **[[dailybrief-roundup-2026-05-27|PolyArch/humanize RLCR loop]]**: Claude implements + Codex reviews independently until acceptance criteria met. **Cross-vendor agent-review loop**.

## Verifier-discipline-first corrective (Samuel McDonald, 2026-06-15)

A **STRUCTURALLY MAJOR canonical-corrective** to the prevailing Loop Engineering discourse: [[samueljmcd|Samuel McDonald]] publishes [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|"My Thoughts on Loop Engineering"]] arguing that **the verifier — not the generator — is the bottleneck**. Adds **10th canonical voice** to the cluster at the **verifier-discipline-first-tier**.

**Central reformulation**: *"A loop is a generator wired to a verifier. The generator was never the bottleneck. The verifier is."*

**Closing canonical**: *"Design the verifier, not the prompt."*

### Open vs Closed loops

| Type | Characteristics | Outcome |
|---|---|---|
| **Open loop** | Wide exploratory space; goal + conditions but freedom in between | Novel output **+ slop-machine on loose criteria + budget-burner** |
| **Closed loop** | Goal + defined steps + evaluation at each step + stopping condition | **Production-tier results today**; bounded paths; normal budget |

*"Closed loops are what produce results today. People credit the autonomy for that. The autonomy is not the reason. The evaluation gate is."*

### Inner Loop vs Outer Loop

| Layer | Scope | What it verifies | Maturity |
|---|---|---|---|
| **Inner loop** | Single task | The task itself (write + test + run + fix + confirm) | **Mature** — most agents do it now |
| **Outer loop** | Across sessions | That you do not repeat last week's mistake (persistent lesson carry-forward) | **Still half-built** — value sitting on the table |

*"The agent forgets when the context window resets. The repository does not."* Outer-loop persistent-memory homes: **`SKILL.md` + `AGENTS.md`**.

### Research roots

- **ReAct** (Yao et al.; Princeton + Google) — alternates reasoning and action; *"think, act, observe, repeat until done"*
- **Reflexion** (Shinn et al.) — ReAct with memory; **canonical seed of persistent memory**

### Bun port reframed — "verification is the architecture"

[[bun|Bun Zig→Rust port]] via Dynamic Workflows reads as the **flagship verification-architecture demonstration**:
- Pass 1: map correct Rust lifetime for every struct field
- Pass 2: each file as behaviour-identical port; hundreds of agents in parallel + **2 reviewer agents on every file**
- Separate layer of agents **existed only to refute what the others produced**
- Fix loop drove build + test suite until both ran clean

*"The verification is not a step at the end. It's actually the architecture."*

### Anthropic's own caveat — "not yet in production"

McDonald flags Anthropic's own published caveat on the Bun port: **the port is not yet in production**. McDonald's reframe: *"A 99.8% pass on an existing suite is a benchmark result… Production is the behaviour nobody wrote a test for yet. The gap between those two is the gap this whole industry keeps tripping over."*

**Canonical ceiling-framing**: *"A loop that goes green is not a loop that is correct. It is a loop that satisfied the verifier you gave it. The quality of the output is capped by the quality of that verifier, and not one point higher."*

### 6 mechanical parts of a working loop

1. Scheduled trigger to discover work + start the agent
2. Isolated git worktrees so parallel agents do not stand on each other's changes
3. Skills files so you are not re-explaining conventions every run
4. Connectors to tools the work already lives in
5. Separated generator-and-verifier roles (*"an agent grading its own homework grades generously"*)
6. Memory — the file that outlives the conversation and carries the lesson forward

### Native-tooling capacity-anchors

- `/goal` — v2.1.139+
- Dynamic workflows — v2.1.154+ (research preview); **capped at 16 concurrent + 1000 agents per run**

*"Not every job is a workflow job, and dressing a small task up as one is its own kind of waste."*

### Management closing

*"Management in the age of agents is not about hiring capable workers. The workers are capable and cheap. It is about designing the constraints they run inside, the same as it always was with people."*

### Zodchii operationalization at practitioner-tier (2026-06-16)

[[zodchii-builder-checker-looping-team-2026-06-16]] — [[zodchii|Zodchii]] publishes Jun 16 (1 day after McDonald) **builder + checker 2-agent looping-team architecture** that **operationalizes McDonald's verifier-discipline-first principle** at the Claude Code practitioner-tier:

| McDonald canonical principle (Jun 15) | Zodchii operationalization (Jun 16) |
|---|---|
| *"A loop is a generator wired to a verifier"* | builder = generator; checker = verifier |
| *"Design the verifier, not the prompt"* | dedicated checker agent with read-only tools |
| *"agent grading its own homework grades generously"* | builder ≠ checker discipline |
| *"A loop that goes green is not a loop that is correct"* | cycle-cheat-prevention stop-rule |
| *"autonomy is not the reason; the evaluation gate is"* | 4 canonical stop-rules in CLAUDE.md |

**Zodchii canonical stop-rules**:
- **ALL GREEN**: every check passes — stop and report success with proof
- **5 cycles used**: stop and report what still fails (canonical-timing-anchor)
- **Same failure twice in a row**: stop — "the builder is guessing, not fixing"
- **A fix makes a previously passing check fail**: stop — "something is being broken to fix something else"

**Closing canonical articulation** (Zodchii): *"It didn't get smarter, it just stopped quitting before the job was done."*

**2-voice canonical-Loop-Engineering-corrective same-week paired-articulation**: McDonald at corrective-tier (Jun 15) + Zodchii at practitioner-tier (Jun 16) = first wiki-captured cross-tier canonical-corrective same-week pairing.

### Cherny "strongly agree" + Rahul GS english→code-interpreters reframing (2026-06-17)

[[rahulgs-english-code-interpreters-10-point-thesis-2026-06-17]] — [[rahulgs|Rahul GS]] publishes Jun 17 a **10-point canonical thesis** reframing Fable+ class models as **"english → code interpreters"** + 10 canonical-discipline-shifts (small/large-diff-management-for-review + time-to-ship-≠-time-to-PR + bottleneck-solving + agency + risk-management-over-line-by-line + cost-of-complexity-changing + duck-typing-canonical-reframing + logical-verification-at-enormous-cost + code-permissions-as-canonical-opt-in).

**STRUCTURALLY CRITICAL**: [[boris-cherny|Boris Cherny]] (Claude Code creator) responds *"Strongly agree with all of the above. **We are entering the next era of code**, where the model is able to generate correct code for an increasingly large percent of tasks. **Our job is to make sure the model and our systems have the right guardrails**, then to run Claude Code + an[..."* — **first wiki-captured Cherny direct-voice "strongly agree" validation of a non-Anthropic-authored canonical-framework**.

**Comment-thread Evolution Plus AI canonical-corollary**: *"If it is an english to code interpreter, it compiles your spec faithfully, not your intent. The error doesn't vanish, it moves upstream from the code into the english. So the scarce skill becomes removing ambiguity from your own description"* — first wiki-captured **operator-side corollary to McDonald's verifier-discipline-first principle**: McDonald says *"design the verifier"*; Evolution says *"the scarce skill = removing ambiguity from your own description (the input to the verifier)"*.

**First wiki-captured 3-voice canonical-corrective + operationalization + validation same-week cluster**:
- Jun 15 McDonald **corrective-tier**: *"Design the verifier, not the prompt"*
- Jun 16 Zodchii **practitioner-tier operationalization**: builder + checker looping-team + canonical-stop-rules
- Jun 17 Cherny **vendor-creator-tier validation**: *"strongly agree" + "right guardrails"*

### Sydney Runkle (LangChain) — 4-layer canonical Loop Engineering stack (2026-06-16/17)

[[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — [[sydney-runkle|Sydney Runkle]] publishes **"The Art of Loop Engineering"** with **LangChain-side 4-layer canonical Loop Engineering stack**. Extends Loop Engineering cluster from 10-voice to **11-voice** (Sydney Runkle at LangChain-tier).

| Layer | What it does | Impact | LangChain primitive |
|---|---|---|---|
| **1: Agent loop** (model + tools) | Model calls tools repeatedly until task complete | Automate work | `create_agent` |
| **2: Verification loop** (agent + grader) | Output scored against rubric + retried with feedback if failed | Ensure quality | `RubricMiddleware` |
| **3: Event-driven loop** (verification + system) | Events trigger agent runs that update a real system | Work at scale | LangSmith Deployment + Fleet channels |
| **4: Hill-climbing loop** (system + engine) | Production traces feed analysis agent that improves harness config | Continuous improvement | LangSmith Engine trace analysis agent |

**Sydney Runkle's canonical pivot**: *"We've been thinking about loops 1 and 2 for a while. But focus should pivot to loops 3 and 4 where value compounds by embedding agents into your ecosystem that continuously improve in response to your criteria."* — **first wiki-captured 2-voice 2-day same-week canonical-pivot-to-outer-loop articulation** (McDonald Jun 15 *"inner mature; outer half-built"* + Sydney Runkle Jun 16-17 *"loops 1-2 mature; pivot to loops 3-4"*).

**Sydney Runkle's 4-canonical-voice cross-reference cluster**: explicit references to Nadella (frontier-ecosystem) + Steinberger (Loop Engineering coinage) + Cherny (vendor-creator) + Karpathy (loopcraft). *"AI leaders like Steipete, Boris, and Andrej have all arrived at the same conclusion: the potential in agents is in the loops you build around them."*

### Block Builderbot — STRUCTURALLY MASSIVE production-scale operationalization (2026-06-17)

[[block-builderbot-launch-2026-06-17]] — [[block|Block]] launches **Builderbot** at production-scale:
- **200,000 operations per day**
- **1,500 PRs merged per week**
- **15% of all production code changes across Block**
- 100% of Block engineers using AI
- Built on Block's open-source [[goose|Goose]] (contributed to AAIF Linux Foundation)
- Brad Axen (Head of AI Capabilities): *"the missing layer between AI coding tools and how engineering actually works at scale"*

**First wiki-captured concrete production-scale operationalization of [[ai-native-organizations|AI-native organizations]] thesis** at firm-tier. **First wiki-captured "shift from AI-assisted coding to AI-native engineering" canonical framing**. **First wiki-captured Block-side concrete operationalization of [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14|Nadella firm-tier learning-loop canonical-architecture]]** (3 days post-Nadella).

### 0xMovez — 10-step canonical playbook + 2-model split-architecture (2026-06-18)

[[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — [[0xmovez]] publishes (Apr 22 orig; cross-device-clipped Jun 18) **STRUCTURALLY MASSIVE 10-step canonical-playbook for self-improving operator-tier Loop Engineering** using **Kimi K2.6 + Opus 4.8 2-model split-architecture**:
- **Kimi K2.6**: 300 parallel agents × 4,000 coordinated steps (up from K2.5's 100/1,500); $0.95/M in + $4.00/M out + $0.16 cache hits
- **Opus 4.8 verify-gate**: *"4x less likely than 4.7 to let a flaw pass; first Claude to score 0% on uncritically reporting flawed results"*

Canonical articulation: **"The engine learns. The closer keeps it honest."**

10-step playbook: (1) Write a spec, not a prompt + (2) Read decomposition plan + (3) Let it be wasteful + (4) Demand real files + (5) Point Opus at the output + (6) Save the workflow as a Skill + (7) Feed your own documents in + (8) Turn verify-feedback into a permanent rule (`CONSTRAINTS.md` canonical-pattern) + (9) Replay skill on new inputs + (10) Promote loop to background agent.

**Canonical cost-collapse anchor**: 20 minutes run #1 → 30 seconds run #50.

**Canonical operator-tier-RSI framing**: *"The system around it is getting smarter. Your skill library grows with every project."* — first wiki-captured **operator-tier-RSI canonical proof-point** (system-tier RSI vs model-weight-tier RSI).

Extends cluster to **12-voice canonical-cluster** with 0xMovez at operator-tier-2-model-split-RSI-discipline tier.

### Anthropic Claude Code Artifacts — vendor-side feature launch (2026-06-18)

[[claude-code-artifacts-launch-2026-06-18]] — [[anthropic]] launches **Claude Code Artifacts** as live, shareable visual pages built from full session context. 9-role canonical use-case taxonomy (Legal + Privacy + Security + FinOps + SWE + Designers + Staff + SRE + Engineering-managers). Private-to-org by default. **First wiki-captured 2-vendor 1-day vendor-side + firm-tier canonical-convergence on conversation-as-development-environment** (Anthropic Claude Code Artifacts + [[block-builderbot-launch-2026-06-17|Block Builderbot Brad Axen Jun 17]]).

### Hornof knowledge-work-plugins — owner-tier 11-role canonical-plugin taxonomy (2026-06-17)

[[hornof-knowledge-work-plugins-claude-cowork-2026-06-17]] — wiki owner [[owner/profile|@hornof]] open-sources `knowledge-work-plugins` repository: **11 plugins for knowledge workers** in [[claude-cowork|Claude Cowork]] (productivity + sales + customer-support + product-management + marketing + legal + finance + data + enterprise-search + bio-research + cowork-plugin-management). **First wiki-captured owner-side substantive published artifact**. Canonical plugin-structure: `.claude-plugin/plugin.json` + `.mcp.json` + `commands/` + `skills/` — file-based markdown + JSON, no code, no infrastructure, no build steps.

### 5-day 11-event STRUCTURALLY MASSIVE Loop-Engineering canonical-cluster (Jun 13-18)

[[loop-engineering-multi-author-jun-18-cluster-2026-06-18]] documents the **fastest canonical-discourse-convergence + production-operationalization + practitioner-content-cluster captured to date**: 11 substantive Loop-Engineering events spanning Jun 13 (Hanako) + Jun 15 (McDonald) + Jun 16 (Zodchii + Greg Isenberg) + Jun 17 (Rahul GS+Cherny + Sydney Runkle + Block Builderbot + Hornof knowledge-work-plugins) + Jun 18 (Anthropic Claude Code Artifacts + 0xMovez Kimi-Opus 10-step + 5-author roundup-tier cluster including "Loop Engineering = THE AI skill every builder needs in 2026" canonical-positioning + Memory-vs-Selection canonical-reframing).

### Hanako practitioner-tier — "the bottleneck was never the model" (2026-06-13)

[[hanakoxbt-claude-loops-while-you-sleep-2026-06-13]] — [[hanako|Hanako (@hanakoxbt)]] publishes practitioner-tier 5-canonical-discipline-articulations: *"a loop is just Claude on a schedule"* + *"start with one loop, not ten"* + *"boring + bounded + easy-to-verify"* canonical good-first-loop-properties + *"babysit the rules not the work"* + *"the bottleneck was never the model"*. Opens with canonical Cherny-behavioral-reference (*"few thousand agents working overnight while he sleeps"* + *"runs most of it from his phone"* + *"hasn't written a line of code this year"*).

### AIEWF conference-tier recognition (2026-07-06)

The [AI Engineer World's Fair Daily Dispatch](https://www.latent.space/p/aiewf-daily-dispatch-locomotives) — "the great loops debate and the state of AI engineering," surfaced in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]] — puts the loop-architecture debate on the main-conference agenda. No new specific technique beyond what the cluster above already captures, but it confirms loop engineering has crossed from practitioner-X-thread discourse into the flagship AI-engineering conference's framing of the field's state of play. Consistent with the `gaining-mainstream-recognition` maturity tag.

### Anthropic official 4-type loop taxonomy — vendor-canonical articulation (2026-07-06)

[[claude-code-getting-started-loops-2026-07-06]] — [[delba-oliveira|Delba Oliveira]] ([[claude-code]] team) publishes **"Getting started with loops"** on the Claude Blog / `@ClaudeDevs`, boosted same-day by [[thariq-shihipar|Thariq]] (322K views). **First wiki-captured official-vendor definition + classification of "loop"** — the Anthropic-canonical answer to the "what actually *is* a loop" question the practitioner cluster (Steinberger → Cherny → Van Horn → McDonald → Sydney Runkle) had left under-specified.

**Official Anthropic definition**: *"loops as agents repeating cycles of work until a stop condition is met"* — categorized by (1) how triggered, (2) how stopped, (3) which Claude Code primitive, (4) task-fit.

**4-type taxonomy with "you hand off X" framing** (reframes loop design as *choosing which piece of your own judgment you delegate*):

| Loop | You hand off | Use it when | Primitive |
|---|---|---|---|
| **Turn-based** (the agentic loop) | The check | Exploring / deciding | Custom verification skills (`SKILL.md`) |
| **Goal-based** | The stop condition | You know what "done" looks like | `/goal` (evaluator model gates each stop attempt) |
| **Time-based** | The trigger | Work happens outside your project on a schedule | `/loop` (local) → `/schedule` (cloud routine) |
| **Proactive** | The prompt | Recurring + well-defined | Dynamic workflows + `/schedule` + `/goal` + skills + **auto mode** |

**Maps the taxonomy onto primitives the wiki already tracks** — this is the official spine under the practitioner discourse: turn-based = the inner agentic loop (verification via skills); goal-based = Van Horn's Stage-4 "ralph productized"; time-based/proactive = Stage-5 orchestration loops (scheduling replaces the human kickoff). Confirms the wiki's independently-assembled lineage against Anthropic's own framing.

**Vendor-canonical restatement of verifier-discipline** (echoes McDonald + Zodchii): *"The quality of a loop's output depends on the system around it"* — clean codebase + self-verification skills + reachable docs + **fresh-context second agent for `/code-review`** (*"a reviewer with fresh context is less biased and not influenced by the main agent's reasoning"*). When a result misses the standard, *"try to encode it to improve the system for all future iterations"* — the outer-loop / `SKILL.md`-as-memory principle in vendor voice.

**Token-discipline checklist** (vendor-side companion to Van Horn's 3 hard-stops): right primitive + model per job · clear success/stop criteria · **pilot before a large run** (dynamic workflows can spawn hundreds of agents) · scripts for deterministic work · match interval to change-rate · review via `/usage` (by skills/subagents/MCPs), `/goal` (turns + tokens), `/workflows` (per-agent tokens, stop any agent).

Extends the Loop-Engineering cluster with the **first official Anthropic-vendor-documentation-tier voice** (prior vendor-creator-tier was Cherny's individual "strongly agree"; this is team-authored canonical documentation). Practitioner counter-signal persists in the boost thread: `@CallofdutyFan32` reports burning a Fable Max 20× limit on an unattended loop with *"a 500% improvement"* when babysat — live evidence for the closed-loop / verifier-gate thesis over naive autonomy.

### Production receipts — Uber + Jane Street (July 2026)

Two July datapoints extend the cluster from practitioner-content and vendor-docs into **firm-scale production receipts**:

- **[[praveen-neppalli-uber-agentic-adoption-2026-07-09|Uber]]** (2026-07-07): 99% of engineers using AI tools, **>70% of PRs attributed to local/cloud agents**, 2,500+ agent skills. Its **Agentic Pods** program (2-week shadow→build→validate→ship sprints pairing AI-proficient engineers with domain experts; 16 pods / 16 functions in 2 months) operationalizes *"the workflow becomes the unit of automation — not the individual task"* — a firm-tier restatement of the Stage-5 "loop = unit of work" thesis + Sydney Runkle's event-driven-loop layer. Pairs with [[block-builderbot-launch-2026-06-17|Block Builderbot]] as a 2-firm production-scale [[ai-native-organizations]] cluster.
- **[[cvxv666-jane-street-trading-agent-loops-2026-07-09|Jane Street / Horizon]]** (viral, unverified figures): a **generator + adversarial-verifier** two-agent loop (one builds a trading strategy, one tries to kill it via backtest) — the same builder-checker architecture as Zodchii/McDonald, now in quant finance, marketed under the literal phrase *"Loop Engineering."* Its reply-thread supplies a clean real-world statement of the **verifier ceiling**: surviving "data it's never seen" across thousands of trials is textbook multiple-testing/overfitting bias — *a loop that goes green is not a loop that is correct.* First wiki-captured out-of-domain (quant-trading) confirmation of both the pattern and its ceiling.

## Key Papers / Posts

- **ReAct paper** (2022): [arXiv:2210.03629](https://arxiv.org/abs/2210.03629) — academic origin of the reason-act-observe-repeat loop
- **AutoGPT** (2023): goal-driven self-prompting loop; seeded *"agents are a toy"* discourse
- **[[geoffrey-huntley|Huntley]] ralph** (2025-07): [ghuntley.com/ralph/](https://ghuntley.com/ralph/) — bash-one-liner with context-reset discipline
- **[[claude-code|Claude Code]] `/goal` launch** (2026 spring) — ralph productized as Anthropic-canonical primitive
- **[[steipete-loops-engineering-vision-md-2026-06-07|Steinberger Loops Engineering tweet]]** (2026-06-07): *"you should be designing loops that prompt your agents"*
- **[[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny 5-tip recipe]]** (2026-06-05): Anthropic-internal-creator-voice canonical checklist for autonomous-Opus operation
- **[[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn WTF Is a Loop synthesis]]** (2026-06-07): comprehensive synthesis-essay surfacing the 5-stage lineage + Cherny WorkOS receipts + Gas Town + roborev + Uber cap + Gartner deployment-gap
- **[[claude-code-getting-started-loops-2026-07-06|Delba Oliveira — Getting started with loops]]** (2026-07-06): first official Claude Code team loop taxonomy — Anthropic-canonical definition + 4-type classification (turn / goal / time / proactive) mapped to `/goal`, `/loop`, `/schedule`, dynamic workflows, auto mode

## Related Concepts

- [[claude-md-pattern]] — CLAUDE.md / VISION.md project-tier canonical content-template stack; VISION.md is Steinberger's push-back primitive
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's *"A harness for every task"* + 3-failure-mode framework (agentic laziness / self-preferential bias / goal drift) that loops exist to solve
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — Anthropic Dynamic Workflows canonical docs (16 concurrent / 1000 total runtime constraints; pair-with-`/goal` recommendation)

## Verification-pending

- Whether *"fleets that design your loops"* (Steinberger 2026-09 prediction) materializes
- Primary source for Van Horn's *"~4% of all public commits on GitHub"* Claude-Code-share figure
- Primary source for Uber $1500/person/tool/month cap (Van Horn cites without link)
- Gartner Hype Cycle agentic-AI Peak-of-Inflated-Expectations citation primary
- Cherny *"context rot isn't a thing with 4.8 imo"* test methodology — what was the test
