# Developer Handoff

## Purpose

Track major code and documentation changes so the next session (human or AI) can continue quickly and safely.

## Update Rule

After every major code change, update this file in the same working session.

A major change includes:
- new features
- architecture or deployment changes
- content model changes
- any change affecting project behavior

## Current Baseline

- Project initialized as an ultra-minimal portfolio documentation setup.
- Hosting direction set to Cloudflare Workers Static Assets (static-first).
- Shared AI context established in `docs/ai/project-context.md`.
- Tool-specific instruction files added (`AGENTS.md`, `CLAUDE.md`, `.cursor/rules/*.mdc`).

## Date
- 2026-03-30

## Change Summary
- Built the first static version of the portfolio website in `public/` with a homepage, project detail pages, and a custom `404.html`.
- Added initial content for seven projects provided by the user, with per-project screenshot placeholders and stable slug-based paths.
- Added a shared stylesheet that keeps the site intentionally plain, white-background, and easy to maintain.
- Added `wrangler.jsonc` for Workers Static Assets deployment and deployed the site to Cloudflare.

## Files Updated
- `public/index.html`
- `public/styles.css`
- `public/404.html`
- `public/projects/email2chatgpt.html`
- `public/projects/commercial-loan-pricing-profitability.html`
- `public/projects/salessurfer.html`
- `public/projects/ws3910-weather-dashboard.html`
- `public/projects/sankeyfi.html`
- `public/projects/easyextract.html`
- `public/projects/historical-price-tracker.html`
- `public/screenshots/README.md`
- `wrangler.jsonc`
- `docs/dev-handoff.md`

## Validation Performed
- Verified file structure and content creation in the workspace.
- Confirmed project list page links to each detail page using stable static routes.
- Ran `npx wrangler --version`, `npx wrangler check`, and `npx wrangler deploy`.
- Deployment URL: `https://rick-wills-portfolio.rick-wills.workers.dev`

## Follow-Ups
- Replace screenshot placeholders with real uploaded images and add `<img>` tags on each project detail page. (Placeholders reworked on 2026-09-26; see below.)
- Decide whether to keep this as the final production Worker name or rename before wider sharing.

## Date
- 2026-09-26

## Change Summary
- Made the site easier to read: centered 680px column, system font, clearer link and focus styles. Still white and plain.
- Added a "Rick Wills" site header on every page and a "← All projects" link at the top of each detail page.
- Rewrote the home intro so it describes the projects instead of the site.
- Dates now show as words (`March 2026`) inside `<time datetime="2026-03">` tags.
- Home list shows a "Live site" link for projects that have one (Sankeyfi, easyextract).
- Removed the developer note ("Add images in: /public/screenshots/...") that visitors could see. Detail pages now say "Screenshots coming soon." and have a ready-to-copy `<figure>` example in an HTML comment.
- Links now use short URLs (`/projects/sankeyfi`), which Cloudflare serves directly. Old `.html` links still work because Cloudflare redirects them.
- Added `favicon.svg`, plus description and Open Graph tags so shared links show a proper title and summary.

## Files Updated
- `public/index.html`, `public/404.html`, `public/projects/*.html`
- `public/styles.css`
- `public/favicon.svg` (new)
- `public/screenshots/README.md`
- `docs/content-model.md`, `docs/deployment/cloudflare-workers.md`, `docs/dev-handoff.md`

## Validation Performed
- Ran `npx wrangler dev` and checked with `curl`: `/`, `/projects/sankeyfi`, and `/favicon.svg` return 200; `/projects/sankeyfi.html` returns 307 to `/projects/sankeyfi`; a missing page returns 404.
- Took Playwright screenshots at 1280px and 390px widths: the layout looks right and nothing scrolls sideways.

## Follow-Ups
- Add real screenshots (see `public/screenshots/README.md`).
- Consider adding contact links (email, GitHub, LinkedIn) to the home page.
- Add live links for the other projects if they are public.

## Handoff Template (Copy For Future Updates)

## Date
- YYYY-MM-DD

## Change Summary
- What changed
- Why it changed

## Files Updated
- `path/to/file`

## Validation Performed
- Commands run
- Manual checks completed

## Follow-Ups
- Remaining work
- Known risks or open questions
