# Tesla Fleet API — GitHub Pages hosting

Personal setup for read-only odometer checks on two Tesla Model Y cars.
The domain is `https://yo-da-man.github.io`.

## What's in this repo

- `.nojekyll` — tells GitHub Pages to serve files as-is, so the
  `.well-known` folder is published.
- `.well-known/appspecific/com.tesla.3p.public-key.pem` — the app's PUBLIC
  key, which Tesla fetches when the partner account is registered.
- `callback.html` — the OAuth redirect page. After signing in on Tesla,
  Tesla sends you back here with `?code=...` in the URL and the page shows
  the code so it can be pasted to Baxter.
- `index.html` — a plain landing page.

The PRIVATE key is NOT in this repo. It stays on Baxter's machine and is
used to sign API requests. Never commit it here.

## Setup

1. On GitHub, create a new public repository named exactly
   `yo-da-man.github.io`.
2. Upload everything in this folder to the repo's main branch (drag and
   drop works in the GitHub web UI).
3. In the repo, go to Settings → Pages → Build and deployment → Source:
   "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
4. Wait a minute, then check these load:
   - https://yo-da-man.github.io/
   - https://yo-da-man.github.io/.well-known/appspecific/com.tesla.3p.public-key.pem
   - https://yo-da-man.github.io/callback.html

## Tesla developer form values

- Allowed Origin URL: `https://yo-da-man.github.io`
- Allowed Redirect URI: `https://yo-da-man.github.io/callback.html`
- Allowed Returned URL: (leave blank)
