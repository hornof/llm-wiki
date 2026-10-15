---
name: Hugging Face
type: company
focus: open-source AI platform; model and dataset distribution
status: acquisition-announced-close-unconfirmed
last_updated: 2026-10-15
---

## What It Is

**Hugging Face** is the open-source AI platform most of the ecosystem distributes through — model hub, datasets hub, Spaces — founded by **Clément Delangue**.

**The business-model numbers are what the wiki tracks it for, and they are unusual**: a **$100M annual run rate** on a user base that is **97% free**, i.e. a **3% paid conversion rate.** That is a distribution business whose economics look nothing like the labs it distributes for — and it is the context for why a $12.9B acquisition price reads as paying for the ecosystem position rather than the revenue.

## Traction Signals

- **2026-09-17: open-weight safety partnership with Base Labs and Goodfire** ([[dailybrief-roundup-2026-09-17]], TechCrunch): a three-party effort shipping **methods for open-model training and monitoring**. Turns the [[#Open Alignment team|Open Alignment team]] announced a week earlier from a staffing statement into named collaborators and a scope. Notable for what it balances: the governance fortnight of AEF-1, the reported standards body and Microsoft's code of conduct is **entirely closed-lab**; this is the open-weights counterpart, and open-weight safety is the part none of those artifacts covers. → [[frontier-ai-governance]] *(Announcement; methods not published.)*

> [!note] On `status:` (corrected 2026-09-14, disambiguated 2026-10-15)
> The field read `gaining-traction` until 2026-09-14, while the first entry below recorded a **confirmed $12.9B [[nvidia|NVIDIA]] acquisition**. Same defect class as the [[claude-mythos]] naming contradiction: the body was kept current, the frontmatter was not. As with Mythos, the schema's company states have no slot for *acquired / acquisition pending*, so the value here is descriptive rather than from the allowed set — see `CLAUDE.md`.
>
> **The 2026-10-15 lint flagged this page as self-contradicting and it is not — but it reads that way, which is its own defect.** The field says `close-unconfirmed`; the body shouts **"DEAL-CONFIRMED-AT-$12.9B."** **Both are right: the *deal* is confirmed (NVIDIA, $12.9B, 2026-09-03) and the *close* is not** — the 09-03 entry itself ends *"close-timeline / antitrust exposure still pending"* and the 08-27 entry ends *"deal terms/close-timeline verification-pending."* **Nothing beside the field said so, so a reader or a lint had to reconstruct it from three entries.** Stated here instead.
>
> **This is the [[anysphere]] trap, and this page is the one still exposed to it.** Anysphere carried *"close unconfirmed"* for **five weeks after the merger actually closed on 2026-08-14** — the wiki only caught it at lint. **The NVIDIA close is now six weeks past confirmation with no close date captured**, and the wiki has no way to check without fetching. **Highest-value verification item on this page**: did the acquisition close, and when? Until then the field is accurate-by-default rather than accurate-by-evidence, which is exactly how the anysphere error happened.

- **2026-09-10: Open Alignment team — Thomas Wolf calls for "100x more transparency and research"** ([[dailybrief-roundup-2026-09-10-neutral]], via Digg): Hugging Face is **staffing a dedicated team for open-model safety and alignment, including cybersecurity**. Notable for its timing on two fronts: it lands mid-[[nvidia|NVIDIA]]-acquisition (below), and in the same window as the [[ai-vulnerability-discovery|OpenAI agent-swarm HF breach]] that put HF's security posture under scrutiny — i.e. the open-weights hub building its own safety function rather than inheriting one from an acquirer. Partial answer to [[jack-clark|Jack Clark's]] *"Why Hugging Face worries me"* ecosystem-concentration argument. Open question: whether decentralized alignment research can match frontier-lab safety programs at scale. *(Secondary reporting; team size, scope and leadership unnamed — verification-pending.)*
- **2026-09-03: the deal is confirmed at $12.9B — "Nvidia confirms it will buy Hugging Face for $12.9 billion"** ([[dailybrief-roundup-2026-09-03]], TechCrunch): the [[nvidia|NVIDIA]] acquisition (talks 08-24 → AINews-reported 08-27, below) is now **officially confirmed** with a precise figure: **$12.9B**. Same-day, [[jack-clark|Jack Clark]]'s [[jack-clark|Import AI 471]] runs *"Why Hugging Face worries me"* on the ecosystem-concentration fallout, and the [[ai-vulnerability-discovery|OpenAI agent-swarm HF breach]] (Ajeya Cotra) puts HF's security posture under scrutiny in the same window. The open governance question (neutral hub vs CUDA-tilt) is unchanged and now live. **Close-timeline / antitrust exposure still pending.**
- **2026-08-27: acquisition confirmed — NVIDIA buys Hugging Face for $13B** ([[dailybrief-roundup-2026-08-27]], AINews/Latent Space, *primary/terms not fetched*): the acquirer for the 08-24 *"$13B talks"* (below) is **[[nvidia|NVIDIA]]**. The compute-substrate vendor acquires the open-source model and dataset distribution hub — **the sharpest instance of NVIDIA moving from the substrate tier into the application tier** (cf. [[nvidia-nemotron-3-ultra-550b-2026-06-04|Nemotron]] open-weights). Open question: does NVIDIA keep HF **neutral and decentralised** or pull it toward a CUDA-proprietary stack lock-in. Routes into [[ai-margin-collapse]] (the compute layer consolidating the open-weights *distribution* surface, not just the silicon). Lands same-day as [[ai-vulnerability-discovery|OpenAI's HF-security-incident retro]] — the AINews pairing reads as *"incumbent labs now learning failure modes from open-source infra."* **Deal terms/close-timeline verification-pending.**
- **2026-08-24: reported $13B acquisition talks** ([[dailybrief-roundup-2026-08-24]], TechCrunch, *primary not fetched; reported talks not closed*): Hugging Face **reportedly in talks to be acquired for $13B** — the largest ecosystem-layer M&A signal the wiki had captured. Daily Brief read: *"a $13B offer means the acquirer sees open-source model distribution as **infrastructure, not a moat-breakable feature**"*; founder hesitation framed as a **community-vs-exit** tension (*"the real value isn't the models — it's the community lock-in and dataset velocity"*). Prices the [[hugging-face|$100M-ARR / ~half-the-Fortune-500]] penetration anchors at a $13B infrastructure multiple and extends the [[ai-margin-collapse|open-weights-as-infrastructure]] thread. **Acquirer unnamed; deal not closed — verification-pending.**
- **2026-07-09/11: Delangue "open source AI matters more than ever" — half the Fortune 500 on HF models** ([[dailybrief-roundup-2026-07-11]], TechCrunch podcast, *primary not fetched*): Clément Delangue reiterates open-source momentum, claiming **~half of the Fortune 500 use Hugging Face models**. Enterprise-penetration data point extending the [[dailybrief-roundup-2026-06-25|Jun-25 $100M-ARR / 97%-free-user]] business-model anchor; pairs with the [[ai-margin-collapse|open-weights ecosystem]] thread.
- **2026-06-25: $100M ARR on a 97%-free user base** ([[dailybrief-roundup-2026-06-25]]) — Delangue's own figures, and the first Hugging Face revenue anchor the wiki held. **The 3% conversion rate is the number worth remembering**: it is what makes the later $12.9B price a bet on position rather than on earnings.
- **Two or more earlier surfaces** as the recurring model-hub and datasets-hub reference across practitioner walkthroughs.

## Key People

- **Clément Delangue** — CEO and co-founder; the source of the Jun 25 revenue figures. *(Bio and prior affiliations uncaptured.)*

## How to Use It

- **Model hub** — the open-weights distribution layer.
- **Datasets hub.**
- **Spaces** — hosting for demos and apps.
- **Pro** — the paid tier, converting 3% of users per the Jun 25 figures.

## Compared To

- **[[allenai|Ai2 / Allen Institute]]** — fully-open-source frontier *research* against Hugging Face's *distribution*. **Creator versus platform**, which is the distinction that makes the NVIDIA acquisition matter: buying the platform reaches every creator at once.
- **The Chinese open-weights cluster** ([[z-ai|Z.ai]], Alibaba-NLP, [[deepseek|DeepSeek]]) — **Hugging Face is the Western distribution channel for models built outside the West**, which is the fact that gives [[jack-clark|Jack Clark's]] ecosystem-concentration worry its force.
- **[[github]]** — models and datasets against code and collaboration. The structural analogy the $12.9B price implicitly invokes.

## Resources

- [[dailybrief-roundup-2026-06-25]] — the $100M ARR and 97%-free-user figures, from Delangue
- [[allenai]] — the open-source research counterpart
- [[z-ai]] — a major publisher of models distributed through HF
- [[alibaba]] — Alibaba-NLP, same cohort
