---
layout: default
title: Projects
---

<div class="gallery-container">
  {% for image in site.static_files %}
    {% if image.path contains '/assets/images/projects/' %}
      {% assign img_name = image.path | split: '/' | last %}
      
      <div class="gallery-item">
        <img src="{{ image.path }}" alt="{{ img_name }}" onclick="openModal('{{ image.path }}', '{{ img_name | escape }}')">
      </div>
      
    {% endif %}
  {% endfor %}
</div>

<!-- Fullscreen Modal -->
<div id="imageModal" style="display:none;">
  <span onclick="closeModal()" style="cursor:pointer;">&times;</span>
  <img id="modalImage" style="display:block; margin:auto; max-width:80%;">
  <div id="modalDescription" style="color:#fff; text-align:center; margin-top:20px;"></div>
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
