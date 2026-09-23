HOW TO DEPLOY
=============

This zip has two folders:

1) docs/         <- THIS is what goes in your GitHub repo's docs/ folder.
                     Delete everything currently inside your repo's docs/
                     folder, then drag in everything from this docs/ folder
                     (index.html, style.css, search.json, sitemap.xml,
                     robots.txt, site_libs/).

   IMPORTANT: this docs/ folder does NOT include your images/ folder
   (organizer photos, event photos, programme PDF) because those files
   were never uploaded to me. Before you commit, also copy your existing
   images/ folder (from your current repo) into this docs/ folder, so the
   final docs/ contains: index.html, style.css, search.json, sitemap.xml,
   robots.txt, site_libs/, AND images/.

2) site-source/  <- These are the editable source files (index.qmd,
                     style.css, _quarto.yml). Keep these at the root of
                     your repo (outside docs/) so future edits + `quarto
                     render` continue to work. They just document what
                     produced the docs/ folder above.

After committing to main, check the Actions tab for the Pages deployment,
then hard-refresh the live page.
