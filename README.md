# Data Science Education Portal

[![Deploy Status](https://github.com/ca-datascience/ca-datascience.github.io/actions/workflows/quarto-publish.yml/badge.svg)](https://github.com/ca-datascience/ca-datascience.github.io/actions/workflows/quarto-publish.yml) [![Accessibility Check](https://github.com/CA-DataScience/ca-datascience.github.io/actions/workflows/a11y.yml/badge.svg)](https://github.com/CA-DataScience/ca-datascience.github.io/actions/workflows/a11y.yml)

A Quarto-based website providing educational resources, curriculum guidance, and community updates for data science students and educators in California.

**Live Site:** https://ca-datascience.github.io

---

## Table of Contents

- [Installation & Setup](#installation--setup)
- [Website Overview](#website-overview)
- [Adding a New Blog Post](#adding-a-new-blog-post)
- [Adding an Event to the Calendar](#adding-an-event-to-the-calendar)
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

## Adding an Event to the Calendar

Events are displayed on the [Events & Workshops](https://ca-datascience.github.io/blog/events.html) page. The calendar automatically sorts events into "Upcoming" and "Past" sections based on the current date.

### How It Works

Events are stored in a single YAML data file: `_data/events.yml`. When the site builds, a Python script reads this file and generates the event cards automatically. You don't need to write any HTML—just add your event to the YAML file.

### Step-by-Step: Adding a New Event

#### 1. Open the events data file

Open `_data/events.yml` in your text editor. You'll see a list of existing events.

#### 2. Add your event entry

Add a new event to the `events` list. Each event requires the following fields:

```yaml
  - title: "Your Event Title"
    date: "YYYY-MM-DD"
    end_date: ""
    time: "Start Time - End Time Timezone"
    location: "Venue or Platform"
    description: "A brief description of the event (1-2 sentences)."
    link: ""
    category: "workshop"
```

#### 3. Field Reference

| Field | Required | Description | Example |
|-------|----------|-------------|---------|
| `title` | Yes | The name of the event | `"Python for Beginners Workshop"` |
| `date` | Yes | Start date in `YYYY-MM-DD` format | `"2025-03-15"` |
| `end_date` | No | End date for multi-day events (leave `""` for single-day) | `"2025-03-17"` |
| `time` | Yes | Time range with timezone | `"9:00 AM - 4:00 PM PST"` |
| `location` | Yes | Physical venue or virtual platform | `"UC Berkeley, Evans Hall"` or `"Online via Zoom"` |
| `description` | Yes | Brief event description (shown on the card) | `"A hands-on introduction to Python..."` |
| `link` | No | URL to more information (leave `""` if none) | `"/posts/2025-03-15-python-workshop.html"` |
| `category` | Yes | Event type (determines badge color) | `"workshop"` |

#### 4. Category Options

Choose one of these categories for the `category` field:

| Category | Color | Use For |
|----------|-------|---------|
| `conference` | Navy blue | Multi-day conferences, large gatherings |
| `workshop` | Dark green | Hands-on training sessions, tutorials |
| `webinar` | Dark purple | Online presentations, virtual talks |
| `meetup` | Brown | Informal gatherings, networking events |
| `hackathon` | Dark red | Coding competitions, hack days |
| `other` | Gray | Anything that doesn't fit above |

#### 5. Complete Example

Here's a full example of adding a new workshop event:

```yaml
# _data/events.yml

events:
  - title: "Introduction to Data Visualization with Python"
    date: "2025-06-10"
    end_date: ""
    time: "1:00 PM - 5:00 PM PST"
    location: "Online via Zoom"
    description: "Learn to create compelling visualizations using matplotlib, seaborn, and plotly. This hands-on workshop covers best practices for effective data storytelling."
    link: "/posts/2025-06-10-data-viz-workshop.html"
    category: "workshop"

  # ... existing events below ...
```

#### 6. Multi-Day Event Example

For events spanning multiple days, use the `end_date` field:

```yaml
  - title: "California Data Science Summit 2025"
    date: "2025-09-20"
    end_date: "2025-09-22"
    time: "All Day"
    location: "Los Angeles Convention Center"
    description: "Three days of keynotes, workshops, and networking for data science educators across California."
    link: "https://example.com/summit-2025"
    category: "conference"
```

This will display as "September 20 - 22, 2025" on the event card.

#### 7. Preview your changes

Run the local development server to see your event:

```bash
quarto preview
```

Navigate to `http://localhost:3196/blog/events.html` to verify:
- Your event appears in the correct section (Upcoming or Past)
- The date, time, and location display correctly
- The category color badge is correct
- The description is readable and not cut off
- The "Learn more" link works (if you added one)

#### 8. Commit and push

Once you've verified everything looks good:

```bash
git add _data/events.yml
git commit -m "Add [Event Name] to events calendar"
git push origin your-branch-name
```

### Tips

- **Event order doesn't matter** - Events are automatically sorted by date when the page renders
- **Past events are kept** - Old events automatically move to the "Past Events" section; no need to delete them
- **Link to a blog post** - If your event has a detailed blog post, link to it using `/posts/YYYY-MM-DD-post-name.html`
- **External links work too** - You can link to external registration pages or event websites
- **Keep descriptions concise** - Aim for 1-2 sentences; longer details should go in a linked blog post

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

Contact the maintainers at [ds-help@berkeley.edu](mailto:ds-help@berkeley.edu)

---

## Project Structure

```
ca-datascience.github.io/
├── _quarto.yml              # Main Quarto configuration
├── index.qmd                # Homepage
├── blog.qmd                 # Blog listing page
├── faqs.qmd                 # FAQ page
├── _data/                   # Data files
│   └── events.yml           # Events calendar data
├── students/                # Student resources section
│   ├── index.qmd
│   └── resources.qmd
├── educators/               # Educator resources section
│   └── index.qmd
├── blog/                    # Blog subsections
│   └── events.qmd           # Events calendar page (reads from _data/events.yml)
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
