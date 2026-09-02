# Deploy notes — September 2026 satellite-site update

Everything in this folder mirrors the repo layout. Drag the contents of `staging/`
(NOT this README) into the root of the Netlify-connected repo, overwriting the
existing files, then commit and push in GitHub Desktop.

## Files to drag in (15 — all overwrite existing files)

Root:
- `index.html`
- `404.html`
- `sitemap.xml`
- `netlify.toml`
- `SEO-PLAN.md`

Folders (each contains one `index.html` — drop the folder onto the repo root and
choose "replace"):
- `accessibility/`
- `privacy/`
- `terms/`
- `sell-gold-naples/`
- `sell-silver-naples/`
- `sell-jewelry-naples/`
- `sell-coins-naples/`
- `sell-diamonds-naples/`
- `sell-watches-naples/`
- `estate-jewelry-buyer-naples/`

## Files to DELETE from the repo (2)

These are debug artifacts that are currently served publicly from the live site:
- `debug-9e641e.log`
- `tablet_debug.png`

## Files NOT changed (leave them as they are)

`seo.css`, `sunscroll.js`, `robots.txt`, `logo.webp`, `og-image.png`,
`logo-animated.html`, `og-image-generator.html`

## Commit message suggestion

    Frame site as a satellite of Naples Estate Jewelry: shared schema entity, showroom address/hours, funnel links, copy de-dup, legal operator wording, redirects

## After Netlify finishes building

1. Netlify → Forms: `jewelry-photo-estimate` should still be listed.
2. Spot-check: `/shop` redirects to the main shop, `/debug-9e641e.log` and
   `/SEO-PLAN.md` return 404.
3. Search Console (property already exists): Sitemaps → resubmit `sitemap.xml`;
   URL Inspection → Request indexing for `/` and the seven `sell-*` /
   `estate-jewelry-buyer-naples/` pages.
