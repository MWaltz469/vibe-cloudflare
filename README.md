# Vibe Cloudflare

A static site deployed to Cloudflare Pages. Free tier, always on, no cold starts.

## Quick Start (3 steps)

### 1. Get Your Cloudflare Credentials

- Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
- **Account ID** → Workers & Pages → right sidebar
- **API Token** → My Profile → API Tokens → Create Token → use **"Edit Cloudflare Workers"** template

### 2. Add Secrets & Variables to GitHub

Go to your repo → **Settings** → **Secrets and variables** → **Actions**.

**Secrets** tab — add these two:

| Secret | Value |
|---|---|
| `CLOUDFLARE_ACCOUNT_ID` | Your account ID |
| `CLOUDFLARE_API_TOKEN` | The API token you created |

**Variables** tab — add these:

| Variable | Value | Required |
|---|---|---|
| `PROJECT_NAME` | Your project name (becomes `https://<PROJECT_NAME>.pages.dev`) | Yes |
| `CUSTOM_DOMAIN` | e.g. `mysite.com` or `app.mysite.com` | No |

### 3. Push to Main

That's it. The workflow auto-creates the Cloudflare Pages project and deploys. No dashboard setup needed.

Your site goes live at `https://<PROJECT_NAME>.pages.dev`.

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
