# SmartHub Static Website (HTML only)

This folder is a pure static website. No Laravel, no build step required.

## Files

- `index.html`
- `styles.css`
- `email-confirmation/index.html`
- `.nojekyll`

## Upload to a New GitHub Repository

1. Create a new empty repository on GitHub (for example: `smarthub-website-html`).
2. Run these commands from this folder:

```powershell
cd D:\SmartHubv14\SmartHubv5\website-html
git init
git add .
git commit -m "Initial static SmartHub website"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/<NEW_REPO>.git
git push -u origin main
```

## Deploy to Cloudflare Pages

- Project type: Pages
- Connect your new GitHub repository
- Production branch: `main`
- Build command: `exit 0`
- Build output directory: `.`

## Supabase Redirect URL

After deployment, set your redirect URL to:

- `https://<YOUR_DOMAIN>/email-confirmation/`

And update your local SmartHub config file (`supabase.local.json`) with the same URL.
