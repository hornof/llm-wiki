---
title: "Yann LeCun on What Comes After LLMs (Unsupervised Learning, Jacob Effron)"
type: source
medium: podcast-episode
url: https://www.youtube.com/watch?v=ngBraLDqzdI
ingested: 2026-05-18
---

## Summary

Long-form interview (May 15 2026) between Jacob Effron (Redpoint, Unsupervised Learning podcast) and Yann LeCun, covering: (1) the AMI Labs technical thesis — world models / JEPA as the path to "AI for the real world"; (2) **Tapestry**, LeCun's parallel sovereign-AI / federated-training open-platform play; (3) why LeCun left Meta and his view of Llama 4 as a disappointment that catalyzed organizational refocus; (4) the divergence in 2023 from Hinton and Bengio over GPT-4; (5) latest JEPA-collapse-prevention work (**SIGREG** / "L-E world model" paper); (6) flat assertion that *"LLMs are intrinsically unsafe."* First wiki capture of LeCun's full current technical and organizational narrative in one interview.

## Key Claims / Takeaways

### "AI for the real world" — AMI Labs thesis

- **AMI = Advanced Machine Intelligence.** Motto: *"AI for the real world."* LLMs are useful for language-substrate domains (math, code, legalese); the physical world is *"high-dimensional, continuous, noisy, messy"* and requires a different architecture.
- **World model = ability to predict consequences of own actions.** *"From my point of view, I cannot imagine how you can even think of building an agentic system without that system having the ability to predict the consequences of its actions."* Once you have prediction, you can **plan by search and optimization** — not autoregressive next-token generation.
- **Pixel-level prediction is a losing proposition.** Five-year-ago epiphany: every successful self-supervised image/video representation method (Dino V1/V2/V3, MAE, MoCo, BYOL) is non-generative; generative ones (VAE, sparse autoencoders, masked autoencoder I-MAE) have been disappointing.
- **Joint Embedding Predictive Architecture (JEPA)** — take an image, corrupt it, run both through encoders, predict the representation of the original from the corrupted one. Works much better than predicting pixels.
- **Hierarchical world models** within ~1 year. *"We'll have a general methodology to train hierarchical models on a very wide variety of modalities."* Plans 12–18-month timeline for action-conditioned world-model demonstrations on robotics, industrial process control, healthcare.
- **5-year "world domination"** — *"Linus Torvalds said his goal was 'total world domination,' and he actually managed to do it; the entire internet runs on Linux."* LeCun's analogous claim for world models, delivered with the same explicit joke.
- **Headquartered in Paris** with NY office — *"purposely set up the headquarters of AMI Labs in Paris"* to escape Silicon Valley *"herd behavior"* where *"everybody is digging the same trench."*

### "By early 2027 it'll be obvious to everyone" — paradigm-shift timeline

- *"I think the realization that you need a change of paradigm is happening as we speak and will become completely obvious to people by early 2027. Now that doesn't mean we'll have a solution by then."* — first wiki-captured concrete LeCun timeline for paradigm-shift recognition (not for the technology landing).
- *"VLAs (vision-language-action models) are now seen as a failure — not reliable enough, requiring too much training data."* Brick on the road to robotics.

### Data-efficiency anchor: the 17-year-old driver

- *"How is it that a 17-year-old can learn to drive in like a dozen hours or maybe 20 hours? We have millions of hours of training data of people driving cars. We still don't have level-five learning cars. So imitation learning obviously doesn't work even for just the task of autonomous driving."* — Cleanest data-efficiency calibration anchor for the world-model vs imitation-learning argument.

### "LLMs are intrinsically unsafe"

- *"LLMs are intrinsically unsafe. I don't think they can be made reliable and safe. They cannot be made reliable because you can't stop them from hallucinating. And if they are agentic, you cannot guarantee they're not going to take an action that they didn't predict the outcome of."*
- *"Some of my colleagues at Meta didn't like me saying this, but..."* — LeCun explicitly acknowledges this is an internal-controversial position.
- Coding is the exception *"because you can actually verify that the code you generate satisfies your specification. But not everything is coding."* Cites coding agents *"wiping up your hard drive"* as the obvious failure-mode genre.
- **Objective-driven AI architecture as the fix**: give the system a *cost function* describing task completion + *safety constraints* it cannot violate by construction; the system optimizes a sequence of actions against a world-model prediction. *"The LLM can always escape. There's a gap between training error and test error. There's always going to be a prompt where the system is going to do really stupid things."*

### Tapestry: sovereign AI for the rest of the world

A separate idea LeCun has been forming for 3 years: a **federated-learning open-platform LLM** where contributors keep their data local but share **parameter vectors**.

