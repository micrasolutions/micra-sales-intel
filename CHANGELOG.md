# Changelog — Micra Lead Research System

All notable changes to this product. Follows Keep a Changelog / SemVer.

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
