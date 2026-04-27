---
description: Ingest new files from raw/, misc/, and journal/ into wiki/.
argument-hint: optional max number of sources to process
---

Ingest new source material from `raw/`, `misc/`, and `journal/` into the `wiki/`.

Workflow:

1. Determine how many sources to process this run.
   - Default: process **5–10 sources thoroughly**.
   - If `$ARGUMENTS` is a number, limit this run to that many sources.

2. Find unread sources.
   - Walk all three source roots:
     - `raw/` (subfolders: `articles/`, `claude-exports/`, `podcast-transcripts/`, `youtube-transcripts/`, `voices-memos/`, `slack-exports/`, `jira/`, `email-archives/`, `pdfs/`, `arxiv-papers/`, `zotero/`, `notes/`).
     - `misc/` (free-form user-curated notes — e.g. `people.md`, `my-lessons.md`, `conversations.md`, `random.md`, `meta-relocation.md`). Treat each top-level file as one source.
     - `journal/` (daily notes and similar). Treat each daily/journal entry as one source. **Skip** `README.md`, `daily-note-template.md`, and any other file whose name ends in `-template.md` or that is obviously scaffolding rather than content.
   - A file is "already summarised" if any wiki page lists its path in its frontmatter `sources:` field. Skip those.
   - Also skip anything already mentioned as ingested in `wiki/log.md`.
   - Also skip top-level `README.md` files in any source root.

3. For each selected source, do all of the following:
   - **Read the file in full.** For long PDFs or transcripts, read enough to extract the substantive content — do not skim.
   - **Write a `source-summary` page** in `wiki/` following the heading skeleton from `CLAUDE.md` (`## One-paragraph summary` · `## Key claims` · `## Notable quotes` · `## Open questions` · `## Sources`). Required frontmatter: `title`, `type: source-summary`, `sources: [<path into raw/, misc/, or journal/>]`, `related`, `created`, `last-updated`.
   - **Create or update concept / project / person pages** for the ideas, initiatives, and people the source discusses. One idea per page (atomic). If a relevant page already exists, extend it rather than duplicating.
   - **Cross-link with `[[wiki-links]]`** between the source-summary and every concept/project/person page it touches. Update `related:` frontmatter on both sides.
   - **Attribute every claim to its source** inline, per the style guide in `CLAUDE.md`. Flag contradictions explicitly when two sources disagree.

4. Update `wiki/index.md`.
   - Add a one-line entry for every newly created page, in the correct section (Concepts / Projects / People / Source summaries).
   - If you meaningfully changed an existing page's purpose, update its description.

5. Append entries to `wiki/log.md`.
   - One line per change, newest at the bottom.
   - Format: `YYYY-MM-DD — <action> — <page> — <short note>` (use today's date).
   - Never edit or delete past entries.

6. At the end of the run, report:
   - How many sources were ingested.
   - Which wiki pages were created vs. updated.
   - Any sources you deliberately skipped and why.
