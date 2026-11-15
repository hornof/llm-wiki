---
title: "What thousands of conversations look like inside a language model"
type: source
medium: article
url: https://operator0x.com/field-notes/qwen-conversation-state-space/
ingested: 2026-11-15
---

## Summary

A field note by Operator_0x, an independent author, mapping the internal states of [[qwen|Qwen3-1.7B]] across a few thousand question-and-answer examples in four languages plus Python. It records the final-layer vector at each token and projects them into 3D. The pictures suggest conversations lie on a thin sheet, with Chinese offset from the Latin-script languages. The useful part is that the author then measures how much the pictures mislead. Treat it as a careful exploratory post, not a paper: single-turn examples, one layer, one small model.

## Key Claims / Takeaways

- **Setup:** frozen Qwen3-1.7B, *"each position’s vector contains 2,048 numbers"*. *"900 question-and-answer examples per language"* in English, Chinese, German and Croatian, plus *"90 Python coding examples"*. Qwen generated the answers itself, so the languages aren't exact translations.
- **The flat sheet:** in 3D, *"a best-fitting plane contained approximately 99.3% of the English token states’ variation within this 3D projection"*.
- **Then the check:** *"that view left out 82.4% of the original variation"*, and *"the best plane fitted in the full space captured only 28.7%"*. The sheet is mostly a product of the projection.
- **Still structured:** three directions holding 17.6% is *"roughly 120 times"* what an even spread would give. The main axes *"strongly tracked language, with topic structure still present after accounting for language."*
- **Choice of frame changes the picture:** fitting the projection to conversation averages instead of the vocabulary moved the captured share of average-vector variation from *"42.4%"* to *"80.1%"*.
- **Caveats the author states:** *"These are single question-and-answer examples, not sampled real-world multi-turn conversations."* Lines between points are *"a visual aid"*, not measured trajectories, and variance *"measures geometric spread, rather than an amount of meaning or reasoning."*
- **For the owner:** a worked example of how a 3D embedding plot can look meaningful and capture under a fifth of the data. Worth remembering before trusting any PCA picture of model internals. [Judgment.]

## Pages Updated

- [[mechanistic-interpretability]] — new section
- [[qwen]] — Community Sentiment
