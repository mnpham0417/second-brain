---
title: "Source: Tinker product update — Kimi K2.6 and Qwen3.6 (2026-04-23)"
type: source-summary
sources: [raw/gmail/2026-04-23-tinker-new-in-tinker-kimi-k2-6-and-qwen3-6.md]
related: [[minh-pham]], [[rgpo-empire-ai]]
created: 2026-04-26
last-updated: 2026-04-26
---

## One-paragraph summary

Product update from **Thinking Machines (Tinker API)** announcing three new models on the Tinker platform: **Kimi K2.6** (32k and 128k context options), **Qwen3.6-35B-A3B** (MoE, 64k context), and **Qwen3.6-27B** (Dense, 64k context) (raw/gmail/2026-04-23-tinker…). Same pricing as predecessors. Kimi K2.6 upgrades long-horizon coding and multi-agent tasks; Qwen3.6 improves agentic coding and tool-use.

## Key claims

- **Kimi K2.6** is now on Tinker, with 32k and 128k context-length options (raw/gmail/2026-04-23-tinker…).
- **Qwen3.6-35B-A3B** is on Tinker as a Mixture-of-Experts model with 64k context (raw/gmail/2026-04-23-tinker…).
- **Qwen3.6-27B** is on Tinker as a dense model with 64k context (raw/gmail/2026-04-23-tinker…).
- All three are priced "the same as their predecessors" Kimi K2.5 and Qwen3.5 (raw/gmail/2026-04-23-tinker…).
- Positioning: Kimi K2.6 — long-horizon coding and multi-agent tasks; Qwen3.6 — agentic coding and tool-use; both pitched as "increased reliability for long tasks at distinct points on the size–capability spectrum" (raw/gmail/2026-04-23-tinker…).
- Tinker's Twitter / X handle: `@tinkerapi` (raw/gmail/2026-04-23-tinker…).

## Notable quotes

- "Kimi K2.6 offers upgrades on long-horizon coding and multi-agent tasks, while Qwen3.6 improves on agentic coding performance and tool-use." — Thinking Machines team.

## Open questions

- Does Minh's [[rgpo-empire-ai]] training stack use any of these base models? (Currently uses **Qwen2.5-3B** per HPC job emails — see [[gmail-amazon-science-offer-2026-04-22]] sidebar context. Qwen3.6 may be relevant if rgpo scales up.)
- Is Tinker pricing competitive with vllm/Together/Replicate for fine-tune + serve workloads on the same models? (Not from this source.)

## Sources

- `raw/gmail/2026-04-23-tinker-new-in-tinker-kimi-k2-6-and-qwen3-6.md`
