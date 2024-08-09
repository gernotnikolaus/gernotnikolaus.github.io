---
layout: default
title: Projects
---

<div style="display: flex; flex-wrap: wrap; justify-content: space-around;">

  {% for image in site.static_files %}
    {% if image.path contains '/images/' %}
      {% assign img_name = image.path | split: '/' | last %}
      {% assign img_desc = site.data.image_descriptions[img_name] %}
      
      <div style="margin: 10px;">
        <img src="{{ image.path }}" alt="{{ image.name }}" style="width: 300px; cursor: pointer;" onclick="openModal('{{ image.path }}', '{{ img_desc | escape }}')">
      </div>
      
    {% endif %}
  {% endfor %}

</div>

<!-- Fullscreen Modal -->
<div id="imageModal" style="display:none; position: fixed; z-index: 1; padding-top: 60px; left: 0; top: 0; width: 100%; height: 100%; overflow: auto; background-color: rgba(0,0,0,0.9);">
  <span style="position: absolute; top: 20px; right: 35px; color: #fff; font-size: 40px; font-weight: bold; cursor: pointer;" onclick="closeModal()">&times;</span>
  <img id="modalImage" style="margin: auto; display: block; width: 80%; max-width: 700px;">
  <div id="modalDescription" style="text-align: center; color: #fff; margin-top: 20px; font-size: 18px;"></div>
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
