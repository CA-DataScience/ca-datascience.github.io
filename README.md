# Data Science Education Portal

A Jekyll-based website providing educational resources for data science students and educators.

## Managing FAQs

The website includes a simple FAQ section using markdown headers and paragraphs.

### Structure of an FAQ Item

Each FAQ consists of a level 2 heading (##) followed by paragraph text:

```markdown
## Your Question Here?
Your detailed answer goes here. You can include multiple paragraphs if needed.
```

### How to Add a New FAQ

1. Open the `/faqs.md` file
2. Add a new section with a level 2 heading (##) for your question
3. Write the answer as paragraph text directly below the heading
4. Save the file

### Customizing the FAQ Appearance

The styling for the FAQ section is defined in `assets/css/style.scss`. You can modify:

- Colors: Change the heading colors
- Spacing: Adjust margins and padding
- Typography: Modify the font size or weight

## Adding Blog Posts

This site uses Jekyll's built-in blogging system. To add a new blog post:

### 1. Create a New File in the `_posts` Directory

Create a new Markdown file in the `_posts` directory with the following naming convention:

```
YYYY-MM-DD-title-with-hyphens.markdown
```

For example:
- `2025-05-01-introduction-to-pandas.markdown`
- `2025-05-15-data-visualization-techniques.markdown`

### 2. Add Front Matter

Each post must begin with YAML front matter (metadata). Use this template:

```yaml
---
layout: post
title:  "Your Post Title Here"
date:   YYYY-MM-DD HH:MM:SS -0700
categories: category1 category2
---
```

Example:
```yaml
---
layout: post
title:  "Introduction to Pandas"
date:   2025-05-01 10:00:00 -0700
categories: python tutorials
---
```

The categories are optional and can be customized based on your post content.

### 3. Write Your Content

After the front matter, write your post content using Markdown. Jekyll supports:

- Headers (# ## ###)
- Lists (- or 1. 2. 3.)
- Code blocks (```python)
- Links
- Images

### 4. Add Code Snippets (Optional)

Jekyll has built-in support for code highlighting:

```
{% highlight python %}
import pandas as pd
df = pd.read_csv('data.csv')
print(df.head())
{% endhighlight %}
```

### 5. Preview Your Post

To preview your post locally:

1. Install Jekyll if you haven't already:
   ```
   gem install jekyll bundler
   ```

2. Run the Jekyll server:
   ```
   bundle exec jekyll serve
   ```

3. View your site at `http://localhost:4000`

### 6. Publishing

Once you're satisfied with your post:

1. Commit the new file to the repository
2. Push to the main branch
3. GitHub Pages will automatically deploy your changes

Your post will appear on the Blog page, accessible from the homepage.
