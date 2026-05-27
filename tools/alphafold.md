---
name: AlphaFold
type: tool
category: platform
status: mainstream
last_updated: 2026-05-27
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

## Compared To
- **Traditional methods (X-ray crystallography, cryo-EM)**: Accurate but slow (months to years per structure), expensive, not scalable.
- **Rosetta**: Prior computational approach; far less accurate than AlphaFold.
- **[[isomorphic-labs]]**: Not a competitor — builds on top of AlphaFold outputs to design binding compounds.
- **ESMFold2 (Alex Rives, May 2026)**: ESM-project competitor. *Claims* to beat AlphaFold3 on protein-protein interaction benchmarks, with lab tests validating binders targeting five therapeutic proteins. First wiki-captured AlphaFold3-rivaling competitor signal. Verification-pending: specific benchmark deltas, whether validated binders are clinically meaningful or proof-of-concept-only. — [[dailybrief-roundup-2026-05-27]]

## Resources
- [[hassabis-deepmind-alphafold-agi]] — Hassabis on AlphaFold as 50-year grand challenge, Nobel Prize, drug discovery timeline
- [[google-deepmind]] — parent organization
- [[isomorphic-labs]] — downstream drug discovery application
