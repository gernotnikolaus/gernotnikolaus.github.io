---
layout: default
title: Blog
---
<div class="portfolio-grid">
  {% assign sorted_posts = site.posts | sort: 'date' | reverse %}
  {% for post in sorted_posts %}
  
  <div class="portfolio-card">

    {% if post.image %}
      <a href="{{ post.url }}">
        <img src="{{ post.image }}" class="card-image">
      </a>
    {% endif %}

    <div class="card-content">
      <h3>
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h3>

      <p class="card-meta">
        {{ post.date | date: "%b %Y" }}
      </p>

      <p class="card-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 25 }}
      </p>

      {% if post.tags %}
      <div class="card-tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}

      <a href="{{ post.url }}" class="read-more">Read more →</a>
    </div>

  </div>

  {% endfor %}
</div>
