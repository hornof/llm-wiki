---
title: "croovies — 'Senior engineer, loop orchestrator sample setup' (r/ClaudeAI)"
type: source
medium: reddit-post
url: https://www.reddit.com/r/ClaudeAI/comments/1wd44vj/senior_engineer_loop_orchestrator_sample_setup/
ingested: 2026-09-12
---

## Summary

A r/ClaudeAI post (2026-09-10) in which **croovies** publishes the full **mission note** driving a production orchestrator agent — an agent prompted as an engineering manager ("Lloyd") that supervises up to 16 separate [[claude-code|Claude Code]] sessions, tracks work in a local SQLite ticket table, and is woken on a 90-minute ping. Claimed throughput: **800+ tickets filed, 370+ completed**, across 8 such orchestrators. The most complete practitioner disclosure of outer-loop orchestration structure the wiki has captured since [[loop-engineering|the Van Horn/Zodchii cluster]], and the first with the prompt text itself published rather than described.

## Key Claims / Takeaways

### The stated preconditions (3)

1. Agents can message each other.
2. Something can message the agent **on a loop** (croovies uses a 90-minute interval).
3. **A locally running SQLite database** the orchestrator owns.

### The mission note's three sections — Who / What / How

- **Who** — *"if your orchestrator was a person you hired… who are they? what is their title? what is their expertise?"* Rationale given: *"Giving your agent a grounding identity like this will help the model think differently, because it's role playing as that type of person."*
- **What** — what to do on wake: check email, logs, deployments; and *how to react* to what it finds. Named as where the operator's own value lives.
- **How** — the working style, built incrementally: *"When your agent does something you don't like — add a law to guide the working style."* Compound-engineering accretion applied to the orchestrator's own conduct ([[claude-md-pattern]], [[skill-md]]).

### Every-pulse actions (the wake-up checklist)

- Run a "Bug Reports from Feedback" playbook against email; cross-check new bugs against recently closed PRs/tickets.
- Sweep the backlog for un-staffed fast-follows and staff them *"if they still make sense."*
- Determine whether recently merged tickets require doc updates; file and staff.
- **Query this instance's own OS logs over the last ~15 minutes** for Error/Fault, crashes, WATCHDOG fires, relaunch loops, sync/scan failures, repeated warnings — then *"dispatch a read-only investigation agent to root-cause it"* before filing a bug and staffing the fix.
- Explicit negative rule: *"Do NOT ticket transient/expected noise — only genuine problems."*

### The four "laws" (the interesting part)

1. **Plan review by a rival model before any code is written.** For non-trivial features the builder produces a `ce:brainstorm → ce:plan` doc under `docs/spikes/` **with no feature code**; the manager spawns a **Codex** agent to review *the plan*; the builder revises; only then does building start. This is *in addition to* the existing rule that every PR gets a Codex code review plus `/ce:review`.
2. **Model-tier routing by task complexity, passed explicitly.** Complex work (multi-file, concurrency, data, persistence, security, architecture, high-stakes correctness) → [[claude-fable-5|Fable 5]]; less complex (cosmetic, mechanical, docs) → Opus 4.8. Noted gotcha: *"Pass the model EXPLICITLY on create_session (omitting it does not pick a tier)."*
3. **Decisions to the human go through a structured multiple-choice prompt**, batched up to 4 at a time with a recommended option — because an open question *"temporarily gates child message_parent delivery,"* so ask promptly and re-check every child once the gate clears.
4. **Review strictly before human QA, never after.** No ticket reaches "QA (human)" until the codex review has run on its PR and `/ce:review` has run for non-trivial changes, with all findings resolved. *"The ONLY legitimate re-QA loop is when [the human's] own QA feedback requires changes."*

### Why SQLite

*"This is basically an internal Jira / Memory, and it will survive all the compacts. It lets your orchestrator have context the builder agents don't have."* — durable state deliberately placed **outside** the context window, and deliberately **asymmetric** between supervisor and worker.

### The cost, stated

Two Claude Max accounts at $200 and one Codex account at $100 — **$500/month** — *"I hit the limits with the Claudes, and the Codex is just for adversarial reviews."* Cross-vendor by design: the rival model exists to disagree.

### Scale

16 agents per orchestrator, 8 orchestrators. These are *"not subagents — separate claude sessions that can run their own subagents."*

## Community reception (mixed, and worth keeping)

- The auto-generated mod-bot TL;DR after 30 comments: the community was *"very impressed with the sophisticated multi-agent orchestrator concept"* but *"the tea is that the slick, pixel-art UI in the screenshot is from OP's own paid, Mac-only tool called Scape."* Requests for a repo were met with "it's a paid product," and downvoted. *"The final verdict: everyone agrees the concept is a fantastic glimpse into the future… but this specific implementation is a closed-source product that requires a hefty subscription budget."*
- **Undisclosed-until-asked commercial interest** — croovies disclosed the tool at the bottom of the post and declined to name it in replies (*"not promoting it in this post"*), drawing *"But you are promoting it."* Discount accordingly; the mission-note text is still the artifact of value and is independently reproducible.
- **Why self-managed over an existing orchestrator** (asked re: [[openclaw|OpenClaw]] and Hermes): *"Everything I build has a human controllable ui. I want lots of automation, with lots of control. So the orchestrators log their actions… the goal is building personal automation infrastructure that you can trust."*
- **Alternative substrates named by commenters**: `herdr` + tmux tabs/panes (*"you can easily manage 20+"*), OpenClaw, Hermes, Orca, and **Beads** (`gastownhall/beads`, Dolt-backed, syncs with remote issue trackers) — *"you can model the whole work-graph"* ([[graph-engineering]] adjacency).
- Dissent on the UI: *"dating profile version of an agent's style."*

## Pages Updated

- [[loop-engineering]]
- [[agentic-engineering]]
- [[ai-margin-collapse]]

## Notes

- **croovies / Scape** — create-candidate, single wiki surface, vendor-interested. No page created.
- **Beads / herdr / Orca** — single-surface tool mentions; not paged.
- Ticket counts (800+/370+) and throughput are self-reported with no artifact. The **structure** is the durable content; treat the numbers as `[unsourced]`.
