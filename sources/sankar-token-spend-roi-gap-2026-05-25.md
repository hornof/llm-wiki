---
title: "Sankar: 100k token spend → 18k ships; 44% wasted on bug-fixes"
type: source
medium: twitter-thread
url: https://x.com/Aiswarya_Sankar/status/2059298259949232484
ingested: 2026-05-27
---

## Summary

Aiswarya Sankar X post (2026-05-25, quote-tweeting Ed Zitron on Uber): *"This is what we've been seeing with every company we work with. Try justifying spending 100k on token spend when only 18k even makes it to a stable prod feature. In the rush to maximize AI token spend, companies are wasting over 44% on bug fixes."* The Zitron quote-tweet surfaces a **Uber COO Andrew Macdonald** statement (via Business Insider, 2026-05-26) that it is *"getting harder to justify"* AI costs because there is no demonstrable link between AI spend and meaningful feature output — flagged by Zitron as *"the first time I've seen a company say this directly."*

## Key Claims / Takeaways

### Headline numbers (Sankar field-data framing)

- **$100K token spend → $18K shipped** as the typical funnel observed across Sankar's client base. Implied 82% non-shipped rate.
- **>44% of token spend goes to bug-fixes** (Sankar framing). Quoted-comment from Dex (@divmgl) extends: *"Rework at $0.27 is low. I'd be willing to bet rework will become $0.70 once companies and engineering teams catch wind."*
- **Methodology not surfaced**: client sample size, "stable prod feature" definition, and the "44%" categorization basis are not specified in the post. **Verification-pending.**

### The Uber COO datum (quote-tweet via Zitron)

- **Andrew Macdonald, Uber COO**: AI costs are *"getting harder to justify"* — no demonstrable link between AI spend and meaningful feature increase. Reported by Business Insider, 2026-05-26.
- **Zitron's framing**: *"first time I've seen a company say this directly"* — names this as a discrete event in the AI-ROI narrative arc.
- **Why it matters**: Uber is a public-market operator at material AI-spend scale; a sitting COO publicly questioning AI ROI is qualitatively different from analyst skepticism. Verification-pending: the Business Insider primary was not fetched; the precise Macdonald quote and full context (was this an earnings call? interview? off-record?) need confirmation.

### Counter-take in comments (Robert Nowell)

- *"100k spent → 18k shipped is a pretty reasonable value funnel and I would argue mirrors historical engineering effort pretty well. 80% of the time, what you prototype doesn't make it to production. That's R&D. If you ship 100% of the code you write, you are shipping junk."*
- **The framing question Sankar replies with**: *"the best way to measure this is what is the PR close (not merge) rate before and after. The % of PRs that are either closed without merging or left open indefinitely has also skyrocketed since AI code gen."*
- **Why the counter-take matters**: it reframes the same $100K→$18K funnel as a normal R&D ratio, not a new failure mode. The empirical test Sankar proposes — **PR-close-rate delta pre- vs post-AI-codegen** — is the falsifiable version. If pre- and post-AI rates are similar, the "rework crisis" narrative weakens; if post-AI close rates are materially higher, the narrative strengthens.

### conor brennan-burke framing

- *"tokenmaxxing is a mistake. the key metric is not how many tokens you spend, it's how many actually become useful."*
- Sankar replies: *"exactly!"*
- **Coins / surfaces "tokenmaxxing"** as the rhetorical anti-pattern: optimizing for token throughput rather than shipped-value yield.

## Pages Updated

- [[ai-roi-gap]] — new topic page; Sankar's $100K→$18K funnel + 44% rework figure are the practitioner-data anchor
- [[ai-labor-market-impacts]] — counter-anchor evidence (token-spend-vs-feature-output as a productivity-paradox data point)

Verification-pending: Sankar's client-base sample size and methodology for the 44% figure; Macdonald quote provenance and full context; PR-close-rate delta as proposed-but-unmeasured falsifiable test.

## Adjacent sources

- [[cyb3rops-four-stages-ai-coding-hype-2026-05-26]] — quote-tweets this post; same theme framed as the "grind phase" of a 4-stage hype cycle
- [[levie-ceo-ai-psychosis-2026-05-23]] — executive-side framing of the same gap (CEOs see happy path, operators see rework)
- [[techcrunch-bort-ceo-ai-psychosis-2026-05-27]] — TechCrunch synthesis that cites layoffs.fyi + MIT + Berkeley research
