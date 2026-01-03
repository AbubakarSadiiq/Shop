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

Vercel deployment & custom domain
---------------------------------
You can deploy this static site to Vercel (recommended for fast CDN-backed hosting) and point a custom domain to it.

Two ways to deploy:

1) Quick deploy via Vercel web UI
	- Sign in to https://vercel.com and import this GitHub repository.
	- Vercel auto-detects static projects. Ensure the Project's Root has `index.html` present.
	- After import, Vercel will create deployments for every push to `main`.

2) Deploy using Vercel CLI (PowerShell)
	- Install Vercel CLI: `npm i -g vercel` (requires Node.js)
	- Login: `vercel login you@domain.com`
	- From project root: `vercel --prod` to create a production deployment.

Adding a custom domain on Vercel
--------------------------------
1. In your Vercel dashboard open the project → Settings → Domains → Add.
2. Enter your domain (example: `example.com`) and follow the verification steps.
3. Update DNS at your registrar:
	- For apex/root domain (example.com): add A records pointing to Vercel IPs (76.76.21.21) or use the Vercel-provided ALIAS/ANAME if supported.
	- For subdomain (www.example.com): create a CNAME record pointing to `cname.vercel-dns.com` (Vercel will provide the exact target during setup).
4. After DNS propagates, Vercel will issue an SSL certificate automatically and serve your site.

Vercel CLI commands for domain management
----------------------------------------
After installing and logging in with `vercel login`:

```powershell
# Deploy the current repo as production
vercel --prod

# Add a custom domain to the project (replace example.com)
vercel domains add example.com

# Alias a specific deployment to your domain
vercel alias <deployment-url> example.com
```

Notes & DNS tips
- DNS propagation can take up to 24–48 hours but often completes in minutes/hours.
- If you manage DNS on a service like Cloudflare, temporarily disable proxying (orange cloud) during verification and enable it afterward if desired.
- Vercel supports automatic HTTPS via Let's Encrypt for verified domains.

If you want, I can add a small `vercel.json` configuration file (I can do that now) to ensure the site always serves `index.html`. I can also prepare the exact `vercel` CLI commands for you to run locally and guide you through adding the domain.

Contact
If you need help with deployment or updating content, open an issue or contact the site owner.
