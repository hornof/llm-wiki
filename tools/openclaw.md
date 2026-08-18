---
name: Openclaw
type: tool
category: framework
status: mainstream
last_updated: 2026-08-18
---

## What It Is

**Openclaw** is a [[peter-steinberger|Peter Steinberger]]-created open-source AI-agent framework that turns LLMs into autonomous, locally-running **personal agents** you interact with through everyday messaging apps (iMessage, WhatsApp) as you would a human assistant. Launched late 2025 as *Clawdbot* → briefly *Moltbot* → **OpenClaw** (Jan 2026). It is also wiki-tracked for its **heartbeat / cron always-on infrastructure** positioning within the [[concepts/loop-engineering|Loop Engineering cluster]]. Documentation at `docs.openclaw.ai`.

## Traction Signals

- **2026-08 (web refresh): most-starred repository in GitHub history — ~347K stars (April 2026)** ([openclaw.wikipedia](https://en.wikipedia.org/wiki/OpenClaw), [Fast Company](https://www.fastcompany.com/91550800/how-peter-steinberger-built-openclaw)): explosive growth to the top of GitHub all-time, shipping **production-grade security** (self-hosted agents viable for Fortune 500) — the security-hardening research wave includes *ClawKeeper* ([arXiv 2603.24414](https://arxiv.org/pdf/2603.24414)) and an OpenClaw threat-model case study ([arXiv 2603.12644](https://arxiv.org/pdf/2603.12644)). Basis for the **status upgrade gaining-traction → mainstream**.
- **2026-02-16 (web refresh): Steinberger joins [[openai|OpenAI]] to build "next-generation personal agents"** ([steipete.me](https://steipete.me/posts/2026/openclaw)); **OpenClaw is *not* shutting down** — it transitions to an **independent, OpenAI-backed foundation**, keeping the code free and community-driven. Structurally notable: the [[concepts/loop-engineering|Loop-Engineering]] 2nd-voice steward moving in-house at OpenAI while the project stays open (pairs with [[codex|Codex]]'s OpenAI-side open-model-routing — OpenAI courting the operator-control / personal-agent layer). *(Web-sourced; primary = Steinberger's own post.)*
- **2026-06-17: Sydney Runkle (LangChain) canonical heartbeats reference** — [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17|"The Art of Loop Engineering"]] explicitly cites Openclaw heartbeats: *"One popular example of crons in action is 'heartbeats' in openclaw, which turn your agent into an always-on, proactive assistant."* **First wiki-captured LangChain-tier canonical validation of Openclaw heartbeats canonical-pattern**. — [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]]

- **2026-06-17: Sydney Runkle (LangChain) canonical heartbeats reference** — [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17|"The Art of Loop Engineering"]] explicitly cites Openclaw heartbeats: *"One popular example of crons in action is 'heartbeats' in openclaw, which turn your agent into an always-on, proactive assistant."* **First wiki-captured LangChain-tier canonical validation of Openclaw heartbeats canonical-pattern**. — [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]]
- **2026-06-16: Greg Isenberg practitioner-poll Q1 framing** — [[gregisenberg-pick-a-side-7-question-poll-2026-06-16|"Pick a side"]] Q1: *"Openclaw vs Hermes?"* — klöss picks Openclaw; community-tier signal for canonical-tooling-positioning. **First wiki-captured Greg Isenberg practitioner-tier Openclaw canonical positioning signal**. — [[gregisenberg-pick-a-side-7-question-poll-2026-06-16]]
- **2026-05-30: Steinberger OpenClaw / Crabbox 10-hour agent runs** — Peter Steinberger (Openclaw project steward) details a workflow using GPT-5.5 + Crabbox to scale agent execution up to **10 hours**. *"The multi-hour runs significantly increase confidence in production-ready output."* — [[dailybrief-roundup-2026-05-30]]

## How to Use It

Documentation at `docs.openclaw.ai`. **Heartbeats canonical-pattern**: cron-based scheduling that turns agents into always-on, proactive assistants (Sydney Runkle canonical articulation). **10-hour multi-hour-runs canonical-pattern**: GPT-5.5 + Crabbox infrastructure for sustained-confidence production-tier output (Steinberger May 2026 articulation).

## Strategic Position

Pairs structurally with:
- [[peter-steinberger|Peter Steinberger]] — project steward; canonical [[concepts/loop-engineering|Loop Engineering]] 2nd-voice (Loop-Engineering-coinage-context per [[steipete-loops-engineering-vision-md-2026-06-07]])
- [[concepts/loop-engineering|Loop Engineering canonical-cluster]] — Openclaw at **canonical-cron-and-heartbeat infrastructure-tier** within 11-voice cluster
- [[hermes-agent]] — competing/complementary tool (Greg Isenberg Q1 framing); single-source-defer carry-over
- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17|Sydney Runkle Event-driven loop (Level 3)]] — Openclaw heartbeats canonical-pattern reference at LangChain-tier
- [[hanakoxbt-claude-loops-while-you-sleep-2026-06-13|Hanako "a loop is just Claude on a schedule"]] practitioner-tier canonical-simplicity framing — Openclaw heartbeats operationalizes this at canonical-cron-tier
- [[block-builderbot-launch-2026-06-17]] — Builderbot Slack-tag-canonical-trigger vs Openclaw heartbeats canonical-cron-trigger = first wiki-captured 2-vendor canonical-trigger-mechanism cluster

## Compared To

- **Openclaw heartbeats** vs **Hermes Agent** — practitioner-tier preference debate (Greg Isenberg Jun 16 Q1)
- **Openclaw multi-hour-runs** vs **Anthropic Dynamic Workflows 16-concurrent + 1000-agents-per-run** (per [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|Samuel McDonald canonical capacity-anchor]]) = canonical multi-hour-runs vs canonical multi-agent-fanout architectural-choice
- **Openclaw cron-tier** vs **LangSmith Deployment + Fleet channels** (per [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17|Sydney Runkle Level 3 Event-driven loop]]) = open-source vs commercial canonical-positioning

## Resources

- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — LangChain-tier canonical heartbeats validation
- [[gregisenberg-pick-a-side-7-question-poll-2026-06-16]] — practitioner-tier Q1 framing
- [[dailybrief-roundup-2026-05-30]] — Steinberger OpenClaw / Crabbox 10-hour agent runs
- [[steipete-loops-engineering-vision-md-2026-06-07]] — Steinberger Loop Engineering canonical context
- [[concepts/loop-engineering]] — Loop Engineering canonical-cluster
- [[peter-steinberger]] — project steward
