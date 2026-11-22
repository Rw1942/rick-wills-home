# Minimal Portfolio Website

This project is a super simple, ultra-minimal portfolio website.

It is intentionally plain:
- white background
- default text styling
- minimal CSS
- minimal JavaScript

The site will list projects and allow visitors to open a detail page for each project to view screenshots and additional writing.

## Core Project Goals

- Show a list of projects with:
  - project title
  - project date
  - short description
- Allow click-through to a project detail page
- Display screenshots and longer notes on the detail page
- Keep everything easy to maintain for a beginner

## Deployment Target

The site is deployed on Cloudflare using Workers Static Assets (static-first approach).

The Worker runtime is available for future needs, but the default approach is static files first and minimal logic.

## Documentation Map

- `docs/product-brief.md`: product requirements and non-goals
- `docs/architecture.md`: technical architecture and constraints
- `docs/content-model.md`: how project content and screenshots are organized
- `docs/deployment/cloudflare-workers.md`: deployment workflow
- `docs/ai/project-context.md`: canonical AI context for Cursor, Claude, and Codex
- `docs/dev-handoff.md`: handoff template and update process after major changes

## AI Instruction Files

- `AGENTS.md`: OpenAI Codex guidance
- `CLAUDE.md`: Claude Code guidance
- `.cursor/rules/*.mdc`: Cursor project rules
- `.claude/settings.json` and `.mcp.json`: Claude Code permissions and the Cloudflare MCP server (see "Cloudflare operations" in `AGENTS.md`)

All tool-specific files point back to `docs/ai/project-context.md` to stay in sync.
