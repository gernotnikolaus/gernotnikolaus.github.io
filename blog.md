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
    <button onclick="filterCategory('personal')">Personal</button>
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

<div class="portfolio-grid">

  {% for post in site.posts %}

  <div class="portfolio-card {{ post.categories | first }}"
       data-category="{{ post.categories | first }}"
       data-tags="{{ post.tags | join: ' ' }}">

    {% if post.image %}
      <a href="{{ post.url }}">
        <img src="{{ post.image }}" class="card-image">
      </a>
    {% endif %}

    <div class="card-content">
      <h3>
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h3>

      <p class="card-meta">
        {{ post.date | date: "%b %Y" }} · {{ post.categories | first }}
      </p>

      <p class="card-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 25 }}
      </p>

      {% if post.tags %}
      <div class="card-tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}

      <a href="{{ post.url }}" class="read-more">Read more →</a>
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

  document.querySelectorAll('.portfolio-card').forEach(card => {

    let category = card.dataset.category;
    let tags = card.dataset.tags;

    let categoryMatch = (activeCategory === "all" || category === activeCategory);

    let tagMatch = selectedTags.length === 0 ||
      selectedTags.every(tag => tags.includes(tag));

    if (categoryMatch && tagMatch) {
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }

  });
}
</script>