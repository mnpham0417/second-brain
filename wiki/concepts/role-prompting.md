---
title: Role prompting
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[effective-prompting]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

Assign the model a persona ("You are a fabric supplier…", "Act as a senior CFO…") to focus its content and tone on that perspective ([[project-how-to-use-claude-export]]).

## Definition

A prompting technique where the user instructs the model to adopt a specific role or perspective. Per the *Claude prompting guide*: "Ask Claude to adopt a specific role or perspective when responding." ([[project-how-to-use-claude-export]]).

## Key distinctions

- **Role assignment vs. audience specification**: role prompting tells the model *who it is*; audience specification tells the model *who it's writing for*. Both can be combined.
- **Single-role vs. role-switching**: the guide's negotiation example pushes role-switching — first speak as the supplier with objections, then switch and advise the buyer ([[project-how-to-use-claude-export]]).

## Examples

- *"You are a fabric supplier for my backpack manufacturing company. I'm preparing for a negotiation with this supplier to reduce prices by 10%…"* ([[project-how-to-use-claude-export]]).
- *"Act as a seasoned CFO and analyze this report and prepare a briefing for our board of directors."* ([[project-how-to-use-claude-export]]).

## Related

- [[effective-prompting]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`

> Note: the source claims role-playing "increas[es] the intelligence and performance of Claude's response." That is the source's framing — it does not cite an eval. Treat as the source's claim, not an established benchmark fact.
