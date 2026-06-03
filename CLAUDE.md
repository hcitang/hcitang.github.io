# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Tony Tang's personal academic website (https://hcitang.github.io), a Jekyll site hosted on GitHub Pages. Theme is a hand-modified fork of Minimal Mistakes (via jponttuset's site). Deployment is automatic: push to `master` and GitHub Pages rebuilds the site.

## Commands

```bash
bundle update                          # install/update gems
jekyll serve --watch --port 5000       # run locally at http://localhost:5000
```

No tests, no linting.

## Structure

- `_config.yml` — site-wide config. Top navigation links live here (`links:`), as does owner/bio info shown in the author sidebar. "Research" and "Blog" nav items point externally to ricelab.github.io.
- `index.md` — homepage (layout `home2`).
- `_pages/` — main pages (cv, teaching, resources, fun, site-index). Each sets its own `permalink:` in front matter. This dir is pulled in via `include: ["_pages"]` in config.
- `_posts/` — blog-style posts, mostly grad-student advice/resources linked from `_pages/resources.md`. Permalink format is `/:year/:title/`, so internal links look like `{{site.baseurl}}/2018/proposal-writing/`.
- `_layouts/` + `_includes/` — theme HTML. `cv.html` is a custom layout for the CV page; `home2.html` for the homepage.
- `secret-toys/` — unlisted static HTML pages.
- `_CNAME` — note the underscore prefix; the custom-domain CNAME is intentionally disabled.

## Conventions

- Content edits are almost always in `index.md`, `_pages/*.md`, or `_config.yml` — not the theme files.
- Commit messages follow the pattern `<file>: <what changed>` (e.g. `index.md: added smu visit`).
