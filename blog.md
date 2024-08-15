---
layout: default
title: Blog
---

<div class="blog-list">
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
    {% for post in sorted_posts %}
    <div class="blog-post">
        <h2 class="blog-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p class="blog-preview">
            {% assign content = post.content | split: '</p>' %}
            {% if content[0] %}
                {% assign first_paragraph = content[0] | remove: '<p>' | remove: '</p>' %}
                {{ first_paragraph | strip_html | truncatewords: 150, '...' }}
            {% endif %}
        </p>
        <a class="read-more" href="{{ post.url }}">Read More</a>
        <hr class="post-divider">
    </div>
    {% endfor %}
</div>
