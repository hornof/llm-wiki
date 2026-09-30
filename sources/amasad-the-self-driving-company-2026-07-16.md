---
title: "The Self-Driving Company"
type: source
medium: twitter-thread
url: https://x.com/amasad/status/2077802290304684404
published: 2026-07-16
ingested: 2026-09-30
---

## Summary

**Amjad Masad's own account** of [[replit|Replit]] running itself on agents. **The wiki folded this on 2026-08-04 from Sviokla's Forbes write-up**; this is the primary, obtained as a `_raw` backfill and predating that write-up by three weeks.

**The figures hold.** What the secondhand version dropped is more interesting than what it kept.

## Key Claims / Takeaways

- **The controls, stated with the gains**: *"In the past six months, engineers at Replit have nearly tripled code output. **Review times held steady. Reversions and product incidents have stayed flat. Quality metrics improved**, and releases have accelerated. **All the typical trade-offs you might expect have not occurred.**"*
- **What the agents actually do**, beyond code: *"investigate production incidents, review pull requests, answer questions, analyze business data, triage support tickets, research sales accounts, and improve the systems that power Replit Agent itself."*
- **The escalation branch is claimed**: agents *"taking goals from people, gathering context, performing work, **checking the results, and escalating when human judgment is needed.**"*
- **Not one intelligence**: *"It feels like a single master intelligence threaded through every employee, even though it is not. It is an expanding system of agents operating across the company."*
- **The definition**: *"A self-driving company is not one without people. People still choose the destination. They decide which problems matter, make difficult tradeoffs, exercise taste, and take responsibility for the outcome. But increasingly, they do not perform every step required to get there."*
- **The trigger, dated**: *"The shift began late last year… we returned from the Christmas break feeling that something fundamental had changed. Models could sustain work over much longer horizons. Tasks that had repeatedly failed, like **alert triage and root-cause investigation**, began working."*
- **The infrastructure, named**: their **agent harness, microVMs and remote filesystem infrastructure** let any engineer *"orchestrate swarms of agents in parallel"* — *"then we locked the whole thing behind **access policies, token proxies, audit logging, and our ZeroTrust network**. At that point we felt safe giving the agent access to"* GitHub, GCP, Azure, Linear, Notion, Slack, ZenDesk.
- *"People don't feel like they've been automated. They feel like they've been promoted."*

## Judgment

**The controls claim is what a sceptic should test, and it is the part the Forbes fold lost.** Tripled output is a throughput number anyone can hit by lowering the bar. **Tripled output with review latency, reversion rate and incident rate all flat is a different assertion**, and it is the one the whole thesis rests on. Still self-reported, and *"quality metrics improved"* is undefined.

**The escalation branch matters against the wiki's own running finding.** The confidence-threshold pattern specifies three branches — act, escalate to a stronger model, route to a human — and the wiki has repeatedly recorded that the third is specified everywhere and operated nowhere ([[gregisenberg-escalate-to-human-button-2026-09-25]]). **Replit claims to operate it.** No escalation rate, no criteria, no evidence — but a claim is more than the consumer agents make.

**The permission perimeter came before the capability.** Access policies, token proxies, audit logging and ZeroTrust were built *first*, and only then *"we felt safe giving the agent access."* **That ordering is the org-scale version of the finding that hard blocks hold where written rules don't**, and it is the least quotable and most transferable thing in the post.

**Vendor's own post about its own company.** Every metric self-reported, none audited, and the company sells the agent product the story is about.

## Pages Updated

- [[replit]]
