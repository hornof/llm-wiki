---
title: "The Enron Brain: a wiki from 45k Enron emails, every fact cited"
type: source
medium: article
url: https://www.thisandthat.chat/enron/
ingested: 2026-10-23
---

## Summary

A Show HN research page from this+that (methodology at `/enron/methodology.html`, read alongside). From 45,047 emails in eight Enron mailboxes, it built **214 wiki pages and 49,401 facts. Each fact cites one email and quotes a sentence from it, word for word.** Facts that change over time expire on a date or move into dated "phases." It's an [[llm-wiki-pattern|LLM wiki]] built in one batch over a closed corpus, and the most carefully measured example of the pattern the wiki holds.

## Key Claims / Takeaways

- **Pipeline:**
  1. **Entity types:** proposed by a model from a 3,200-message sample, 57 in all; a person kept 54.
  2. **Entities:** an organization needed 25+ mentions to get a page; a person cut ambiguous names.
  3. **Pages:** a model read every message naming the entity and returned facts with source sentences. Quotes were checked by exact match and duplicates merged. Neither merging nor the closing pass may drop facts.
  4. **Verification:** a newer model checked each fact against its cited email and kept, rewrote or dropped it.
- **Models:** Opus 5 built the pages, Opus 5.5 verified them, and Fable 5.1 judged the audits. In a one-entity comparison, Haiku 4.5 found about half as many facts and misquoted 13.9%.
- **Audit (500 random facts, held out):**
  - Fully supported: 392 before verification, 466 after two passes.
  - Core unsupported: 0 before, 1 after pass 1, 0 after pass 2.
  - A person regraded 50 verdicts and agreed with 48. Both disagreements traced to a line-break tooling bug.
  - All verdicts are published as audit.json.
- **Supersession:** 19,528 facts carry an expiry. 175 pages model relationship *phases* (e.g. counterparty → acquirer). Expiring a fact when a later message resolves it was proposed but not built.
- **Cost:** $11,215 at list prices: $8,857 to build, $2,358 to check. A batch discount would halve the build.
- **Stated limits:**
  - Message date ≠ event date.
  - Alias merges can be wrong; two false merges were caught by hand.
  - Long messages were read only in windows.
  - **Verification checks that a fact matches the mail, not that the mail is true.**
- No repository is linked.

## Pages Updated

- [[llm-wiki-pattern]]: new 10-23 section
