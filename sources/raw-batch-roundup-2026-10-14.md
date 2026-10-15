---
title: "Raw batch roundup — 2026-10-14 (Muse retention numbers; profit-funded agentic companies; small teams; architectural drift)"
type: source
medium: article
ingested: 2026-10-14
local_source: "_raw/Post by @deedydas on X 1.md; _raw/Post by @garrytan on X 3.md; _raw/Post by @MarioNawfal on X.md; _raw/I made a tool for architecture review....md; _raw/Post by @system_monarch on X.md"
---

## Summary

Five `_raw` drops. **One carries actual numbers**, two are positions from principals, one is a tool with a genuinely new problem statement, and one is off-topic.

## 1. Muse retention, measured (@deedydas, 2026-10-11)

> *"Meta Muse's retention is out, and it's almost as good as ChatGPT! It's **higher than ChatGPT at D7 (>30%)** and just lower at **D14 (22%)**. Not quite in the elite D14 tier of **WA (67%), YT (59%), Insta (54%)** or **TikTok/Snap (37%)**, though. Muse is one of the highest retaining AI products!"* — **source: Sensor Tower.**

### Judgment

**This is the first retention figure the wiki holds for any AI agent product, and retention is the measure that matters most for the claims it has been recording.** [[meta|Muse]] has been tracked through five angles — the per-user Linux VM, Amazon blocking it, the connector opening, the small-business rollout, Wang's manifesto — **and every one was about capability or distribution. None said whether anyone keeps using it.**

**The comparison set is the useful part and it cuts against the headline.** *"Almost as good as ChatGPT"* is true and **both are far below the messaging and video apps**: 22% at D14 against WhatsApp's 67% and Instagram's 54%. **So the best-retaining AI agent product keeps roughly a third as many users at two weeks as the social apps it is positioned against** — and Muse's whole premise is replacing the app you would otherwise open.

