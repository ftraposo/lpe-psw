# London Political Economy & Political Science Early Career Workshop

A Quarto version of the workshop site — same design and content as the static HTML build, but managed as a Quarto project so you get `quarto render` / `quarto publish` for free, with an easy upgrade path if you ever want multiple pages (e.g. a "Past Editions" page) or R/Python-driven content later.

## Files

- `index.qmd` — the page content (same sections as before: hero, about, themes, CFP, key dates, venue, organizers, footer)
- `style.css` — all styling, unchanged from the original
- `_quarto.yml` — project config. Notably sets `theme: none` so Quarto's default Bootstrap styling is disabled and your custom CSS renders exactly as designed.

## Editing content

Same as before — every placeholder is wrapped in `[square brackets]` and highlighted in green. Open `index.qmd` and search for `placeholder` or `[...]` to find them:

- Date, venue, and submission deadline (hero section)
- About text (two paragraphs)
- Call for Papers copy and submission rules
- Key dates timeline (4 milestones)
- Venue address and travel info
- Organizer names and affiliations
- Contact email and social links
- Footer year

The content sits inside a single fenced raw-HTML block (` ```{=html} ... ``` `) in `index.qmd`, so you're editing plain HTML exactly as before — Quarto just leaves it untouched and drops it straight into the page.

## Working locally

1. [Install Quarto](https://quarto.org/docs/get-started/) (or `pip install quarto-cli`, which installs the same CLI).
2. From the project folder, preview with live reload:
   ```bash
   quarto preview
   ```
3. Build the static site into `docs/`:
   ```bash
   quarto render
   ```
   This is the folder GitHub Pages will serve from — see below.

## Deploying to GitHub Pages

**Option A — serve the `docs/` folder (simplest, matches original setup)**

1. Create a new repository on GitHub (e.g. `lpe-psw`).
2. Push the whole project, including the rendered `docs/` folder:
   ```bash
   git init
   git add .
   git commit -m "Initial Quarto workshop site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", choose the **main** branch and **/docs** folder, then save.
5. Whenever you edit `index.qmd`, run `quarto render` again, commit the updated `docs/` folder, and push.

**Option B — `quarto publish` (no manual render/commit step)**

```bash
quarto publish gh-pages
```

This renders the site and pushes it straight to a `gh-pages` branch, then you point GitHub Pages at that branch instead of `docs/`. Re-run the same command whenever you update the content.

### Optional: custom domain

Same as before — add a `CNAME` file to the repo root (or to `docs/` if serving from that folder) containing just the domain name, and point your DNS at GitHub Pages.

## Design notes

- Fonts: Fraunces (display), Inter (body), IBM Plex Mono (dates/labels) — loaded from Google Fonts via CDN, injected through `include-in-header` in `_quarto.yml`.
- Colors and type live as CSS variables at the top of `style.css` (`:root`) if you want to adjust the palette.
- `theme: none` in `_quarto.yml` is what keeps Quarto from injecting Bootstrap and its own typography — don't remove it unless you want to redesign around Bootstrap instead.
