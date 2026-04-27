# CLAUDE.md

Operating instructions for Claude when working in this second-brain vault.

## 1. Project Structure

This vault has two halves: **`raw/` is the user's** (read-only to Claude), **`wiki/` is Claude's** (created and maintained by the assistant). `journal/` and `content/` come online in Part 2.

```
second-brain/
├── raw/                 # source documents — never modified by Claude
│   ├── articles/             # web articles, blog posts, newsletters
│   ├── claude-exports/       # exported claude.ai conversations
│   ├── podcast-transcripts/  # podcast transcripts (text only)
│   ├── youtube-transcripts/  # YouTube video transcripts
│   ├── voices-memos/         # user's voice memos + transcripts
│   ├── slack-exports/        # Slack workspace/channel exports
│   ├── jira/                 # Jira issue exports
│   ├── email-archives/       # exported email threads
│   ├── pdfs/                 # generic PDFs (books, slides, reports)
│   ├── arxiv-papers/         # academic preprints
│   ├── zotero/               # Zotero library exports
│   └── notes/                # exports from other note apps
├── wiki/                # Claude's domain — synthesis layer
│   ├── index.md              # master catalog of every wiki page
│   ├── log.md                # append-only activity log of Claude's edits
│   ├── concepts/             # concept and topic pages
│   ├── projects/             # project-specific pages
│   └── people/               # people dossiers
├── journal/             # daily notes (Part 2)
└── content/             # content pipeline (Part 2)
```

### Special files in `wiki/`

- **`index.md`** — the master catalog. Every wiki page is listed here once, grouped by section (Concepts, Projects, People) with a one-line description. Update it whenever a new page is created or a page's purpose changes meaningfully.
- **`log.md`** — append-only activity log. One line per change, newest at the bottom. Format: `YYYY-MM-DD — action — page — short note`. Never edit or delete past entries.

## 2. Page Conventions

### Frontmatter (required on every wiki page)

```yaml
---
title: <human-readable title>
type: <concept | entity | source-summary | comparison | project | person>
sources: [raw/articles/2024-01-15-attention.md, raw/arxiv-papers/2017-vaswani-attention.pdf]
related: [[transformers]], [[self-attention]]
created: YYYY-MM-DD
last-updated: YYYY-MM-DD
---
```

- `title` — full human-readable title.
- `type` — exactly one of: `concept`, `entity`, `source-summary`, `comparison`, `project`, `person`.
- `sources` — list of paths into `raw/` that the page draws from. Empty list `[]` is allowed when a page is purely synthesis of other wiki pages.
- `related` — list of `[[wiki-links]]` to neighboring pages.
- `created` — date the page was first created.
- `last-updated` — date of the most recent meaningful edit (touch this whenever you change the body).

### Linking and atomicity

- Use **`[[wiki-links]]`** for every reference to another wiki page. Never use bare filenames or relative paths inline.
- Pages are **atomic — one idea per page**. If a page starts covering two topics, split it.
- Prefer many small linked pages over a few sprawling ones.

### Heading structure

Use a consistent skeleton per `type`:

- **concept** — `## TL;DR` · `## Definition` · `## Key distinctions` · `## Examples` · `## Related` · `## Sources`
- **entity** — `## Summary` · `## Details` · `## Related` · `## Sources`
- **source-summary** — `## One-paragraph summary` · `## Key claims` · `## Notable quotes` · `## Open questions` · `## Sources`
- **comparison** — `## What's compared` · `## Side-by-side` · `## When to pick which` · `## Sources`
- **project** — `## Goal` · `## Status` · `## Decisions` · `## Open questions` · `## Timeline` · `## Related`
- **person** — `## Who` · `## Areas of work` · `## Notable interactions` · `## Related`

Drop sections that don't apply, but don't reorder or rename them.

## 3. Style Guide

- **Clear, concise prose.** Short sentences. Plain words. No throat-clearing.
- **Prefer bullet points** over paragraphs whenever you're listing claims, examples, or distinctions. Reserve prose for definitions and arguments that need flow.
- **Attribute every claim to its source.** Inline, like: `The model was trained on 15T tokens ([[2024-meta-llama3]]).` If you can't point to a source in `raw/` or another wiki page, say so explicitly: *"unsourced — Claude inference."*
- **Note contradictions explicitly.** When two sources disagree, write both, attribute each, and flag the disagreement: `> Source A says X ([[…]]); source B says Y ([[…]]). Unresolved.` Do not silently pick a side.
- No filler ("it is worth noting that…"), no hedging chains ("may potentially perhaps…"), no AI-vocabulary tics ("delve", "crucial", "tapestry").
- Dates in ISO format (`YYYY-MM-DD`).

## 4. Domain Context

_To be written after a short interview with the user — left blank for now._
