---
title: "Deep Neural Nets: 33 years ago and 33 years from now"
type: source
medium: article
url: http://karpathy.github.io/2022/03/14/lecun1989/
ingested: 2026-05-06
---

## Summary
Karpathy reimplements LeCun et al. (1989) handwritten digit recognition in PyTorch and uses it as a lens to argue that deep learning's macro architecture has been roughly constant for 33 years — the revolution has been scale (data, model size, compute) and minor algorithmic upgrades. He extrapolates 33 years forward to a 2055 in which users interact with mega-models in natural language. Resurfaces on the 2026-05-06 Daily Brief because the 2055 projection reads as exactly the [[software-3-0]] thesis Karpathy formalizes 4 years later.

## Key Claims / Takeaways
- **1989 baseline**: LeCun et al. — 9,760 parameters; 7,291 16×16 digit images; 3 days on a SUN workstation; ~4% test error.
- **Reproducibility note**: original dataset was lost; reconstructed from MNIST. PyTorch reimplementation reaches similar test error.
- **Compute scale**: 3 days → 90 seconds on M1 MacBook (~3,000× speedup).
- **Data + model scale**: ~100M× more pixel information; ~1,000,000× larger networks (vs typical modern vision models).
- **Algorithmic upgrades**: cross-entropy loss + AdamW + dropout cut error 60% with no extra data — "small" changes contribute meaningful gains.
- **Macro-level constancy** (verbatim): "Not much has changed in 33 years on the macro level. We're still setting up differentiable neural net architectures made of layers of neurons and optimizing them end-to-end with backpropagation."
- **Forward projection** (verbatim): "you will ask a 10,000,000X-sized neural net megabrain to perform some task by speaking... to it in English." The natural-language interface to a mega-model is the [[software-3-0]] thesis stated 4 years before he names it.

## Pages Updated
- [[andrej-karpathy]] — added under "Notable Takes" as the early 2022 articulation of what becomes Software 3.0
- [[software-3-0]] — added the 2022 essay as a foundational primary source predating the AI Ascent 2026 talk
- [[index]] — added under Sources & References → Foundational primary sources

## Notes
- This is a 2022 essay surfaced in 2026; treating as a foundational secondary source (Karpathy's own historical commentary), filed alongside [[karpathy-llm-wiki-overview]] and [[karpathy-llm-wiki-gist]].
