# Shared Project Context (Canonical)

This is the single source of truth for AI project context.

`AGENTS.md`, `CLAUDE.md`, and `.cursor/rules/*.mdc` should stay concise and reference this document instead of duplicating long instructions.

## Project Summary

- Project type: ultra-minimal personal portfolio website
- Primary content: list of completed projects
- Deployment: Cloudflare Workers Static Assets (static-first)

## Required Product Behavior

- Home/list view shows:
  - project title
  - project date
  - short description
- Each project links to a detail page with:
  - screenshots
  - additional writing

## Design Requirements

- White background
- Plain typography and layout
- Very low visual complexity
- Keep CSS and JS minimal

## Technical Constraints

- Prefer plain HTML/CSS/JS
- Keep dependencies minimal
- No database, auth, or CMS by default
- Only add serverless logic for real, explicit needs

## Content Conventions

- Use stable slugs per project
- Keep screenshots under a predictable folder per slug
- Use consistent date formatting
- Keep writing concise and practical

## Deployment Conventions

- Static assets should be the default serving path
- Keep routing straightforward (`404-page` style unless SPA is intentionally adopted)
- Avoid custom caching rules unless justified
- Agents deploy with Wrangler and reach the rest of the Cloudflare account through the Code Mode MCP server in `.mcp.json`, both using `CLOUDFLARE_API_TOKEN` (see "Cloudflare operations" in `AGENTS.md`)

## Documentation Conventions

- Keep docs beginner-friendly
- Prefer explicit examples over abstract wording
- Update `docs/dev-handoff.md` after major code changes

## Agent Sync Policy

When project behavior changes:
1. Update this file first.
2. Update `AGENTS.md`, `CLAUDE.md`, and relevant Cursor rules if needed.
3. Ensure tool-specific files remain short wrappers, not separate sources of truth.