- **The need**: *"If you're someone outside the US or China and your AI assistant was built in California or Beijing, you may speak a language those systems haven't been trained to handle particularly well, you may have a culture not particularly well understood by people in Silicon Valley and China, not well represented by training data publicly available on the internet... a value system, political opinions absolutely not represented."*
- **The mechanism**: contributors exchange parameter vectors with a global server; each local worker updates toward the global consensus while training on local data; *"as training progresses, all those parameter vectors converge towards a consensus model essentially which is kind of a repository of all human knowledge."*
- **The sovereignty pitch**: *"There's a lot of countries — India, France, Vietnam, Morocco, Switzerland, Korea, Japan, Kazakhstan — who absolutely want some level of sovereignty for AI not just for their industry but also for the citizen. They don't want the citizen to get brainwashed by a Chinese model or a California model."*
- **The historical analogy**: *"Remember who the big players of the internet infrastructure were in 1996. Sun Microsystems, HP, Dell... All of this was totally wiped out by Linux. The entire internet runs on Linux. Even Microsoft Azure runs Linux. So OpenAI, Anthropic etc. of today are the Sun Microsystems and HPUX of yesterday."* — strong, dated, falsifiable claim.

### Why LeCun left Meta — the Llama 4 disappointment narrative

- **Llama 4 disappointed.** *"Llama 4 was a bit of a disappointment, and because Mark Zuckerberg was disappointed by it he kind of rebooted the entire organization, reorganized it and hired new people, etc."*
- **Two-mode R&D mismatch**: in 2023 GenAI was created, taking ~60–70 scientists from FAIR; that organization was *"under so much short-term pressure that it became very conservative"* — so the mismatch wasn't between FAIR and Meta, it was between FAIR research and the GenAI product organization.
- **Mistral genesis**: *"Two of the authors of Llama basically created Mistral with another guy from Google"* during the Llama-2 → Llama-3 handover. *"This is not a happy time at Meta for various reasons."*
- **Meta dropped its robotics AI group** (led by Dhruv Batra, *"now at Amazon"*). *"Most of the applications were probably for things Meta was not particularly interested in"* — manufacturing, healthcare, industrial process control.
- **The Scale acquisition catalyzed**: *"Yeah, definitely. I don't have any sort of inside information to comment on this, but it's possible that Mark sees in Alex (Wang) kind of a potential successor to himself, like a younger version of himself."* — LeCun is careful but lets the framing stand.
- **Zero technical contribution to Llama**: *"My one contribution to Llama was to argue for open-sourcing Llama 2."* During a months-long internal debate, with legal/policy opposed and Bosworth + engineering for, LeCun and Bosworth pushed for open-sourcing. *"In fact that's exactly what happened. We jump-started the AI industry by open-sourcing Llama 2."*

### Why his views diverged from Hinton and Bengio (2023)

- *"I didn't change my mind. They changed their mind. And at just about the same time, and it was basically GPT-4."*
- **Hinton's calculation**: cortex has ~16B neurons; if backprop needs ~10 actual neurons per virtual neuron, that's ~1.6B virtual neurons, *"oh my god GPT-4 is close to this, so maybe it's as smart as humans."* LeCun: *"I do not believe this claim at all... This is Jeff's way of saying 'I can retire, I can declare victory.'"*
- **Hinton softened more recently**: *"He's much less vocal about the potential dangers now than he was a year or two ago. He kind of realized [LLMs are] probably not a way to design truly intelligent systems."*
- *"Same kind of thing with Yoshua. I think what they are both worried about is the ability of society and the political system to ensure the benefits of AI would be maximized and AI would not just make a few rich people even richer."* — Bengio's concern is the political-economy version, not the doomer scenario.
- **Anthropic critique**: *"Certainly not as apocalyptic as what even Anthropic has claimed, and has tried to lobby governments into scaring governments into regulating AI... I don't subscribe to this at all."* On whether Anthropic genuinely believes the safety framing: *"I think they genuinely believe it but also I think there are some commercial reasons for them to believe that and to brainwash some people and government into thinking their systems are dangerous."* — LeCun's sharpest dated critique of Anthropic's safety positioning to date.

### Latest research: SIGREG and "LEworldmodel" paper

