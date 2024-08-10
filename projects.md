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
let scrollPosition = 0;

function openModal(src, desc, link) {
    var modal = document.getElementById("imageModal");
    var modalImg = document.getElementById("modalImage");
    var modalDesc = document.getElementById("modalDescription");
    var modalLink = document.getElementById("modalLink");

    modal.style.display = "block";
    modalImg.src = src;
    modalDesc.textContent = desc || "No description available.";
    modalLink.innerHTML = link || ""; // Use innerHTML to allow HTML content

    // Disable scrolling by fixing the body position
    scrollPosition = window.pageYOffset;
    document.body.style.position = 'fixed';
    document.body.style.top = `-${scrollPosition}px`;
    document.body.style.width = '100%';
}

function closeModal() {
    var modal = document.getElementById("imageModal");
    modal.style.display = "none";
    
    // Re-enable scrolling by restoring the body position
    document.body.style.position = '';
    document.body.style.top = '';
    window.scrollTo(0, scrollPosition);
}

// Close the modal when clicking outside the image
document.getElementById("imageModal").addEventListener('click', function(event) {
    if (event.target === this) {
        closeModal();
    }
});
</script>
