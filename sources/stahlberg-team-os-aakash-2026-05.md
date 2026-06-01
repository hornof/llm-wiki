---
title: "Hannah Stahlberg's Team OS pattern (Aakash Gupta podcast + followup essay + Maven workshop)"
type: source
medium: podcast-episode
url: https://www.youtube.com/watch?v=0UArKLQ6bXA
ingested: 2026-05-18
---

## Summary

Two-layer capture from May 2026: (1) **Hannah Stahlberg**, PM at DoorDash and former Google APM with ~1,500 documented hours in Claude Code, on @aakashgupta's podcast (full transcript captured) explaining her **Team OS** pattern — a shared Claude-Code-compatible repository where every team function checks in their context and anyone on the team can query it in natural language; (2) Aakash Gupta's followup Substack essay *"I spent the last week building you a Team OS in Claude Code"* synthesizing four independent practitioner instantiations (Stahlberg at DoorDash, Dave Killeen at Pendo, Gabor Meyer at Google, Carl Vellotti solo) that converged on the same three-layer architecture. The pattern is the first wiki-captured **shared / team-scoped instantiation** of the [[company-brain]] thesis built on file-based markdown rather than enterprise infrastructure.

## Key Claims / Takeaways

### Three-folder Team OS architecture

Stahlberg's repo structure (file-based; framework-agnostic — works with Claude Code, Codex, Cursor, GitHub Copilot):

1. **`.claude/`** — shared agents, commands, skills used by everyone on the team.
2. **`product-development/`** — function-named subfolders (PM, Eng, Design, Data, Research, Support, etc.). Each function's owner checks in canonical context: decision logs, customer notes, meeting summaries, design docs, dashboards.
3. **`team/`** — team-level documents: onboarding guides, retros, team norms.

At the root: **`CLAUDE.md`** (the orienting file). Stahlberg's deliberately minimal: it contains a **doc index** (where to find what), the team roster + Slack handles, and key Slack channels with purposes. *"You don't want very much in your CLAUDE.md file. Claude MD should be very, very, very lean, especially in a team repository."* — direct practitioner confirmation of the [[claude-md-pattern]] 200-line ceiling.

### Why minimal CLAUDE.md + progressive loading wins

- **CLAUDE.md loads every session.** Remaining files load **progressively** as natural-language queries reference them.
- *"The way that this repo is structured is around the theory of context management."* Stahlberg names four context primitives: (1) what's in the session, (2) what gets loaded next, (3) what stays out, (4) how context degrades over a long session.
- **Slack-handle awareness in CLAUDE.md** enables natural queries like *"Slack Alex about the bug that came up on the customer call today"* — Claude resolves Alex's Slack ID + uses Slack MCP to send. No per-query disambiguation needed.

### The killer use case — 15 seconds vs Slack ping + wait

Aakash's followup essay reports the moment that convinced him: a new engineer at DoorDash needed context on a 3-month-old customer decision. Instead of pinging Stahlberg in Slack and waiting, the engineer opened the Team OS repo, asked the question in natural language, and got *"the full reasoning in 15 seconds."*

- *"Hannah wasn't involved. She wasn't even online. She had made herself unnecessary for context questions."* — Inverts the PM book conventional wisdom (*"make yourself indispensable"*).
- **Demo claim**: a Team OS query that found the answer using **3% of the context window**. The architecture is context-efficient by design.
- **Generalization**: 4 independent practitioner instantiations (Stahlberg/DoorDash, Killeen/Pendo, Meyer/Google, Vellotti solo) converged on the same architecture without coordination. *"That convergence is what convinced me to write this."*

### The cross-functional collapse

- *"It used to be that all product decisions were made by the PM and engineers were just writing code and design was just doing design. But now engineers are building products and maybe even deploying them without a PM. Designers are prototyping and building products and the whole everyone on the team is starting to make product decisions."*
- *"As PMs, we're starting to do a lot more data analysis, also prototyping, making designs. So we're starting to see a lot more blended functions where everyone needs to have the best context."*
- One PM previously supporting 3–4 engineers now supporting 10+. *"On top of that, where they might have just mainly concerned themselves with design and engineering in the past, now they have to interface with everybody: sales, marketing, support."*

### The OpenAI harness-engineering quote (the load-bearing framing)

Aakash's essay opens with a line from OpenAI's Feb 2026 harness-engineering post:

> *"That Slack discussion that aligned the team on an architectural pattern? If it isn't discoverable to the agent, it's illegible in the same way it would be unknown to a new hire joining three months later."*

Aakash extends: *"They were talking about AI coding agents. But read it again. It applies to your entire product team."* — the **"illegible-to-agent = illegible-to-new-hire"** equation reframes Team OS as solving the institutional-memory problem and the agent-context problem with the same artifact.

### Cost-of-context-question math

Aakash's lookup-cost calculation:
- A context question is *"rarely just the lookup time. It's the lookup, the Slack ping, the wait, the context-switch back."*
- *"At 10 of those a day at 10 minutes of total productive time lost each, you're at over 8 hours a week. Most teams I've talked to are higher."*
- This is the **first quantified ROI argument captured in the wiki** for shared-memory infrastructure at the team level.

