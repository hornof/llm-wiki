---
title: "The components of agent memory"
type: source
medium: article
url: https://www.anthropic.com/research/components-of-agent-memory
ingested: 2026-11-07
---

## Summary

Anthropic Engineering post by Lance Martin, published 2026-11-06. It splits agent memory into notes Claude writes during a session and "dreaming", an offline pass where Claude rereads transcripts to correct, reorganize and promote its notes. It reports evals on CL-Bench 1.0, Claude Plays Pokémon, a Stainless document corpus and the Harvey LAB legal benchmark. One of those evals has Claude build and maintain a linked wiki, which is the [[llm-wiki-pattern]] measured by a lab.

## Key Claims / Takeaways

- **Definition.** Agent memory is *"knowledge that Claude gains from experience"* and retains between sessions as readable context. It excludes weight changes, in-context learning and compaction.
- **Dreaming** borrows sleep-time compute from Letta and UC Berkeley: Claude reflects on logs *"to fix mistakes or produce new notes and representations"*.
- **Closing the loop on CL-Bench 1.0.** Sonnet 4.6 stopped at untested theories. *"Claude Opus 5 was the first of these models to close the loop"*, writing rules plus how it knew each rule was true. Opus 5.5 and Sonnet 5.5 also closed it and scored about the same as Opus 5 with memory.
- **Salience in Pokémon.** *"Sonnet 3.7 wrote 413 memory files across 225 folders and earned one badge"*. Fable 5 *"wrote nine files in two folders, plus a single top-level file called global.md , and earned four badges"*. Opus 5.5 kept a small folder of notes and *"beat the game"*.
- **Tell the model what memory is for, not how to use it.** A fixed *"record only failures"* rule cost Opus 5 and Opus 4.7 much of their gain. Steering helped older models: prompting Sonnet 4.6 to read its memory and test its theories *"nearly doubled its benchmark score"*. Sonnet 5 read its memory unprompted *"9 out of 10 times"*.
- **Dreaming corrects a wrong note.** In Pokémon, a note put the Mt. Moon PokéCenter on the wrong side. After dreaming checked the note against the transcript, Claude went back into the cave and reached Cerulean City. The uncorrected run never got past the mountain.
- **A Claude-built wiki, measured.** Corpus: *"about 350,000 files, roughly 420M tokens"* from Stainless, with 25 questions. Over 128 Opus 5 sessions coordinated by a shared log, *"performance on the 25 questions grew from 13% to 48% of graded criteria"*. With search plus wiki the score *"rose from 54% to 61%"* against *"53% when it had access to the search tool alone"*. Search plus wiki *"saved about 20,000 tokens per question"*.
- **The wiki helps on multi-document questions, not single-document lookups.** On 24 merger questions, *"Claude scored 87% when it consulted the wiki, compared with 73% when it used search alone"*. On a LAB task answerable from one document, no clear gain. On another, the wiki grew larger than the source files and *"effectively abstracted nothing"*.
- **Shared tables lose facts; quoted per-document pages keep them.** Several agents writing one shared table of contract terms kept *"41 of the 57 facts (72%)"* because they overwrote each other. One agent per contract, quoting terms word for word, met *"100% of the criteria"*.
- **Second pass fixes dangling links.** A second dreaming pass *"found nine links to a missing page in the wiki and repointed them"*, and added three pages including an index.
- **Keep the injected layer small.** Claude Code's auto memory loads *"only the first 200 lines or 25 KB of MEMORY.md"*, which works as an index. The post cites Claude Code docs warning that longer instruction files reduce adherence.
- **Open questions it names:** when to write memory (in-session costs attention, dreaming is delayed), how to keep it current (dreaming costs compute), and whether transcript search should be the foundation.
- **Not settled here:** the Harvey Dreaming "6× completion rate" claim carried on [[agentic-ai]]. This post uses Harvey's LAB benchmark but gives no production completion-rate figure.

## Pages Updated

- [[llm-wiki-pattern]] — new section on Anthropic's measured wiki
- [[anthropic]] — Traction Signals
- [[claude-code]] — auto-memory 200-line / 25 KB load limit
- [[company-brain]] — dreaming measured
