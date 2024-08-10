---
layout: default
title: Projects
---

<div class="filter-buttons">
  <button class="filter-button" data-filter="all">All</button>
  {% assign all_hashtags = "" %}
  {% for item in site.data.hashtags %}
    {% for hashtag in item.hashtags %}
      {% unless all_hashtags contains hashtag %}
        <button class="filter-button" data-filter="{{ hashtag }}">{{ hashtag }}</button>
        {% assign all_hashtags = all_hashtags | append: hashtag | append: "," %}
      {% endunless %}
    {% endfor %}
  {% endfor %}
</div>

<div class="gallery-container">
  {% assign images = site.data.hashtags %}
  {% assign reversed_images = images | reverse %}

  {% for item in reversed_images %}
    {% assign img_path = item.path %}
    {% assign img_hashtags = item.hashtags %}
    {% assign img_description = item.description %}

    <div class="gallery-item" data-hashtags="{{ img_hashtags | join: ',' }}" data-description="{{ img_description }}">
      <img src="{{ img_path }}" alt="Image" onclick="openModal('{{ img_path }}', '{{ img_description | escape }}')">
    </div>
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

document.querySelectorAll('.filter-button').forEach(button => {
  button.addEventListener('click', function() {
    var filter = this.getAttribute('data-filter');
    document.querySelectorAll('.gallery-item').forEach(item => {
      if (filter === 'all' || item.getAttribute('data-hashtags').includes(filter)) {
        item.style.display = 'block';
      } else {
        item.style.display = 'none';
      }
    });
  });
});
</script>

<style>
.filter-buttons {
  margin-bottom: 20px;
}

.filter-button {
  margin: 5px;
  padding: 10px;
  border: none;
  background-color: #ddd;
  cursor: pointer;
}

.filter-button:hover {
  background-color: #ccc;
}
</style>
