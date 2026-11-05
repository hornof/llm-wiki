---
title: "Qwen 3.8 27B on my laptop can interpret model weights, too"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/
ingested: 2026-11-05
---

## Summary

[[simon-willison|Simon Willison]] reran the first experiment from [[takehi-weight-space-programming-2026-11-02|Sparks of Weight-Space Programming]]: give a model the raw weights of a small game-playing network as text, with no tools, and ask which game it was trained on. Qwen 3.8 27B on a laptop got three of four games right, taking 46 to 65 minutes each. Willison separates the paper's two claims and says the wider commentary goes too far. AINews (2026-11-04) adds a Reddit report of Claude editing 8 neurons of Gemma 4 12B the same way.

## Key Claims / Takeaways

- **Two claims, treated separately.** *"The paper combines two topics that I think deserve to be treated separately"*: what models can do with raw weights without running anything, and what they can do once armed with code. Willison takes the no-tools one as *"the more interesting of the two"*.
- **Critics named.** *"spaCy author Matthew Honnibal called the paper misleading for conflating the two, and Sean Goedecke deconstructed the Qwen3.5-0.8B update example as taking the same steps that a human ML researcher would use."* Neither critique was fetched.
- **Qwen 3.8 27B results.** Pac-Man after *"46m 12s and 43,506 reasoning tokens"* at 72% stated confidence; Pong *"in 1h 4m 54s"*; Breakout *"in 52m 25s"* at 88%. *"Qwen failed at the Freeway prompt"*, calling it a Pac-Man-like game. Willison runs it in LM Studio; the default 8,192-token context *"failed with errors"*.
- **Kimi K3.1 Pro** via OpenRouter *"successfully guessed Breakout after 9m 41s and 19,493 reasoning tokens"*.
- **Willison's limits.** *"I expect a sufficiently experienced human being armed with a notepad and a pencil could get there with enough effort."* And: *"I'm not ready to declare that the age of source code is over"*.
- **Reproducible.** The prompts are public in the paper's repo (`RikiyaT/lm_understand-logs`, folder `exp1_which_game`) and run with Willison's `llm -f <url>`.
- **A practitioner edit (Reddit, via AINews, 2026-11-04).** Using Claude Opus 5.5 with a Python kernel and direct weight access, one user edited *"8 MLP neurons—about 92k / 11.9B parameters, roughly a 100 KB diff"* of Gemma 4 12B to change how it translates one Italian past tense, and reports *"182/200 unrelated translations unchanged"*. Self-reported; this one used tools, so it's the paper's second claim, not the first.

## Pages Updated

- [[qwen]] — Community Sentiment
- [[gpt-6-astra]] — weight-space section, follow-up note
- [[simon-willison]] — Current Focus
