---
layout: default
title: Blog
---

<div class="filter-container">

  <!-- CATEGORY FILTER -->
  <div class="category-filters">
    <button onclick="filterCategory('all')">All</button>
    <button onclick="filterCategory('project')">Projects</button>
    <button onclick="filterCategory('experience')">Experience</button>
    <button onclick="filterCategory('insight')">Insights</button>
  </div>

  <!-- TAG FILTER -->
  <div class="tag-filters">
    <label><input type="checkbox" value="climate"> Climate</label>
    <label><input type="checkbox" value="humanitarian"> Humanitarian</label>
    <label><input type="checkbox" value="health"> Health</label>
    <label><input type="checkbox" value="fieldwork"> Fieldwork</label>
    <label><input type="checkbox" value="biodiversity"> Biodiversity</label>
    <label><input type="checkbox" value="risk"> Risk</label>
  </div>

</div>

<div class="portfolio-grid" id="portfolio">

  {% for post in site.posts %}
  <div class="card"
       data-category="{{ post.categories | join: ' ' }}"
       data-tags="{{ post.tags | join: ' ' }}">

    {% if post.image %}
    <img src="{{ post.image }}" class="card-image">
    {% endif %}

    <div class="card-content">
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>

      <p class="meta">
        {{ post.date | date: "%b %Y" }} | {{ post.categories[0] }}
      </p>

      <p>{{ post.excerpt | strip_html | truncatewords: 20 }}</p>

      <div class="tags">
        {% for tag in post.tags %}
          <span>{{ tag }}</span>
        {% endfor %}
      </div>
    </div>

  </div>
  {% endfor %}

</div>

<script>
let activeCategory = "all";

function filterCategory(category) {
  activeCategory = category;
  applyFilters();
}

document.querySelectorAll('.tag-filters input').forEach(cb => {
  cb.addEventListener('change', applyFilters);
});

function applyFilters() {
  let selectedTags = Array.from(document.querySelectorAll('.tag-filters input:checked'))
                          .map(cb => cb.value);

  document.querySelectorAll('.card').forEach(card => {

    let cardCategory = card.dataset.category;
    let cardTags = card.dataset.tags;

    let categoryMatch = (activeCategory === "all") || cardCategory.includes(activeCategory);

    let tagMatch = selectedTags.length === 0 ||
      selectedTags.every(tag => cardTags.includes(tag));

    if (categoryMatch && tagMatch) {
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }

  });
}
</script>