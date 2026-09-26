# Content Model

## Purpose

Define a simple, stable structure for project entries and screenshots.

## Project Fields

Each project must include:
- `slug`: URL-safe unique ID (example: `weather-dashboard`)
- `title`: human-readable project name
- `date`: when the project was completed
- `description`: short summary for list page
- `details`: longer write-up for detail page
- `screenshots`: list of image paths

## Recommended Data Shape

```json
{
  "slug": "weather-dashboard",
  "title": "Weather Dashboard",
  "date": "2025-11",
  "description": "Small dashboard for hourly weather checks.",
  "details": "Longer write-up about scope, decisions, and outcomes.",
  "screenshots": [
    "/screenshots/weather-dashboard/overview.png",
    "/screenshots/weather-dashboard/detail.png"
  ]
}
```

## Screenshot Folder Convention

Use one folder per project slug:

```text
public/screenshots/<slug>/
```

Examples:
- `public/screenshots/weather-dashboard/overview.png`
- `public/screenshots/weather-dashboard/detail.png`

## Writing Guidelines

- Keep list-page descriptions to 1-2 concise sentences
- Keep detail-page writing practical and specific
- Avoid marketing language
- Prefer plain language over jargon

## Date Format

Use one format consistently across all projects:
- `YYYY-MM` (recommended), or
- `YYYY-MM-DD` if day precision matters

Do not mix date formats within the same site.

On the pages, show the date in words and keep the machine-readable
`YYYY-MM` value in a `<time>` tag:

```html
<time datetime="2026-03">March 2026</time>
```
