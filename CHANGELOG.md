# Changelog — Micra Sales Intel

All notable changes to this product. Follows Keep a Changelog / SemVer.

## [1.2.1] — 2026-07-10 — Import reliability
### Fixed
- `workflow.json` now carries a top-level `id` and drops the loose `tags` array, matching the
  shape n8n itself exports. Without this, `n8n import:workflow` (CLI) failed with
  `NOT NULL constraint failed: workflow_entity.id`. Verified re-import succeeds on a live n8n.

## [1.2.0] — 2026-07-10 — Free by default (Groq)
### Changed
- **LLM provider switched to the Groq free tier** (`openai/gpt-oss-120b`, OpenAI-compatible
  API). This is the exact configuration the product was verified end-to-end on — and it needs
  **no credit card**, so "self-host free, forever" is now true at the install step, not just
  in marketing. Previously the workflow required a paid Anthropic key (`sk-ant-`), which broke
  the free promise for Community users on step one.
- `INSTALL.md` / `README.md` now walk you through a free Groq key (`console.groq.com`)
  instead of a paid Anthropic key.
- The key is added as an n8n **Bearer Auth credential** (not an environment variable), so
  setup works identically on **n8n Cloud, Desktop, and self-hosted** — the previous `$env`
  approach fails on n8n Cloud, which is the path first-timers are steered toward.
- Workflow now uses `responseMode: responseNode` (fixes an "unused Respond node" error on
  n8n 2.x) and a stricter anti-hallucination system prompt that flags "Unknown — verify".
- Trimmed the README package table to the files actually shipped.

## [1.0.0] — 2026-07-02
### Added
- n8n workflow (`workflow.json`): form intake → Claude research → report display
- No-code form UI for non-developers (n8n Form Trigger)
- Research prompt (`prompts/lead-research.md`) — reuses the Micra Factory Research Agent
- 10-minute install guide (`INSTALL.md`) with troubleshooting
- Example output, 10-lead demo dataset (`demo-leads.csv`)
- README, Loom recording checklist, landing page copy, Gumroad package structure
- Retry-on-fail (2×) and 60s timeout on the LLM call

### Notes
- Built entirely on existing Micra Factory (n8n). No new infrastructure.
- Requires: n8n + an Anthropic API key.

## [1.1.0] — 2026-07-02 — Micra Sales Intel™
### Changed
- **Expanded output only** — same workflow, same 4 nodes, same infrastructure.
- Report upgraded from a 6-section research brief to a 12-section McKinsey-grade Sales
  Intelligence brief: Executive Summary, 3 Buying Signals, 5 Ice Breakers, 5 Discovery
  Questions, Business Risks, Recent News, Decision Maker Summary, AI Cold Email, LinkedIn DM,
  30-Second Meeting Brief, CRM Summary, Next Best Action.
- Prompt bumped to v2.0 (`prompts/lead-research.md`).
- LLM `max_tokens` 1500 → 3000 to fit the fuller brief (only change inside the workflow node).
- Form + workflow renamed to Micra Sales Intel.

### Unchanged (per ticket)
- Workflow structure, node count, wiring, infrastructure, dependencies, install steps.

## [Unreleased] — planned
- Optional email delivery of the report
- Optional public-web enrichment step (fetch node) before the LLM call
- Batch mode: run a CSV of leads in one go
