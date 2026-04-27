# raw/email-archives/

Exported email threads worth keeping for reference. Be deliberate — don't dump your whole inbox; archive what you'll actually want to look up later.

## What belongs here

- `.mbox` archives of specific labels/folders
- `.eml` files for individual threads
- `.md` renderings of threads with sender, recipients, date, and body

## Where to export from

- **Gmail** — [Google Takeout](https://takeout.google.com/) → select Mail → choose specific labels → download `.mbox`.
- **Apple Mail** — select a mailbox → `Mailbox → Export Mailbox…` → produces an `.mbox` package.
- **Outlook (desktop)** — `File → Open & Export → Import/Export → Export to a file → .pst`, then convert with `readpst` if you want `.eml`/`.mbox`.
- **Single thread** — Gmail "Print → Save as PDF", or "Show original" → save the raw `.eml`.

Filename convention: `YYYY-MM-DD-subject-slug.eml` for threads; `<label>-YYYY-MM.mbox` for archives. **Strip credentials, OTPs, and reset links before saving.**
