# Screenshot upload folders

Add project images into these folders:

- `/public/screenshots/email2chatgpt/`
- `/public/screenshots/commercial-loan-pricing-profitability/`
- `/public/screenshots/salessurfer/`
- `/public/screenshots/ws3910-weather-dashboard/`
- `/public/screenshots/sankeyfi/`
- `/public/screenshots/easyextract/`
- `/public/screenshots/historical-price-tracker/`

Recommended naming:

- `image-01.png`
- `image-02.png`

Then show the image on the project page (for example
`/public/projects/sankeyfi.html`). Each page has a ready-to-copy example
in an HTML comment under the "Screenshots" heading:

```html
<figure>
  <img src="/screenshots/sankeyfi/image-01.png"
       alt="Sankey chart built from a sample CSV file">
  <figcaption>Optional short caption.</figcaption>
</figure>
```

Remove the "Screenshots coming soon." line once a page has real images.
Always write alt text that says what the screenshot shows.