- **JEPA collapse problem**: trivial solution is for the system to predict a constant representation — *"representation collapse."* Multiple anti-collapse approaches:
  - **Contrastive learning** (LeCun's 1993 method) — works but doesn't scale with dimension.
  - **Becker-Hinton 1989 / Schmidhuber 1992** — mutual-information maximization.
  - **Distillation methods (Dino, BYOL)** — work but theoretically not well understood.
  - **Variance regularization** — VICReg (2022) → **SIGREG (Sketched Isotropic Gaussian Regularization)**, work by Randall Balestriero (now at Brown) and student at MILA: forces the distribution of encoder outputs to be jointly Gaussian; cleanest information-content regularizer to date.
- **Recommended read**: the **LEWorldModel** paper — *"If you want to read one paper, read that paper. It's L-E world model. I'm not responsible for the name; Randall picked it up."*

### "LLMs are not software architects"

- *"LLMs are good programmers. They're not software architects. They're not computer scientists. They can program for us. So they're not in a state where they can just replace humans entirely. It changes the world of humans. Humans now go one level up in the abstraction hierarchy and our world is to decide what to build. But like building it, you can get help from LLMs."*
- *"LLMs are particularly successful at domains where the language itself is the substrate of reasoning — not for anything else."* This is the cleanest single-sentence statement of why LeCun expects the LLM curve to flatten on tasks like *"a stem cell to turn into a pancreas beta cell that produces insulin"* (he uses the type-1 diabetes example specifically).

### Self-supervised learning surprise

When asked what he's changed his mind on: *"What surprised me is that self-supervised learning became incredibly successful, but not for video — for language. LLMs basically are a blindingly successful example of self-supervised learning."* — LeCun acknowledges he didn't predict LLMs would be the breakout self-supervised-learning success.

## Why It Matters

- **Most complete LeCun narrative captured to date**. Previous wiki sources have AMI Labs financials and one-liner LLM-skeptic quotes; this interview provides the full technical, organizational, and personal arc in LeCun's own voice over 80+ minutes.
- **"By early 2027 it'll be obvious"** is a **falsifiable timeline** for paradigm-shift recognition. Adds to the wiki's timeline-calibration triangle alongside [[zephyr-karpathy-10-year-agent-window-2026-05-14|Karpathy's 10-year window]], [[kris-lovejoy|Lovejoy's 2031 IT-admin-50%]] prediction, and [[import-ai-456-clark-rsi-radical-optionality-2026-05-11|Korinek's 6-year explosive regime]].
- **"OpenAI/Anthropic = Sun Microsystems and HPUX of yesterday"** is a strong, dated, falsifiable claim about commercial closed-source AI labs — pairs cleanly with [[willison-legacy-mobile-rewrite-2026-05-14|Willison's "languages used to be LOCK IN"]] thesis but applied at the company-stack level.
- **Tapestry as first wiki capture** of LeCun's sovereign-AI / federated-training play. Distinct from AMI Labs technically (federated LLM training, not world models); distinct organizationally; complementary thesis.
- **"LLMs are intrinsically unsafe"** is the cleanest single-sentence anti-LLM safety framing LeCun has stated publicly. Worth holding against [[anthropic]]'s safety-first positioning as a deliberate counterweight.
- **Llama 4 disappointment + Scale-acquisition succession framing** are non-trivial reporting about Meta's internal state. LeCun is the highest-credibility direct-witness source on this.
- **"Predicting in token space vs abstract representation space"** is the cleanest framing of the world-model thesis: *"What I'm talking about with JEPA is you don't do this in token space. You do this in abstract thoughts space."*

## Caveats

- **Interview format limits primary-document precision**. Quotes are captured verbatim from the transcript provided; if any are eventually contested in print, the transcript is the source of record.
- **LeCun has commercial incentives** to talk down LLMs (he runs an explicitly anti-LLM-architecture lab). The substantive technical arguments (data efficiency, planning-vs-autoregression, abstract representation) stand on their own; the framing language ("dead end," "intrinsically unsafe") is doing work beyond the technical content.
- **Tapestry has no public release timeline, no named partners, no demo**. Captured as an articulated thesis, not a deployed system. If the project ships, the source becomes more anchoring; until then, treat as LeCun's stated strategic direction.
- **"Anthropic brainwashing governments" framing** is rhetorically loaded and would be unusual coming from a less senior figure. Capture verbatim; do not propagate as wiki-voice claim.

## Cross-references

- [[yann-lecun]] — entity page; major update with AMI Labs/Tapestry/Llama-4-disappointment/Hinton-Bengio-divergence narrative.
- [[ami-labs]] — entity page; updated with Paris HQ rationale, 5-year-domination timeline, hierarchical-models 1-year roadmap.
- [[world-models]] — concept page; updated with SIGREG anti-collapse method and LEWorldModel paper as recommended read.
- [[meta]] — should create or update with Llama 4 disappointment, robotics-group dissolution, Scale-acquisition-as-succession framing.
- [[anthropic]] — capture LeCun's "brainwashing governments" critique under counter-takes.
- [[mistral]] — Llama-author origin story (two Llama authors + a Google engineer founded Mistral during Llama-2 → Llama-3 handover).
- [[andrej-karpathy]] / [[kris-lovejoy]] / [[import-ai-456-clark-rsi-radical-optionality-2026-05-11]] — timeline-calibration triangle: LeCun "by early 2027 obvious" / Karpathy 10-year / Lovejoy 2031 / Korinek 6-year explosive regime.
- [[willison-legacy-mobile-rewrite-2026-05-14]] — adjacent thesis on languages as no-longer-LOCK-IN; LeCun extends to company stack via the Sun/HPUX/Linux analogy.

## Pages Updated

- [[yann-lecun]] (updated — "by early 2027 obvious" timeline, Tapestry first capture, Llama 4 disappointment + Mistral genesis + Scale/Wang succession framing, divergence-from-Hinton-Bengio 2023, "LLMs intrinsically unsafe" framing, SIGREG/LEWorldModel pointer; date bumped to 2026-05-18)
- [[ami-labs]] (updated — Paris HQ rationale + 1-year hierarchical-model roadmap + 12–18-month world-model demos + 5-year-domination framing + "AI for the real world" motto; date bumped to 2026-05-18)
- [[world-models]] (updated — SIGREG anti-collapse method + LEWorldModel recommended-read pointer + "predict in abstract representation space, not token space" framing; date bumped to 2026-05-18)
