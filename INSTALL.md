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

## Step 2 — Import the workflow (1 min)
1. In n8n: **Workflows → Import from File**.
2. Select **`workflow.json`** from this package.
3. Click **Save**.

## Step 3 — Connect your key (2 min)
The workflow calls Groq over an authenticated HTTP request. Add your key once as a credential:
1. Open the workflow → click the **Generate Research** node.
2. Find **Credential to connect with** → **Create New Credential**.
3. Choose **Bearer Auth** → paste your Groq key (the `gsk_...` value) into the **Token** field → **Save**.
4. Back on the canvas, toggle the workflow **Active** (top right).

> Why a credential (not an environment variable)? It works identically on **n8n Cloud,
> Desktop, and self-hosted**, and your key stays encrypted in n8n — no server config needed.

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
- *"unauthorized" / 401:* the Bearer Auth credential is wrong. Re-open the **Generate Research** node → re-check the credential → re-paste your key from [console.groq.com](https://console.groq.com) → API Keys.
- *No report / node error:* make sure the **Generate Research** node has the Bearer Auth credential selected (Step 3).
- *Form URL 404:* the workflow isn't **Active**. Toggle it on (Step 3.4).
- *Don't have n8n yet:* see Step 0 above — n8n Cloud is the fastest path.

> **Note on how it works:** this tool reasons from the model's knowledge plus the lead
> details you enter. It has no live web access, so it deliberately flags anything it
> can't be sure of as *"Unknown — verify"* rather than inventing facts. Treat it as a
> sharp pre-call briefing scaffold, not a real-time data feed.
