---
layout: default
title: Gallery
---

<div class="gallery-container">
  {% assign images = site.data.image_data %}
  {% assign reversed_images = images | reverse %}

  {% for item in reversed_images %}
    {% assign img_path = item.path %}
    {% assign img_description = item.description %}

    <div class="gallery-item">
      <img src="{{ img_path }}" alt="Image" onclick="openModal('{{ img_path }}', '{{ img_description | escape }}')">
    </div>
  {% endfor %}
</div>

<!-- Fullscreen Modal -->
<div id="imageModal">
  <span onclick="closeModal()">&times;</span>
  <div id="modalContent">
    <img id="modalImage">
    <div id="modalDescription"></div>
  </div>
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

// Close the modal when clicking outside the image
document.getElementById("imageModal").addEventListener('click', function(event) {
    if (event.target === this) {
        closeModal();
    }
});
</script>
