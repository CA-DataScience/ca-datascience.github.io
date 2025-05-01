---
layout: page
title: Link Examples
permalink: /link-examples/
---

## Proper Link Formatting for GitHub Pages

When creating links in Jekyll for GitHub Pages, use the `relative_url` filter for internal links:

```html
<!-- For internal pages -->
<a href="{{ '/data-science/' | relative_url }}">Data Science</a>

<!-- For assets like CSS or images -->
<img src="{{ '/assets/images/example.jpg' | relative_url }}" alt="Example">

<!-- For blog posts -->
<a href="{{ '/jekyll/update/2025/04/23/welcome-to-jekyll.html' | relative_url }}">Welcome Post</a>
```

This ensures your links work properly both locally and when deployed to GitHub Pages.