# Mingyuan Zhang's Homepage

Personal website built with [Hugo](https://gohugo.io/) and the
[PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, deployed to
GitHub Pages at <https://mingyuanzhang.com>.

## Setup

Hugo is the only dependency:

```bash
brew install hugo
```

The theme is a git submodule, so clone with:

```bash
git clone --recurse-submodules https://github.com/zmydev/myzh.github.io.git
```

If you already cloned without it:

```bash
git submodule update --init --recursive
```

## Local development

```bash
hugo server -D
```

Then open <http://localhost:1313>. Pages live-reload as you edit.

To reproduce a production build locally:

```bash
hugo --gc --minify
```

The rendered site lands in `public/` (gitignored).

## Project structure

```
hugo.yaml                  # all site configuration
content/
  _index.md                # homepage: bio, education, research, honors, service
  publications.md          # publication list
  articles/_index.md       # Articles section
  projects/_index.md       # Projects section
assets/css/extended/       # custom CSS, auto-loaded by PaperMod
layouts/_partials/         # extend_head.html loads KaTeX
layouts/_shortcodes/       # {{< social >}} renders the configured social icons
static/
  papers/                  # paper PDFs, served at /papers/<file>.pdf
  images/                  # profile photo, favicon, logos
  CNAME                    # custom domain
themes/PaperMod/           # theme (git submodule)
```

## Writing content

### Articles

Create `content/articles/my-article.md`:

```markdown
---
title: "My Article"
date: 2026-08-28
summary: "One-line description shown in the listing."
tags: ["Machine Learning"]
---

Your content here.
```

LaTeX renders via KaTeX and is enabled site-wide (`params.math` in `hugo.yaml`):
`$x^2 + y^2 = r^2$` inline, `$$...$$` for display. Set `math: false` in a page's
front matter to skip loading it.

Set `draft: true` to keep a page out of production builds; `hugo server -D`
still shows it.

### Projects

Same shape, under `content/projects/`.

### Publications

`content/publications.md` is a single hand-maintained markdown page. Add new
entries at the top. PDFs go in `static/papers/` and are linked as
`/papers/<file>.pdf` — the same URLs the previous Quarto site used.

### Homepage

Everything on the homepage lives in `content/_index.md`. The name, tagline, and
social icons sit in a small HTML block at the top; the social links themselves
are configured under `params.socialIcons` in `hugo.yaml`.

## Configuration

All of it is in `hugo.yaml`: navigation (`menu.main`), social links
(`params.socialIcons`), theme behaviour (table of contents, reading time, dark
mode), and `baseURL`.

To add PaperMod's site search, add a `JSON` entry under `outputs.home` in
`hugo.yaml` and create `content/search.md` with `layout: "search"`.

## Deployment

Pushing to `master` triggers `.github/workflows/hugo.yml`, which builds the site
and publishes it to GitHub Pages. The custom domain comes from `static/CNAME`,
which Hugo copies to the site root on every build.

## Updating the theme

```bash
git submodule update --remote --merge themes/PaperMod
```

## Resources

- [Hugo documentation](https://gohugo.io/documentation/)
- [PaperMod wiki](https://github.com/adityatelange/hugo-PaperMod/wiki)
