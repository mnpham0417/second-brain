---
title: Few-shot prompting
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[effective-prompting]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

Show the model an example of the output you want instead of (or in addition to) describing it. The example anchors style, format, and tone better than a description does ([[project-how-to-use-claude-export]]).

## Definition

A prompting technique where the user includes one or more concrete examples of the desired output inside the prompt. The *Claude prompting guide* frames it as: "Provide examples of the kind of output you're looking for. If you want a specific format or style, show Claude an example." ([[project-how-to-use-claude-export]]).

## Key distinctions

- **Few-shot vs. zero-shot**: zero-shot describes the task only; few-shot includes examples.
- **Example as anchor vs. example as constraint**: the cited guide treats examples as a *reference point* — the model is expected to match style and tone, not echo content verbatim ([[project-how-to-use-claude-export]]).

## Examples

From the *Claude prompting guide*: instead of "Write a professional email", paste a prior email you've sent, then describe the new situation; Claude matches your tone and structure ([[project-how-to-use-claude-export]]).

## Related

- [[effective-prompting]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`
