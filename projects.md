---
layout: default
title: Projects
---

<div class="gallery-container">
  {% assign images = site.static_files | where: "path", "/assets/images/projects/" %}
  {% assign reversed_images = images | reverse %}

  {% for image in reversed_images %}
    {% assign img_name = image.path | split: '/' | last %}
    {% assign img_desc = img_name %} <!-- Use file name as description -->
    
    <div class="gallery-item">
      <img src="{{ image.path }}" alt="{{ image.name }}" onclick="openModal('{{ image.path }}', '{{ img_desc | escape }}')">
    </div>
  {% endfor %}
</div>

<!-- Fullscreen Modal -->
<div id="imageModal">
  <span onclick="closeModal()">&times;</span>
  <img id="modalImage" src="" alt="Modal Image">
  <div id="modalDescription"></div>
</div>

<script>
function openModal(src, desc) {
    var modal = document.getElementById("imageModal");
    var modalImg = document.getElementById("modalImage");
    var modalDesc = document.getElementById("modalDescription");
    modal.style.display = "block";
    modalImg.src = src;
    modalDesc.textContent = desc || "No description available.";
}

function closeModal() {
    var modal = document.getElementById("imageModal");
    modal.style.display = "none";
}
</script>
