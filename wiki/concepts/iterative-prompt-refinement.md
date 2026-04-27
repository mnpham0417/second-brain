---
title: Iterative prompt refinement
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[effective-prompting]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

When a first response misses, don't say "make it better" — name the specific deltas: tone, length, examples, structure. Specific deltas converge faster than vague nudges ([[project-how-to-use-claude-export]]).

## Definition

A prompting technique where the user refines an initial response by issuing targeted, enumerable change requests rather than holistic feedback. The *Claude prompting guide* frames "make it better" as the canonical bad refinement and contrasts it with a numbered list of concrete adjustments ([[project-how-to-use-claude-export]]).

## Key distinctions

- **Specific deltas vs. holistic feedback**: "shorten the second paragraph; make tone casual; add a customer example" beats "make it better" ([[project-how-to-use-claude-export]]).
- **Refinement vs. restart**: the guide treats refinement as a continuation, not a fresh prompt — Claude builds on what it produced.

## Examples

From the *Claude prompting guide*: "That's a good start, but please refine it further. Make the following adjustments: 1. Make the tone more casual and friendly, 2. Add a specific example of how our product has helped a customer, 3. Shorten the second paragraph to focus more on the benefits rather than the features." ([[project-how-to-use-claude-export]]).

## Related

- [[effective-prompting]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`
