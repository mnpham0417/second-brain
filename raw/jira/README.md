# raw/jira/

Jira issue exports — tickets, epics, sprint reports.

## What belongs here

- CSV / JSON exports from Jira filters
- Individual ticket exports (XML or rendered Markdown)
- Sprint and release reports

## Where to export from

- **Filter export** — run a JQL search → `Export → CSV (current fields)` or `Export → JSON`.
- **Single issue** — `··· → Export → XML` (full fidelity) or `Export → Word`, then convert.
- **REST API** — `GET /rest/api/3/search?jql=<query>` and paginate; useful for scripted re-pulls.
- **Atlassian-Python-API / jira-cli** — for repeat pulls, script the export and dump JSON here.

Filename convention: `YYYY-MM-DD-<filter-or-project>.csv` (or `.json`); for single tickets, use the issue key, e.g. `PROJ-1234.md`.
