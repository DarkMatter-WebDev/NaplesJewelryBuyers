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

   Files (11): `index.html`, `404.html`, `sitemap.xml`, `robots.txt`,
   `netlify.toml`, `seo.css`, `sunscroll.js`, `logo.webp`, `nej-mark.webp`,
   `og-image.png`, `SEO-PLAN.md`

   ⚠️ `nej-mark.webp` is NEW (2026-09-23) — the Naples Estate Jewelry octopus
   mark used by BOTH the nav lockup and the hero wordmark. If it does not
   travel, the top-left corner and the hero both show a broken image.

   ℹ️ `logo.webp` (the old gold "NAPLES JEWELRY BUYERS" crest, 162 KB) is now
   referenced by NOTHING — the hero sets its wordmark in type instead. It is
   kept in the repo deliberately: no page loads it, so it costs nothing, and
   it is the only copy of that artwork. Delete it only on the owner's say-so.

   Folders (10): `accessibility/`, `privacy/`, `terms/`, `sell-gold-naples/`,
   `sell-silver-naples/`, `sell-jewelry-naples/`, `sell-coins-naples/`,
   `sell-diamonds-naples/`, `sell-watches-naples/`, `estate-jewelry-buyer-naples/`

   (`.git`, `.gitignore`, or Netlify-specific files that were already in the repo
   are fine to leave.)
5. GitHub Desktop → commit → push. Netlify rebuilds in about a minute.

## Commit message suggestion

    Lead the brand lockup with Naples Estate Jewelry; keep Naples Jewelry Buyers as the descriptor; fix dead schema logo URL

## Why this change (2026-09-23)

A different company owns an exact-match **"Naples Jewelry Buyers"** Google
Business Profile (5.0★ / 49 reviews, 11542 Tamiami Trl E, (239) 420-1918,
`naplesjewelrybuyersllc.com`). Searching that name on Google Maps goes straight
to them — we do not appear at all. Anyone who read this site, remembered the
name and looked it up later was being handed to a competitor.

So the page now teaches the name that resolves to OUR profile. ⛔ Do not flip
these back:

- nav lockup → octopus mark + "Naples **Estate Jewelry**", with "Jewelry
  Buyers" as the small descriptor beneath
- hero → the gold "NAPLES JEWELRY BUYERS" crest image is GONE, replaced by a
  typeset wordmark: octopus mark, "NAPLES" in **Cinzel 900** with a metallic
  gold gradient (`background-clip: text`, with a flat-gold `@supports`
  fallback), then a hairline rule flanking letterspaced "ESTATE JEWELRY".
  Cinzel was already being downloaded by this page and used nowhere, so this
  costs no extra request and no image. Sizes are `clamp()`-based, so it is
  sharp on any screen; measured with no horizontal overflow at 1243 / 375 /
  320 px, and the ≤380 px rule tightens the tracking so the flanking rules
  stay readable
- trust pill → "★ 5.0 — Naples Estate Jewelry on Google" (same link as before,
  `cid=17050430560749692864`, which is our real GBP)
- footer → "Naples Estate Jewelry" primary, "Naples Jewelry Buyers" as the
  descriptor line; same flip on all 10 sub-page footers
- schema `logo` → `branding/nav-logo.webp` (the old `branding/logo.webp` was
  deleted from naplesestatejewelry.com on 2026-09-01 and had been returning 404)

⛔ Deliberately NOT changed, because they hold the #1 organic ranking for
"naples jewelry buyers": the domain, every `<title>`, the H1, body copy, URLs,
canonicals, and the schema `name`/`alternateName` (already correct — `name` is
"Naples Estate Jewelry", `alternateName` includes "Naples Jewelry Buyers",
sharing one `@id` with the main site).

## After Netlify finishes

- `https://naplesjewelrybuyers.com/nej-mark.webp` returns 200 (nav mark) — NEW.
- `/sunscroll.js` and `/logo.webp` return 200 (background + crest), `/seo.css`
  returns 200 (service pages styled).
- `/README-DEPLOY.md`, `/SEO-PLAN.md`, `/debug-9e641e.log` return 404.
- Netlify → Forms still lists `jewelry-photo-estimate`.
- The nav reads "Naples Estate Jewelry / JEWELRY BUYERS" on desktop and phone,
  with no broken image; the hero reads octopus / NAPLES / ESTATE JEWELRY, the
  "NAPLES" in gradient gold (not flat) on Chrome, Safari and Firefox.
- `/logo.webp` still returns 200 but nothing requests it any more — that is
  expected, not a regression.
- Search Console: no reindex needed — titles and copy are unchanged. Watch that
  the `/` position for "naples jewelry buyers" stays at ~1 over the next 2 weeks.
