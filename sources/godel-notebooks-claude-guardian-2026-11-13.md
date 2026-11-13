---
title: "‘Ahead of his time’: AI helps unlock discoveries hidden in notebooks of man who transformed maths"
type: source
medium: article
url: https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths
ingested: 2026-11-13
---

## Summary

The Guardian (2026-11-13) on Jan von Plato, a Helsinki logician who has spent since 2017 on Kurt Gödel's 1940s "workbooks", and who in September started working through them with Claude. Claude produced a 650-page explanation in a couple of days and extracted 663 theorems, which von Plato then checked in the Coq proof assistant. The article doesn't name a Claude model. It is a useful counterweight to benchmark news: a long-context reading task on real archival material, with a formal checker at the end and an independent logician's caveat.

## Key Claims / Takeaways

- **The material:** *"16 notebooks that Gödel wrote in the early 1940s"*, *"1,009 pages of densely written text about maths and logic"*, much of it in Gabelsberger shorthand. Before Claude, progress was *"about a page a week"*.
- **What von Plato gave Claude:** his transcriptions, *"as well as six books he had previously written on Gödel and other secondary scientific literature."* The human did the shorthand transcription; Claude read the transcriptions.
- **The output:** *"In a couple of days, I got to see a 650-page explanation of the workbooks. It had to be controlled page for page"*. His reason it worked: *"The AI can connect all the pieces in a thousand pages."*
- **Checked with a proof assistant:** Claude *"found 663"* theorems with a proof, sketch or idea. In Coq, *"About 400 were verified as stated, about 200 were repaired"*, and *"About 50 were false"*. A reconstructed proof of the independence of the axiom of choice also passed Coq.
- **The caveat:** Joel David Hamkins (Notre Dame), who hadn't seen the reconstruction, said that if it stands *"it is remarkable and historically interesting. Although how much is Claude and how much is Gödel is a job for the historians."*
- **For the owner:** the method is the transferable part: a domain expert supplies clean inputs and context, the model reads across the whole corpus, and a formal checker sorts its output into verified, repaired and false. [Judgment.]

## Pages Updated

- [[ai-for-science]] — new section
- [[anthropic]] — Traction Signals
