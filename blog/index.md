---
layout: default
title: Blog
---

<h1>Blog</h1>

{% for post in site.posts %}
  <div class="blog-item">
    <a class="blog-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="blog-date">{{ post.date | date: "%b %-d, %Y" }}</span>
  </div>
{% endfor %}
