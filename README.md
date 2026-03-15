# Aubrey's Command Center

A personal, private, portable admin toolkit. Runs entirely in your browser — no school data ever stored on a server.

---

## What You Need

| Thing | Cost | Where |
|-------|------|-------|
| GitHub account | Free | github.com |
| Cloudflare account | Free | cloudflare.com |
| Anthropic API key | ~$5–10/month usage | console.anthropic.com |

---

## Step 1 — GitHub Setup

1. Go to **github.com** and create a free account
2. Click **New repository**
   - Name it: `aubrey-command-center`
   - Set to **Public**
   - Click **Create repository**
3. Click **Add file → Upload files**
4. Upload `index.html` (rename `index2.html` to `index.html` first)
5. Click **Commit changes**
6. Go to **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** → **/ (root)**
   - Click **Save**
7. Wait 2–3 minutes — your live URL will be:
   `https://[your-github-username].github.io/aubrey-command-center`

---

## Step 2 — Anthropic API Key

1. Go to **console.anthropic.com**
2. Create an account and add a payment method
3. Click **API Keys → Create Key**
4. Name it: `aubrey-command-center`
5. **Copy the key immediately** — you won't see it again
6. Save it somewhere safe (Notes app, password manager)

Typical usage: $3–8/month depending on how often you use AI features.

---

## Step 3 — Cloudflare Worker

1. Go to **cloudflare.com** and create a free account
2. In the left sidebar click **Workers & Pages**
3. Click **Create → Create Worker**
4. Name it: `aubrey-ap-proxy`
5. Click **Deploy**
6. Click **Edit code**
7. **Delete all the default code** and paste in the entire contents of `worker.js`
8. Click **Deploy**
9. Go to **Settings → Variables and Secrets**
   - Click **Add variable**
   - Variable name: `ANTHROPIC_API_KEY` (exact, case-sensitive)
   - Value: paste your Anthropic API key from Step 2
   - Click **Deploy**
10. Copy your Worker URL — it will look like:
    `https://aubrey-ap-proxy.[your-account].workers.dev`

---

## Step 4 — First Launch

1. Open your GitHub Pages URL in any browser or on iPhone
2. Click **⚙ Setup** in the top right
3. Fill in:
   - **Your Name:** Aubrey
   - **School Name:** your school
   - **Worker URL:** paste your Cloudflare Worker URL from Step 3
4. Click **Save Configuration**
5. Done — all settings are saved and will reload automatically every time you open the app

---

## iPhone Setup (Optional but Recommended)

1. Open your GitHub Pages URL in **Safari**
2. Tap the **Share button** (box with arrow)
3. Tap **Add to Home Screen**
4. Name it: `Admin Command`
5. Tap **Add**

It will appear on your home screen and launch full-screen like a real app.

---

## Updating the App

When a new `index.html` is provided:
1. Go to your GitHub repo
2. Click on `index.html`
3. Click the **pencil icon** (Edit)
4. Click **...** → **Delete file** OR simply drag and drop the new file to upload
5. Commit — the live site updates in ~60 seconds

---

## Privacy & Data

- **Zero server storage** — all data lives in your browser only
- **No student PII** is ever sent to AI — only anonymous aggregates and codes
- **Daily Summary** auto-deletes after 24 hours
- **Settings** persist in your browser's localStorage — private to your device
- Closing the tab clears all session data (incidents, teachers, observations)
- FERPA safe when used as intended — no identifiable student data transmitted

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| AI features not working | Check Worker URL in Setup — must include `https://` |
| "Method not allowed" error | Worker deployed correctly but API key not set — check Cloudflare Variables |
| Settings not saving | Make sure you clicked **Save Configuration** |
| Page not loading on GitHub | Wait 5 min after first deploy, check Pages settings |
| iPhone not showing full-screen | Must use Safari and "Add to Home Screen" |

---

## Your URLs

| Thing | URL |
|-------|-----|
| Live app | `https://[username].github.io/aubrey-command-center` |
| GitHub repo | `https://github.com/[username]/aubrey-command-center` |
| Cloudflare Worker | `https://aubrey-ap-proxy.[account].workers.dev` |

---

*Personal · Private · Portable*
