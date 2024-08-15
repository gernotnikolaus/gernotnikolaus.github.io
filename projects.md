---
layout: default
title: Projects
---

<div class="blog-list">
    {% assign sorted_projects = site.projects | sort: 'date' | reverse %}
    {% for project in sorted_projects %}
    <div class="blog-post">
        <h2 class="blog-title"><a href="{{ project.url }}">{{ project.title }}</a></h2>
        <p class="blog-preview">
            {% assign content = project.content | split: '</p>' %}
            {% if content[0] %}
                {% assign first_paragraph = content[0] | remove: '<p>' | remove: '</p>' %}
                {{ first_paragraph | strip_html | truncatewords: 150, '...' }}
            {% endif %}
        </p>
        <a class="read-more" href="{{ project.url }}">Read More</a>
        <hr class="post-divider">
    </div>
    {% endfor %}
</div>
