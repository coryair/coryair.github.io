# Cory Hernandez

A small about-and-contact site, written in HTML with an embedded stylesheet.
No JavaScript, dependencies, or build step.

## Edit and preview

Edit `index.html` to change the bio, email address, or styling. Open it directly
in a browser, or run `python3 -m http.server 8000` and visit
<http://localhost:8000>.

## Publish on GitHub Pages

1. In the repository's **Settings → Pages**, set **Source** to **GitHub Actions**.
2. Push to `main` (or `master`). The `Deploy site to GitHub Pages` workflow
   packages the static files and deploys them to GitHub Pages.

Pull requests package the site without deploying. The workflow can also be run
manually from the Actions tab on `main` or `master`.

Only `index.html`, `robots.txt`, `.nojekyll`, and an optional `CNAME` are published.
If you add images or other assets, include them in the workflow's copy step.

The previous Jekyll site and blog posts remain available in Git history.
Old blog URLs are no longer published.
