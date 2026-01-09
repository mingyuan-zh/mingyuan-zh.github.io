# Content Creation Guide

Quick reference for creating content on your Quarto website.

## Article Template

Create a new article in `articles/`:

```yaml
---
title: "Your Article Title"
date: 2025-01-15
description: "Brief description for listings"
categories:
  - Machine Learning
  - Tutorial
---

## Introduction

Your content here with **bold** and *italic* text.

## Math Examples

Inline: $E = mc^2$

Display:
$$
\mathcal{L}(\theta) = \frac{1}{n}\sum_{i=1}^{n} \ell(f(x_i; \theta), y_i)
$$

## Code Examples

```python
def example():
    return "Hello, World!"
```

## Conclusion

Wrap up your article.
```

## Research Note Template

Create in `research-notes/`:

```yaml
---
title: "Research Note Title"
date: 2025-01-15
description: "Summary of research findings"
categories:
  - Research
---

## Key Findings

Your research notes here.

## Mathematical Formulation

$$
R_{\phi}(f) = \mathbb{E}[\phi(f(X), Y)]
$$
```

## Project Template

Create in `projects/`:

```yaml
---
title: "Project Name"
date: 2025-01-15
description: "Project description"
categories:
  - Project
github: https://github.com/username/repo
---

## Overview

Project description.

## Installation

```bash
pip install -r requirements.txt
```

## Usage

```python
from project import main
main()
```

## Links

- [GitHub](link)
- [Demo](link)
```

## Jupyter Notebook Usage

1. Create `.ipynb` files in any content directory
2. Quarto will automatically execute and render them
3. Use markdown cells for LaTeX: `$$E = mc^2$$`
4. Code cells execute automatically (or use `freeze: true` to prevent execution)

## LaTeX Quick Reference

- Inline math: `$x^2$` → $x^2$
- Display math: `$$\int_0^1 f(x) dx$$`
- Greek letters: `$\alpha, \beta, \gamma$` → $\alpha, \beta, \gamma$
- Subscripts: `$x_i$` → $x_i$
- Superscripts: `$x^2$` → $x^2$
- Fractions: `$\frac{a}{b}$` → $\frac{a}{b}$
- Sum: `$\sum_{i=1}^{n}$` → $\sum_{i=1}^{n}$
- Integral: `$\int_a^b$` → $\int_a^b$

## Code Block Languages

Supported languages include:
- `python`
- `r`
- `julia`
- `bash`
- `sql`
- `javascript`
- `html`
- `css`
- And many more!

## Tips

1. **Date Format**: Use `YYYY-MM-DD` format for dates
2. **Categories**: Use consistent category names for better organization
3. **Descriptions**: Keep descriptions concise (1-2 sentences)
4. **Notebooks**: Test notebooks locally before committing
5. **Math**: Preview math rendering with `quarto preview`
