---
title: "Jane Street's generate-backtest-kill trading loop (cvxv666 / Horizon promo)"
type: source
medium: twitter-thread
url: https://x.com/antpalkin/status/2074919448008356077
ingested: 2026-07-09
---

> [!note] Promotional framing + unverified figures
> This is a viral X post that doubles as a promo for **Horizon** (`@horizon_trade_x`), which markets a retail version of the loop. The headline figures — $6B spent, 4,032 GPUs, $39.6B 2025 revenue — are **unverified marketing claims**. Ingested for the *loop pattern* and the built-in skeptic critique, not the numbers.

## Summary

A viral post (clipped 2026-07-09) framing **Jane Street's edge as a loop, not an idea**: AI agents that **generate → backtest → kill → repeat** thousands of trading strategies a week, keeping only what survives out-of-sample data. Notable because the promoting product's own tagline is *"How Quants Use **Loop Engineering** to Build Alpha"* — the [[loop-engineering]] register has reached quant-trading marketing.

## Key Claims / Takeaways

- **The pattern (the signal)**: a **two-agent loop** — one agent **builds** a strategy, a second agent **tries to kill it** (backtests ~5 years in seconds; only survivors go live). This is the **generator + adversarial-verifier** architecture the wiki already tracks under [[loop-engineering]] (Zodchii builder-checker, McDonald "design the verifier") — here applied to quantitative trading. *"The edge was never a smarter idea. It was volume… test 100 strategies for every 1 you test by hand, and a second agent kills the 97 that only look good on old data."*
- **Horizon** (`@horizon_trade_x`) markets a chat-box version: one plain-English sentence spins up the same two agents for retail. Promoted as *"$150B setup, free while beta open."*
- **The skeptic critique is the important part** (and validates the wiki's verifier-ceiling thread):
  - *"The multiple testing bias here is off the charts"* / *"if they actually did it as simply as you say they'd just be overfitting"* — surviving "data it's never seen" across thousands of trials is textbook **data-mining / multiple-testing bias**. A loop that goes green isn't correct; it satisfied the verifier ([[loop-engineering|"the quality is capped by the verifier"]]).
  - *"The part that actually mattered was Jane Street firing anyone who fell in love with their own strategy — which Horizon cannot do for you."* The human discipline (kill your darlings) is the real edge; the tool automates the mechanism, not the discipline.

## Why it matters

Two things worth capturing: (1) **loop-engineering vocabulary and the generator/adversarial-verifier pattern have crossed into quant-finance** — an out-of-domain confirmation of the pattern's generality; (2) the reply thread is a clean, real-world articulation of the **overfitting ceiling** on generate-and-filter loops — more trials without genuine out-of-sample discipline manufactures false winners. Treat the Jane Street figures as unverified promo; keep the *pattern + critique*.

## Pages Updated

- [[loop-engineering]] — generator/adversarial-verifier loop in quant trading + the overfitting-ceiling critique
