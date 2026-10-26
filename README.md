# Airsite — Web Designer & UI/UX Developer

Bilingual (English / Arabic) portfolio site. Static files only, no build step: `index.html` is the main page, `assets/` holds its images (WebP), and `projects/` holds the eight example sites with their images in `projects/pimg/`. The example sites load only when a visitor reaches or opens them, and images load as they scroll into view.

## Run locally

The example sites load with `fetch`, so serve the folder (opening `index.html` by double-click will not show the project previews):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Push to GitHub

```bash
cd airsite
git init -b main
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Deploy

### GitHub Pages (automatic)
1. In the repo go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Push to `main`. The workflow in `.github/workflows/deploy.yml` publishes the site.
4. Your site will be at `https://<your-username>.github.io/<repo-name>/`.

### Netlify
Import the repo at app.netlify.com. Leave the build command empty and set the publish directory to `.` (already in `netlify.toml`).

### Vercel
Import the repo at vercel.com. Framework preset: **Other**, no build command. `vercel.json` is included.

## Notes
- The site is split for fast loading: `index.html` is about 2.3 MB and each example site lives in `projects/` and loads only when it is needed; all images are compressed WebP files with long-lived caching.
- Edits made inside the site's built-in editor are saved in the visitor's browser (localStorage); to change the live site for everyone, edit `index.html` and push.
