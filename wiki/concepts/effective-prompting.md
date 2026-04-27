---
title: Effective prompting (umbrella)
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[few-shot-prompting]], [[chain-of-thought-prompting]], [[role-prompting]], [[iterative-prompt-refinement]], [[llm-statelessness]], [[socratic-tutoring-prompt-pattern]], [[how-to-use-claude]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

A small bundle of techniques — *be specific*, *show examples*, *ask for step-by-step thinking*, *iterate*, *assign a role*, *carry context across turns* — that reliably raises the quality of LLM responses ([[project-how-to-use-claude-export]]). Each technique has its own atomic page; this page indexes them.

## Definition

Per the *Claude prompting guide* shipped with the [[how-to-use-claude]] starter project, "effective" prompts (a) state the task at the start, (b) supply context and constraints, (c) decompose complex tasks, and (d) explicitly request the format and depth of the response. Vague prompts get vague answers; structured prompts get structured answers ([[project-how-to-use-claude-export]]).

## Key distinctions

- **Be specific vs. vague**: "Help me with a presentation" vs. "I need a 10-slide deck for our quarterly sales meeting covering Q2 performance, top products, Q3 targets" ([[project-how-to-use-claude-export]]).
- **Few-shot vs. zero-shot**: showing an example of desired output beats describing it. See [[few-shot-prompting]].
- **Step-by-step vs. one-shot reasoning**: ask for explicit reasoning on hard tasks. See [[chain-of-thought-prompting]].
- **Role-assigned vs. generic voice**: assigning a persona ("act as a CFO") shifts both content and tone. See [[role-prompting]].
- **Single-shot vs. iterative**: refine with specific deltas ("make tone more casual; add a customer example") rather than "make it better". See [[iterative-prompt-refinement]].
- **Stateful vs. stateless conversations**: Claude does not retain prior conversations — every new chat needs the context re-injected. See [[llm-statelessness]].

## Examples

The guide gives bad/good prompt pairs across content creation, document Q&A, data analysis, and brainstorming. The recurring pattern in the "good" version: numbered structure, named audience, named output format, and explicit asks for citations or visualizations ([[project-how-to-use-claude-export]]).

## Related

- [[few-shot-prompting]]
- [[chain-of-thought-prompting]]
- [[role-prompting]]
- [[iterative-prompt-refinement]]
- [[llm-statelessness]]
- [[socratic-tutoring-prompt-pattern]]
- [[how-to-use-claude]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`
