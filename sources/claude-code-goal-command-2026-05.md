---
title: "Claude Code `/goal` command (ClaudeDevs official + Deutscher amplification + Reddit tutorial)"
type: source
medium: twitter-thread
url: https://x.com/ClaudeDevs/status/2054351031279186040
ingested: 2026-05-18
---

## Summary

Three-layer surfacing of Claude Code's `/goal` command and the companion long-running-primitive cluster: (1) **@ClaudeDevs official X post May 12 2026** documenting `/goal` as *"the Ralph loop, built into Claude Code"* with explicit references to `/loop`, `/schedule`, stop hooks, and auto mode; (2) **@milesdeutscher X amplification May 11 2026** *("/goal is f*cking insane")* with @promptcowboy's full template prompt in the comment thread; (3) **Reddit r/AIAgentsInAction tutorial May 17 2026** ("/goal: Full Guide for Non-technical Folks") with when-to-use / don't-use guidance and a critical Reddit comment thread on context-management and Ralph-loop-implementation comparisons. First dedicated wiki capture of `/goal` as a Claude-Code-native long-running-task primitive; prior coverage only via [[zephyr-7-claude-setups-2026-05-15|Zephyr's setup #7]]. **First wiki capture of Anthropic openly identifying the Ralph loop as the underlying mechanism**.

## Key Claims / Takeaways

### What `/goal` is (per Anthropic official)

- **`/goal <completion-condition>`** — Claude Code runs a self-checking loop after every step. *"Every time Claude tries to stop, it checks your condition against the transcript. Not done? It keeps going. Done? You get a 'Goal achieved' summary."*
- Example given: `/goal all tests in test/auth pass and the lint step is clean`
- **Ralph loop framing acknowledged**: *"It's the Ralph loop, built into Claude Code."* — Anthropic explicitly identifying the long-known agentic-engineering pattern as the underlying mechanism.
- **Documentation**: code.claude.com / *Keep Claude working toward a goal* (Claude Code Docs).

### Companion long-running primitives (per Anthropic official)

| Primitive | Purpose |
|---|---|
| `/goal <condition>` | Self-checking loop; runs until condition met |
| `/loop` | Run Claude on repeat ("iterative refactors, cleanups, burning down your backlog") |
| `/schedule` | Run Claude on a cadence ("nightly test runs, morning triage, weekly cleanup") |
| **Stop hooks** | Programmatic control over when Claude is allowed to finish ("run your test suite, hit a CI endpoint, gate on whatever you want") |
| **Auto mode** | Required for long-running operation; enabled with `shift+tab` in CLI or the mode selector on desktop |

- **The discipline**: *"Long-running only works if Claude doesn't have to wait on you. That's why we have auto mode."*

### When to use `/goal` (per Reddit r/AIAgentsInAction tutorial)

Use for:
- *"The job has 10+ sequential steps"*
- *"'Done' can be described in specific, measurable terms"*
- *"You'd normally spend time re-prompting or checking progress manually"*

Don't use for:
- Single-step tasks
- Open-ended exploration with no clear finish state
- *"Anything you need to review mid-run before continuing"*

The tutorial's load-bearing recommendation: *"Vague finish lines will waste tokens because the model keeps running checks against a target it can't verify."* — **the prerequisite is a verifiable success condition**.

### The full `/goal` prompt template (Prompt Cowboy in Deutscher comment thread)

```
/goal [THE FINAL OUTCOME — what "done" looks like in one line]

── CONTEXT ──
· Project: [what you're building]
· Stack: [languages, frameworks, infra]
· Current state: [what exists today]
· Working dir: [path or repo]
· ...
```

Template is comment-thread payload, not Anthropic-official. Captured here as a practitioner artifact.

### Critical practitioner comments (the load-bearing payload)

