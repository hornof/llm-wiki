---
name: Gemini
type: model
provider: Google DeepMind
status: available
last_updated: 2026-10-28
---

> **Status note:** `available` refers to Gemini 4 Argon, which has been generally available since 2026-10-13. **Gemini 4 Carbon** (2026-10-28) is restricted: cyber defenders first, then trusted partners in the Fairwind Program, with no public date yet. The status field doesn't fit that, the same gap as [[claude-mythos]].

## What It Is

Google's frontier model line, built by [[google-deepmind]]. This page covers the Gemini 4 generation, which has two frontier tiers so far:

| Model | Announced | General availability | Introductory price (input / output, per 1M tokens) |
|---|---|---|---|
| **Gemini 4 Argon** | 2026-09-30, cyber defenders only | 2026-10-13: API, AI Studio, Antigravity, Gemini app, AI Mode in Search | $2 / $10 until 2026-11-30, then $4 / $20 |
| **Gemini 4 Carbon** | 2026-10-28, cyber defenders only | not announced | $2 / $10, then $4 / $20 |

- **Context:** Argon has a 1M-token limit shared between input and output. Output was raised from 64K to 1M ([[google-gemini-4-argon-launch-2026-10-13]]). Carbon's limit isn't stated.
- **Other Gemini models the wiki mentions:** Gemini 3.8 Flash (and a "3.8 Flash Cyber" variant), Gemini Omni, which anchors [[deepmind-genie-4-world-model-2026-10-27|Genie 4]]'s simulations, and Gemini Robotics.
- **The release pattern is the distinctive part.** Both Gemini 4 models went to cyber defenders before anyone else, with Google *"actively engaged in the U.S. government’s voluntary process"* for pre-release testing. Argon took two weeks from announcement to general availability. If Carbon follows the same gap, it would reach general availability around mid-November (my inference; Google gave no date).

*This page was created 2026-10-28. On 2026-09-30 [[google-deepmind]] recorded the missing page as the wiki's most valuable page to create, and held off until a primary source was fetched.*

## Strengths & Weaknesses

**All numbers below are Google's.** No independent evaluation is in the wiki yet.

- **Cybersecurity is the lead claim.**
  - Carbon: SEC-bench Pro 88.2%, ExploitGym 54.8%, CWE-bench 71.0%, all evaluated without guardrails ([[google-gemini-4-carbon-2026-10-28]]).
  - Argon: 68% on CWE-bench v1.
  - Google's Chrome team says Carbon beat an unnamed lab's frontier model by more than 10× at writing patches.
- **Long-horizon engineering:**
  - Google says Carbon runs "for days" on multi-step tasks.
  - Argon's internal record includes C/C++-to-Rust migrations of 800K+ lines and a refactor of a 6M-line Chromium folder.
  - Argon raised agentic code submissions in Antigravity 35%+ and cut rollbacks by nearly a third.
- **Rankings Google cites:**
  - Carbon is #1 on the Artificial Analysis Intelligence Index v5.0 (59) and #4 on WebDev Arena (1768).
  - Argon is #1 on the Vals Index and AutomationBench (51.3%), and scores 77.9% on DeepSWE v1.1.
- **Alignment claims for Carbon:**
  - Terminal-Bench 4.0 cheating at 0.0%, with cheating attempts at 0.4%.
  - High-severity misalignment alerts down almost 80%.
  - About half as many unsupported claims as Argon.
  - Prompt-injection success on Gray Swan IPI at 0.0%, against Argon's 0.7%.
- **Weaknesses:** none recorded yet, because the wiki has only Google's posts. The Terminal-Bench cheating number is worth checking against [[claude-opus-5-5|Opus 5.5]]'s harness record, and so is the 10× Chrome comparison, which doesn't name the competitor.

## When to Use It

- **Argon** is the generally available choice. Budget for its price doubling after 2026-11-30.
- **Carbon** is cyber-defense only for now.
- Pick these for long-context work (1M tokens) and security tasks. For other work there's no independent evidence yet; compare on your own tasks.

## Community Sentiment

**Nothing independent yet.** Digg's summary of the Carbon launch called the figures *"Google’s characterizations, not independently established results"* ([[google-gemini-4-carbon-2026-10-28]]). Gemini's agent incident on 2026-09-18 is recorded on [[google]].

## Resources

- [[google-gemini-4-carbon-2026-10-28]] — Carbon announcement
- [[google-gemini-4-argon-launch-2026-10-13]] — Argon announcement (09-30) and general availability (10-13)
- [[google-deepmind]] — the lab
- [[dailybrief-roundup-2026-10-01]] — Argon's first appearance in the briefs, headline only
