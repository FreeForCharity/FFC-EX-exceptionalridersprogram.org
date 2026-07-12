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

## Structure

Plain static HTML capture — no build step. All CSS/JS/fonts/images are served from this
repository; external font hosts (Google Fonts) were downloaded and localized, and WordPress
analytics/tracking beacons were stripped during migration.

## Migration notes

- WordPress search forms and the Divi contact form (both non-functional without a backend)
  were removed; the contact page now links directly to the charity's published email.
- `wp-json`, XML-RPC, oEmbed, RSS feed, and comment artifacts were stripped.
- The site self-identifies as a registered 501(c)(3) non-profit on its donate page; no EIN is
  published on the site, so the footer carries FFC attribution only (no fabricated status/EIN line).

## Maintenance

- Edit the HTML in place; every push to `main` redeploys.
- `linkcheck.yml` runs lychee weekly and on pushes/PRs to catch link rot.
- `check-assets.yml` fails CI if any asset is loaded from an external host.
- See the migration tracking issue in this repo for what was captured, stripped, and flagged.

---

Supported by [Free For Charity](https://freeforcharity.org).
