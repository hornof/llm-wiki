---
name: Reflection AI
type: company
focus: open-weight frontier models
status: emerging
last_updated: 2026-11-15
---

## What It Is

**Reflection AI** (often just "Reflection") is a New York lab, founded in 2024, that builds open-weight frontier models and presents itself as an American alternative to Chinese open models such as [[deepseek|DeepSeek]] ([[forbes-ai-50-2026]]). Its founders are **Misha Laskin** and **Ioannis Antonoglou**, former [[google-deepmind|Google DeepMind]] researchers who led early Gemini work. Forbes's 2026 AI 50 lists $2.1B raised at an $8B valuation, from investors including [[nvidia|Nvidia]], [[sequoia-capital|Sequoia]], Lightspeed and 1789 Capital. At the time of that list it had not released a model and was building a data center in South Korea.

Its first model, **Beam** (501B parameters), shipped in October 2026 under Apache 2.0, with its tokenizer and the training harness it used.

*(Page merged 2026-09-10 from the former `reflection` + `reflection-ai` split. Rewritten 2026-11-15 to remove `canonical-` filler from an automated pass. The earlier version gave "$5.4B–$6.3B" as one deal's range; the figures come from two reports. It also carried two claims no source in the wiki supports, one about an investor's partner and one about building custom AI for Korean companies; both were removed.)*

## Traction Signals

- **2026-10-16: Beam's licence and harness** ([[dailybrief-roundup-2026-10-16]], Digg). Beam is available across platforms as Apache 2.0 open weights. Reflection is also releasing the tokenizer and Mirror CLI, the open-source harness it used to train Beam. The repo, [`reflection-oss/mirror`](https://github.com/reflection-oss/mirror), is a terminal coding agent that edits files, runs commands and runs parallel tasks in separate worktrees; it had 15 stars on 2026-10-16. Labs that ship open weights don't usually ship the agent harness used in training, so this is the unusual part. See [[domain-specific-harness]]. *(Digg summary plus the brief's repo entry; architecture and benchmarks still not captured.)*
- **2026-10-06: Beam, a 501B open-weight model** ([[dailybrief-roundup-2026-10-06]], reflection.ai; not fetched). It shipped the same day as [[mistral-ai|Mistral Large 4]], whose weights were staged for three weeks later. Nothing beyond the parameter count was captured that day.
- **2026-06-22: compute lease from SpaceX's Colossus 2** ([[spacex-reflection-ai-150m-month-compute-deal-2026-06-22]]). TechCrunch reports $150M a month and $5.4B through 2029; a Digg summary gives $6.3B for a lease of Nvidia GB300 GPUs from [[colossus-2|Colossus 2]]. Neither source explains the gap. It's the only Colossus 2 tenant the wiki knows of.
- **2026-04: Forbes AI 50** ([[forbes-ai-50-2026]]): $2.1B raised, $8B valuation, still pre-product.

## Key People

- **Misha Laskin** and **Ioannis Antonoglou**: co-founders, formerly at Google DeepMind.

## How to Use It

Beam's weights are open under Apache 2.0, and Mirror is on GitHub. The wiki hasn't recorded benchmarks, hardware needs or where Beam is hosted.

## Compared To

- **Other open-weight labs:** [[mistral-ai|Mistral]] (sold to European governments as a non-American option), [[allenai|Ai2]] and [[meta|Meta]]'s Llama. Forbes frames Reflection as the American answer to DeepSeek ([[ai-50-2026-snapshot]]), which makes open weights a geopolitical position as much as a technical one.

## Resources

- [[forbes-ai-50-2026]]: founders, funding, investors
- [[ai-50-2026-snapshot]]: open source as a geopolitical play
- [[spacex-reflection-ai-150m-month-compute-deal-2026-06-22]]: the Colossus 2 lease
- [[colossus-2]]: the cluster
- [[dailybrief-roundup-2026-10-06]], [[dailybrief-roundup-2026-10-16]]: Beam and Mirror
