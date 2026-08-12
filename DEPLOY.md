# Deploying the Carbide docs to Vercel

The docs in this folder are a [Mintlify](https://mintlify.com) site. Deploying to Vercel takes a few minutes.

## Prerequisites

- The docs are in a Git repository (this repo)
- A [Vercel](https://vercel.com) account (free tier is fine)
- A GitHub account (Vercel imports from GitHub)

## Option A — Vercel import (recommended)

1. Push this repository to GitHub.
2. On Vercel: **Add New → Project** → import the repository.
3. Vercel detects the docs automatically:
   - **Framework preset:** `Mintlify`
   - **Build command:** (Mintlify's builder handles it)
   - **Output directory:** `_mintlify` (Vercel's Mintlify integration sets this)
4. Deploy. Your site is live at `https://<project>.vercel.app`.

> [!TIP]
> The `mint.json` at the docs root is the Mintlify configuration — it defines the
> navigation, theme color, and branding. Edit it and redeploy to restyle.

## Option B — Mintlify CLI + Vercel

```bash
npm i -g mintlify
mintlify dev        # preview locally at localhost:3000
```

Then connect the repo to Vercel as above, or use Mintlify's own hosting
(`mintlify deploy`) if you prefer not to use Vercel.

## Local preview

```bash
npx mintlify dev
```

Open http://localhost:3000. Edits to `.mdx` files hot-reload.

## Keeping it in sync

The docs describe the *implemented* language — when the compiler changes, update
the relevant page. The [Roadmap](/roadmap) and [Decisions](/design/decisions)
pages are the contract: every design decision must be recorded there, per the
spec (§83).
