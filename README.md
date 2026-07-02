# Micra Sales Intel™

Paste a company URL, get a McKinsey-grade sales intelligence brief in 60 seconds — no coding.

**[→ See a real example report first](example-output.md)** before you install anything.

## What it is
An n8n workflow that gives you a simple web form. Enter a lead, get a complete 12-section
sales brief: executive summary, buying signals, ice breakers, discovery questions, business
risks, recent news, decision-maker summary, a ready-to-send cold email and LinkedIn DM, a
30-second meeting brief, a CRM summary, and your next best action.

## What's in this package
| File | What it's for |
|---|---|
| `workflow.json` | The n8n workflow — import this |
| `INSTALL.md` | 10-minute, no-code setup |
| `prompts/lead-research.md` | The research prompt (edit to customize the report) |
| `example-output.md` | A real sample report — read this first |
| `demo-leads.csv` | 10 demo leads to try it on |
| `loom-checklist.md` | Script for your demo video |
| `landing-copy.md` | Sales page copy |
| `gumroad-structure.md` | How the paid package is bundled |
| `CHANGELOG.md` | Version history |

## Quick start
1. Read **[the example report](example-output.md)** (30 seconds) — see what you're about to get.
2. Read **INSTALL.md** (10 minutes).
3. Import `workflow.json` into n8n, add your Anthropic API key, activate.
4. Open the form URL, enter a lead from `demo-leads.csv`, submit.
5. Read your first brief.

## Requirements
- n8n — Cloud, Desktop, or self-hosted ([get n8n](https://n8n.io) if you don't have it)
- An Anthropic API key ([console.anthropic.com](https://console.anthropic.com))

## Customize it
Open `prompts/lead-research.md` and edit the report structure or tone, then update the
`system`/`content` text in the **Generate Research (Claude)** node. Everything else stays the same.

## Support
Issues installing? The most common fixes are in `INSTALL.md` → Troubleshooting.
