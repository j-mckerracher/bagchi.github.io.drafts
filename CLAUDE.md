# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Static personal/academic website for Saurabh Bagchi (Purdue ECE professor). Hosted on GitHub Pages at `www.saurabhbagchi.us`. No build step — edit files, push, done.

## No build tooling

No npm, no bundler, no test suite. Deployment = `git push` to master; GitHub Pages serves the site directly.

To preview locally:
```bash
python3 -m http.server 8080
```

## Structure

- `index.html` — landing page with slideshow and tabbed sections
- `home.html`, `news.html`, `leadership.html`, `research.html`, `vita.html`, etc. — individual content pages
- `left.html` — sidebar nav (loaded via jQuery into other pages)
- `css/style.css`, `css/tabs.css` — custom styles; Bulma 0.8 + Bootstrap 5 + Font Awesome 4.7 loaded from CDN
- `Leadership.html` — capital-L version is the actively maintained leadership page (differs from `leadership.html`)
- `Research/`, `News/`, `Classes/`, `Presentations/` — subdirectory content
- `vita.html` — full CV (1 MB); `vita.pdf` — PDF version

## Key conventions

- Pages use Bulma CSS utility classes for layout.
- jQuery is used for loading shared partials (e.g. `left.html` sidebar) via `$("#nav").load("left.html")`.
- News items in `news.html` follow the format `[Mon YYYY] Description. [ [WWW](url) ]`.
- The `Leadership.html` (capital L) is the canonical leadership page; `leadership.html` (lowercase) is a secondary/older version.
- No templating engine — shared elements (nav, footer) are either copy-pasted or loaded with jQuery.
