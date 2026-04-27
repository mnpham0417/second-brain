# raw/slack-exports/

Slack workspace and channel exports. Don't paste secrets/tokens that may live in messages — review before importing.

## What belongs here

- Workspace export `.zip` archives (or extracted JSON folders)
- Single-channel JSON exports
- Manually copied threads saved as `.md`

## Where to export from

- **Workspace export** (admin only) — `<workspace>.slack.com/services/export` → choose date range → download the `.zip` Slack emails when ready.
- **Single channel via Slack API** — `conversations.history` with a bot token, paginate, save the JSON.
- **slackdump** (CLI) — `slackdump -t <token> <channel>` for a richer per-channel export.
- **Manual** — `··· → Copy link` on a thread, then save the rendered text into a `.md` file.

Filename / folder convention: keep workspace exports in their own dated subfolder (`workspace-2026-04-export/`); single-thread captures as `YYYY-MM-DD-channel-topic.md`.
