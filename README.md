# Vibe Cloudflare

A static site deployed to Cloudflare Pages. Free tier, always on, no cold starts.

## Quick Start (3 steps)

### 1. Get Your Cloudflare Credentials

- Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
- **Account ID** → Workers & Pages → right sidebar
- **API Token** → My Profile → API Tokens → Create Token → use **"Edit Cloudflare Workers"** template

### 2. Add Secrets to GitHub

Go to your repo → **Settings** → **Secrets and variables** → **Actions** → add these two:

| Secret Name | Value |
|---|---|
| `CLOUDFLARE_ACCOUNT_ID` | Your account ID |
| `CLOUDFLARE_API_TOKEN` | The API token you created |

### 3. Configure & Push

Open `.github/workflows/deploy.yml` and set your project name at the top:

```yaml
# ──────────────────────────────────────────────
# CONFIG — edit these to customize your deploy
# ──────────────────────────────────────────────
env:
  # Project name → becomes https://<PROJECT_NAME>.pages.dev
  PROJECT_NAME: "vibe-cloudflare"

  # Custom domain (optional) — leave empty to skip
  # e.g. "mysite.com" or "app.mysite.com"
  CUSTOM_DOMAIN: ""
```

- Change `PROJECT_NAME` to whatever you want → your site goes live at `https://<PROJECT_NAME>.pages.dev`
- Set `CUSTOM_DOMAIN` if you have a domain on Cloudflare (otherwise leave blank)
- The project auto-creates on first deploy — no manual setup in the dashboard needed

Push to `main` and you're live.

## Project Structure

```
vibe-cloudflare/
├── public/
│   ├── index.html              # Your site (edit this)
│   └── styles.css              # Styles (edit this)
├── .github/workflows/
│   └── deploy.yml              # Auto-deploy config
├── wrangler.toml               # Cloudflare Pages config
└── README.md
```

## Local Preview

Open `public/index.html` in a browser, or:

```sh
npx wrangler pages dev public
```

## What You Get (Free Tier)

- Unlimited bandwidth and requests
- 500 builds/month
- Custom domain support
- Global edge CDN (300+ locations)
- Always on — no cold starts, no sleep, no shutdown
