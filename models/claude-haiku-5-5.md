---
name: Claude Haiku 5.5
type: model
provider: Anthropic
status: available
last_updated: 2026-11-15
---

## What It Is

[[anthropic|Anthropic]]'s small, fast model, released 2026-10-07 ([[anthropic-claude-haiku-5-5-2026-10-07]]). It's meant for high-volume, cost-sensitive work and as a subagent under [[claude-opus-5-5|Opus 5.5]] or Sonnet 5.5 on coding tasks. It's the first Haiku-class model with an adjustable effort setting. Model ID `claude-haiku-5-5`; available on the Anthropic API, AWS, Google Cloud and Azure.

**Price:** $0.10 per million input tokens for prompts up to 100k tokens and $0.50 above that; output $0.50 and $2.50 on the same split. Haiku 4.5 was $1.00 input and $5.00 output, and Anthropic says the average cost to run is about 75% lower.

## Strengths & Weaknesses

- **Well behind Sonnet 5.5 on agentic coding, closer on computer use** (Anthropic's numbers): Terminal-Bench 4.0 39.2% against Sonnet 5.5's 70.6%, and OSWorld 2.1 (offline subset) 72.4% against 83.9%. Haiku 4.5 scored 0.0% on Terminal-Bench 4.0, so this is a large step for the tier.
- **No independent benchmarks yet.** The wiki has only Anthropic's launch figures.

## When to Use It

- **Subagents, classification, summarization, routing and extraction**, where volume matters more than the hardest reasoning. At a tenth of Haiku 4.5's input price, it's the default choice for this kind of work. [Judgment, from the launch page.]
- **Not for long, unattended coding runs.** The Terminal-Bench gap says to keep those on Sonnet or Opus.

## Community Sentiment

- **2026-10-28: playing games against GPT-6 Luna.** One of [[simon-willison]]'s vibe-coded browser games, Battle Drones, pits models against each other, and the demo shows Haiku 5.5 against GPT-6 Luna ([[willison-vibe-game-development-2026-10-28]]). A demo, not a measurement.
- **2026-11-05: its system card carries Anthropic's R&D acceleration estimate.** METR's assessment cites a 1.7x speed-up in Anthropic's AI R&D from the Haiku 5.5 system card, lower than METR's own figure because METR includes unreleased internal models ([[metr-anthropic-ai-rd-acceleration-2026-11-05]]).

## Resources

- [[anthropic-claude-haiku-5-5-2026-10-07]]: Anthropic's launch post (price, benchmarks, availability)
- [[willison-vibe-game-development-2026-10-28]]: Battle Drones demo
- [[metr-anthropic-ai-rd-acceleration-2026-11-05]]: the system-card figure, via METR
- [[anthropic]]: model lineup table
