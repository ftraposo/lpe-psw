HOW TO DEPLOY
=============

docs/         -> replace everything in your repo's docs/ folder with this
                 (index.html, style.css, search.json, sitemap.xml,
                 robots.txt, site_libs/).

                 IMPORTANT: also copy your existing images/ folder into
                 this docs/ folder before committing — it's not included
                 here since it was never uploaded to me.

site-source/  -> index.qmd, style.css, _quarto.yml — keep these at your
                 repo root (outside docs/) for future edits + `quarto render`.

WHAT CHANGED THIS ROUND
========================
- The 3 hero-side photos are now a carousel (prev/next arrows + dots)
  instead of a cropped fixed-height grid — images show at their natural
  size/aspect ratio, one at a time.
- Removed the duplicate photo gallery that used to sit below the Past
  Edition programme list (same 3 photos were showing twice on the page).
