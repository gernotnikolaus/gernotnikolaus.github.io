---
layout: default
title: Projects
---

<div class="gallery-container">
  {% for image in site.static_files %}
    {% if image.path contains '/assets/images/projects/' %}
      {% assign img_name = image.path | split: '/' | last %}
      {% assign img_desc = site.data.image_descriptions[img_name] %}
      
      <div class="gallery-item">
        <img src="{{ image.path }}" alt="{{ image.name }}" onclick="openModal('{{ image.path }}', '{{ img_desc | escape }}')">
      </div>
      
    {% endif %}
  {% endfor %}
</div>

<!-- Fullscreen Modal -->
<div id="imageModal">
  <span onclick="closeModal()">&times;</span>
  <img id="modalImage">
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
