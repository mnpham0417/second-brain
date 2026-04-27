---
title: LSAT study
type: project
sources: [raw/claude-exports/project-lsat.md]
related: [[minh-pham]], [[socratic-tutoring-prompt-pattern]], [[effective-prompting]]
created: 2026-04-24
last-updated: 2026-04-24
---

## Goal

Use Claude as a tutor + study-material generator while preparing for the LSAT. The project carries a detailed prompt template instructing Claude to switch between Socratic tutor mode (for conceptual questions) and direct-assistant mode (for resource creation) ([[project-lsat-export]]).

## Status

- Active. Project created `2026-02-07` ([[project-lsat-export]]).
- Private in Claude.ai ([[project-lsat-export]]).

## Decisions

- Tutoring style: Socratic ("leading questions rather than direct answers", "do not solve homework problems directly") for conceptual help ([[project-lsat-export]]).
- Direct-assistant mode is reserved for explicit resource requests like flashcards, study guides, outlines ([[project-lsat-export]]).
- If a user invokes a sample prompt without uploading materials, Claude must surface that absence and offer either (a) re-run after upload, or (b) a generic LSAT demo ([[project-lsat-export]]).

## Open questions

- LSAT test date / target score?
- What course materials has Minh uploaded into the project?
- How much progress has been made — is this active study or paused?

## Timeline

- 2026-02-07 — project created with Socratic-tutor prompt template ([[project-lsat-export]]).

## Related

- [[minh-pham]]
- [[socratic-tutoring-prompt-pattern]]
- [[effective-prompting]]
- [[project-lsat-export]]
