---
name: Mozilla
type: company
status: active
last_updated: 2026-05-07
---

## What It Is

Mozilla is the nonprofit-backed organization behind Firefox, Thunderbird, and a portfolio of open-source web infrastructure. First wiki appearance in May 2026 in an AI-engineering context: Mozilla had preview access to [[claude-mythos]] and used it to drive a step change in Firefox security-fix throughput.

## Traction Signals

- 2026-05 — **20× monthly fix volume jump**: Firefox security fix volume rose from a baseline of ~20-30 per month to **423 in April 2026 alone** under [[claude-mythos]] preview access. Specific finds included a 20-year-old XSLT bug and a 15-year-old `<legend>` element bug — see [[willison-firefox-claude-mythos-2026-05]].
- Mozilla quote, captured by Willison: "Suddenly, the bugs are very good." And: "It is difficult to overstate how much this dynamic changed for us over a few short months."

## Practices Worth Tracking

- **Filter-not-firehose workflow**: Mozilla's framing — "steering them, scaling them, and stacking them to generate large amounts of signal and filter out the noise" — is the same shape as the production-quality agent stacks captured elsewhere in the wiki ([[heygurisingh-career-ops]], Karpathy's review-every-diff discipline in [[agentic-engineering]]).
- **Defense-in-depth compounds**: Many model-attempted exploits were caught by Firefox's existing security mechanisms. Existing security work compounds with model-driven discovery rather than getting bypassed.

## Resources

- [[willison-firefox-claude-mythos-2026-05]] — primary source: Willison's coverage of Mozilla's Claude Mythos preview-access program (May 2026)
- [[claude-mythos]] — model used in the partnership
