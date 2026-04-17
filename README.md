# SmartHub Static Website (HTML only)

This folder is a pure static website. No Laravel and no build step required.

## Files

- `index.html` (professional landing page)
- `styles.css` (responsive UI styling)
- `app.js` (download metrics + redirect logic)
- `email-confirmation/index.html` (kept for auth redirect route)
- `.nojekyll`

## Download Tracking + Redirect

When users click **Download for Windows**:

1. The site increments a public counter using CountAPI.
2. It resolves the latest GitHub release.
3. It redirects users to the newest Windows installer asset (fallback: release page).

Configured in `app.js`:

- `RELEASE_OWNER`
- `RELEASE_REPO`
- `TRACKING_NAMESPACE`
- `TRACKING_KEY`

## Deploy to Cloudflare Pages

- Project type: Pages
- Connect repository: `23sc4122ms-sys/SmartHub1`
- Production branch: `main`
- Build command: `exit 0`
- Build output directory: `.`

## Supabase Redirect URL

Email confirmation is intentionally not shown on the homepage UI, but the route is available for auth redirects:

- `https://<YOUR_DOMAIN>/email-confirmation/`

Set the same URL in your SmartHub local config (`supabase.local.json`) for:

- `SMARTHUB_SUPABASE_EMAIL_REDIRECT_URL`
