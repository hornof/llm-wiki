---
title: "Decoupled DiLoCo: A new frontier for resilient, distributed AI training"
type: source
medium: article
url: https://deepmind.google/blog/decoupled-diloco/
ingested: 2026-05-06
---

## Summary
Google DeepMind announces Decoupled DiLoCo: a distributed-training architecture that divides training across isolated compute "islands" with asynchronous data flow. Builds on the original DiLoCo (which reduced inter-datacenter bandwidth) by adding fault tolerance — a single chip failure no longer interrupts the whole training run. Validated on a 12B-parameter Gemma 4 trained across four U.S. regions.

## Key Claims / Takeaways
- **Problem**: "Frontier AI model training requires a large, tightly coupled system in which identical chips must stay in near-perfect synchronization." At scale, sync across thousands of chips becomes operationally untenable.
- **Innovation**: asynchronous islands of learners; localized failure containment; chaos-engineering-driven self-healing; ability to mix hardware generations in one run.
- **Substrate**: built on Google's Pathways architecture.
- **Lead**: Arthur Douillard. Core contributors: Keith Rush, Yani Donchev, Zachary Charles, Josef Dean, others from Google DeepMind and Google Research.
- **Bandwidth result**: 198 Gbps → 0.84 Gbps across 8 datacenters.
- **Resilience result**: 88% goodput vs 27% for standard methods at high failure rates.
- **Production result**: 12B Gemma 4 trained across four U.S. regions at 2-5 Gbps; >20× faster than conventional sync methods; 64.1% accuracy vs 64.4% baseline.
- **Strategic framing**: distributed-training infrastructure is becoming a competitive frontier alongside model recipes themselves — reinforces "infra as moat" thesis from [[ai-50-2026-snapshot]].

## Pages Updated
- [[google-deepmind]] — added Decoupled DiLoCo under Notable Research; updated last_updated
- [[index]] — added under Recent ingests

## Notes
- No standalone concept page warranted yet (system, not paradigm).
- Possible future entity: people/arthur-douillard if he becomes a tracked voice (currently single-post lead author).
