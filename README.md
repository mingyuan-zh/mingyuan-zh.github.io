# Mingyuan Zhang's Homepage

Personal website built with Quarto, featuring technical articles, research notes, and projects.

## Features

- **LaTeX Math Rendering**: Full support for mathematical notation using MathJax
- **Jupyter Notebooks**: Execute and display Python code with outputs
- **Blog/Articles**: Technical articles and blog posts
- **Research Notes**: Research summaries and technical insights
- **Projects**: Showcase of code repositories and implementations

## Building the Site

To build the site locally:

```bash
quarto render
```

To preview the site:

```bash
quarto preview
```

## Python/Jupyter Setup

For Jupyter notebook support, install Python dependencies:

```bash
pip install -r requirements.txt
```

Quarto will automatically detect and execute `.ipynb` files when rendering.

## Writing Content

### Articles

Create articles in the `articles/` directory:

```bash
quarto create articles/my-article.qmd
```

Articles support:
- LaTeX math: `$E = mc^2$` or `$$\int_0^1 f(x) dx$$`
- Code blocks with syntax highlighting
- Jupyter notebooks (`.ipynb` files)

### Research Notes

Create research notes in `research-notes/`:

```bash
quarto create research-notes/my-note.qmd
```

### Projects

Create project pages in `projects/`:

```bash
quarto create projects/my-project.qmd
```

### Jupyter Notebooks

You can use `.ipynb` files directly in any section. Quarto will:
- Execute code cells
- Display outputs (plots, tables, etc.)
- Render markdown cells with LaTeX support

Example:
```bash
quarto render articles/my-notebook.ipynb
```

## Deployment

This site is configured for GitHub Pages. The `_site` directory contains the rendered HTML files.

### GitHub Pages Deployment

1. Push changes to the repository
2. GitHub Actions will automatically build and deploy
3. The workflow installs Python dependencies and renders all content including notebooks

### Manual Deployment

```bash
quarto render
# Then deploy the _site directory to your hosting service
```

## Project Structure

```
.
├── index.qmd              # Main homepage
├── about.qmd              # About page
├── publications.qmd       # Publications listing
├── articles/              # Technical articles
│   └── index.qmd
├── research-notes/        # Research notes
│   └── index.qmd
├── projects/             # Projects
│   └── index.qmd
├── _quarto.yml           # Quarto configuration
├── requirements.txt      # Python dependencies
├── assets/               # Images, CSS, and static assets
└── papers/              # PDF files of research papers
```

## LaTeX Math Examples

Inline math: `$x^2 + y^2 = r^2$`

Display math:
$$
\mathcal{L}(\theta) = \frac{1}{n}\sum_{i=1}^{n} \ell(f(x_i; \theta), y_i)
$$

## Resources

- [Quarto Documentation](https://quarto.org/docs/)
- [Quarto Websites](https://quarto.org/docs/websites/)
- [Quarto Jupyter](https://quarto.org/docs/computations/jupyter.html)
- [MathJax Documentation](https://www.mathjax.org/)
