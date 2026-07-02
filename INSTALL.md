# Install — Micra Sales Intel (under 10 minutes, no coding)

You need: **n8n** and an **Anthropic API key**. Don't have either yet? Both steps below
take you straight there.

---

## Step 0 — Get n8n (skip if you already have it)
Don't have n8n? Go to **[n8n.io](https://n8n.io)** and choose one:
- **n8n Cloud** — fastest start, free trial, no install (recommended for first-timers)
- **n8n Desktop** — a downloadable app for Mac/Windows
- **Self-hosted** — if your team already runs its own n8n instance

Any of the three works identically for this product.

## Step 1 — Get your API key (2 min)
1. Go to **console.anthropic.com** → sign in → **API Keys** → **Create Key**.
2. Copy the key (starts with `sk-ant-`). Keep it handy.
3. **Note:** brand-new Anthropic accounts sometimes need a payment method added before a
   key will authorize requests, even on the free trial credit. If Step 4 gives you an
   "unauthorized" error, check **console.anthropic.com → Billing** first.

## Step 2 — Add the key to n8n (2 min)
- **n8n Cloud:** Settings → **Variables/Environment** → add `ANTHROPIC_API_KEY` = your key.
- **n8n Desktop / self-host:** add `ANTHROPIC_API_KEY=sk-ant-...` to your environment and restart n8n.

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
- *No report / error:* the API key isn't set correctly. Re-check Step 2.
- *"unauthorized":* the key is invalid, or your Anthropic account needs a payment method
  on file — check **console.anthropic.com → Billing** (see Step 1 note).
- *Form URL 404:* the workflow isn't **Active**. Toggle it on (Step 3.3).
- *Don't have n8n yet:* see Step 0 above — n8n Cloud is the fastest path.
