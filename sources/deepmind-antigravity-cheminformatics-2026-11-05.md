---
title: "Agentic Cheminformatics with Google Antigravity"
type: source
medium: article
url: https://deepmind.google/blog/agentic-cheminformatics-with-google-antigravity/
ingested: 2026-11-05
---

## Summary

Google DeepMind released a set of Cheminformatics Skills for [[antigravity|Google Antigravity]] and walked through a drug-design example. The agent pulls compounds from papers, cleans them, runs a standard medicinal-chemistry analysis, trains potency models and proposes new molecules with synthesis routes. The design point is a split: the language model plans and reasons, and deterministic chemistry software (RDKit) does every calculation.

## Key Claims / Takeaways

- **Speed claim.** The agent *"proposes novel rigidified macrocycles with synthetic routes in just an hour"*, against a workflow that *"typically takes multiple days for a single iteration"*. DeepMind's own figure.
- **The division of labour.** *"the underlying language model handles workflow orchestration, database navigation and scientific reasoning, while deterministic chemistry tools execute molecular calculations"*. Grounded in RDKit, with connectors to ChEMBL and PubChem.
- **Why the split matters.** *"This task has no margin for error – alter a single atom or bond and you have described a different compound"*.
- **The worked example.** Crizotinib versus lorlatinib, two lung-cancer drugs, where lorlatinib's ring closure removes rotatable bonds and raises potency. The agent retrieved *"thousands of compounds"*, ran matched molecular pair analysis, trained potency models on scaffold and chronological splits, and proposed new macrocycles.
- **Output is proposals, not results.** No synthesized or tested compound is reported.

## Pages Updated

- [[antigravity]] — Traction Signals
- [[ai-for-science]] — new section
- [[google-deepmind]] — Traction Signals
