---
title: "The Jev Revolution: What Engineers Are Already Building with System One Models"
type: source
medium: article
url: https://latent.space/p/jev-revolution/
ingested: 2026-11-12
---

## Summary

Richard MacManus for [[latent-space|Latent Space]] (2026-11-11), from the AI Engineer Code Summit. TypeSafe CEO Diogo Almeida's keynote called for putting [[jev|Jev]] calls inside ordinary code. Glean and UiPath showed how they use it. It's conference reporting, so the claims are the speakers' own.

## Key Claims / Takeaways

- **Definition used at the summit:** *"non-generative models that return structured choices, scores, or probabilities"*, faster and cheaper than reasoning LLMs.
- **Almeida's pitch:** Jev is *"reliable intelligence"* for *"just automating everything"*, and *"code is the language of automation , therefore you need to integrate with code."* His line on LLM reliability: *"you get Einstein 95% of the time, but Mr. Bean 5% of the time."*
- **Glean:** used alongside LLMs and classifiers, suited to *"zero-shot flexibility."* Users shouldn't care which kind of model is behind a feature: *"we want to hide away all the complexity of whether we are using Jev or we are using a full-blown LLM."*
- **UiPath's tournament:** Jev ranks document chunks in small groups and the winners advance round by round. The whole process *"took under a second , even with thousands of Jev calls."*
- **For the owner:** the useful pattern is treating a decision model as a function call inside code, not a chat model, and composing many cheap calls (UiPath's tournament). [Judgment.]

## Pages Updated

- [[jev]] — Community Sentiment
