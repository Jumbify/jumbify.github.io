# Jumbify Website

Small static placeholder site for `jumbify.com`.

## Hosting

The site deploys to the `jumbify` Vercel project in `noah-skinner-s-projects`.
It is plain HTML/CSS: use the Other framework preset with no install or build
command and serve the repository root. A Pro plan is required for commercial use.

To link a fresh checkout and deploy:

```sh
vercel link --yes --project jumbify --scope noah-skinner-s-projects
vercel deploy --prod --scope noah-skinner-s-projects
```

Keep the existing DNS records until the Vercel deployment and domain settings
are verified. Change only the website records at cutover; preserve mail records
and other subdomains, including `games.jumbify.com`.

Vercel's domain API recommended these records when migration was prepared:

| Type | Host | Value |
| --- | --- | --- |
| A | `@` | `216.198.79.1` |
| A | `@` | `64.29.17.1` |
| CNAME | `www` | `5ec25e487de64fe7.vercel-dns-017.com` |

At cutover, replace the four GitHub Pages apex A records (`185.199.108.153`
through `185.199.111.153`) and the existing `www` CNAME. Keep the current
nameservers. `www.jumbify.com` is configured to redirect to `jumbify.com`.
Recheck the Vercel domain settings before using these values at a later date.

`CNAME` preserves the GitHub Pages fallback during the migration and is excluded
from Vercel uploads. The storefront source for `/beta` has not been added yet.

## Files

- `index.html` - the live page.
- `assets/css/jumbify.css` - all site styling.
- `images/logo.svg` - favicon/brand mark.
- `CNAME` - GitHub Pages custom domain during migration.

## Local Preview

Open `index.html` directly, or run a simple static server:

```sh
python3 -m http.server 8000
```