- **Luca Capone (`@LucaCaponeX`)**: *"The key most people miss: /goal only works well when your CLAUDE.md is solid. Without project context, it wanders. With it, feels like a junior dev who actually read the docs."* — **names CLAUDE.md as a prerequisite, not a complement**, to long-running `/goal` execution. Direct cross-confirmation of [[claude-md-pattern|the CLAUDE.md pattern]] as the discipline that makes longer-horizon primitives viable.
- **JoJo.hl (`@realJoJo`)**: *"It really depends, I have very low success rate blindly trusting /goal. It will consume more tokens and eventually end up in outcomes that you lose track of. Good for research, but not too good for building things."* — practitioner-side failure-mode framing; counterweight to the Deutscher-style enthusiasm.
- **Soo Yoon (`@sooyoon_eth`)**: *"Prompt injection is the new SQL injection. If your agent can run on autopilot for hours and you haven't tested jailbreaks continuously via ACOST, you're flying blind."* — security framing applied specifically to long-running unattended execution.
- **Victor (`@victor_explore`)**: *"Agents running for hours unattended is the moment we stopped being typists and became managers."* — the cleanest single-sentence framing of the role-shift `/goal` enables.
- **moltoffer (`@rushcoder2`)**: *"The real game changer is letting agents run while you sleep. Wake up to finished tasks > babysitting Claude all day."* — cross-confirms [[sairahul1-solo-founder-13-agent-playbook-2026-05-15|sairahul1's "agents working while you sleep"]] framing from the same week.
- **Reddit `Ok-Ship812`**: *"Infinite recursion might inflate those api costs to surprising levels. I'd hope there would be default protections against that in place but I would not bet my dangly bits on it."* — operational-cost-runaway concern; pairs with Carlos's *"How does /goal work in terms of token costs, 5h and weekly rates in Codex?"* question.
- **Reddit `pro-vi`** (re: context handling): *"[/goal] doesn't [automatically compact]. That's why it's an inferior implementation than the original Ralph loop."* — Ralph-loop-purist counter-take that Anthropic's implementation lacks the context-management discipline of the original pattern. **Worth holding as a practitioner-disputed claim**: Anthropic's official post says `/goal` checks the condition against the transcript; whether the transcript is auto-compacted is not specified.

### Disputed origin claim

- **Johannes Copeland (`@AIByJohannes`)**: *"Copied from Codex btw."* — one-line claim that `/goal` originated in Codex and was copied by Claude Code. No corroboration; no Anthropic response. Captured as a disputed-origin data point.
- Deutscher's framing: *"Already active in Claude Code AND Codex"* — neutral on origin, names both.

## Why It Matters

- **First wiki capture of Anthropic openly identifying the Ralph loop** as the underlying mechanism for `/goal`. Prior wiki content covers the Ralph loop only implicitly through agentic-engineering discussions; this is the **vendor-side acknowledgment that the long-running-loop primitive is now a default Claude Code feature**.
- **Luca Capone's CLAUDE.md-as-prerequisite framing is the load-bearing finding**: long-running primitives like `/goal` are only as good as the project-context discipline they execute against. This is **the inverse direction** of how [[claude-md-pattern]] has typically been framed — until now, CLAUDE.md was discussed as a per-session quality improvement; Luca's framing makes it a **prerequisite for unattended-execution capability** that the wiki has not previously captured.
- **Five Claude Code long-running primitives now named in one official post**: `/goal`, `/loop`, `/schedule`, stop hooks, auto mode. Pairs with [[zephyr-7-claude-setups-2026-05-15|Zephyr's setup #5 (scheduled tasks)]] and [[milesdeutscher-claude-personal-cfo-2026-05-14|Deutscher's BotFather/Dispatch mobile-access patterns]] — the **unattended-execution-stack is now structurally complete** as of mid-May 2026.
- **Security framing (Soo Yoon)** is the cleanest single-sentence statement of the new risk surface created by long-running unattended agents: *"prompt injection is the new SQL injection."* If `/goal` adoption grows, prompt-injection-during-loop becomes the load-bearing security failure mode. The wiki has lighter coverage of agent-security than agent-capability; worth elevating on a future pass.
- **Operational-cost concerns** are surfacing across both X and Reddit threads — token-cost-of-unattended-loops is named as a binding practical constraint. Pairs with [[latentspace-codex-rises-claude-meters-2026-05-14|Anthropic's subscription-metering formalization]]: long-running primitives raise the cost-floor right as Anthropic is metering API-rate-equivalent overage.

## Caveats

- **Three drops are clipped at different fidelities**: ClaudeDevs is a verbatim Anthropic-official thread; Reddit tutorial is anonymous-poster summary with bot moderator artifact; Deutscher amplification is content-marketing register with valuable comment-thread payload. Treat ClaudeDevs as authoritative on what `/goal` is; treat Reddit + Deutscher as practitioner reception data.
- **Origin claim ("Copied from Codex")** is uncorroborated. The Ralph loop predates both Codex and Claude Code as a community-known agentic pattern; vendor-side priority on `/goal` syntax specifically is not settled by this surface.
- **Context-auto-compaction question (Reddit pro-vi)** is unresolved. Worth verifying against Anthropic's documentation on a future pass.
- **No quantitative benchmark** for `/goal` success-rate, token-cost overhead, or completion-time vs manual re-prompting. All evidence is anecdotal.

## Cross-references

- [[claude-code]] — the host tool; updated with `/goal` + companion long-running primitives + Ralph-loop-mechanism acknowledgment.
- [[claude-md-pattern]] — Luca Capone's CLAUDE.md-as-prerequisite framing is the inverse-direction reinforcement of the pattern.
- [[zephyr-7-claude-setups-2026-05-15]] — Zephyr's setup #7 was the first wiki mention of `/goal`; this is the dedicated Anthropic-official capture.
- [[milesdeutscher-claude-personal-cfo-2026-05-14]] — same author's earlier wiki capture; BotFather / Dispatch mobile-access pattern complements the unattended-execution stack.
- [[sairahul1-solo-founder-13-agent-playbook-2026-05-15]] — same-week "agents working while you sleep" framing; cross-confirmed by moltoffer comment in the Deutscher thread.
- [[svpino-subagent-pilled-2026-05-15]] — adjacent multi-agent-decomposition discipline; subagent-per-task + `/goal`-per-subagent is the natural composition.
- [[agentic-engineering]] — `/goal` is the Karpathy-discipline operationalized as a vendor-supplied primitive.
- [[agentic-ai]] — `/goal` is the Claude-Code-specific instance of the broader long-running-agentic-loop pattern.

## Pages Updated

- [[claude-code]] (updated — `/goal` + `/loop` + `/schedule` + stop hooks + auto mode named as Claude Code long-running primitives under Key Concepts; Ralph-loop-mechanism acknowledgment captured; Anthropic-official documentation pointer added; date bumped to 2026-05-18)
- [[claude-md-pattern]] (updated — Luca Capone's "/goal only works well when CLAUDE.md is solid" framing added as a Notable Variant: CLAUDE.md-as-prerequisite for unattended-execution capability, inverse-direction of the typical per-session-quality framing; date bumped to 2026-05-18)
