---
name: Claude Mythos
type: model
provider: Anthropic
status: announced
last_updated: 2026-05-07
---

## What It Is

Claude Mythos is an [[anthropic]] preview model — not yet generally available as of May 2026. Surfaced publicly through two channels in the same week:

1. **Mozilla preview-access partnership** (May 2026): Mozilla used Mythos preview access to drive a 20× monthly fix-volume jump on Firefox, including a 20-year-old XSLT bug and 15-year-old `<legend>` bug — [[willison-firefox-claude-mythos-2026-05]].
2. **Anthropic interpretability research**: Mythos preview is one of three models Anthropic's Natural Language Autoencoders paper benchmarks against (alongside Claude Opus 4.6 and Claude Haiku 3.5) — [[anthropic-natural-language-autoencoders-2026-05]].

## Strengths & Weaknesses

- **Security-bug discovery**: produces vulnerability reports good enough that Mozilla shipped 423 fixes in a single month (April 2026) — a categorical jump from the prior baseline of ~20-30 monthly fixes against AI-generated bug reports. Mozilla quote (via Willison): "Suddenly, the bugs are very good."
- **Reasoning depth signal**: implied capability jump that matters for security review specifically — moves AI-generated bug reports across the slop/signal threshold for an open-source flagship project.
- **No public benchmarks** as of May 7 2026 — Mythos is preview-only; standard frontier-model benchmark numbers haven't been published.

## When to Use It

- **Public availability**: not yet GA. Access is via Anthropic preview-access program; structure and eligibility not publicly documented.
- **First-party Anthropic interpretability work**: NLA paper uses Mythos as one of the target models, suggesting it's part of Anthropic's research pipeline as well as a future product.

## Community Sentiment

Limited — only two public references as of May 7 2026. Both are Anthropic-adjacent (Mozilla has preview access; Anthropic's own research uses it). Independent practitioner sentiment will require wider availability.

## Naming Convention

The "Mythos" name breaks the established Opus/Sonnet/Haiku tier pattern — first time Anthropic has named a Claude model outside that scheme since the 4.x families launched. Worth tracking whether Mythos is a tier above Opus, a research-track sibling, or a different positioning entirely. Insufficient public detail to call this yet.

## Resources

- [[willison-firefox-claude-mythos-2026-05]] — Mozilla / Firefox security partnership; production-grade existence proof
- [[anthropic-natural-language-autoencoders-2026-05]] — Anthropic interpretability research using Mythos
- [[willison-code-w-claude-2026]] — Code w/ Claude 2026 event coverage; Mythos surfaced separately from Opus 4.7 announcement
