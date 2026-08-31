# PublishFlow site

A plain HTML/CSS static site (no build step) covering what TikTok's developer
app review typically wants to see:

- `index.html` — what the integration does, in plain terms
- `workflow.html` — technical detail for reviewers: scopes requested, OAuth
  flow, data handling, redirect URI
- `privacy.html` — privacy policy
- `terms.html` — terms of service

## Before you submit to TikTok review

Search each file for `[bracketed text]` and replace it with real info:

- `[Your Company Name]`, `[Address]`, `[Your Jurisdiction]`
- `support@yourdomain.com` → your real support address
- The redirect URI in `workflow.html` → the exact callback URL registered in
  your TikTok developer app
- `https://github.com` link in `index.html` → your real repo, or remove it
- Dates marked `[Month DD, YYYY]`

Have someone (ideally a lawyer) review the privacy policy and terms before
relying on them — they're a solid starting draft, not legal advice.

## Deploy to Vercel

**Option A — CLI**

```bash
npm i -g vercel
cd publishflow-site
vercel        # first deploy, follow the prompts
vercel --prod # promote to your production vercel.app URL
```

**Option B — GitHub**

1. Push this folder to a new GitHub repo.
2. In the Vercel dashboard: **Add New → Project → Import** the repo.
3. Framework preset: **Other** (it's static HTML, no build command needed).
4. Deploy.

Either way you'll get a `your-project.vercel.app` URL — that's what you put
in the TikTok developer console as your app's website and privacy policy
URL (e.g. `https://your-project.vercel.app/privacy`).

## Customizing

- Colors, type, and spacing are all CSS variables at the top of `style.css`.
- The product is named "PublishFlow" throughout — find/replace if you're
  using a different name for your app.
