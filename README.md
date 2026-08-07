# danielfoust.com

Personal website for Daniel Foust — plain HTML/CSS/JS, no build step, no dependencies.

## Structure

```
index.html      Home / about page
projects.html   Personal projects
resume.html     Resume (experience, education, skills)
css/styles.css  All styling (light/dark mode via prefers-color-scheme)
js/main.js      Small script (sets footer year)
assets/         Images, resume.pdf, etc.
```

## Editing content

- **About/bio**: edit the `#about` section in `index.html`.
- **Contact links**: edit the `.social-links` block in `index.html` (email, GitHub, LinkedIn).
- **Projects**: copy a `<article class="project-card">` block in `projects.html` for each
  new project, fill in the title, description, tags, and links.
- **Resume**: edit the `#experience`, `#education`, and `#skills` sections in `resume.html`.
  Drop a PDF at `assets/resume.pdf` to enable the "Download PDF" button.

## Running locally

No build tools needed. From the project root:

```
python3 -m http.server 8000
```

Then open http://localhost:8000 in a browser.

## Deploying

The site is static, so it can be hosted anywhere that serves plain files. A few common options:

- **GitHub Pages** — free, deploys straight from this repo. Enable it in the repo's
  Settings → Pages, set the source to this branch (or `main`) and root folder, then
  add a `CNAME` file containing `danielfoust.com` to the repo root.
- **Netlify** or **Vercel** — free tier, drag-and-drop or connect the repo, gives you
  a URL plus easy custom-domain + HTTPS setup.
- **Cloudflare Pages** — free, connects to the repo, includes DNS if you move
  domain management to Cloudflare.

Once you pick a host, point `danielfoust.com` at it by updating DNS records in
GoDaddy's DNS management (no need to use GoDaddy's website builder — you're only
using GoDaddy as the domain registrar/DNS host, which is fine).
