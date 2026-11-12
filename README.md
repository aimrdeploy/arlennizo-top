# ARLENNIZO Worker + AMP pages

Production domain: https://arlennizo.top/
GitHub repository: https://github.com/aimrdeploy/arlennizo-top

## AMP page storage

Store standalone AMP documents in `amp/` as `<slug>.html`.
Register each slug in `amp/manifest.json`:

```json
{
  "slugs": ["panduan-menonton", "film-terbaru"]
}
```

The Worker fetches each page from GitHub raw content and serves it directly at:

- `https://arlennizo.top/panduan-menonton`
- `https://arlennizo.top/film-terbaru`

The same manifest supplies AMP URLs to `https://arlennizo.top/sitemap.xml`.

## Requirements for each AMP document

- Include the AMP runtime and required AMP boilerplate.
- Include a canonical URL pointing to `https://arlennizo.top/<slug>`.
- Keep the filename and manifest slug identical.
- Do not include a leading slash or `.html` in manifest slugs.

Changes to GitHub raw files may take up to about 5 minutes to appear because the Worker caches GitHub responses.
