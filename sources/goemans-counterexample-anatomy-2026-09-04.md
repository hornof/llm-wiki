---
title: "Goemans's Unsplittable-Flow Conjecture: The Anatomy of AI-Assisted Counterexample Discovery"
type: source
medium: paper
url: https://arxiv.org/abs/2611.23244
ingested: 2026-11-20
---

## Summary

A paper by Jingwei Ge, Na Xie, Li Li and Jiayang Li (arXiv page says submitted 4 Sep 2026; it surfaced in the 2026-11-19 brief). Dmitry Rybin had announced a seven-vertex counterexample to Goemans's unsplittable-flow conjecture, found through a conversation with ChatGPT. The authors' point is that the conversation produced an answer without an explanation, so they built the theory that explains it. Abstract read; full paper not read.

## Key Claims / Takeaways

- **The gap:** the ChatGPT interaction *"did not reveal why this particular topology and its demand, fractional-flow, and cost choices work together, whether the example belongs to a broader family, or which structural features determine where counterexamples can occur."*
- **What they built:** a construction pipeline that starts from a tree where failure is impossible, adds shortcut arcs, and gives exact conditions for when a counterexample works. It recovers Rybin's example and *"characterizes all counterexamples it supports."*
- **AI with the theory:** told to follow the pipeline, ChatGPT found counterexamples on new topologies and *"found valid constructions starting from 93 other rooted arborescence shapes."*
- **Their reading of the original:** *"Rybin's interaction lies between blind enumeration and a complete theory-guided construction."*

## Pages Updated

- [[ai-for-science]] — finding an answer versus explaining it
