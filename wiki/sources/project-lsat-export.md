---
title: "Source: LSAT (project export)"
type: source-summary
sources: [raw/claude-exports/project-lsat.md]
related: [[lsat-study]], [[socratic-tutoring-prompt-pattern]], [[minh-pham]]
created: 2026-04-24
last-updated: 2026-04-24
---

## One-paragraph summary

Export of the private Claude.ai project "LSAT", created `2026-02-07` by Minh Pham. Carries no docs but a substantial prompt template that defines a two-mode tutor: a Socratic mode for conceptual help (leading questions, no homework solving) and a direct-assistant mode for explicit resource requests (flashcards, study guides, outlines). The template also includes guidance for adapting to struggling students and a fallback flow when a user fires a "sample prompt" without uploading course materials ([[project-lsat-export]]).

## Key claims

- Two-mode operation: tutor vs. direct assistant; mode chosen by intent of user request, with clarification if ambiguous ([[project-lsat-export]]).
- Tutor mode rules: leading questions, gentle nudges, no direct homework answers ([[project-lsat-export]]). See [[socratic-tutoring-prompt-pattern]].
- Direct-assistant mode rules: deliver requested artifact efficiently, don't stall with preliminary questions ([[project-lsat-export]]).
- Pedagogy guidance: hierarchical organization, multiple modalities, active recall, spaced repetition ([[project-lsat-export]]).
- For struggling students: decompose, analogize, swap explanations ([[project-lsat-export]]).
- Missing-materials fallback: detect sample-prompt-without-upload and offer either re-run-after-upload or a generic LSAT demo ([[project-lsat-export]]).

## Notable quotes

> "Use leading questions rather than direct answers… Do not solve homework problems directly." — LSAT project prompt template ([[project-lsat-export]])

> "Don't delay creation by asking multiple preliminary questions unless essential information is missing." — LSAT project prompt template ([[project-lsat-export]])

## Open questions

- Is this prompt template adapted from an Anthropic-published "study with Claude" template, or hand-authored?
- Does the user actually use both modes in practice, or have conversations clustered into one?

## Sources

- `raw/claude-exports/project-lsat.md`
