---
layout: default
title: Blog
---

<div class="blog-list">
    {% for post in site.posts %}
    <div class="blog-post">
        <h2 class="blog-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <a class="read-more" href="{{ post.url }}">Read More</a>
        <hr class="post-divider">
    </div>
    {% endfor %}
</div>