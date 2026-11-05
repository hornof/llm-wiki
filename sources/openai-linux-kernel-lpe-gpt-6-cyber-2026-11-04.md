---
title: "OpenAI's autonomous pipeline patches 948 Linux kernel privilege-escalation bugs; GPT-6 Cyber rolls out to Daybreak Red"
type: source
medium: article
url: https://latent.space/p/ainews-it-s-swapping-season/
ingested: 2026-11-05
---

## Summary

OpenAI says an autonomous pipeline for finding, exploiting and patching vulnerabilities produced patches for 948 local privilege-escalation (LPE) bugs in the Linux kernel in one run, using an unreleased cyber model. OpenAI's own post, *A thousand fewer paths to root*, blocks fetching, so this page works from Latent Space's AINews summary of 2026-11-04 and from Digg's summary of The Verge on GPT-6 Cyber, which OpenAI began rolling out the same week. All figures are OpenAI's or its researchers' own claims.

## Key Claims / Takeaways

- **948 LPE patches for about $1.2M in API cost.** In *"a single run with an upcoming cyber model, it validated and generated patches for 948 local privilege escalation (LPE) vulnerabilities in the Linux kernel, at a total API cost of $1.2M"*. Greg Brockman *"cites about $1,000 per vulnerability"*.
- **Against a normal year.** Eric Wallace *"says researchers typically find about 20 Linux LPEs a year"* and that the model *"found about 1,000 in one week using about $1M of tokens"*. OpenAI says it is now putting *"a significant amount"* of frontier compute toward pro bono open-source patching.
- **Novel techniques claimed.** The agents *"discovered and used at least 10 Linux exploitation techniques that its team and consulted experts consider novel"*.
- **Disclosure.** OpenAI says it is *"working with Linux maintainers and Patch the Planet partners on reports and patches"*. The brief's own caveat: no CVE numbers and no maintainer sign-off yet, so it isn't known how many patches will land.
- **Cost trend, one comparison.** *"GPT‑5.6 Sol at 166 vulnerabilities for about $500k in July 2026, against 948 for about $1.2M with the new model"*. That's roughly $3,000 per bug falling to about $1,300. A commenter thinks the real internal cost is far lower; AINews calls that *"an unverified estimate"*.
- **Which model.** *"The run used an unreleased model, separate from the rumored GPT‑6.2 Sol and Astra models"*.
- **GPT-6 Cyber (Digg, via The Verge).** Rolling out to select members of the Daybreak Red program for authorized defensive work. *"OpenAI classifies it as Critical"* under its Preparedness Framework; GPT-5.6 Cyber *"was classified High"*. It *"went out of bounds less than 1 percent of the time in a test, compared with around 5 percent for GPT-5.6 Cyber"*. On ExploitGym, *"GPT-6 Cyber scored 48.5 percent. GPT-5.6 Cyber scored 32.1 percent, and GPT-6 Astra scored 42.4 percent"*. OpenAI also credits it with *"81 previously unknown Firefox vulnerabilities"*. Digg's own caveat: *"Those test results do not establish how the model will behave in deployment."*
- **Not established:** whether GPT-6 Cyber is the "upcoming cyber model" that ran the kernel pipeline. Neither summary says so.

## Pages Updated

- [[ai-vulnerability-discovery]] — new section
- [[openai]] — Traction Signals
