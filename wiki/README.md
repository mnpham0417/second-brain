# wiki/

Claude's domain. Pages here are created and maintained by the assistant as it processes material from `raw/`, journal entries, and conversations.

Think of `wiki/` as the synthesized layer on top of `raw/` — distilled concepts, projects, and people, with links back to the sources they came from.

## Layout

- `index.md` — master catalog of every page in the wiki
- `log.md` — append-only activity log of changes Claude makes
- `concepts/` — concept and topic pages (ideas, techniques, frameworks)
- `projects/` — project-specific pages (goals, status, decisions, links)
- `people/` — dossiers on people (collaborators, authors, contacts)

## Conventions

- Filenames are kebab-case: `prompt-caching.md`, `dissertation-proposal.md`, `jane-doe.md`.
- Every page links back to its sources in `raw/` (and to other wiki pages where relevant).
- New or substantially-updated pages get an entry in `index.md` and a line in `log.md`.
