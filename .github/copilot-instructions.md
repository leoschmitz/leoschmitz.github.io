# GitHub Pages Jekyll Blog - AI Agent Instructions

## Project Overview
This is a Jekyll-based personal portfolio site hosted on GitHub Pages featuring video game reviews. Uses the **Minima** theme with the **jekyll-feed** plugin for RSS feed generation. The site serves as both a gaming content hub and a brief professional information page (about).

## Essential Workflows

### Local Development
- **Start development server:** `bundle exec jekyll serve` (auto-reloads on file changes)
- **Build static site:** `bundle exec jekyll build` (output to `_site/` directory)
- **Install dependencies:** `bundle install` (reads from Gemfile)

### Adding Content
- **Blog posts:** Create files in `_posts/` with naming format `YYYY-MM-DD-title.markdown` (e.g., game reviews)
- **Pages:** Create `.markdown` files in root with front matter layout (see `about.markdown`, `index.markdown`)
- **Front matter:** YAML header required at top of all content files (see examples: `layout`, `title`, `date`, `categories`)
- **About page:** Should include academic research info, LinkedIn profile link, and professional background

## Architecture & Key Files

| File/Folder | Purpose |
|---|---|
| `_config.yml` | Jekyll configuration (site title, theme, plugins, build rules) |
| `_posts/` | Video game reviews and other blog posts (uses `YYYY-MM-DD-title.markdown` format) |
| `_layouts/` | Custom theme layouts: `default` (chrome/header/footer), `home` (masonry card gallery), `post`, `page` |
| `assets/main.scss` | All site styling (masonry card grid, teal accent) |
| `about.markdown` | About page (layout: page) - includes academic research, LinkedIn, and professional info |
| `index.markdown` | Homepage (layout: home, renders the card gallery) |
| `404.html` | Custom 404 error page |
| `Gemfile` | Ruby dependencies (Jekyll 4.4.1, Minima 2.5, jekyll-feed) |
| `README.md` | Project documentation (describes site purpose and content types) |

## Development Conventions

### Markdown Files
- Use `.markdown` extension (not `.md`) for consistency with theme
- Always include YAML front matter with at minimum: `layout`, `title`, `permalink` (for pages)
- Blog posts need: `layout: post`, `title`, `date`, `categories`
- Date format in posts: `YYYY-MM-DD HH:MM:SS +/-HHMM`

### Git Hosting
- Repository name follows GitHub Pages convention: `leoschmitz.github.io`
- Site deploys from the `master` branch via a GitHub Actions workflow (`.github/workflows/pages.yml`), which builds with the repo's Gemfile
- Static assets (PDFs, images) are served from root or asset directories

### Content Types
- **Video game reviews:** Posted in `_posts/` with `categories: gaming` or similar tags
- **Professional links:** LinkedIn, academic content and other Leo's personal data linked in `about.markdown`

### Theme & Templates
- **Theme:** fully custom (`theme: minima` is set only for dependency reasons; all layouts and styles are overridden in `_layouts/` and `assets/main.scss`)
- **Design:** masonry card gallery (CSS columns), light background, green/teal accent (`#0d9488`), rounded cards with hover lift
- **Plugins:** jekyll-feed generates RSS feed automatically
- Theme layouts referenced in front matter: `home`, `page`, `post`
- Posts may set `image: <path>` in front matter to show a photo on the card; without one, a teal gradient placeholder is used

## Important Notes
- Do NOT modify `_config.yml` without restarting `bundle exec jekyll serve`
- Excluded from processing: `.sass-cache/`, `.jekyll-cache/`, `node_modules/`, `vendor/` (see `_config.yml` exclude rules)
- GitHub Pages deploys via `.github/workflows/pages.yml`; on first push, enable Pages in repo settings with source "GitHub Actions"
