---
title: Chain-of-thought prompting
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[effective-prompting]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

Ask the model to "think step-by-step" or "explain your reasoning" on hard tasks. Surfacing intermediate steps tends to improve final-answer quality on multi-step problems ([[project-how-to-use-claude-export]]).

## Definition

A prompting technique that elicits explicit intermediate reasoning before the final answer. The *Claude prompting guide* phrases it as: "For complex tasks, ask Claude to 'think step-by-step' or 'explain your reasoning.' This can lead to more accurate and detailed responses." ([[project-how-to-use-claude-export]]).

## Key distinctions

- **Step-by-step request vs. structured decomposition**: a bare "think step-by-step" works, but the guide's worked example goes further by *enumerating the steps* the model should walk through (e.g., "1. Current productivity blockers, 2. Potential solutions, 3. Implementation challenges, 4. Methods to measure improvement") and asks for a brief explanation of reasoning at each step ([[project-how-to-use-claude-export]]).
- **CoT vs. final-answer-only**: the technique trades response length for accuracy and traceability.

## Examples

From the *Claude prompting guide*, productivity-improvement question: instead of "How can I improve team productivity?", the better prompt names four reasoning steps to walk through and asks for an explanation per step plus a final summary ([[project-how-to-use-claude-export]]).

## Related

- [[effective-prompting]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`
