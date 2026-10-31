# CarProfit Website

Static Vietnamese landing page for the CarProfit mobile application. It introduces the product, explains its main capabilities, previews six feature areas, and directs visitors to official app-store listings when those URLs are available.

## Scope

- Product introduction only: no login, backend, database, forms, analytics, or tracking.
- Six feature areas: vehicle management, home overview, trips, income/expenses, performance analytics, and investment payback.
- Separate `/terms/` and `/support/` pages linked from the footer. Terms are a draft requiring legal review; the official support contact is intentionally not fabricated and must be configured before public launch.
- Existing iOS prototype captures are used for Home and Trips. Their displayed values are sample data.
- The other four feature previews are clearly labelled illustrative layouts, not screenshots of a released app. Replace them with approved captures from the corresponding app builds when available.
- App Store and Google Play buttons remain marked "Sắp ra mắt" until their official public URLs are configured. Never use placeholder or unpublished store URLs.

## Local development

```bash
cd website
npm install
npm run dev
```

## Build checks

```bash
npm run check
npm run build
```

## Configure store links

Edit `src/data/store-links.ts` after both app listings are approved:

- `appStoreUrl`: public App Store product URL.
- `googlePlayUrl`: public Google Play product URL.

Leave a value empty while its listing is not publicly available.

## Cloudflare Pages

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Root directory | `website` |
| Build command | `npm run build` |
| Build output directory | `dist` |
| Node.js | `22.12.0` |

The site is static and does not require secrets, server functions, or environment variables.
