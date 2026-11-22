---
trigger: glob
globs: "public/**"
paths:
  - "public/**"
---

# Site content and design

The site is a plain list of projects, each linking to a detail page with a longer write-up and screenshots.

## Adding or changing a project

- Each project has a stable slug used in three places: the list entry in `public/index.html`, its page `public/projects/<slug>.html`, and its screenshots in `public/screenshots/<slug>/` (add the folder to `public/screenshots/README.md`).
- A list entry has the title linked to the detail page, the date in a `<p class="meta">` line and a description of one or two sentences.
- A detail page has the title, the same date, the longer write-up, a "Screenshots" section and the "Back to all projects" link. Copy an existing page so the markup stays the same.
- Dates are `YYYY-MM` everywhere; do not mix formats.
- Screenshots get alt text that says what the image shows. A project without images keeps the `screenshot-placeholder` box.

## Design

- White background, default typography and the small shared stylesheet in `public/styles.css`. No frameworks, build step, client-side JavaScript, animation or decorative effects unless the owner asks.
- Write descriptions in plain language: short, concrete, no marketing tone.
