---
title: "Redefining Druggable Space"
type: source
medium: article
url: https://www.toposbio.ai/
published: 2026-09-30
ingested: 2026-09-30
---

## Summary

**Topos Bio's company site.** An AI-native drug-discovery startup targeting **intrinsically disordered proteins** — the part of the proteome that structure-prediction tools built around a single folded conformation do not address.

**This is a vendor marketing page, clipped as a `_raw` drop.** It carries no paper, no benchmark and no validated result. What it does carry is a clearly stated technical bet and three dated external signals.

## The bet

> *"Proteins are dynamic. We believe drug discovery should begin there."*

Rather than predicting **a** structure, Topos models a protein's **conformational ensemble** — *"the collection of structures it can adopt"* — across the ordered-to-disordered spectrum. Three named components:

- **Topos-2** — the ensemble-prediction model.
- **BioScape** — *"a generative map of the human proteome"*, mapping conformational ensembles proteome-wide, browsable by cellular compartment. Subcellular assignments combine **Human Protein Atlas** localization data with **JensenLab COMPARTMENTS** confidence scores as a backfill.
- **Topos-Bind** — small-molecule interaction with those ensembles, *"bringing binding into the same framework used to predict protein motion."*

Their framing of what a drug is, which is the clearest sentence on the page:

> *"Since protein shape gives rise to function, drug design can be thought of as **reshaping the landscape of shapes accessible to the protein**."*

**The one novelty claim, hedged by them:**

> *"**To our knowledge**, this is the first generative model that produces ensembles of disordered proteins bound to small molecules."*

## External signals, with dates

| Date | Signal |
|---|---|
| **2026-01-08** | **$10.5M seed** for AI drug discovery (Axios Pro, "Exclusive") |
| **2026-03-17** | Collaboration with **Dalriada Drug Discovery** — mass spectrometry and proteomics paired with Topos's modelling, aimed at intrinsically disordered proteins (PR Newswire) |
| **2026-06-30** | Joins **Eli Lilly's TuneLab** — federated access to models trained on *"decades of Eli Lilly proprietary ADMET data"*, while contributing Topos's own data back |

## Judgment

**The TuneLab membership is the most interesting item and it is not about Topos.** A large pharma company operating a **federated model platform where a seed-stage startup both consumes models trained on decades of proprietary ADMET data and contributes its own data to train them further** is a structure the wiki has not recorded anywhere — it is the [[company-brain|proprietary-data-as-moat]] question answered by pooling rather than hoarding. **Whether incumbents in other regulated industries copy that shape is a better question than anything about this company.**

**The technical bet is legible and falsifiable, which is more than most AI-bio marketing manages.** [[alphafold|AlphaFold]] and successors predict a structure; **intrinsically disordered proteins do not have one**, and they are a large and genuinely undrugged fraction of the proteome. Targeting the gap in the dominant tool's formulation is a coherent wedge. **Whether the ensembles are accurate is entirely unevidenced here** — no held-out benchmark, no comparison to molecular-dynamics baselines, no validated binder.

**Seed-stage, one surface, no page.** Three dated third-party signals on a company's own site are three links, not three independent surfaces the wiki has seen. **Recorded on [[ai-for-science]]; no `companies/` page created.**

**Set against the wiki's own recent entries**, it lands in a busy week: [[anthropic|Anthropic's]] AI-discovered enzyme system, DeepMind's [[frontier-ai-governance|SynthID Bio]] protein watermarking, and the [[fda-accelerated-ai-pathway-pilot-2026-05-26|FDA's AI-evidence pathway]]. **The generative-biology stack is accumulating tooling, provenance and a regulatory route at roughly the same time**, which is the pattern worth tracking rather than any single company.

## Pages Updated

- [[ai-for-science]]
