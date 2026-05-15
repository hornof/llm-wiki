---
title: "Willison: programming languages used to be LOCK IN, and they're increasingly not so"
type: source
medium: article
url: https://simonwillison.net/2026/May/14/not-so-locked-in/
ingested: 2026-05-15
---

## Summary

Simon Willison short blog item, 2026-05-14, amplifying Mitchell Hashimoto's framing of Bun's migration from Zig to Rust under coding-agent leverage: *"Programming languages used to be LOCK IN, and they're increasingly not so."* Willison pairs it with a same-week practitioner anecdote of a mid-sized tech company completing a **coding-agent-driven rewrite of legacy iPhone and Android apps to React Native**, selected because they could *"port back to native"* if circumstances changed. The provisional-vs-binding distinction is the load-bearing claim: agentic coding is converting platform-stack choices from one-way doors into reversible bets.

## Key Claims / Takeaways

- **Mitchell Hashimoto verbatim** (from Bun's Zig→Rust migration thread): *"Programming languages used to be LOCK IN, and they're increasingly not so."* The Bun project's reversal — moving the JavaScript runtime backend from Zig to Rust under agent leverage — is the cited primary signal.
- **Anonymous practitioner anecdote**: a mid-sized tech company rewrote legacy iPhone + Android apps to **React Native** under coding-agent leverage. The selection criteria explicitly included reversibility — *"acknowledged they could port back to native if circumstances changed."*
- **The structural claim**: agentic coding lowers the maintenance burden that traditionally favored cross-platform / framework choices. Once the maintenance-cost differential shrinks, the *direction* of the platform choice matters less than the *reversibility*.
- **Adjacency to [[willison-james-shore-maintenance-2026-05-11|the maintenance-cost identity]]**: Shore's framing was *if AI lets you ship 3× faster, maintenance must drop to 1/3 or you've mortgaged tech debt*. This piece is the same maintenance-cost claim restated as a strategic-flexibility primitive: if maintenance cost drops, *all platform choices become more reversible*.
- **No specific numbers** in the Willison post (no LOC counts, no hours, no cost). The piece is short on metrics, long on framing.

## Why It Matters

- **Reversibility-as-the-new-default** is a useful primitive for VPE-evaluation conversations. The traditional argument-from-lock-in (React Native vs native, Postgres vs alternative, single-cloud commit) was always proportional to migration cost. If agentic coding compresses migration cost, every prior platform-lock-in argument needs to be re-evaluated.
- **Pairs cleanly with the [[end-of-finetuning]] thesis**. The end-of-finetuning argument was that constitutional spec + JVLP replaces task-specific weight updates. The end-of-platform-lock-in argument has the same shape: agent leverage replaces one-way platform commits with reversible bets. Both are "the binding constraint just dropped" stories.
- **Bun's Zig→Rust reversal as the primary signal** is structurally important — Bun was *built on* Zig as a deliberate technical choice (Andrew Gallant pre-LLM-era reasoning). The Zig→Rust move under agent leverage is the cleanest existence proof that even apparently-committed platform choices can flip.
- **Wiki maintenance angle**: this argument applies to the wiki's own technical stack and the [[llm-wiki-pattern]] discipline. The lower-lock-in regime means the choice of (Obsidian-vault + git + Claude Code) is itself a *reversible* bet — informative for any wiki-architecture-evolution conversation that comes up later.
- **Identity-mirror to [[anthropic-spacex-higher-limits-2026-05-06|the SpaceX/Colossus compute lock-in]]**: at the *infrastructure* tier, frontier labs are *increasing* their lock-in (multi-year compute deals); at the *application* tier, builders are *decreasing* their lock-in (agent-driven platform reversibility). The two trends run opposite directions — concentration at the substrate, dispersion at the top.

## Cross-references

- [[people/simon-willison]] — amplification surface; consistent voice on practitioner-side AI-coding implications.
- [[willison-james-shore-maintenance-2026-05-11]] — maintenance-cost identity; structural prior for the lock-in argument.
- [[end-of-finetuning]] — same "binding constraint just dropped" shape applied to model adaptation.
- [[tools/claude-code]] — the harness this kind of agent-driven platform migration would run on.

## Pages Updated

- [[people/simon-willison]] (updated — Hashimoto "languages used to be LOCK IN" amplification + legacy-mobile rewrite anecdote added under notable takes)
