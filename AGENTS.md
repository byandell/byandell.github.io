# Brian Yandell's Personal Website — Project Memory

## Project Overview

Personal portfolio and blog site for Brian Yandell (professor emeritus, UW-Madison Statistics, retired 2023). Tagline: "Life Beyond Retirement" (from Shakespeare's *The Tempest*). Hosted at https://byandell.github.io.

## Technology Stack

- **Static site generator:** Jekyll (GitHub Pages compatible), based on Jekyll-Now template (v1.2.0)
- **Markup:** Markdown (Kramdown with GitHub Flavored Markdown)
- **Styling:** SCSS/CSS (`style.scss`, partials in `_sass/`)
- **Syntax highlighting:** Rouge
- **Plugins:** `jekyll-sitemap`, `jekyll-feed`
- **Dependencies:** `Gemfile` (github-pages gem)
- **RStudio project:** `.Rproj` file present; some content generated programmatically in R

## Directory Structure

```
byandell.github.io/
├── _config.yml          # Site config: name, description, avatar, social links, URL
├── _layouts/            # HTML templates (default.html, page.html, post.html)
├── _includes/           # Reusable HTML components (analytics, meta, SVG icons)
├── _sass/               # SCSS partials (_reset, _variables, _highlights, _svg-icons)
├── _posts/              # Blog posts (Markdown, dated filenames)
├── pages/               # Thematic content pages and subdirectories
│   ├── ewing/           # Content about Bland Ewing and related science
│   └── sysgen/          # Systems genetics content
├── images/              # Image assets
├── style.scss           # Main compiled stylesheet
├── index.md             # Homepage
├── about.md             # About page
├── blog.md              # Blog listing page
├── AGENTS.md            # This file
├── Gemfile
└── README.md
```

## Blog Posts (`_posts/`)

Files follow the naming convention `YYYY-MM-DD-Title-Words.md`. Some posts have pre-compiled `.html` counterparts (not source files). Current posts span 1982–2026, covering:

- Data science, data models, data sovereignty
- Indigenous data science and ESIIL research
- Environmental and systems thinking
- Personal reflections (Jaron Lanier/AI, Bland Ewing, Pope and AI, gravity/antigravity)

## Thematic Pages (`pages/`)

| File | Topic |
|------|-------|
| `system.md` | Systems thinking and collaborative teams |
| `eds.md` | Environmental Data Science (primary research focus) |
| `indigenous.md` | Indigenous data science and sovereignty (ESIIL) |
| `reflect.md` | Personal reflections and family |
| `collaborate.md` | Collaboration and team development |
| `software.md` | Software history: APL, Fortran, R packages (R/qtl, ewing, pickgene, pda) |
| `coach.md` | Coaching |
| `team.md` | Team development |
| `sources.md` | Sources and references |
| `envsys.md` | Environmental systems |
| `covid19.md` | COVID-19 related content |
| `ewing/` | Bland Ewing biography and systems ethology science |
| `sysgen/` | Systems genetics |

## Key Content Themes

1. **Bland Ewing / Systems Ethology** — Long-running project reconnecting with mentor Bland Ewing (UC-Berkeley, 1971–73), documenting his life story (cassette tapes being digitized) and formalizing his modeling ideas into the R package [`ewing`](https://github.com/byandell/ewing) and the draft book [Systems Ethology](https://byandell.github.io/SystemsEthology).

2. **Indigenous Data Sovereignty** — Involvement with ESIIL and Indigenous data governance frameworks.

3. **Environmental Data Science** — Primary post-retirement research area.

4. **Personal/Professional Memoir** — Reflections on 40+ years in academia (biostatistics PhD at UC-Berkeley, faculty at UW-Madison Statistics 1983–2023).

## Site Configuration (`_config.yml`)

- **URL:** `https://byandell.github.io`
- **Permalink:** `/:title/`
- **Avatar:** GitHub profile picture (`https://avatars.githubusercontent.com/u/325732`)
- **Social links:** GitHub (`byandell`), LinkedIn (`brian-yandell-62198620`)
- Disqus and Google Analytics are configured but currently disabled

## Notes

- Pre-compiled `.html` files exist alongside some `.md` sources in `_posts/` and `pages/` — these are build artifacts, not source files. Edit only the `.md` source files.
- The `.gitignore` excludes `about.html`, `index.html`, and compiled page HTML, consistent with treating them as build artifacts.
- RStudio is the primary editing environment.
