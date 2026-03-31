# Deploying On Cloudflare Workers (Static Assets)

## Goal

Deploy a mostly static website on Cloudflare with the option to add lightweight Worker logic later.

## Why This Approach

- Keeps hosting simple
- Serves static files globally through Cloudflare
- Leaves room for small serverless features if needed later

## Prerequisites

- Cloudflare account
- Node.js installed locally
- `wrangler` CLI available (`npx wrangler` also works)

## Deployment Model

Use Workers Static Assets with a static output directory.

Default behavior:
- If a request matches a static file, Cloudflare serves that file.
- Worker code can be added for routes that need custom logic.

## Starter Wrangler Configuration

Use `wrangler.jsonc` (or `wrangler.toml`) with an assets directory:

```jsonc
{
  "$schema": "./node_modules/wrangler/config-schema.json",
  "name": "minimal-portfolio",
  "compatibility_date": "2026-03-30",
  "assets": {
    "directory": "./public",
    "not_found_handling": "404-page"
  }
}
```

Notes:
- `directory` should point at your static site output.
- `404-page` works well for multi-page static portfolios.
- Use SPA mode only if you later move to client-side routing.

## Basic Deploy Steps

1. Build or prepare static files (if a build step exists).
2. Verify files are present in the configured assets directory.
3. Run deploy:

```bash
npx wrangler deploy
```

4. Open the deployed URL and verify:
   - list page renders
   - project links work
   - screenshots load
   - `404.html` appears for missing routes

## Caching Guidance

- Start with Cloudflare defaults.
- Avoid custom cache rules unless there is a specific need.
- If stale assets appear after deploy, purge cache and re-check.

## Keep It Minimal

Do not add Worker runtime logic unless there is a concrete requirement.
For now, the project should remain static-first and straightforward.
