---
title: "Source: How to use Claude (starter project export)"
type: source-summary
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[how-to-use-claude]], [[effective-prompting]], [[few-shot-prompting]], [[chain-of-thought-prompting]], [[role-prompting]], [[iterative-prompt-refinement]], [[llm-statelessness]]
created: 2026-04-24
last-updated: 2026-04-24
---

## One-paragraph summary

Export of the Claude.ai starter project "How to use Claude" — a default sample project. It carries one doc, *Claude prompting guide*, which lays out six general prompting principles (be clear and specific; use examples; encourage thinking; iterate; leverage Claude's knowledge; use role-playing) plus task-specific tips for content creation, document Q&A, data analysis, and brainstorming, and three rules for minimizing hallucinations and maximizing performance ([[project-how-to-use-claude-export]]).

## Key claims

- Be clear and specific: state the task at the start, give context, break down complex tasks ([[project-how-to-use-claude-export]]). See [[effective-prompting]].
- Provide examples of the format/style you want — i.e., few-shot prompting ([[project-how-to-use-claude-export]]). See [[few-shot-prompting]].
- For complex tasks, ask Claude to "think step-by-step" or "explain your reasoning" — chain-of-thought ([[project-how-to-use-claude-export]]). See [[chain-of-thought-prompting]].
- Iterative refinement beats vague feedback like "make it better"; specify exactly what to change ([[project-how-to-use-claude-export]]). See [[iterative-prompt-refinement]].
- Role-playing ("You are a fabric supplier…") "increas[es] the intelligence and performance of Claude's response" ([[project-how-to-use-claude-export]]). See [[role-prompting]].
- Tell Claude it's okay to admit uncertainty to reduce hallucination ([[project-how-to-use-claude-export]]).
- "Claude doesn't retain information from previous conversations, so include all necessary context in each new conversation" ([[project-how-to-use-claude-export]]). See [[llm-statelessness]].
- Task-specific guidance: specify audience, define tone/style, define output structure (for content creation); ask for citations and refer to documents by name (for Q&A) ([[project-how-to-use-claude-export]]).

## Notable quotes

> "Role-playing also encourages Claude to more readily adopt the nuances of specific perspectives, increasing the intelligence and performance of Claude's response." — *Claude prompting guide* ([[project-how-to-use-claude-export]])

> "Claude doesn't retain information from previous conversations, so include all necessary context in each new conversation." — *Claude prompting guide* ([[project-how-to-use-claude-export]])

## Open questions

- Does the guide reflect current Anthropic guidance as of 2026-04, or is it frozen to the export date (2025-10)?
- The guide claims role-playing increases response *intelligence* — is there a public Anthropic eval cited for that, or is it a stylistic claim?

## Sources

- `raw/claude-exports/project-how-to-use-claude.md`
