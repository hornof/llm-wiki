---
title: Karpathy X post — HTML as the new default LLM output format
type: source
medium: twitter-thread
url: https://x.com/karpathy/status/2053872850101285137
ingested: 2026-05-11
---

## Summary

[[andrej-karpathy]] X post (May 8 2026) quote-tweeting [[thariq-shihipar]]'s article "Using Claude Code: The Unreasonable Effectiveness of HTML." Karpathy independently confirms the pattern ("This works really well btw") and stretches it into a generalized taxonomy of LLM-output formats with a clear progression: **raw text → markdown → HTML → ... → interactive neural videos/simulations**. Explicitly bridges the HTML-output pattern to the [[model-rendered-ui]] / Flipbook trajectory by citing [[thread-zan2434-flipbook]] as the speculative endpoint.

## Key Claims / Takeaways

- **Confirms the HTML-output trick at primary-voice level**: "at the end of your query ask your LLM to 'structure your response as HTML', then view the generated file in your browser. I've also had some success asking the LLM to present its output as slideshows, etc."
- **Audio-in / vision-out asymmetry**: "audio is the human-preferred input to AIs but vision (images/animations/video) is the preferred output from them." Argues ~1/3 of the human brain is dedicated to vision; vision is "the 10-lane superhighway of information into brain." Output format should match this bandwidth asymmetry, not bottleneck on it.
- **4-step taxonomy of LLM output format evolution** (Karpathy's framing, verbatim):
  1. **raw text** — hard/effortful to read
  2. **markdown** — bold, italic, headings, tables; a bit easier on the eyes — **current default**
  3. **HTML** — still procedural with underlying code, but a lot more flexibility on graphics, layout, interactivity — **"early but forming new good default"**
  4. *...skipped intermediate steps (slideshows, mixed media)...*
  - **n. interactive neural videos / simulations** — generated directly by a diffusion neural net; the speculative endpoint
- **Explicit bridge to model-rendered-ui**: cites [[thread-zan2434-flipbook]] (Flipbook prototype) as "the direction" the taxonomy extrapolates toward. First time the wiki has a Karpathy-level voice connecting the HTML-output-prompting practitioner pattern to the [[model-rendered-ui]] research direction.
- **Open question**: how exact/procedural "Software 1.0" artifacts (e.g. interactive simulations) get woven together with neural artifacts (diffusion grids). Karpathy flags this as an open architectural problem on the path from step 3 to step n.
- **Input-side companion**: "audio nor text nor video alone are not enough, e.g. I feel a need to point/gesture to things on the screen." Pointing/gesturing as the missing input modality. Mind-meld framing — not BCI, just more bandwidth.
- **"TLDR: hot tip try ask for HTML"** — Karpathy explicitly markets the prompt-level swap as a near-term high-leverage practitioner trick, alongside the longer-arc taxonomy framing.

## Practitioner reception (comment thread)

- **Theodore Twombly (@IAmTheoTwombly)**: "I ended up having it save every html it has generated and integrate it into my internal wiki so that I can just have my local, personal website that I can refer to from time to time." Implies a [[llm-wiki-pattern]]-adjacent emergent use — HTML output as a *durable artifact* rather than an ephemeral render.
- **Mohammad Siam (@SiamSaaS)**: "'structure your response as HTML' is the most underrated prompt trick. Instantly turns any LLM output into a shareable, formatted document."
- **Cameron Cundiff (@ckundo)**: pointing to artifact.land as an existing surface for HTML-output sharing — practitioner-built ecosystem already forming.

## Why This Matters for the Wiki

- **Upgrades [[concepts/model-rendered-ui]]** from a single-prototype concept (Flipbook) to a Karpathy-articulated trajectory with intermediate stages (HTML is *between* current Markdown defaults and the eventual Flipbook endpoint).
- **Strengthens the [[claude-code]] HTML-output practitioner pattern** by giving it a primary-source Karpathy citation rather than only the Willison amplification of Thariq's article.
- **First-class connection between the [[claude-code]] practitioner surface and the [[model-rendered-ui]] research surface** — these have been tracked separately until now. Karpathy's taxonomy is the bridge.

## Pages Updated

- [[andrej-karpathy]] — new notable take added (HTML taxonomy / audio-in vision-out)
- [[thariq-shihipar]] — upstream-relationship note (Karpathy is amplifying Thariq's article, not the other way around)
- [[model-rendered-ui]] — Karpathy taxonomy added as the 4-stage framing connecting current HTML practitioner pattern to Flipbook-style endpoint
- [[claude-code]] — HTML pattern now cites Karpathy as a primary voice in addition to Willison/Thariq
- [[willison-html-effectiveness-2026-05]] — cross-reference: Karpathy independently amplified the same Thariq article on May 8
