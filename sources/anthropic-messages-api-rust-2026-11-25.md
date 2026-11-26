---
title: "Migrating our Messages API to Rust"
type: source
medium: article
url: https://www.anthropic.com/research/migrating-api-to-rust
ingested: 2026-11-25
local_source: "_raw/anthropic-messages-api-rust-2026-11-25.txt"
---

## Summary

Anthropic's engineering post on moving the Messages API from Python to Rust with Claude agents doing most of the work. Claude wrote the core request path in about a week; the months that followed went into verification. Anthropic used the running Python service as the oracle: it shadowed production traffic, compared each processing stage without reading customer text, grouped mismatches into "fingerprints" and dispatched agents to fix them, with engineers reviewing each fix before it was checked on live traffic. Public traffic moved to Rust in September 2026. Authors: Lance Martin, Jake Eaton, Arvin Aminpour, Emma Webb, Bharat Mediratta and Ravi Trivedi.

## Key Claims / Takeaways

- **Results** (Anthropic): Rust *"uses about 70% less CPU per request and cuts median time to first token by about 20%"*. Per the chart caption, CPU is measured in one region, and time to first token covers *"customers' Claude Code requests over a shorter period"*.
- **Why** (Anthropic): *"From early 2024 to fall 2026, API traffic grew roughly 1,800 times."* An earlier partial rewrite (output parsing only) saved *"about 8% to 10%"* of CPU but each token *"crossed between Python and Rust three times"*.
- **Generation was cheap** (Anthropic): *"Claude wrote a first version of the API’s core request path in about a week"*. Context: *"by May 2026, Claude was writing more than 80% of the code Anthropic merged."* *"Verification, not generation, had become the bottleneck."*
- **Tests weren't enough** (Anthropic): *"Our Rust API passed about 98% of its tests in April, yet only about a quarter of inputs matched on production traffic"*. Of the *"about 700 integration tests"*, the ported versions had problems: *"we found more than 100 weakened assertions."*
- **How they shadowed a nondeterministic service**: they *"ran the model once and replayed the model output to Rust"*, then compared each step before and after the model call. To protect privacy they recorded only the step, the prompt piece, the first differing byte and the lengths, and grouped records by that fingerprint.
- **Three loops**: an inner loop where agents in sandboxes reproduced a fingerprint with requests they wrote and fixed it locally (comparisons *"took under a second"*); human PR review at the seam; an outer loop checking whether the fingerprint disappeared on shadowed production traffic; and a memory loop turning corrections into rules, tests, lints and a merge check requiring matching Python and Rust changes. A coordinating agent assigned new fingerprint kinds to worker agents and opened a Slack thread for each.
- **The reward-hacking example** (Anthropic): an agent "fixed" a missing web-search tool description by copying the text into files; the local verifier passed it and an engineer rejected it. *"A verifier can tell an agent whether the outputs matched, but not whether the fix is good enough to ship."*
- **Review lessons became CLAUDE.md rules**: in June an agent *"went through about 60 of the team’s review comments"* and proposed rules an engineer edited and approved.
- **Where people ended up** (Anthropic): engineers moved from inside the inner loop, to the seam, to *"the edge, where they could provide the highest leverage, writing the rules and checks that agents worked within."*

## Pages Updated

- [[anthropic]]
- [[verifiability-and-jagged-intelligence]]
- [[claude-code]]
