---
layout: default
title: Projects
---

<div class="gallery">
{% assign images = site.static_files | where: "path", "/assets/images/projects/" %}
{% for image in images %}
  <div class="gallery-item">
    <img src="{{ image.path | relative_url }}" alt="Project Image">
  </div>
{% endfor %}
</div>
