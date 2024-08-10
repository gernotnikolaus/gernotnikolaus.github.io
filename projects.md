---
layout: default
title: Projects
---

<div class="gallery-container">
  {% assign images = site.data.image_data %}
  {% assign reversed_images = images | reverse %}

  {% for item in reversed_images %}
    {% assign img_path = item.path %}
    {% assign img_description = item.description %}
    {% assign img_link = item.link %}

    <div class="gallery-item">
      <img src="{{ img_path }}" alt="Image" onclick="openModal('{{ img_path }}', '{{ img_description | escape }}', '{{ img_link | escape }}')">
    </div>
  {% endfor %}
</div>

<!-- Fullscreen Modal -->
<div id="imageModal">
  <span onclick="closeModal()" id="closeModal">&times;</span>
  <div id="modalContent">
    <img id="modalImage">
    <div id="modalDescription"></div>
    <div id="modalLink"></div>
  </div>
</div>

<script>
function openModal(src, desc, link) {
    var modal = document.getElementById("imageModal");
    var modalImg = document.getElementById("modalImage");
    var modalDesc = document.getElementById("modalDescription");
    var modalLink = document.getElementById("modalLink");

    modal.style.display = "block";
    modalImg.src = src;
    modalDesc.textContent = desc || "No description available.";
    modalLink.innerHTML = link || ""; // Use innerHTML to allow HTML content
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