---
description: Run a health check on the wiki.
argument-hint:
---

Run a health check across `wiki/`. **Report only — do not fix anything yet.**

Checks to run:

1. **Broken `[[wiki-links]]`** — any link whose target page does not exist in `wiki/`.
2. **Orphan pages** — pages in `wiki/` that no other wiki page links to (excluding `index.md` and `log.md`).
3. **Missing required frontmatter** — pages missing any of: `title`, `type`, `sources`, `related`, `created`, `last-updated`. Also flag pages whose `type` is not one of `concept`, `entity`, `source-summary`, `comparison`, `project`, `person`.
4. **Stale pages** — pages whose `last-updated` is **30+ days** before today.
5. **Contradictions** — claims across pages that disagree without being flagged as a known disagreement (per the style guide, contradictions should be called out inline).
6. **Index drift** — wiki pages that exist but are not listed in `wiki/index.md`, and entries in `wiki/index.md` that point to pages that no longer exist.

Output format — a structured report grouped by check:

```
## Broken wiki-links
- [[foo]] referenced in wiki/concepts/bar.md — target missing

## Orphan pages
- wiki/concepts/baz.md — no inbound links

## Missing frontmatter
- wiki/people/alice.md — missing `last-updated`

## Stale pages
- wiki/projects/old-thing.md — last-updated 2025-09-01 (236 days)

## Contradictions
- [[transformers]] says X; [[attention]] says Y — not flagged as disagreement

## Index drift
- wiki/concepts/new.md — present but not in index.md
```

After the report, **ask the user which findings they want fixed before making any changes.**
