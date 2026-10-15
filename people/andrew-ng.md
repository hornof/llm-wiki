---
name: Andrew Ng
type: person
affiliation: Stanford University; DeepLearning.AI; Landing AI; AI Fund
signal_sources: [twitter, youtube, newsletter, coursera]
last_updated: 2026-10-15
---

## Notable Takes (selected, May–June 2026)

- **2026-08-14 — "The AI Engineering Skills Map"** ([[andrew-ng-ai-engineering-skills-map-2026-08-14]], anchors [[ai-engineering-skills]]): from **10,000+ job postings** + dozens of expert/hiring-manager interviews + surveys, Ng names the **four core AI-engineering skills** — (1) building & deploying AI applications (evals + error-analysis loops as the core sub-skill), (2) software-engineering fundamentals (steer agents in *"the precise language of software engineering"*), (3) using coding agents (context management, verifiers, multi-agent orchestration, avoid the prod-DB disaster), (4) **shaping the build** (*"our work is shifting toward deciding what should be in the spec"* — product sense + ownership). Framed as **skills not a role** (like cloud skills). Consistent with his FDE-fragmentation + loop-engineering + context-advantage takes below — and a **canonical, data-backed curriculum** for the wiki's own hands-on-ramp mission. Per-skill deep-dives promised.
  - **2026-08-21 — deep-dive series begins: Skill #1 "Building & Deploying AI Applications"** ([[andrew-ng-ai-engineering-skills-building-deploying-2026-08-21]]): decomposes Skill #1 into six sub-skills — LLM foundations, grounding-with-data, building agentic systems, **evaluation-driven development** (*"the most important trait that distinguishes someone great at building AI systems"*), operating in production, ML foundations. Unifying frame: AI output is unpredictable, so building is *iterative, not plannable up front.* SWE fundamentals (Skill #2) flagged as next. Fleshes out [[ai-engineering-skills]].

- **2026-07-10 — claimed escalation: "prompting is gone in 3-6 months" (SECOND-HAND, unverified)** ([[how-to-build-first-ai-loop-slate-2026-07-10]]): Rahul (@sairahul1) attributes to Ng, via a 32-minute video, the quote *"100% of my tasks are done by ai agents, self-improving loops are next. Give it 3-6 months and prompting is gone."* A far more absolutist framing than Ng's [[andrew-ng-loop-engineering-3-loop-validation-2026-06-30|Jun 30 3-loop validation]] — and used as the hook for a promotional [[slate|Slate]] thread. **Not directly sourced; treat as claimed until the primary video surfaces.** Note the tension with Ng's own repeated *"jobpocalypse narrative is false"* / "humans have a context advantage" position (below) — an unqualified "prompting is gone" would be out of character, which is further reason for skepticism about the paraphrase.

