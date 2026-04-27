---
description: Append a timestamped note to wiki/log.md.
argument-hint: the thought or note to capture
---

Capture the note in `$ARGUMENTS` to `wiki/log.md`.

Steps:

1. **Append a single timestamped line** to the bottom of `wiki/log.md`. Use today's date in ISO format. Format:

   ```
   YYYY-MM-DD — note — <short tag if useful> — $ARGUMENTS
   ```

   Never edit or delete past entries — `log.md` is append-only.

2. **Update existing wiki pages if the note touches them.**
   - Scan `wiki/index.md` for any project, person, or concept named in `$ARGUMENTS`.
   - If a matching page exists, add a brief note to the appropriate section (e.g. for a `project` page, under `## Decisions` or `## Open questions`; for a `person` page, under `## Notable interactions`). Bump `last-updated` to today.
   - Use the same attribution style as elsewhere — link back to the log entry or other related pages with `[[wiki-links]]`.

3. **Do not create new pages.** If the note mentions something that does not yet have a wiki page, leave it in `log.md` only. Surface it to the user as a suggestion at the end of your response so they can decide whether to promote it later.
