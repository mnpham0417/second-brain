---
title: "Source: Random scratch notes (misc/random.md)"
type: source-summary
sources: [misc/random.md]
related: [[minh-pham]]
created: 2026-04-24
last-updated: 2026-04-24
---

## One-paragraph summary

A two-line scratchpad with a personal sizing fact and one **plaintext API credential**. The credential is deliberately not reproduced in this wiki; see *Open questions* below ([[misc-random]]).

## Key claims

- Minh's On Cloud 6 Waterproof shoe size is **8.5** ([[misc-random]]).
- The file contains a **Gemini API key in plaintext**. The literal value is not reproduced here — copying secrets out of `raw`/`misc` and into the wiki would multiply the exposure surface ([[misc-random]]).

## Notable quotes

_(none — no prose; one of two lines is a credential and is intentionally not quoted.)_

## Open questions

- The Gemini API key should be moved to a secret store (e.g. macOS Keychain, 1Password, or `.env` outside the iCloud-synced vault) and rotated. Flagging for the vault owner. Until rotated, treat any sync of `misc/random.md` to a less-trusted device or backup as a credential exposure event.
- What did the API key get used for? (No usage context in the source.)

## Sources

- `misc/random.md`
