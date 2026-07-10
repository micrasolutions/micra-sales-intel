# Install — Micra Sales Intel (under 10 minutes, no coding)

You need: **n8n** and a **free Groq API key**. Don't have either yet? Both steps below
take you straight there — and neither costs anything.

---

## Step 0 — Get n8n (skip if you already have it)
Don't have n8n? Go to **[n8n.io](https://n8n.io)** and choose one:
- **n8n Cloud** — fastest start, free trial, no install (recommended for first-timers)
- **n8n Desktop** — a downloadable app for Mac/Windows
- **Self-hosted** — if your team already runs its own n8n instance

Any of the three works identically for this product.

## Step 1 — Get your free Groq API key (2 min)
1. Go to **[console.groq.com](https://console.groq.com)** → sign in (free, **no credit card**) → **API Keys** → **Create API Key**.
2. Copy the key (it starts with `gsk_`). Keep it handy.
3. That's it — Groq's free tier runs this workflow at no cost. There's nothing to pay and no card to add.

## Step 2 — Add the key to n8n (2 min)
- **n8n Cloud:** Settings → **Variables/Environment** → add `GROQ_API_KEY` = your key.
- **n8n Desktop / self-host:** add `GROQ_API_KEY=gsk_...` to your environment and restart n8n.

## Step 3 — Import the workflow (1 min)
1. In n8n: **Workflows → Import from File**.
2. Select **`workflow.json`** from this package.
3. Click **Save**, then toggle the workflow **Active** (top right).

## Step 4 — Run your first report (2 min)
1. Open the workflow → click the **Lead Intake Form** node → copy the **form URL**
   (or click **Test workflow** and use the test form URL).
2. Open the form in your browser.
3. Fill in **Lead name** and **Company** — the only two required fields. Website, role,
   and extra context are optional but improve the brief's accuracy if you have them.
4. Submit. **Your sales intelligence brief appears in seconds.** 🎉

---

## Done ✅
That's it. Bookmark the form URL — every submission generates a fresh brief.

**Troubleshooting**
- *No report / error:* the API key isn't set correctly. Re-check Step 2 (the variable must be named exactly `GROQ_API_KEY`).
- *"unauthorized" / 401:* the key is wrong or wasn't picked up. Re-copy it from [console.groq.com](https://console.groq.com) → API Keys, re-save the variable, and restart n8n.
- *Form URL 404:* the workflow isn't **Active**. Toggle it on (Step 3.3).
- *Don't have n8n yet:* see Step 0 above — n8n Cloud is the fastest path.

> **Note on how it works:** this tool reasons from the model's knowledge plus the lead
> details you enter. It has no live web access, so it deliberately flags anything it
> can't be sure of as *"Unknown — verify"* rather than inventing facts. Treat it as a
> sharp pre-call briefing scaffold, not a real-time data feed.
