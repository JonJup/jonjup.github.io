# Academic Website + Blog

Handcrafted homepage (`index.html`) with a Quarto-powered blog (`blog/`).  
Write posts in `.qmd` or `.Rmd` from RStudio, push to GitHub, done.

## Structure

```
.
├── index.html                  ← Your main homepage (hand-edited)
├── .nojekyll                   ← Tells GitHub Pages to skip Jekyll
├── blog/
│   ├── _quarto.yml             ← Quarto config (blog only)
│   ├── index.qmd               ← Blog listing page
│   ├── styles.css              ← Blog styles (matches main site)
│   └── posts/
│       └── my-post-name/
│           └── index.qmd       ← A blog post
└── .github/
    └── workflows/
        └── publish.yml         ← Auto-renders blog & deploys everything
```

## Setup

1. Create a GitHub repo: `yourusername.github.io`
2. Copy these files in, push to `main`
3. In repo **Settings → Pages**, set source to **GitHub Actions**
4. Site goes live at `https://yourusername.github.io`

## Writing a new blog post

1. Create a folder under `blog/posts/`:
   ```
   blog/posts/my-new-post/index.qmd
   ```

2. Add a YAML header:
   ```yaml
   ---
   title: "My Post Title"
   description: "Brief summary."
   author: "Jonathan"
   date: "2025-03-15"
   categories: [R, methods, HMSC]
   execute:
     echo: true
     warning: false
   ---
   ```

3. Write content with R code chunks as usual.

4. **Preview locally** (optional):
   ```bash
   cd blog
   quarto preview
   ```

5. **Add a card to `index.html`** — copy an existing `<a class="blog-card">` block
   in the Blog section and update the title, date, excerpt, tags, and link.

6. Commit & push:
   ```bash
   git add .
   git commit -m "New post: My Post Title"
   git push
   ```

GitHub Actions will install R + your packages, render the blog, and deploy
everything (~2-3 min).

## Adding R packages

Edit `.github/workflows/publish.yml`, under the `packages:` section:

```yaml
packages: |
  any::knitr
  any::rmarkdown
  any::ggplot2
  any::dplyr
  any::sf          # ← add here
  any::terra
```

## Using .Rmd instead of .qmd

Both work. Just name the file `index.Rmd`. The YAML header is nearly identical.
