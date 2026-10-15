---
name: AlphaFold
type: tool
category: platform
status: mainstream
last_updated: 2026-10-15
---

## What It Is
Google DeepMind's protein structure prediction system. Solved what Hassabis describes as a "50-year grand challenge" in biology — predicting the 3D folded structure of proteins from their amino acid sequence. Won Demis Hassabis the Nobel Prize in Chemistry in 2024.

Protein structure is foundational to drug discovery: knowing the 3D shape of a protein (and what's on its surface) is a prerequisite for designing compounds that bind to and affect it.

## Traction Signals
- Nobel Prize in Chemistry, 2024 (Demis Hassabis)
- Described by Hassabis as DeepMind's proudest moment — [[hassabis-deepmind-alphafold-agi]]
- Directly enabled the founding of [[isomorphic-labs]] to build the next layer of drug discovery on top of AlphaFold outputs
- Widely adopted by structural biologists; protein structure database built from AlphaFold predictions released publicly

## How to Use It
AlphaFold predictions are accessible via the EMBL-EBI AlphaFold database (alphafold.ebi.ac.uk). AlphaFold 3 (released 2024) extends predictions to DNA, RNA, and small molecules in addition to proteins.

## Key Concepts
- **Protein folding**: The process by which a linear amino acid sequence folds into a specific 3D structure that determines protein function.
- **Binding site**: The region on a protein's surface that a drug compound must target.
- **In silico exploration**: Running drug candidate simulations computationally rather than in a wet lab — AlphaFold enables this for the structural step.

## The formulation's boundary — two surfaces, Sept–Oct 2026

**Refreshed at the 2026-10-15 lint, which flagged this page as genuinely behind rather than dormant.** Two surfaces in six weeks say the same thing from different directions: **AlphaFold solved a problem, and the page should be clearer about which one.**

**1. Intrinsically disordered proteins fall outside the formulation** ([[topos-bio-redefining-druggable-space-2026-09-30]], 2026-09-30). AlphaFold and its successors **predict a structure.** A large and largely undrugged fraction of the proteome **does not have one** — it occupies a conformational ensemble rather than a fold. That is not a failure of the model; **it is a question the model's output type cannot express**, and it is where [[topos-bio-redefining-druggable-space-2026-09-30|a startup is building]] and where [[ai-for-science]] now records the remaining commercial room.

**2. *"Why AlphaFold didn't solve protein folding"*** ([[dailybrief-roundup-2026-10-09]]). **Title only — the piece was not fetched, and it is the highest-value verification item on this page.** If the argument is the disorder/ensemble one above, this page needs one sentence of qualification. **If it argues something stronger — that the folding problem is open even for ordered proteins — then `status: mainstream` and [[ai-for-science|that page's "shipped; Nobel Prize 2024"]] row are both overstating a solved problem**, and the correction is substantial.

**What the page should hold in the meantime, stated carefully:** AlphaFold's achievement is real, Nobel-recognised, and **about single-structure prediction for proteins that have a single structure.** The wiki has been treating *"structure prediction"* and *"protein folding"* as the same problem, and **two independent 2026 surfaces say they are not.**

*(Neither surface fetched in full: the Topos page is the company's own marketing, and the 10-09 item is a headline. **This section records a boundary, not a refutation** — and the status field is deliberately left at `mainstream`, since nothing captured disputes what AlphaFold does, only what it covers.)*

## Compared To
- **Traditional methods (X-ray crystallography, cryo-EM)**: Accurate but slow (months to years per structure), expensive, not scalable.
- **Rosetta**: Prior computational approach; far less accurate than AlphaFold.
- **[[isomorphic-labs]]**: Not a competitor — builds on top of AlphaFold outputs to design binding compounds.
- **ESMFold2 (Alex Rives, May 2026)**: ESM-project competitor. *Claims* to beat AlphaFold3 on protein-protein interaction benchmarks, with lab tests validating binders targeting five therapeutic proteins. First wiki-captured AlphaFold3-rivaling competitor signal. Verification-pending: specific benchmark deltas, whether validated binders are clinically meaningful or proof-of-concept-only. — [[dailybrief-roundup-2026-05-27]]

## Resources
- [[hassabis-deepmind-alphafold-agi]] — Hassabis on AlphaFold as 50-year grand challenge, Nobel Prize, drug discovery timeline
- [[google-deepmind]] — parent organization
- [[isomorphic-labs]] — downstream drug discovery application
