# FFC-EX-exceptionalridersprogram.org

Exceptional Riders Program — FFC-supported charity website (static, GitHub Pages).

This repository holds a fully localized static capture of the former WordPress site at
`exceptionalridersprogram.org`, migrated as part of the FFC Wave-1 WordPress-to-Pages program
([FFC-Cloudflare-Automation#702](https://github.com/FreeForCharity/FFC-Cloudflare-Automation/issues/702)).

## Hosting

- Deployed to GitHub Pages on the default URL:
  <https://freeforcharity.github.io/FFC-EX-exceptionalridersprogram.org/>
- Deployment runs from `.github/workflows/static.yml` on every push to `main`.
- No custom domain and no DNS changes are configured at this stage.

## Migration notes

- All CSS/JS/fonts/images are served from this repository; Google Fonts were downloaded and
  localized, and WordPress analytics/tracking beacons were stripped.
- WordPress search forms and the Divi contact form (non-functional without a backend) were
  removed; the contact page links to the charity's published email.
- Cloudflare-obfuscated email links were decoded to real `mailto:` links.
- `wp-json`, XML-RPC, oEmbed, RSS feed, and comment artifacts were stripped; dead internal
  links (uncaptured event page, origin-blocked author archives, dynamic ICS endpoints) were
  neutralized.
- The site self-identifies as a registered 501(c)(3) non-profit on its donate page; no EIN is
  published on the site, so the footer carries FFC attribution only (no fabricated status/EIN).

## CI

- `static.yml` — deploys to Pages on every push to `main`.
- `check-assets.yml` — fails if any asset loads from an external host.
- `linkcheck.yml` — lychee link check (weekly + on push/PR).

---

Supported by [Free For Charity](https://freeforcharity.org).
