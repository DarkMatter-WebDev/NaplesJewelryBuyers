# Deploy notes — complete site snapshot (September 2026)

`staging/` is now the ENTIRE deployable site, not just the changed files. The
previous deploy replaced the repo root with only the changed files, so
`sunscroll.js`, `logo.webp`, `og-image.png`, `seo.css`, and `robots.txt` went
missing on production (black background, broken logo, unstyled service pages).
Dragging this whole snapshot in restores everything.

## Steps

1. Open the repo folder in Explorer (GitHub Desktop → Repository → Show in Explorer).
2. Select EVERYTHING inside `staging/` EXCEPT this `README-DEPLOY.md`, and drag it
   onto the repo root. When Windows asks, choose **Replace the files in the
   destination** (and merge folders).
3. In the repo root, DELETE these if present (they should not be public):
   - `README-DEPLOY.md` (was pushed by mistake last time)
   - `debug-9e641e.log`, `tablet_debug.png`
4. Confirm the repo root now contains exactly:

   Files (10): `index.html`, `404.html`, `sitemap.xml`, `robots.txt`,
   `netlify.toml`, `seo.css`, `sunscroll.js`, `logo.webp`, `og-image.png`,
   `SEO-PLAN.md`

   Folders (10): `accessibility/`, `privacy/`, `terms/`, `sell-gold-naples/`,
   `sell-silver-naples/`, `sell-jewelry-naples/`, `sell-coins-naples/`,
   `sell-diamonds-naples/`, `sell-watches-naples/`, `estate-jewelry-buyer-naples/`

   (`.git`, `.gitignore`, or Netlify-specific files that were already in the repo
   are fine to leave.)
5. GitHub Desktop → commit → push. Netlify rebuilds in about a minute.

## Commit message suggestion

    Restore site assets; re-frame hero (visible H1, trust pills, how-it-works steps) and move photo estimate to its own section

## After Netlify finishes

- `https://naplesjewelrybuyers.com/sunscroll.js` and `/logo.webp` return 200
  (background + logo are back), `/seo.css` returns 200 (service pages styled).
- `/README-DEPLOY.md`, `/SEO-PLAN.md`, `/debug-9e641e.log` return 404.
- Netlify → Forms still lists `jewelry-photo-estimate`.
- Search Console: resubmit `sitemap.xml`; request indexing for `/` and the seven
  service pages.
