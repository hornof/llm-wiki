---
title: "Anthropic launches Claude Opus 5 — 'Fable-level intelligence at half the cost-per-task,' same $5/$25 per-token price as Opus 4.8, 'most aligned model to date' (2026-07-24)"
type: source
medium: vendor-announcement
url: https://www.anthropic.com/news/claude-opus-5
ingested: 2026-07-25
---

## Summary

Anthropic launches **[[claude-opus-5|Claude Opus 5]]** (2026-07-24, `claude-opus-5`) — the new Opus generation, positioned as *"the frontier intelligence of [[claude-fable-5|Claude Fable 5]] at half the price"* while keeping the **same $5/$25 per-token price as [[claude-opus-4-8|Opus 4.8]]** (the "half" is cost-*per-task* efficiency). Headline behavioral gain: much stronger at **verifying its work and iterating until it succeeds**. Also Anthropic's *"most aligned model to date."* Anchor source for [[claude-opus-5]]. *(Primary fetched.)*

## Key Claims / Takeaways

- **Positioning**: *"greatly improved performance for the same cost as its predecessor, Opus 4.8"*; approaches Fable 5 (CursorBench 3.2 within **0.5%** of Fable 5's peak). Now **default on Claude Max, strongest on Claude Pro**; API + Claude.ai + Claude Code + Cowork; released 2026-07-24.
- **Pricing nuance**: **$5/M in, $25/M out — identical to Opus 4.8.** "Half the price" = **cost per task** (efficiency), per multiple customers reporting *"half the cost per task"* vs Fable 5. Fast Mode ~2.5× speed at 2× base price.
- **Benchmarks (vendor)**: Frontier-Bench v0.1 >2× Opus 4.8; ARC-AGI 3 **3× next-best**; Zapier AutomationBench ~1.5× (*"Opus 5 hit 100%"*); OSWorld 2.0 beats Fable 5 at ~⅓ cost; life-sci / organic-chem (+10.2pp) / protein (+7.7pp) over 4.8.
- **Verify-and-iterate** is the named differentiator — the verifier-discipline the [[loop-engineering]] / [[reward-hacking]] threads emphasize, now a marketed model capability.
- **Alignment/safety**: *"most aligned model to date"*; adheres to Constitution better than 4.8 / Sonnet 5 / Fable 5; **lowest deceptive-behavior rates**; behavioral-audit **2.3** (lowest). Cyber: substantially behind [[claude-mythos|Mythos 5]]; cyber classifiers intervene ~85% less than Fable 5; blocks binary vuln-scanning / pentest / exploit-gen.
- **Prompt-injection** (companion, [[boris-cherny|Cherny]] via [Willison](https://simonwillison.net/2026/Jul/25/boris-cherny/), 2026-07-25): flagged as the **hardest-to-prompt-inject model yet** per the system card — not in the main announcement.

## Why it matters

- **Strict upgrade at constant per-token cost** for existing Opus-4.8 workloads — the "just swap the model id" case, unusual for a generation bump.
- **Safety-as-differentiation**: the "most aligned / lowest deception / hardest to prompt-inject" framing lands directly amid the [[reward-hacking|ExploitGym]] agentic-misalignment discourse — Anthropic positioning Opus 5 as the *trustworthy* frontier-tier option.

## Pages Updated
- [[claude-opus-5]] (new), [[prompt-injection]]

## Verification-pending
- Context window (unstated).
- Independent benchmark replication (all figures Anthropic-published).
- The prompt-injection-resistance claim's specifics (Cherny/system card, not the announcement).
