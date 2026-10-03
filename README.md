# Unlock Financial Freedom — Jekyll site

## Local preview
```
bundle install
bundle exec jekyll serve
```
Visit http://localhost:4000

## Deploy to GitHub Pages
1. Create a new GitHub repo, e.g. `unlock-financial-freedom`
2. Push this folder to it:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/unlock-financial-freedom.git
   git push -u origin main
   ```
3. In the repo: Settings → Pages → Source: deploy from `main` branch, root folder
4. Your site goes live at `https://YOUR_USERNAME.github.io/unlock-financial-freedom/`
5. Update `url` and `baseurl` in `_config.yml` to match before pushing

## Custom domain (optional)
1. Add a `CNAME` file to the repo root containing just your domain, e.g. `unlockfinancialfreedom.com`
2. In your domain registrar, add a CNAME record pointing to `YOUR_USERNAME.github.io`
3. In GitHub repo Settings → Pages, enter the custom domain and enable "Enforce HTTPS"

## Adding a new post
Create a file in `_posts/` named `YYYY-MM-DD-title-slug.md`:
```
---
title: "Your Post Title"
description: "One-sentence meta description for SEO."
---

Post content in Markdown goes here.
```

## Adsterra ad units
All 5 of your Adsterra units have placeholder slots wired in — just uncomment and paste your real codes in:
- **Banner** → `_includes/ad-banner.html` (shows at the top of every page)
- **Native Banner** → `_includes/ad-native.html` (shows above and below every post body)
- **Social Bar** → `_includes/ad-social-bar.html` (sitewide sticky unit)
- **Popunder** → `_includes/ad-popunder.html` (sitewide)
- **Smartlink** → this is just a URL, not an embed. Use it as the link behind a specific CTA (e.g. a "recommended tool" link in a post) rather than a sitewide placement.

Each file has the real Adsterra script structure commented out — swap in your actual `key`/script URLs from your Adsterra dashboard and uncomment.

## Google AdSense
1. Apply at google.com/adsense with your live site URL — approval requires original content (you have plenty) and no policy violations
2. Once approved, Google gives you a publisher ID (`ca-pub-XXXXXXXXXX`) and an exact `ads.txt` line
3. Paste your publisher ID into `_includes/adsense.html` and `_includes/ad-adsense-display.html`, uncomment both
4. Replace the placeholder comment in `ads.txt` with the real line Google gives you
5. Running AdSense alongside Adsterra is allowed, but keep an eye on total ad density per page — AdSense's policies penalize pages that feel ad-heavy, so don't enable every ad unit at once if pages start looking cluttered

## After going live
- Submit the new domain/sitemap to Google Search Console as a new property
- Set up 301 redirects from old Blogger URLs if migrating existing posts
- Sitemap is auto-generated at `/sitemap.xml` via the jekyll-sitemap plugin
