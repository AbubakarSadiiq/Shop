# The Vogue — Static Site

This repository contains the static single-file website for The Vogue (the-vogue-website.html) and related images in the `images/` folder.

Contents
- `the-vogue-website.html` — single-file HTML with inline CSS and JavaScript.
- `images/` — image assets used by the site.

Quick local deploy (GitHub Pages)
1. Push this repository to GitHub.
2. In the repository Settings → Pages, select the `main` branch and the root (/) folder as the source.
3. Save. The site should be published at `https://<your-username>.github.io/<repo-name>/`.

Notes
- The site uses inline styles and scripts. For better caching and maintainability, consider extracting CSS/JS into `assets/`.
- There is a script `scripts/contrast_check.py` included for WCAG contrast checks; run locally with a Python runtime.

Contact
If you need help with deployment or updating content, open an issue or contact the site owner.
