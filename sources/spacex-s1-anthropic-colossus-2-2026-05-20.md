---
title: "SpaceX S-1 confirms Anthropic compute deal; Colossus 2 expansion (unconfirmed)"
type: source
medium: article
url: https://simonwillison.net/2026/May/20/spacex-s1/
ingested: 2026-05-21
---

## Summary

Two adjacent signals surfaced via 2026-05-21 Daily Brief: (1) **Simon Willison's quote of SpaceX's S-1 filing** confirming the Anthropic × SpaceX Colossus compute deal previously captured at the [[anthropic-spacex-higher-limits-2026-05-06|Anthropic-side announcement May 6 2026]]; (2) **@nottombrown X post** flagging Anthropic expansion to **Colossus 2** with GB200 chips — "unconfirmed" per brief framing. These two signals together upgrade the wiki's Colossus thread from Anthropic-marketing-announcement-only ([[anthropic-spacex-higher-limits-2026-05-06]]) to **publicly-filed-document confirmation** (S-1) plus **forward-looking expansion signal** (Colossus 2 GB200 deployment). Primary documents (SpaceX S-1, nottombrown tweet) not deeply fetched in this ingest pass.

## Key Claims / Takeaways

### What the SpaceX S-1 reveals (per Willison framing)

- **SpaceX filed S-1** (IPO registration document) and the filing includes disclosure of the **Anthropic compute deal**. First wiki-captured public-filing-grade confirmation of the deal — prior wiki coverage was Anthropic-side marketing announcement only.
- **Cross-confirms the deal exists** at the disclosure-required level. Public companies (or near-public companies) must disclose material customer relationships in S-1 filings; SpaceX's inclusion of Anthropic in their S-1 confirms the relationship is material to SpaceX's revenue.
- **Brief framing**: *"SpaceX selling compute to Anthropic. That's the move — vertical integration of training infra. Elon's AI play isn't about Grok anymore; it's about owning the electricity and silicon."* Worth holding this framing alongside the [[willison-anthropic-xai-colossus-2026-05|prior Willison capture]] where Willison flagged the **non-commercial discretionary "harm" clause** that gives Musk unilateral authority to reclaim compute — that clause becomes more material now that the relationship is publicly filed.

### What the nottombrown Colossus 2 signal claims

- **Anthropic expanding to Colossus 2** with GB200 chips. Unconfirmed per brief framing.
- **Source**: `@nottombrown` X post — not a Forbes-tier or WSJ-tier source. Treat as practitioner-secondary pending corroboration.
- **GB200** is NVIDIA's Grace Blackwell GB200 NVL72 series, the highest-end NVIDIA training-and-inference platform as of 2026. Colossus 2 housing GB200 would be the **second-largest single training facility on GB200** captured in the wiki after the original Colossus 1 deployment.

### What's still not captured

- **Specific compute scale of Colossus 2** in the Anthropic-Colossus 2 lease (Colossus 1 was 300+ MW / 220K+ NVIDIA GPUs per [[anthropic-spacex-higher-limits-2026-05-06]]).
- **Pricing terms** — is Colossus 2 priced like Colossus 1 (~$5B/year per [[willison-anthropic-xai-colossus-2026-05]] AINews framing) or a different rate?
- **Discretionary "harm" clause** — does the Colossus 2 lease carry the same non-commercial discretionary reclaim clause that Colossus 1 has?
- **SpaceX S-1 specifics** — Willison's post quotes the S-1; the full quoted language and any context around customer-concentration risk should be captured on deep-fetch.

### Same-day context: Hark $700M Series A (separate Digg item)

- **Hark raises $700M Series A at $6B post-money** with NVIDIA + AMD participating (Parkway Venture Capital lead). Same-day signal on the AI-compute-and-foundation-model funding wave (captured in [[dailybrief-roundup-2026-05-21]]).
- Pairs with the Colossus 2 expansion signal as **two same-day signals on AI-compute-capacity capital deployment**.

## Why It Matters

- **Public-filing-grade confirmation upgrades the Colossus thread.** Prior wiki coverage was Anthropic-marketing-only; SpaceX S-1 disclosure is regulator-filed-grade evidence. Worth tracking the S-1's specific risk-factor language around AI-customer dependency.
- **The non-commercial "harm" discretionary reclaim clause** becomes more material when the deal is publicly disclosed. Public-equity investors in SpaceX (post-IPO) get to read that clause in the prospectus; whether it's flagged as a risk factor or a competitive advantage is a tell on how SpaceX positions the AI-compute business.
- **Colossus 2 GB200 expansion (if confirmed) would deepen Anthropic's compute lock-in to SpaceX-controlled infrastructure** — and concentrate Anthropic's training stack on a vendor relationship governed by Musk's discretion. Pairs with [[antonleicht-frontier-ai-access-cut-off-2026-05-13|Leicht's frontier-AI-access framework]]: structural vendor-concentration risk for Anthropic specifically.
- **The frontier-lab IPO cluster expands**: [[openai-ipo-filing-2026-05-20|OpenAI preparing to file]] (May 20) + SpaceX S-1 filed (with Anthropic disclosure) in the same week. Two structurally-significant capital-formation events in the AI-infra layer in three days.

## Caveats

- **Neither primary deeply fetched.** Willison's post quotes the S-1 but the full S-1 language, Anthropic-disclosure-specifics, and any risk-factor flags around the relationship not captured. @nottombrown tweet not directly fetched.
- **Colossus 2 expansion is unconfirmed** per brief framing. Treat as practitioner-secondary signal pending corroboration.
- **Conflict-of-narrative**: Willison's framing emphasizes the SpaceX-as-AI-infra-vendor move; the underlying Anthropic strategy may also be diversification (the [[anthropic-claude-platform-aws-2026-05|Claude Platform on AWS]] partnership from May 12 is the other-vendor-side of the same training-vs-inference decoupling). Worth holding both.
- **Musk-discretionary "harm" clause** is still the load-bearing wild card. If it's enforceable and Musk uses it, the entire Anthropic training stack is at his unilateral discretion. Public-filing disclosure makes the clause harder to walk back later.

## Cross-references

- [[anthropic-spacex-higher-limits-2026-05-06]] — original Anthropic-side announcement of the Colossus 1 deal.
- [[willison-anthropic-xai-colossus-2026-05]] — Willison's initial framing including the discretionary "harm" clause + ~$5B/year pricing.
- [[anthropic-claude-platform-aws-2026-05]] — Anthropic's other-vendor-side training-vs-distribution decoupling.
- [[openai-ipo-filing-2026-05-20]] — same-week IPO-filing companion signal; OpenAI is also preparing to file.
- [[antonleicht-frontier-ai-access-cut-off-2026-05-13]] — vendor-concentration-risk framing relevant to Anthropic's SpaceX lock-in.
- [[anthropic]] — entity page updated with S-1 confirmation + Colossus 2 unconfirmed expansion signal.

## Pages Updated

- [[anthropic]] (updated — SpaceX S-1 confirmation of Colossus deal + Colossus 2 GB200 unconfirmed expansion signal added under compute-and-infrastructure traction signals; date bumped to 2026-05-21)
