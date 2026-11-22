# AGENTS.md

Use `docs/ai/project-context.md` as the canonical project context.

## Project Direction

- Build and maintain an ultra-minimal portfolio website.
- Keep design plain: white background, default text style, minimal layout.
- Keep implementation simple and static-first.

## Source Of Truth

- Canonical context: `docs/ai/project-context.md`
- Product details: `docs/product-brief.md`
- Architecture and constraints: `docs/architecture.md`
- Content structure: `docs/content-model.md`
- Deployment steps: `docs/deployment/cloudflare-workers.md`

## Working Rules

- Prefer plain HTML/CSS/JS unless explicitly asked otherwise.
- Avoid adding dependencies or complexity without clear value.
- Do not introduce Worker runtime logic unless required.
- Preserve clear, beginner-friendly documentation.
- After major code changes, update `docs/dev-handoff.md`.

## Cloudflare operations

Agents deploy and change infrastructure directly. Two tools cover it, and both authenticate with the `CLOUDFLARE_API_TOKEN` environment variable for account `3c526a82504f460f254335ac81d313dd`:

- **Wrangler** (`npx wrangler`) for anything tied to `wrangler.jsonc`: deploys, versions and rollback, D1 migrations and queries, secrets, and `wrangler tail`. The repo has no package.json scripts, so `npx wrangler deploy` publishes `public/` as the `rick-wills-portfolio` Worker.
- **Cloudflare Code Mode MCP** (`cloudflare-api` in `.mcp.json`) for the rest of the account: DNS, routes and custom domains, zone and Worker settings, analytics, other Workers and their resources, and the Cloudflare docs. Call `search` to find the endpoint, then `execute` with `account_id` set to the account ID above. `docs` searches the developer docs. Results are cut off at about 6,000 tokens, so filter inside the code instead of returning whole lists.

Both act on production; `wrangler.jsonc` defines no staging environment. `.claude/settings.json` allows these tools without prompts and still asks before a force push or deleting a Worker, database, bucket or namespace. Account-wide setup, token permissions and the inventory of every project are in the `Rw1942/cloudflare-account` repo, `docs/agent-setup.md`.
