---
layout: page
title: Blog
permalink: /blog/
---

<div class="blog-list">
  <h1>Latest Posts</h1>
  
  <ul class="post-list">
    {% for post in site.posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <h2>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ post.url | relative_url }}" class="read-more">Read More</a>
    </li>
    {% endfor %}
  </ul>
</div>