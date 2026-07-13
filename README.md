# London Political Economy & Political Science Early Career Workshop

A single-page website for the workshop, ready to deploy on GitHub Pages.

## Files

- `index.html` — the page content
- `style.css` — all styling

## Editing content

Every placeholder is wrapped in `[square brackets]` and highlighted in green so it's easy to find. Search the HTML file for `placeholder` or just look for `[...]` text and replace with real content:

- Date, venue, and submission deadline (in the hero section)
- About text (two paragraphs)
- Call for Papers copy and submission rules
- Key dates timeline (4 milestones)
- Venue address and travel info
- Organizer names and affiliations
- Contact email and social links
- Footer year

## Deploying to GitHub Pages

1. Create a new repository on GitHub (e.g. `lpe-psw`).
2. Upload `index.html` and `style.css` to the root of the repository (drag-and-drop on the GitHub web UI works fine, or use git):
   ```bash
   git init
   git add index.html style.css
   git commit -m "Initial workshop site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", choose the **main** branch and **/ (root)** folder, then save.
5. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

### Optional: custom domain

If you have a domain (e.g. from your institution or a registrar), add a `CNAME` file to the repo root containing just the domain name, and configure your DNS provider to point to GitHub Pages (an `A` record to GitHub's IPs, or a `CNAME` record if using a subdomain). GitHub's own docs walk through this under Settings → Pages → Custom domain.

## Design notes

- Fonts: Fraunces (display), Inter (body), IBM Plex Mono (dates/labels) — loaded from Google Fonts via CDN, no build step needed.
- Colors and type live as CSS variables at the top of `style.css` (`:root`) if you want to adjust the palette.
- Fully static — no build tools, frameworks, or dependencies required.
