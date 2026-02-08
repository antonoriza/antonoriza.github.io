# Juan Antonio Oriza – Personal site

Personal blog and site, built with [Hugo](https://gohugo.io) and the HateIt theme.

## Folder structure

- **`content/`** – Your writing (posts and about). Edit only this when you add or change articles.
- **`site/`** – Theme, config, static assets, and Hugo setup. Change only when tweaking design or site settings.

## Run locally

```bash
# From repo root
hugo -s site server
```

Then open http://localhost:1313

## New post

```bash
hugo -s site new posts/your-post-name/index.en.md
```

Edit the new file in `content/posts/your-post-name/`. Add `index.es.md` for the Spanish version.

## Deploy

Push to `main`; GitHub Actions builds and deploys to GitHub Pages.
