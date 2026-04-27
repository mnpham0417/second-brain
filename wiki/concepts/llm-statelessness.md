---
title: LLM conversation statelessness
type: concept
sources: [raw/claude-exports/project-how-to-use-claude.md]
related: [[effective-prompting]], [[project-how-to-use-claude-export]]
created: 2026-04-24
last-updated: 2026-04-24
---

## TL;DR

Claude (and most LLM chat products) does not carry information across separate conversations. Every new chat starts blank, so any context the model needs has to be re-supplied in that chat ([[project-how-to-use-claude-export]]).

## Definition

The user-visible behavior that a chat model treats each new conversation as independent: prior conversations are not visible to the model unless explicitly re-injected ([[project-how-to-use-claude-export]]). Within a conversation, the model does see the running message history, but that scope ends when the conversation does.

## Key distinctions

- **Cross-conversation memory vs. in-conversation context**: the model has the latter (within a conversation's history) but not the former by default ([[project-how-to-use-claude-export]]).
- **Statelessness vs. memory features**: Claude.ai has since shipped explicit memory features in some surfaces — *unsourced — Claude inference; the source predates or doesn't mention them.* The cited guide describes the default behavior and is the relevant guidance when memory features are off.

## Examples

From the *Claude prompting guide*: "Claude doesn't retain information from previous conversations, so include all necessary context in each new conversation." ([[project-how-to-use-claude-export]]).

## Related

- [[effective-prompting]]

## Sources

- [[project-how-to-use-claude-export]] — `raw/claude-exports/project-how-to-use-claude.md`
