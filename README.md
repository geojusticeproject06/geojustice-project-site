# The GeoJustice Project & The GeoJustice Institute — Websites

Two linked single-file sites, repositioned per the latest brand decision:

- **The GeoJustice Project** (`project/index.html`) — the for-profit software
  development company. New slogan: **"Equity Software Matters."** Leads with
  the GeoJustice Decision Platform (product-first), with advisory/consulting
  services positioned as secondary — work that funds the roadmap and gets
  agencies platform-ready, not the core identity.
- **The GeoJustice Institute** (`institute/index.html`) — the nonprofit
  education affiliate. Now carries the original slogan: **"Mapping Equity
  Matters."** Leads with the Skyway Tech Program as the flagship, with GIS
  education for youth (12–24), communities, and organizations.

Each site's footer and a dedicated "affiliate" section cross-link to the
other via a relative path (`../institute/index.html` and
`../project/index.html`), so keep both folders alongside each other in
whatever repo or hosting root you deploy from.

## Design

**Project** — deep ink/paper palette (`#0E1720` / `#F1F3F0`) with amber and
teal accents, JetBrains Mono for headlines/data chrome, Inter for body text.
A coordinate-grid backdrop and spec-sheet-style module list (not rounded
SaaS cards) carry the "software company" identity. The hero's live
"Scenario Studio" demo re-ranks six real Atlanta pilot sites as you drag the
equity-weight slider — the same mechanic as the Need Score / Suitability
Score weighting inside the actual platform.

**Institute** — warm parchment palette (`#F6EFDD` / `#17140F`) with brick
red, forest green, and ochre drawn from the Pan-African / Marcus Garvey
palette, Spectral serif for headlines, Public Sans for body. The flagship
Skyway Tech Program gets a dedicated featured block rather than sitting in
the general program grid.

## What's interactive right now (no backend needed)

- **Project site:** the Scenario Studio slider (pure client-side JS) and
  the "Ask GeoJustice" assistant — a canned FAQ bot (client-side keyword
  matching, no API key, no server function). It answers questions about the
  platform, roadmap, pricing, founder, and the Institute, and routes
  anything else to the contact form.
- **Both sites:** the contact form is Netlify Forms-ready
  (`data-netlify="true"`) — submissions land in your Netlify dashboard with
  no extra setup once deployed there. In this preview / on `file://`, it
  shows a local confirmation instead of submitting.

## Upgrading the assistant to a live AI backend (optional)

The canned FAQ bot deploys with zero setup, but if you want it answering
open-ended questions the way the earlier prototype did, that needs a
Netlify serverless function (`netlify/functions/chat.js`) proxying to the
Anthropic API, with `ANTHROPIC_API_KEY` set under Site settings →
Environment variables in Netlify, so the key never reaches the browser.
Say the word and I'll wire that back in.

## Deploying

Same path you've already walked for GoDaddy + Netlify:
1. Push this folder to a GitHub repo, connect it in Netlify.
2. Decide on structure — either two Netlify sites (one per folder, on
   subdomains like `app.geojustice.org` / `geojustice.org`), or one site
   with both folders served at `/project` and `/institute` — and update the
   cross-links if you change the paths.
3. Point your GoDaddy domain(s) at Netlify: custom domain → nameservers →
   DNS propagation (dnschecker.org) → SSL provisioning.

## Still open

- Real photography/logo assets aren't included — both sites currently use
  SVG marks and color blocks in their place.
- The Institute's 501(c)(3) EIN / donation processor isn't wired up — the
  "Donate" path currently routes to the contact form.
