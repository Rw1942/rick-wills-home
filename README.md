# Rick Wills Projects

A plain static portfolio: a list of projects, each with a detail page for a longer write-up and
screenshots. The HTML and CSS in `public/` used to be served by Cloudflare Workers static assets at
https://rick-wills-portfolio.rick-wills.workers.dev. That Worker was deleted on 2026-11-22
because https://www.rickwills.com replaced this site; the repo is kept for reference.

```sh
npm ci
npm run dev      # local server
npm run deploy   # recreates the Worker; only if the owner asks
```

Coding agents start with `AGENTS.md`.
