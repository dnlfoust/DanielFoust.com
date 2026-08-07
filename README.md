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

## Deploying (GitHub Pages)

This repo is set up for GitHub Pages, serving from the `main` branch root. The
`CNAME` file in the repo root points it at `danielfoust.com`.

One-time setup (GitHub UI, since this isn't scriptable via the API used here):

1. Go to the repo's **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to "Deploy from a branch".
3. Set **Branch** to `main`, folder `/ (root)`, then **Save**.
4. Under **Custom domain**, enter `danielfoust.com` and save (GitHub will verify
   it against the `CNAME` file already in the repo).
5. Once DNS (below) has propagated, check **Enforce HTTPS**.

### DNS records (at GoDaddy)

In GoDaddy's DNS management for `danielfoust.com`, add:

| Type  | Name | Value                  |
|-------|------|------------------------|
| A     | @    | 185.199.108.153        |
| A     | @    | 185.199.109.153        |
| A     | @    | 185.199.110.153        |
| A     | @    | 185.199.111.153        |
| CNAME | www  | dnlfoust.github.io     |

`danielfoust.com` is the primary domain; `www.danielfoust.com` will redirect to
it automatically once both are configured. DNS propagation can take anywhere
from a few minutes to a few hours.

### Other hosting options

The site is plain static files, so it can be hosted anywhere: Netlify, Vercel,
and Cloudflare Pages all work too, if you'd rather use one of those instead.
