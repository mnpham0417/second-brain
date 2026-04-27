# raw/notes/

Personal notes exported from other apps. This is a *raw archive* — keep the original form so you can re-import or diff later. Newly written notes belong in `journal/` or `wiki/`, not here.

## What belongs here

- Apple Notes exports
- Notion page exports
- Old Obsidian / Bear / Roam / Logseq exports being migrated in
- Scanned handwritten notes (with OCR text alongside)
- One-off `.txt` / `.md` files from miscellaneous note apps

## Where to export from

- **Apple Notes** — select notes → `File → Export as PDF`, or use [exporter](https://github.com/AndrewBrobston/Apple-Notes-Exporter) / similar tools for Markdown.
- **Notion** — workspace `Settings → Export all workspace content → Markdown & CSV`; per-page via `··· → Export → Markdown & CSV`.
- **Bear** — `File → Export Notes → Markdown`.
- **Roam / Logseq** — JSON/EDN export from settings; `.md` files for Logseq live on disk already.
- **Evernote** — select notes → `File → Export Notes` → `.enex`, then convert with `evernote2md`.
- **Handwritten** — scan with Apple Notes or Adobe Scan, then OCR (`ocrmypdf` or built-in iOS Live Text).

Filename convention: keep app-specific exports in their own subfolder (`apple-notes-YYYY-MM-DD/`, `notion-YYYY-MM-DD/`); freestanding notes as `YYYY-MM-DD-slug.md`.
