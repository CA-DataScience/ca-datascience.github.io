# Data Science Education Portal

[![Deploy Status](https://github.com/ca-datascience/ca-datascience.github.io/actions/workflows/quarto-publish.yml/badge.svg)](https://github.com/ca-datascience/ca-datascience.github.io/actions/workflows/quarto-publish.yml)

A Quarto-based website providing educational resources, curriculum guidance, and community updates for data science students and educators in California.

**Live Site:** https://ca-datascience.github.io

---

## Table of Contents

- [Installation & Setup](#installation--setup)
- [Website Overview](#website-overview)
- [Adding a New Blog Post](#adding-a-new-blog-post)
- [Contributing](#contributing)
- [Project Structure](#project-structure)

---

## Installation & Setup

### Prerequisites

- **Git** - For version control
- **Quarto** - Static site generator
- **Python 3.11+** with Jupyter - For executable code blocks (optional but recommended)

### Installing Quarto (macOS)

1. **Download Quarto:**
   - Visit [quarto.org/docs/get-started](https://quarto.org/docs/get-started/)
   - Download the macOS installer (.pkg file)

2. **Install Quarto:**
   - Double-click the `.pkg` file and follow the installation prompts
   - This automatically adds Quarto to your PATH

3. **Verify Installation:**
   ```bash
   quarto --version
   ```
   You should see the version number (e.g., `1.4.550`)

4. **Optional - Install Python dependencies:**
   ```bash
   pip install jupyter matplotlib plotly pandas seaborn
   ```
   *Note: Only needed if you're working with blog posts that include executable Python code*

### Running the Site Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ca-datascience/ca-datascience.github.io.git
   cd ca-datascience.github.io
   ```

2. **Preview the site:**
   ```bash
   quarto preview
   ```
   This will:
   - Start a local development server
   - Open your browser to `http://localhost:3196` (or similar)
   - Auto-reload when you save changes

3. **Stop the preview:**
   - Press `Ctrl+C` in the terminal

---

## Website Overview

The site is organized into several main sections:

### **Home / About** (`index.qmd`)
- Landing page with overview of the portal
- Quick navigation to main sections

### **For Students** (`students/`)
- `students/index.qmd` - Getting started guide for learning data science
- `students/resources.qmd` - Curated learning resources, tools, and pathways

### **For Educators** (`educators/`)
- `educators/index.qmd` - Open educational resources and teaching materials

### **Blog & Updates** (`blog.qmd`, `posts/`)
- `blog.qmd` - Main blog listing page showing all posts
- `blog/events.qmd` - Events and workshops calendar/archive
- `posts/` - Individual blog post files (`.qmd` format)

### **FAQs** (`faqs.qmd`)
- Frequently asked questions for both students and educators

### **Assets** (`assets/`)
- `assets/styles.css` - Custom site styling
- `assets/images/` - Images used throughout the site
- `assets/favicon.ico` - Site icon

---

## Adding a New Blog Post

### 1. Create a new file

Create a new `.qmd` file in the `posts/` directory with a descriptive name:

```bash
posts/YYYY-MM-DD-my-post-title.qmd
```

### 2. Add front matter

Start your file with YAML front matter:

```yaml
---
title: "Your Post Title Here"
date: "2024-12-15"
categories: [events, workshop, data-science]
description: "A brief description of your post (shown in listing)"
author: "Your Name"
image: "assets/images/your-image.png"  # Optional featured image
---
```

**Common categories:** `events`, `workshop`, `tutorial`, `data-science`, `education`, `resources`

### 3. Write your content

Use standard Markdown or Quarto syntax:

```markdown
## Section Heading

Your content here with **bold**, *italic*, and [links](https://example.com).

- Bullet points
- Work great

### Subsection

You can include code blocks:

\`\`\`python
print("Hello, Data Science!")
\`\`\`

Or executable code:

\`\`\`{python}
import pandas as pd
df = pd.DataFrame({'x': [1, 2, 3]})
df
\`\`\`
```

### 4. Preview your post

```bash
quarto preview
```

Navigate to the blog page or directly to your post URL:
- Blog listing: `http://localhost:3196/blog.html`
- Your post: `http://localhost:3196/posts/YYYY-MM-DD-my-post-title.html`

### 5. Check for errors

- Make sure images load (use relative paths like `../assets/images/...`)
- Verify links work
- Check that executable code runs without errors
- Test responsive design by resizing your browser

---

## Contributing

We welcome contributions from the data science education community!

### Contribution Workflow

1. **Create a new branch:**
   ```bash
   git checkout -b add-my-blog-post
   ```
   Use a descriptive branch name like `add-workshop-recap` or `fix-typo-faqs`

2. **Make your changes:**
   - Add your blog post or edit existing content
   - Test locally with `quarto preview`
   - Make sure everything renders correctly

3. **Commit your changes:**
   ```bash
   git add .
   git commit -m "Add blog post about X workshop"
   ```

4. **Push your branch:**
   ```bash
   git push origin add-my-blog-post
   ```

5. **Create a Pull Request:**
   - Go to [github.com/ca-datascience/ca-datascience.github.io](https://github.com/ca-datascience/ca-datascience.github.io)
   - Click "Pull requests" → "New pull request"
   - Select your branch
   - Add a clear description of your changes
   - Click "Create pull request"

6. **Wait for CI checks:**
   - GitHub Actions will automatically build your changes
   - Make sure the "PR Build Check" passes (green checkmark)
   - If it fails, review the error logs and fix issues

7. **Get a review:**
   - A maintainer will review your PR
   - Address any feedback or requested changes
   - Once approved, a maintainer will merge your PR

8. **Automatic deployment:**
   - After merge to `main`, the site automatically deploys via GitHub Actions
   - Your changes will be live at https://ca-datascience.github.io within ~2-3 minutes

### Need Help?

Contact the maintainers at [vivrd@berkeley.edu](mailto:vivrd@berkeley.edu)

---

## Project Structure

```
ca-datascience.github.io/
├── _quarto.yml              # Main Quarto configuration
├── index.qmd                # Homepage
├── blog.qmd                 # Blog listing page
├── faqs.qmd                 # FAQ page
├── students/                # Student resources section
│   ├── index.qmd
│   └── resources.qmd
├── educators/               # Educator resources section
│   └── index.qmd
├── blog/                    # Blog subsections
│   └── events.qmd
├── posts/                   # Individual blog posts
│   ├── 2023-10-20-inspire-2024-workshop-recap.qmd
│   ├── inspire-2024-slideshow.qmd
│   └── ...
├── assets/                  # Static files
│   ├── styles.css
│   ├── favicon.ico
│   └── images/
├── .github/workflows/       # GitHub Actions CI/CD
│   ├── quarto-publish.yml   # Auto-deploy on main
│   └── pr-check.yml         # Build check for PRs
└── _site/                   # Generated site (git-ignored)
```

---

## Technical Details

- **Framework:** [Quarto](https://quarto.org/) v1.4.550+
- **Theme:** Lumen (Bootstrap-based)
- **Hosting:** GitHub Pages
- **CI/CD:** GitHub Actions
- **License:** Creative Commons Attribution 4.0 International License

---

## Troubleshooting

### Images not loading (404 errors)

If you see 404 errors for images in the browser console:
- Check that image paths are relative from the `.qmd` file location
- From `posts/` directory, use `../assets/images/...` to go up one level
- Example: `![Alt text](../assets/images/my-image.png)`

### Quarto command not found

- Make sure Quarto is installed and in your PATH
- Try restarting your terminal
- Verify with `quarto --version`

### Port already in use

If `quarto preview` says port 3196 is in use:
```bash
quarto preview --port 4000
```

### Build fails in GitHub Actions

- Check the Actions tab on GitHub for error logs
- Run `quarto render` locally to reproduce the error
- Common issues: missing images, invalid YAML, syntax errors in code blocks
