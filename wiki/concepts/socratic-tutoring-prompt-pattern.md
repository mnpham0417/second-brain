---
title: Socratic-tutoring prompt pattern
type: concept
sources: [raw/claude-exports/project-lsat.md]
related: [[effective-prompting]], [[lsat-study]], [[project-lsat-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

A reusable system-prompt pattern that puts the model into Socratic-tutor mode for conceptual questions (leading questions, no homework solving) and into direct-assistant mode for explicit artifact requests (flashcards, study guides). Mode is chosen by the *intent* of each user request, with clarification when ambiguous ([[project-lsat-export]]).

## Definition

A two-mode system prompt observed in Minh's [[lsat-study]] project. Mode 1 — *tutor*: for conceptual help, the model uses leading questions, gentle nudges when the student strays, and refuses to solve homework problems directly. Mode 2 — *direct assistant*: for explicit resource requests, the model creates the artifact efficiently without preliminary questioning. Mode selection rule: tutor when student asks for understanding/explanation, direct when student asks for a tool/output, ask if unclear ([[project-lsat-export]]).

## Key distinctions

- **Tutor vs. direct-answer chatbot**: pure question-answering optimizes for the answer; this pattern optimizes for the student's conceptual progress ([[project-lsat-export]]).
- **Mode-switching vs. single-mode tutor**: classical Socratic tutors stay in dialogue mode; this pattern is hybrid because rote artifact generation (flashcards, outlines) is a legitimate use that pure Socratic tutoring would mishandle ([[project-lsat-export]]).
- **Pedagogy hooks**: the pattern bakes in active recall, spaced repetition, multiple modalities, and analogy-driven explanation for struggling students ([[project-lsat-export]]).

## Examples

The full prompt template lives in the LSAT project; the export reproduces it verbatim ([[project-lsat-export]]). Two sentences capture the spirit:

> "Use leading questions rather than direct answers… Do not solve homework problems directly." ([[project-lsat-export]])

> "Don't delay creation by asking multiple preliminary questions unless essential information is missing." ([[project-lsat-export]])

## Related

- [[lsat-study]]
- [[effective-prompting]]

## Sources

- [[project-lsat-export]] — `raw/claude-exports/project-lsat.md`
