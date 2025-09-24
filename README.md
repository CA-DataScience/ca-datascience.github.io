# Data Science Education Portal

A Quarto-based website providing educational resources for data science students and educators.

## Quick Start

### Prerequisites
- [Quarto](https://quarto.org/docs/get-started/) installed
- Python 3.11+ with Jupyter
- VS Code with Quarto extension (recommended)

### Local Development

1. Clone the repository
2. Install Python dependencies:
   ```bash
   pip install jupyter matplotlib plotly pandas seaborn
   ```
3. Preview the site:
   ```bash
   quarto preview
   ```
4. Build the site:
   ```bash
   quarto render
   ```

### Publishing

The site automatically deploys to GitHub Pages when changes are pushed to the `main` branch via GitHub Actions.

To publish manually:
```bash
quarto publish gh-pages
```

## Site Structure

- `index.qmd` - Homepage with navigation cards
- `data-science.qmd` - Main resource page with student/educator tabs
- `educators.qmd` - Dedicated educator resources
- `blog.qmd` - Blog listing page
- `faqs.qmd` - Frequently asked questions
- `about.qmd` - About the portal
- `posts/` - Blog posts directory
- `assets/` - Static assets (CSS, images, etc.)
- `_quarto.yml` - Main configuration file

## Adding Content

### New Blog Posts

Create a new `.qmd` file in the `posts/` directory:

```yaml
---
title: "Your Post Title"
date: "2024-MM-DD"
categories: [category1, category2]
description: "Brief description"
author: "Author Name"
---

Your content here...
```

### New Pages

Create a new `.qmd` file in the root directory and add it to the navbar in `_quarto.yml`.

## Migration Notes

This site was migrated from Jekyll to Quarto for:
- Better performance and modern features
- Enhanced responsive design
- Improved content organization
- Better integration with Python/R content

## License

Content is available under Creative Commons Attribution 4.0 International License.