- **2026-06-01 — AI Forward Deployed Engineer (FDE) vs AI Engineer fragmentation thesis** ([[andrewng-ai-fde-vs-ai-engineer-2026-06-01]]): Both OpenAI and Anthropic are scaling FDE teams (Palantir-originated role). Ng predicts **AI Engineer >> AI FDE in eventual headcount** due to (a) vendor-neutrality concerns + (b) client optionality preservation. AI Engineer role will fragment into specialized roles over the decade: **AI FDE, LLMOps Engineer, Evals Engineer, AI Data Engineer, Harness Engineer**. *"Jobpolcalypse narrative of upcoming job-market collapse is false — there will be many AI and non-AI jobs."* First wiki-captured Ng-side counter-position to the [[ai-labor-market-impacts|AI-displacement thesis]]; pairs with [[deedydas-sf-ai-wealth-divide-2026-05-15|Deedy's SF wealth-divide essay]] as bracketed-debate.
- **2026-06-30 — Ng validates Loop Engineering, and names the three loops** ([[andrew-ng-loop-engineering-3-loop-validation-2026-06-30]]). **This matters because of who he is**: the mainstream AI-education voice, not a participant in the practitioner discourse. He credits the coinage explicitly to **[[boris-cherny|Boris Cherny]]** (Claude Code's creator) and **[[peter-steinberger|Peter Steinberger]]** (OpenClaw's creator).
  > **Three loops, by timescale** — the clearest articulation the wiki holds: (1) the **agentic-coding loop**, minutes, where the agent writes, tests and iterates until the spec is met; (2) the **developer-feedback loop**, tens of minutes to hours, where the developer steers; (3) the **external-feedback loop**, hours to weeks, alpha and A/B testing.
  > **And the reframing that is his own contribution**: *"Many people describe this human contribution as **'taste,'** but I prefer to think of it as **humans having a context advantage**, since that gives us a clearer path to helping AI systems get better."* **That is a more actionable claim than taste** — a context advantage can be transferred to a system; taste cannot. He also names the **engineer-as-partial-PM** emerging role, and dates the shift: *"closing the loop took off around end of 2025."*
  > Originally in *The Batch*, distributed on X. **Sixteenth voice in the [[loop-engineering|Loop Engineering]] cluster and the first from outside it.** Pairs with [[bcherny-5-archetype-future-roles-2026-06-28|Cherny's five archetypes]] (Jun 28) and [[gregisenberg-ai-native-company-context-layer-2026-06-27|Isenberg's three pillars]] (Jun 27) — **three voices on AI-native role evolution in one week.**

## Who They Are
British-American computer scientist, Stanford professor, and one of the most influential AI educators in the world. Co-founded Google Brain, was Chief Scientist at Baidu, co-founded Coursera. Now runs DeepLearning.AI (8M+ students), Landing AI (enterprise AI), and the AI Fund (VC). Amazon board member since April 2024. Among the first to advocate GPUs for deep learning (2008) — now standard practice.

## Their Current Focus
Running DeepLearning.AI (AI education at scale), Landing AI (enterprise AI adoption), and AI Fund (investing in AI startups). Vocal advocate for open-source AI and against heavy-handed regulation.

## Notable Takes
- **On AI regulation**: opposed California SB 1047 — "massive liabilities for science-fiction risks" and "stokes fear in anyone daring to innovate" — [[wikipedia-andrew-ng]]
- **On open-source AI**: regulating basic technologies like open-source models "could hinder progress without markedly enhancing safety" — [[wikipedia-andrew-ng]]
- **On AI and jobs**: "Rather than being distracted by evil killer robots, the challenge to labor caused by these machines is a conversation that academia and industry and government should have." — [[wikipedia-andrew-ng]]
- **On GPUs for deep learning** (2008): early advocate when it was controversial; now universal practice — [[wikipedia-andrew-ng]]

- **"Software engineering is the profession AI is hitting hardest" — and openings are still rising (2026-09-11)** ([[andrew-ng-software-engineering-hit-hardest-2026-09-11]]): the apparent contradiction is the point. *"Threatened"* was never a population-level question, it is a **workflow-level** one. AI eats **30–40% of the role**; the engineers still busiest *"didn't out-compete the model on that slice; they stopped fighting for it and built the 60–70% it can't touch instead."* The ones falling behind are *"still writing code like it's 2022."*
  The sharpest part is the risk he actually names: **there is no signal telling you which side of the line you are on.** No single moment announces it.
- **Institutional lag is structural, not a defect**: a curriculum committee, a faculty senate vote, then a year or two before a course exists — against a market reshaping every few months. *"That lag isn't a flaw in the system. It's the system working as designed, just aimed at a problem that no longer moves at its speed."* Pairs with his [[ai-engineering-skills|skill-chain]] and AI-FDE positions. *(Reddit relay of a video clip; primary not fetched, 30–40% is the poster's rendering of Ng's framing — indicative, not a cited statistic.)*

## Key Contributions
- **Google Brain** (2011): co-founded with Jeff Dean; large-scale neural network research
- **Coursera** (2012): co-founded with Daphne Koller; helped launch the MOOC movement
- **DeepLearning.AI**: ML Specialization, Deep Learning Specialization, AI for Everyone — 8M+ students
- **CS229**: Stanford's most popular ML course; free online
- **AI Fund**: $175M VC fund for AI startups (2018)

## Learning Resources
- **DeepLearning.AI** — best starting point for hands-on ML/AI fundamentals; structured specializations
- **CS229** (Stanford/Coursera) — rigorous ML foundations
- **AI for Everyone** (Coursera) — exec-level AI literacy course; highly relevant for leadership perspective

## Where to Follow
- Twitter/X: @AndrewYNg
- Newsletter: The Batch (deeplearning.ai/the-batch)
- YouTube: DeepLearning.AI channel
- Coursera: coursera.org/instructor/andrewng
