# Rick Wills Projects (static portfolio)

A plain, hand-written HTML portfolio: a list of projects with short descriptions, each linking to a detail page with a longer write-up and screenshots. It has no build step and no Worker code. It was served through Workers static assets as the Worker `rick-wills-portfolio` at https://rick-wills-portfolio.rick-wills.workers.dev until that Worker was deleted on 2026-11-22.

This is an older site from March 2026. The owner's main portfolio is https://www.rickwills.com (repo `Rw1942/rickwills-portfolio`, Worker `rickwills-portfolio`, note the missing hyphen), which lists most of the same projects. This site had no traffic in the 30 days before 2026-11-22, so its Worker was deleted and the repo is kept for reference until the owner archives it. Do not deploy it unless the owner asks; `npm run deploy` would recreate the Worker at the same address.

## Commands

Run from the repository root. A fresh checkout or cloud session needs `npm ci` first.

| Task | Command |
|---|---|
| Local server (http://localhost:8787) | `npm run dev` |
| Check (validate config and assets without deploying) | `npm run check` |
| Deploy to production | `npm run deploy` |

`npm run check` is the gate for every change: run it before deploying and report its result. After a deploy, open the home page, one project page and a missing path (it should return the custom 404 page).

## Layout

- `public/index.html`: the project list.
- `public/projects/<slug>.html`: one detail page per project.
- `public/screenshots/<slug>/`: screenshots per project; `README.md` there lists the folders.
- `public/styles.css`: the one stylesheet. `public/404.html`: the not-found page.

## Cloudflare

- Worker `rick-wills-portfolio` (deleted 2026-11-22) on account `3c526a82504f460f254335ac81d313dd`, which served only on workers.dev (no routes or custom domains). It is assets-only: no `main` script, no bindings and no secrets. Preview URLs are on, as they were when the config was standardized.
- `not_found_handling` is `404-page`. Requests for `/projects/<slug>.html` redirect (307) to `/projects/<slug>`, the default HTML handling for static assets.
- Agents deploy and change infrastructure directly. Wrangler (the repository's pinned copy, run through the npm scripts or `npx wrangler`) handles deploys, rollbacks and `wrangler tail`. This project uses Wrangler, so do not run `cf dev`, `cf build`, `cf deploy` or `cf migrate`.
- Cloudflare Code Mode (`cloudflare-api` MCP server) covers the rest of the account: DNS, routes and domains, Worker settings, logs and analytics, other projects, and the Cloudflare docs. Call `search` to find an endpoint, then `execute` with `account_id` set to the account ID above. Results are cut off at about 6,000 tokens, so filter inside the code.
- Both act on production. Wrangler and Code Mode read `CLOUDFLARE_API_TOKEN`. The account-wide standard, token permissions and the inventory of every project are in the `Rw1942/cloudflare-account` repo.

## Working here

- Commit to `main` and deploy with `npm run deploy` once the check passes.
- Keep the site static: plain HTML and CSS, no framework, dependency or Worker script unless the owner asks for one. Add a `main` script only for a concrete need such as a redirect.
- Commit every content change before deploying. In March 2026 a deploy went out with a Treatforce project that was never committed; it was recovered from the live site on 2026-11-22.

## Rules and reference

Rules in `.agents/rules/` hold decisions that are not visible in the code. Claude Code and Antigravity load them automatically; other agents should read the one that matches the files they are changing.

- `.agents/rules/writing-style.md`: the owner's writing rules for copy, docs, commit messages and replies.
- `.agents/rules/content.md`: how project entries, detail pages and screenshots are laid out, and the plain design.
