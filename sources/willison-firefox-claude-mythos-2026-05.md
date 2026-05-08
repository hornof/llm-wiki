---
title: Behind the Scenes Hardening Firefox with Claude Mythos Preview
type: source
medium: article
url: https://simonwillison.net/2026/May/7/firefox-claude-mythos/
ingested: 2026-05-07
---

## Summary

[[simon-willison]] post (May 7 2026) covering [[mozilla]]'s account of using preview access to [[claude-mythos]] to find and ship security fixes in Firefox. The volume jumped from a baseline of ~20-30 monthly fixes to **423 in April 2026 alone**, including a 20-year-old XSLT bug and a 15-year-old `<legend>` element bug. Mozilla's quote captures the capability transition: "Suddenly, the bugs are very good." Willison flags this as a real signal change — AI-generated bug reports went from "unwanted slop" to net-positive enough that an open-source flagship project shipped fixes against them at scale.

## Key Claims / Takeaways

- **First documented Mozilla-tier security partnership with a frontier model**: Mozilla had Anthropic preview access to Claude Mythos, a successor model not yet generally available.
- **Capability jump, not incremental progress**: 20× monthly fix volume in a single month is the kind of step change that lets you separate "model improving" from "model crossing a usefulness threshold."
- **Workflow pattern (Mozilla)**: "Steering them, scaling them, and stacking them to generate large amounts of signal and filter out the noise." Filter-not-firehose — same pattern surfacing in [[heygurisingh-career-ops]] and other production agent stacks.
- **Defense-in-depth signal**: Many model-attempted exploits were blocked by Firefox's existing defenses — the team found this reassuring. Suggests existing security work compounds with model-driven discovery rather than getting bypassed by it.
- **Willison's mood on it**: Surprised. Cites the inversion of his previous skepticism about AI bug reports as "slop."
- **Anthropic preview-access program**: existence confirmed but program structure / eligibility not in the post.

## Why This Matters for the Wiki

First wiki appearance of [[claude-mythos]] (preview Anthropic model not yet GA) and [[mozilla]]. Provides the first ceiling-side production-grade existence proof for AI-driven vulnerability discovery at the open-source-flagship scale — distinct from B2B security tooling vendor claims. Adjacent to [[anthropic]]'s broader security-review product surface announced at Code w/ Claude 2026 ([[willison-code-w-claude-2026]]).

## Pages Updated

- [[claude-mythos]] — new model page (preview)
- [[mozilla]] — new company page
- [[anthropic]] — Mythos preview + security research traction added
- [[simon-willison]] — additional notable take added
