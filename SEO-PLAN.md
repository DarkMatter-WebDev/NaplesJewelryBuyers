# Naples Jewelry Buyers SEO plan

## Completed in this update

- Added indexable pages for the highest-intent service searches: sell gold, sell silver, sell jewelry, sell coins, sell diamonds, sell watches, and estate jewelry buyer in Naples.
- Added unique page titles, meta descriptions, canonical URLs, local service schema, internal links, an XML sitemap, and robots.txt.
- Strengthened the home page’s primary topic and added FAQ structured data.
- Removed unverified superlative/licensing claims. Only use claims such as “#1,” “most trusted,” or “licensed” when they can be documented.

## Launch checklist (do immediately after deployment)

1. Confirm the eight indexable URLs return `200`, redirect HTTP and non-canonical hostname variants to `https://naplesjewelrybuyers.com/`, and submit the sitemap in Google Search Console and Bing Webmaster Tools.
2. Verify the sitemap and every page with Google Search Console URL Inspection. Request indexing for the home page and each new service page.
3. Connect Google Search Console and analytics/call tracking so calls, photo submissions, and organic search queries can be measured.
4. Domain model (decided September 2026): `naplesestatejewelry.com` is the primary domain and the only website listed on the Google Business Profile. `naplesgoldbuyers.com` and `naplesjewelrybuyers.com` are satellite lead-capture sites for the same business. All three declare the same schema entity (`@id https://naplesestatejewelry.com/#business`) with identical name, address, phone, hours, and social profiles, and each satellite links to the showroom, shop, trade-in, city, and Spanish pages on the primary domain. Keep the satellites' copy distinct from each other (no shared card/FAQ/CTA text). Trade-off: link equity is split across three domains, so do not add further satellite domains.

## Google Business Profile: highest local-pack priority

1. Claim and verify one profile that accurately represents the business: Naples Estate Jewelry, 6240 Shirley St, Ste 104, Naples, FL 34109, (239) 404-8505, website https://naplesestatejewelry.com, hours Mon–Fri 11–3 and Sat 11–4, plus the Collier/Lee service area for home visits. Do not create separate profiles for "Naples Gold Buyers" or "Naples Jewelry Buyers", and do not keyword-stuff the business name.
2. Use the most accurate primary category available, then relevant secondary categories only. Add every accepted service, a clear business description, appointment details, and original photos of the team, evaluations, inventory, exterior/signage if applicable, and completed transactions where customers permit it.
3. Ask every completed customer for an honest Google review using a direct review link. Never offer incentives or selectively solicit only positive reviews. Reply to every review promptly and professionally.
4. Publish one useful, original update or offer each month and keep special hours current.

## Authority and content (next 90 days)

- Create one genuinely helpful local guide per month, starting with: “How to sell inherited jewelry in Naples,” “Sterling silver vs. silver plate: what to look for,” and “How gold jewelry is evaluated.” Each guide should include original photos, bylined expertise, and links to the relevant service page.
- Earn citations and links from legitimate local organizations and directories where the business can be accurately listed: Naples Chamber/community groups, estate-sale and probate professionals, local media, relevant jewelers/auction partners, BBB, and major map/data platforms. Never buy links or publish thin city-page clones.
- Ensure the business name, phone, website, service area, and hours match exactly across Google, Apple Maps, Bing Places, Yelp, BBB, and high-quality local directories.
- Add authentic staff expertise, business history, credentials, policies, and customer testimonials only where written permission is available. Do not add review or rating schema unless reviews are actually collected and displayed on this site.

## Measurement

- Each month, record Search Console impressions, clicks, average position, page-level queries, calls, photo-form submissions, Google Business Profile calls/directions, review count, and referring domains.
- Review the data every 30 days. Improve the page that earns impressions but has low clicks first; add content only for real customer questions that the data or conversations reveal.

## Do not do

- Do not promise or pay for a guaranteed #1 rank. Local visibility is driven by relevance, distance, and prominence, and rankings vary by searcher location.
- Do not create near-identical pages for every nearby city, use fake addresses, publish fake reviews, stuff keywords, or use misleading “best/top/#1” claims.

## September 2026 update — satellite consolidation

- The home page and all seven service pages now declare the Naples Estate Jewelry business entity (shared `@id`, full address, geo, hours, email, socials) instead of a separate, address-less "Naples Jewelry Buyers" business.
- Added the showroom (address, hours, directions), shop, trade-in, free-evaluation, city, and Spanish links throughout; fixed the `.co` store links; removed unverifiable claims from visible copy and matched the visible FAQ text to the FAQ schema word for word.
- Legal pages name Naples Estate Jewelry as the operator; the form's consent version is now 2026-09-01.
- Added `/shop`, `/showroom`, `/directions`, and `/es` convenience redirects in `netlify.toml`; force-404 rules for internal files (`SEO-PLAN.md`, `README-DEPLOY.md`, dev utilities); removed publicly served debug files from the site root.
- Hero re-framed to match naplesgoldbuyers.com: visible H1 ("Sell Jewelry, Diamonds, Gold & Silver in Naples, Florida"), trust pills, a 3-step "how it works", two CTAs (Call/Text, Get a Photo Estimate), then the shop/trade-in cross-sell. The photo submission form moved out of the hero into its own `#get-estimate` section (after What We Buy). In-page ids must not start with "s" — `sunscroll.js` hijacks `a[href^="#s"]` clicks.
- Deployed 2026-09-01. Post-deploy checks: all 18 served files byte-match the source, root assets 200, blocked files 404, redirects correct, WebGL background and form verified live.

### Deploy process (lesson from 2026-09-01)

The working folder is not the repo. Changes go into a `staging/` folder that must be a COMPLETE snapshot of the site (10 root files + 10 folders), which is dragged into the GitHub-Desktop repo root with "Replace". The first deploy staged only changed files, the repo root was replaced, and `sunscroll.js`/`logo.webp`/`og-image.png`/`seo.css`/`robots.txt` vanished from production for a short time. See `staging/README-DEPLOY.md`.

### Search engines (done 2026-09-01)

- Google Search Console (domain property): sitemap resubmitted — Success, 8 pages. Coverage: 8 indexed; the 10 "not indexed" are intentional (7 redirect variants, 3 `noindex` legal pages). **Outstanding:** "Request indexing" for `/` and the seven service pages was blocked by the daily quota ("Quota Exceeded") — retry on a later day. Google will recrawl from the sitemap regardless (every URL carries the new `lastmod`).
- Bing Webmaster Tools: sitemap resubmitted (Processing) and all 8 pages submitted through URL Submission (Success).

### Off-site follow-ups
- Confirm showroom hours (Mon–Fri 11–3, Sat 11–4) are current on this site, the Google Business Profile, and Apple Maps, Bing Places, Yelp, Facebook, and Instagram.
- Align naplesgoldbuyers.com's schema `geo` and `paymentAccepted` values to the main site's (they currently differ slightly).
- Watch Search Console for 30 days: the home page title now leads with "Sell Jewelry" rather than "Sell Gold", so some "sell gold naples" impressions may shift to naplesgoldbuyers.com. That is intended.
