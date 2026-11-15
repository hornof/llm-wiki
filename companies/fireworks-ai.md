---
name: Fireworks AI
type: company
focus: inference hosting for open-weight models
status: gaining-traction
last_updated: 2026-11-15
---

## What It Is

**Fireworks AI** hosts open-weight models behind an API, so developers can use them without running their own GPUs. Forbes's 2026 AI 50 lists it as founded in 2022 in San Mateo, with $327M raised at a $4B valuation, and as one of four female-led companies on the list ([[forbes-ai-50-2026]]). In practice the wiki meets it as one of the hosts that serve new open-weight releases on day one.

The page was created on 2026-11-15, when a second customer, Uber, disclosed it had been hit by the same Fireworks breach as Notion.

## Traction Signals

- **2026-11 breach, two known customers.**
  - **Notion** (notice fetched 2026-11-10, [[notion-fireworks-ai-incident-2026-11]]). Fireworks told Notion on November 6 that attackers may have accessed customer data. The exposed data was Notion AI chat transcripts, without user or workspace labels, from under 1% of workspaces. Notion used Fireworks to classify chats for its Insights feature and to serve open-weight models; Insights is disabled.
  - **Uber** (2026-11-14, Digg citing Engadget and TechCrunch, recorded on the same page). Uber named Fireworks as the vendor hacked on October 9. State notices cover 7,870 drivers in three states so far. Fireworks attributed the attack to a group that sells stolen tokens for LLM access.
  - Fireworks' own notice hasn't been fetched, so the wiki doesn't know how many customers were affected in total.
- **2026-05-27: reported at decacorn valuation** ([[dailybrief-roundup-2026-05-27]], Latent Space headline). Latent Space put Fireworks and Baseten past $10B. That's well above Forbes's $4B from about a month earlier; the wiki has no primary source for either round.
- **Serves new open-weight models at launch:** GLM 5.2, at about $4.40 per million tokens per Martin Alderson ([[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]]), and Thinking Machines' Inkling ([[thinking-machines-inkling-open-weights-launch-2026-07-16]]).
- **2026-06-25: 328 tokens/s on GLM-5.2**, beaten by Databricks' 392 tokens/s in Yuchen Jin's comparison ([[dailybrief-roundup-2026-06-25]], Digg).
- **2026-05-04: #14 on Paraform's talent-density list**, one of six AI-infrastructure companies in its top 35 ([[brianlamanna-paraform-talent-density-2026-05]]).

## How to Use It

An API for open-weight models; pricing and the model list aren't recorded in the wiki. If you route prompts through it, or through an app that uses it, the breach is the lesson: a second inference provider behind an app is one more place for prompts, and anything pasted into them, to leak. See the builder note on [[notion-fireworks-ai-incident-2026-11]].

## Compared To

- **Baseten, Together AI, Modal:** the other inference hosts the wiki sees named alongside it at model launches.
- **Lab APIs** (Anthropic, OpenAI): closed models from the lab itself. Fireworks's business depends on open weights being close enough at a fraction of the price; see [[ai-margin-collapse]]. [Judgment.]

## Resources

- [[notion-fireworks-ai-incident-2026-11]]: the breach, Notion's notice and the Uber follow-up
- [[forbes-ai-50-2026]]: funding and valuation
- [[dailybrief-roundup-2026-05-27]]: decacorn report
- [[martin-alderson-glm-5-2-ai-margin-collapse-2026-07-06]]: GLM 5.2 pricing via Fireworks
- [[thinking-machines-inkling-open-weights-launch-2026-07-16]]: Inkling launch hosts
- [[brianlamanna-paraform-talent-density-2026-05]]: talent-density ranking
