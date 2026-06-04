# AGENTS.md

This file provides guidance to Codex (Codex.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based personal academic website for Zelong Guo, hosted on GitHub Pages at `https://zelongguo.github.io/`. The site is forked from the [researcher theme](https://github.com/ankitsultana/researcher) and customized with personal academic content (publications, CV, research).

## Build & Development

This is a static Jekyll site with no build step required for local development. GitHub Pages handles building automatically on push.

**Local development:**
```bash
# Install Jekyll (if not installed)
gem install bundler jekyll

# Serve locally
jekyll serve
# or
bundle exec jekyll serve
```

**Deployment:** Push to `master` branch. GitHub Pages auto-builds and deploys.

## Architecture

### Site Structure
- `_config.yml` — Site configuration (title, URL, kramdown settings, Google Analytics tracking ID)
- `_layouts/` — HTML templates: `default.html` (main layout), `post.html` (blog posts), `research.html`
- `_data/nav.yml` — Navigation menu items (hardcoded absolute URLs)
- `_sass/` — SCSS stylesheets: `_style.scss` (main), `vars.scss` (variables), `typography.scss`, `tables.scss`
- `css/main.scss` — Entry point that imports `_style.scss`
- `_posts/` — Blog posts in Markdown (Jekyll naming convention: `YYYY-MM-DD-title.md`)

### Content Pages
All content pages use `layout: default` in frontmatter:
- `index.md` — Homepage with about section, news feed (HTML table with scrollable div), and visitor counter
- `publications.md` — Publications list (raw HTML, not Markdown)
- `cv.md` — CV summary with links to PDF versions in `/cv/`
- `contact.md` — Contact information
- `media.md` — Media appearances
- `codes.md` — Code/software links
- `research.md` — Research details

### Key Design Decisions
- Navigation is defined in `_data/nav.yml` with absolute URLs (not relative links)
- The news section on `index.md` uses a custom CSS overflow div for scrolling
- Google Analytics tracking is in both `_config.yml` (`tracking_id`) and `_layouts/default.html` (gtag.js)
- The site uses Google Fonts (Lato) and a green accent color (`ForestGreen`) defined in `_sass/vars.scss`
- Max content width is 700px, with responsive breakpoints at 800px and 650px

### Assets
- `img/` — Profile photos and images
- `cv/` — PDF CV files (English and Chinese versions)
- `resources/` — Additional resources
