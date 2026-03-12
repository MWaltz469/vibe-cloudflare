# Vibe Cloudflare

A static site deployed to Cloudflare Pages. Free tier, always on, no cold starts.

## Project Structure

```
vibe-cloudflare/
├── public/
│   ├── index.html        # Landing page
│   └── styles.css        # Styles (dark theme, responsive)
├── .github/workflows/
│   └── deploy.yml        # Auto-deploy on push to main
├── wrangler.toml         # Cloudflare Pages config
└── README.md
```

## Setup

### 1. Get Your Cloudflare Account ID

- Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
- Go to **Workers & Pages** in the sidebar
- Your **Account ID** is shown on the right side of the page

### 2. Create an API Token

- Go to **My Profile** → **API Tokens** → **Create Token**
- Use the **"Edit Cloudflare Workers"** template (covers Pages too)
- Restrict the token to your account
- Copy the token — you won't see it again

### 3. Add Secrets to GitHub

- Go to your repo → **Settings** → **Secrets and variables** → **Actions**
- Add two repository secrets:
  - `CLOUDFLARE_ACCOUNT_ID` — your account ID from step 1
  - `CLOUDFLARE_API_TOKEN` — the API token from step 2

### 4. Push to Main

That's it. Every push to `main` triggers a deploy. Pull requests get preview URLs.

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
