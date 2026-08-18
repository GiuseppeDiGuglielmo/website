# gdg.engineer

Source for [gdg.engineer](https://gdg.engineer), the personal site of Giuseppe
Di Guglielmo.

Static site built with [Astro](https://astro.build), deployed to GitHub Pages
by GitHub Actions on every push to `main`. No client-side JavaScript, no
external requests, no tracking.

## Local development

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # static output in ./dist
npm run preview  # serve the built site
```

## Layout

- `src/data/profile.json` is the canonical source for name, title,
  affiliations, and profile links. Pages and the JSON-LD structured data all
  read from it, so edit facts here rather than in individual pages.
- `src/pages/` holds the routes, `src/layouts/Layout.astro` the shared shell
  and `<head>` metadata.
- `public/` holds static assets served as-is, including `robots.txt`,
  `llms.txt`, and the social preview image.

`plan.md` is the content and information-architecture spec the site is
built against.
