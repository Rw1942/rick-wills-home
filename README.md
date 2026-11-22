# Rick Wills Projects

A plain static portfolio: a list of projects, each with a detail page for a longer write-up and
screenshots. The HTML and CSS in `public/` are served by Cloudflare Workers static assets at
https://rick-wills-portfolio.rick-wills.workers.dev. The main portfolio is now
https://www.rickwills.com.

```sh
npm ci
npm run dev      # local server
npm run deploy   # publish public/ (needs CLOUDFLARE_API_TOKEN)
```

Coding agents start with `AGENTS.md`.
