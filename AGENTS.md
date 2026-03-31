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
