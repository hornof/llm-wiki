---
title: "Gemini Decisions API"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/11/gemini-decisions-api/
ingested: 2026-11-11
---

## Summary

[[simon-willison|Simon Willison]] (2026-11-11) on Google's **Gemini Decision 1**, a model that answers predefined questions with scores instead of text. That makes Google the third vendor in the decision-model category after [[jev|Jev]] and OpenAI. Google's own announcement wasn't fetched; prices and features are as Willison gives them.

## Key Claims / Takeaways

- **Same shape as Jev:** *"it supports the same three types of questions (yes/no, choice, and rubric-scoring) and even reuses Jev's term "Noul" for a yes/no question."*
- **Price:** the same as OpenAI's GPT-6 Luna decision model, *"10 cents per million input tokens, and output is free. Jev remains the cheapest of the three, at 4.2 cents per million."*
- **Modalities:** Jev is text and JSON only, OpenAI's handles text and images, and Gemini *"covers text, images, audio, video, and PDFs."*
- **Probabilities, not verdicts.** On a video test, Jev and OpenAI *"both return 1.0 or 0.0 for yes/no questions"*, while Gemini returned graded values such as a 0.92 probability that the video showed a robot (`0.9234055387792485`).
- **What it means for the owner:** three vendors with near-identical APIs makes the category easier to adopt, since it can be swapped. Gemini's graded probabilities are the one real difference, if they are calibrated. Nobody has checked that yet. [Judgment.]

## Pages Updated

- [[jev]] — Compared To
- [[gemini]] — What It Is (decision model)
