# CarProfit Website

Static Vietnamese landing page for the CarProfit mobile application. The site introduces the product, explains its main capabilities, previews six feature areas, and directs visitors to official app-store listings when those URLs are available.

## Scope

- Product introduction only: no login, backend, database, forms, analytics, or tracking.
- Six feature areas: vehicle management, home overview, trips, income/expenses, performance analytics, and investment payback.
- Separate pages: `/terms/`, `/privacy/`, `/support/`, and `/delete-account/`.
- Existing iOS prototype captures are used for Home and Trips. Their displayed values are sample data.
- Other feature previews are illustrative layouts, not screenshots of a released app. Replace them with approved captures from the corresponding app builds when available.
- App Store and Google Play buttons remain marked "Sắp ra mắt" until their official public URLs are configured. Never use placeholder or unpublished store URLs.
- Legal and account-deletion pages are drafts and must be checked against the actual production app, Firebase configuration, data-retention process, and applicable requirements before public launch.

## Requirements

- Node.js `22.12.0` or newer.
- npm (lockfile is committed; use `npm ci` for reproducible installs).

## Local development

Run from the repository root:

```bash
npm ci
npm run dev
```

## Build checks

```bash
npm run check
npm run build
npm run preview
```

## Configure store links

Edit `src/data/store-links.ts` after the app listings are approved:

- `appStoreUrl`: public App Store product URL.
- `googlePlayUrl`: public Google Play product URL.

Leave a value empty while its listing is not publicly available.

## Cloudflare Pages

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Root directory | `/` (repository root; leave blank if the dashboard treats blank as root) |
| Build command | `npm run build` |
| Build output directory | `dist` |
| Node.js version | `22.12.0` |

The site is static and does not require secrets, server functions, or environment variables. Do not commit `node_modules/`, `dist/`, local environment files, or OS metadata.
