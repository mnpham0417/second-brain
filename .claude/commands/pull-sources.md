---
description: Pull fresh material from real-world sources into raw/ for later triage and /ingest
---

# /pull-sources

Pull the last 7 days of material from configured sources into `raw/`, applying volume caps and filters BEFORE writing. After all sources finish, log results to `wiki/log.md` and remind the user to triage before `/ingest`.

Run each source block below in order. If a source's MCP connector is missing or not configured, skip that block and print a one-line note like `gmail: skipped (connector not available)`.

---

## Global rules (apply to every source)

- **Window:** last 7 days, computed as `today - 7d` in the user's local timezone.
- **Filter before write:** apply the volume cap and include/exclude filters BEFORE creating any file in `raw/`. Never write a file and delete it after.
- **Dedupe:** before writing a file to `raw/<source>/`, check if any existing file in that directory has the same id (e.g. `session_id`, `thread_id`, `event_id`) in its YAML frontmatter. If yes, skip and count it as `dedupe-skip`.
- **Triage header:** every file written to `raw/` MUST start with a one-line blockquote header on line 1, ABOVE the YAML frontmatter:
  ```
  > <source>: <who or what>, <subject or title>. <one-sentence summary of what's inside>.
  ```
  This is so a future-me can skim `raw/` in Obsidian's preview pane and decide what to keep.
- **Frontmatter:** every file has at minimum `source` and `captured` (ISO date, today). Source-specific keys are listed per block.
- **Track counts per source:** keep `written`, `filtered_out`, `dedupe_skipped` for the final log entry.

---

## Source 1: Claude Code sessions (always run)

**Read from:** `~/.claude/projects/` — recurse all subdirectories, find `*.jsonl` files modified in the last 7 days.

**Volume cap:** max 20 sessions per run (most recent first by mtime).

**Include filter:** only sessions with at least 5 user messages (skip trivial/empty/test sessions).

**Exclude filter:** skip sessions where the entire conversation is a single user turn or only contains tool errors.

**Write to:** `raw/claude-sessions/`

**Filename:** `YYYY-MM-DD-<slug>.md` where `YYYY-MM-DD` is the session start date and `<slug>` is a short kebab-case slug auto-generated from the first substantive user message (max 6 words).

**Frontmatter keys:** `source: claude-code`, `captured: <today ISO>`, `session_id: <uuid from JSONL>`.

**Triage header example:** `> claude-code: second-brain vault, drafting pull-sources slash command. Interview-driven design of a per-source ingestion command with caps and filters.`

**Body:** rendered transcript of user + assistant turns (skip raw tool inputs/outputs unless they carry the substance of the conversation).

---

## Source 2: Gmail

**Connector:** `claude_ai_Gmail` (use `mcp__claude_ai_Gmail__search_threads` with a date query, then `mcp__claude_ai_Gmail__get_thread` for each).

**Read from:** INBOX, last 7 days. Search query: `in:inbox newer_than:7d`.

**Volume cap:** max 20 threads per run, most recent first.

**Include filter:** only threads where the user (`mp5847@nyu.edu`) is in `To` or `Cc` of at least one message in the thread.

**Exclude filter:** skip threads where ALL messages are from senders matching `noreply@*`, `notifications@*`, `no-reply@*`, `*-noreply@*`, or `automated@*`. Also skip threads with calendar-invite MIME parts (`text/calendar`) and threads carrying labels `promotions` or `updates`.

**Write to:** `raw/gmail/`

**Filename:** `YYYY-MM-DD-<sender-slug>-<subject-slug>.md` in kebab-case. `YYYY-MM-DD` is the date of the most recent message in the thread. `<sender-slug>` is the local-part of the most recent non-self sender. `<subject-slug>` is the subject with `Re:`/`Fwd:` stripped, lowercased, kebab-cased, truncated to 60 chars.

**Frontmatter keys:** `source: gmail`, `captured: <today ISO>`, `thread_id`, `from`, `to`, `subject`, `date` (ISO of most recent message), `labels` (list).

**Triage header example:** `> gmail: jane@example.com, Re: paper draft feedback. Three rounds of edits on the methods section, with one open question about the eval setup.`

**Body:** rendered thread — for each message, a heading with sender + date, then the plaintext body.

---

## Source 3: Google Calendar

**Connector:** `claude_ai_Google_Calendar` (use `mcp__claude_ai_Google_Calendar__list_events`).

**Read from:** primary calendar. Pull BOTH directions:
- past 7 days (events the user attended)
- next 7 days (upcoming events)

**Volume cap:** max 20 events per run total across both windows. If more than 20 match, prefer the most recent past events first, then upcoming, ordered by start time descending.

**Include filter:** none — pull everything that matches the window.

**Exclude filter:** none.

**Write to:** `raw/google-calendar/`

**Filename:** `YYYY-MM-DD-<event-title-slug>.md` in kebab-case. `YYYY-MM-DD` is the event start date.

**Frontmatter keys:** `source: google-calendar`, `captured: <today ISO>`, `event_id`, `meeting_title`, `attendees` (list of emails), `start` (ISO datetime), `end` (ISO datetime), `duration_min` (int), `organizer` (email), `meeting_link` (Zoom/Meet/etc URL or empty).

**Triage header example:** `> google-calendar: alice@example.com, Research sync with X team. 30-min recurring meeting; description mentions follow-ups on the eval pipeline.`

**Body:** event description (if any), attendee list, location, conferencing link.

---

## After all sources finish

1. Append a single line to `wiki/log.md` (newest at the bottom), format:
   ```
   YYYY-MM-DD — pull-sources — raw/ — claude-code: W written / F filtered / D dedupe-skipped; gmail: …; google-calendar: …
   ```
   where W/F/D are the counts tracked per source. If a source was skipped because its connector wasn't available, write `<source>: skipped (no connector)`.

2. Print a final reminder to the user:
   > Triage `raw/` first — open the new files in Obsidian preview, skim the `>` header on line 1, delete anything you don't want to keep. Then run `/ingest` on what's left.

---

<!--
# Add your own source here

Copy this block, fill it in, and add it to the sequence above. Do NOT remove this scaffold.

## Source N: <name>

**Connector / Read from:** <MCP connector name and tool, OR local path glob>

**Volume cap:** <e.g. max 20 items per run, top N most recent, no more than M per sender>

**Include filter:** <explicit predicate — e.g. only items where I am in To/Cc, only meetings >10 min, only issues assigned to me>

**Exclude filter:** <explicit predicate — e.g. skip noreply@, skip "Daily Standup", skip Done issues>

**Write to:** `raw/<source-slug>/`

**Filename:** `<pattern, e.g. YYYY-MM-DD-author-title.md in kebab-case>`

**Frontmatter keys:** `source: <slug>`, `captured: <today ISO>`, plus: `<your-keys>`

**Triage header example:** `> <source>: <who>, <title>. <one-sentence summary>.`

**Dedupe:** before writing, check `raw/<source-slug>/` for any file whose frontmatter `<id-key>` matches this item's id. If yes, count as dedupe-skip and do not write.

**Body:** <what to render — e.g. message body, transcript, description>
-->