### Stahlberg-specific phrases worth quoting

- *"I think the biggest mistake [PMs make with Claude Code] is that people give up too early."*
- *"Claude Code is the most misleading name in AI"* — because it's not just for code.
- *"There's not really a right or a wrong answer [between Claude, ChatGPT, Cursor, Cowork], although for most advanced PM work, you should be using some type of a coding agent."*
- **In the Weeds** (Substack) — Stahlberg's outlet; *"Claude Code for Everything"* series went viral; running a Maven workshop on Team OS architecture.

## Why It Matters

- **First wiki capture of [[company-brain]] applied at team scale via markdown.** Distinct from:
  - Personal scale ([[milesdeutscher-claude-personal-cfo-2026-05-14|Deutscher's Claude-as-CFO]] folder architecture).
  - Organizational scale ([[ashwingop-company-brain-part-1|Sentra's three-layer substrate]]).
  - The **team layer** is where most knowledge work actually lives, and where the bottlenecks Aakash quantifies (8+ hrs/week per person) compound.
- **Four-practitioner convergence** without coordination is the strongest evidence-of-pattern captured this month — same shape as the [[eng-khairallah-multi-agent-team-course-2026-05-15|multi-agent practitioner cluster]] last week, but for shared-memory infrastructure rather than multi-agent orchestration.
- **Direct practitioner validation of [[claude-md-pattern]]'s minimalist discipline** — Stahlberg arrived at the same "very, very, very lean CLAUDE.md + progressive sub-loading" framing through 1,500 documented hours, independently of the Karpathy → Forrest Chang → Mnilax lineage.
- **The "illegible-to-agent = illegible-to-new-hire" equation** (via OpenAI's harness-engineering post) is the cleanest single-sentence framing of why Team OS solves two problems with one artifact.
- **Stahlberg as a tracked voice**: 1,500 hours in Claude Code is the highest documented single-practitioner usage captured in the wiki. Outlet (*In the Weeds* Substack) + viral "Claude Code for Everything" series + DoorDash production context (already cross-confirmed via [[aakashgupta-doordash-company-brain-2026-05-10]]) warrant a `people/` page.

## Caveats

- **Aakash's followup essay is paywalled** beyond the introduction; the architectural payload and 4-week build plan are behind a $7-day-trial subscription wall. Public-portion claims captured; full implementation detail is gated.
- **Three Hannah Stulberg Substack clippings in the raw drop are all the same fragment** of a "Happy Mother's Day, from In the Weeds!" post about her Maven workshop — bio context, not source content. Cited here for the workshop reference only.
- **Stahlberg's name** appears as both *Stahlberg* and *Stulberg* across surfaces (her Substack URL is `hannahstulberg.substack.com`; the podcast transcript uses *Stahlberg*). **Canonical spelling: Stulberg** (matches her Substack and Maven profile). Flag for verification before any external citation.

## Cross-references

- [[claude-md-pattern]] — Stulberg's "very lean CLAUDE.md + progressive sub-loading" is direct practitioner validation; same week as [[zephyr-7-claude-setups-2026-05-15|Zephyr's setup #1 framing]] and [[milesdeutscher-claude-personal-cfo-2026-05-14|Deutscher's domain-specific extension]].
- [[company-brain]] — team-scale instantiation; pairs with personal (Deutscher) + organizational (Ashwingop) instantiations.
- [[claude-code]] — Stulberg uses Claude Code as the surface; explicitly notes Codex / Cursor / Copilot would work the same way.
- [[mcp]] — Slack MCP integration is what makes the "Slack Alex about X" query work end-to-end.
- [[aakashgupta]] — Aakash Gupta wrote the followup essay synthesizing the 4-practitioner convergence.
- [[aakashgupta-doordash-company-brain-2026-05-10]] — earlier wiki capture of the same DoorDash decision-context-via-AI pattern; Stulberg is now identified as the practitioner behind it.
- [[doordash]] — first wiki capture of DoorDash as a production Team-OS instantiation site (should create a thin page).
- [[ai-native-organizations]] — Team OS is the team-layer instantiation of the AI-native organization thesis (alongside the solo-founder, org-rebuild, junior-tier-elimination, and back-office-IT-services paths).

## Pages Updated

- [[claude-md-pattern]] (updated — Stulberg's 1,500-hour practitioner-validated "very lean CLAUDE.md + progressive sub-loading" framing added as a Notable Variant; team-repo context vs personal/code-project context; date bumped to 2026-05-18)
- [[company-brain]] (updated — "Team-Scale Instantiation: Team OS Pattern (Stulberg, Killeen, Meyer, Vellotti, May 2026)" subsection added with 3-folder + CLAUDE.md architecture and 4-practitioner convergence; date bumped to 2026-05-18)
- [[claude-code]] (updated — Stulberg "Claude Code is the most misleading name in AI" framing + Team OS as cross-functional collapse pattern added under Community Sentiment; date bumped to 2026-05-18)
