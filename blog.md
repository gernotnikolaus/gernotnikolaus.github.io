---
layout: default
title: Blog
---
<div class="blog-list">
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% for post in sorted_posts %}
  <div class="blog-post">

    {% if post.image %}
      <img src="{{ post.image }}" class="blog-image">
    {% endif %}

    <h2 class="blog-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>

    <p class="blog-meta">
      {{ post.date | date: "%B %d, %Y" }}
    </p>

    <p class="blog-preview">
      {{ post.excerpt | strip_html | truncatewords: 40 }}
    </p>

    <a class="read-more" href="{{ post.url }}">Read More</a>

    <hr class="post-divider">
  </div>
{% endfor %}
</div>