**It also bears on [[instinct|Instinct's]] bet.** The wiki recorded Instinct's wager as *one agent doing many errands beats many agents doing one each*, with DoorDash's single-vertical Messages agent as the counter-case. **A 22% D14 for the platform-scale generalist is not a strong result for that bet**, though no comparable figure exists for Instinct.

*(Third-party analyst data relayed in an X post with a chart image not read. Sensor Tower is panel-based mobile estimation, which is directional rather than authoritative; no methodology, cohort definition or date range captured.)*

## 2. "Be profitable and run your company with maximal agentic loops" (@garrytan, 2026-10-12)

> *"Be profitable and run your company with **maximal agentic loops**. You don't need to sell more of your co anymore. **$10M profit per year reinvested is like an annual Series A, no dilution.** The best startups do this now. No whinging about the Series A/B crunch. You don't need saving."*

### Judgment

**[[garry-tan|Tan]] arguing against raising money is notable because of his job**, and the argument is the financial completion of the [[gstack|skills-as-labor]] thesis: *"a markdown file is an employee"* plus *"400× yourself"* means headcount — the thing venture money mostly buys — stops being the constraint. **If agentic loops replace the hiring a Series A funds, the round becomes optional.**

**The arithmetic is doing more work than it admits.** *"$10M profit per year is like an annual Series A"* is true of the cash and false of everything else a round provides — the signalling, the hiring pull, the customer confidence, and **the ability to spend ahead of revenue**, which is the entire point of venture capital. A profitable company reinvesting $10M has $10M; a company that raises $10M has $10M **and has not yet had to earn it.**

**And it only works for businesses that can be profitable early**, which is a narrow class — and conspicuously not the class that needs the frontier-model spend the rest of this wiki documents. **Set against [[pachaar-llm-routing-can-cost-more-2026-09-06|Uber's annual AI budget vanishing by April]] and [[berriai-moyai-self-hosted-coding-agent-2026-10-07|$101,872 in 31 days]], "run maximal agentic loops" has a cost structure Tan does not price here.**

*(X post; no examples, no companies named, no evidence that "the best startups do this now." YC's president arguing founders do not need outside capital is a position with institutional context.)*

## 3. Small teams, via Musk (Alexandr Wang, relayed by @MarioNawfal, 2026-10-11)

> *"Meta's chief AI officer Alexandr Wang says Elon Musk taught him something that helped shape Meta's AI strategy: **you don't necessarily need thousands of engineers to move fast. You need a small group of exceptionally talented people, very little hierarchy, and the freedom to get things done.**"* Wang reportedly brought this to Zuckerberg, *"who embraced it as a central part of their approach to AI."*

### Judgment

**Folded with the caveat that it is a third-party relay of a secondhand attribution** — and because it **confirms Wang's title**, which the wiki declined to assert on 2026-09-27 when his *"Why I'm Building Muse"* manifesto was folded (*"Wang's role/affiliation deliberately not asserted; unverified here"*). **Still thin: a Nawfal summary is not a primary**, but it is a second surface pointing the same way.

**The substance is the oldest idea in software management and the wiki should say so.** Small teams, flat hierarchy, autonomy — this is Brooks, it is the two-pizza rule, it is every engineering-org essay since 1975. **What would be new is evidence that AI changes the optimal team size**, which is exactly what [[ai-native-organizations]] tracks and what this does not provide. *"At some point, adding more people stops making you faster"* was true before transformers.

**Where it does connect: Meta is the largest-resource counterexample on that page.** An organisation with effectively unlimited headcount deliberately constraining team size is a stronger datapoint than a startup doing it from necessity.

## 4. CodeBoarding — architectural drift as the agent problem (r/softwarearchitecture, 2026-10-09)

An open-source engine producing **deterministic architecture diagrams from codebases** via *"purely static and lexicographical analysis so that the generations are accurate and deterministic"*, with all edges from **the actual control-flow graph**. The stated motivation is the interesting part:

> *"My belief is that architecture has never been so important. **With agents doing most of the coding, we need a way to judge the architectural trade-offs they are introducing with each change** — however I've found that **models are not great at surfacing what architectural changes they have made, especially at scale.**"*

The author asks the room: *"how do you put yourself in the loop of architectural drift nowadays, with all the agentic stuff happening?"*

**Top reply, and it is better than the tool:**

> *"For architecture and modeling, AI tends to generate much better output when the AI can **ingest an architecture decision record**. A good ADR explains the **goal and reasoning**, which are two big areas for AI to learn."*

### Judgment

**"Architectural drift" names a failure the wiki has not had a word for, and it is a different class from the ones it tracks.** The record covers agents producing *wrong* code (caught by tests), *insecure* code (caught by scanners), and *ugly* code ([[model-rendered-ui|caught by nobody]]). **This is agents producing locally-correct code that degrades the structure — invisible to every gate on [[loop-engineering]], because each change passes.**

**And the diagnosis is sharp: *"models are not great at surfacing what architectural changes they have made."*** That is not a capability complaint; **it is an observability one.** The agent cannot report the aggregate effect of its own changes, so a per-PR review never sees the trend. **Determinism is the right response** — a diagram you can diff is checkable where a model's summary is not.

**The ADR reply is the stronger insight.** *"A good ADR explains the goal and reasoning"* is **`DECISIONS.md` from the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|four files]], arrived at independently by the architecture community** — and the reason it matters is the same: *"without it a later session re-litigates a decision you already made two hours ago."* **Two communities converging on append-only decision records, from opposite directions.**

*(Self-promoting Reddit post plus a demo link; tool not run, no evaluation, 8-point top comment. The determinism claim is checkable in principle and unchecked here.)*

## 5. Not folded

**@system_monarch on backend concepts** (p99 latency, connection pooling, backpressure, idempotency keys) — **good list, not AI.** Recorded as skipped.

## Pages Updated

- [[meta]], [[instinct]], [[garry-tan]], [[ai-native-organizations]], [[loop-engineering]]
