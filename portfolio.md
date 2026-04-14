---
layout: default
title: Portfolio
---

<div class="filter-container">

  <!-- CATEGORY FILTER -->
  <div class="category-filters">
    <button class="filter-btn all active" onclick="filterCategory('all')">All</button>
    <button class="filter-btn project" onclick="filterCategory('project')">Projects</button>
    <button class="filter-btn experience" onclick="filterCategory('experience')">Experience</button>
    <button class="filter-btn insight" onclick="filterCategory('insight')">Insights</button>
    <button class="filter-btn personal" onclick="filterCategory('personal')">Personal</button>
  </div>

</div>


<div class="portfolio-grid">

  {% for post in site.posts %}

  <a href="{{ post.url }}"
     class="portfolio-card {{ post.categories | first }}"
     data-category="{{ post.categories | first }}"
     data-tags="{{ post.tags | join: ' ' }}">

    {% if post.image %}
      <img src="{{ post.image }}" class="card-image">
    {% endif %}

    <div class="card-content">

      <h3>{{ post.title }}</h3>

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

    </div>

  </a>

  {% endfor %}

</div>


<script>

let activeCategory = "all";

/* ---------------------------
   CATEGORY FILTER
---------------------------- */
function filterCategory(category) {
  activeCategory = category;

  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.classList.remove('active');
  });

  document.querySelector(`.filter-btn.${category}`)?.classList.add('active');

  applyFilters();
}


/* ---------------------------
   TAG FILTER (checkboxes optional)
---------------------------- */
document.querySelectorAll('.tag-filters input')?.forEach(cb => {
  cb.addEventListener('change', applyFilters);
});


/* ---------------------------
   MAIN FILTER FUNCTION
---------------------------- */
function applyFilters() {

  let selectedTags = Array.from(document.querySelectorAll('.tag-filters input:checked'))
                          .map(cb => cb.value);

  document.querySelectorAll('.portfolio-card').forEach(card => {

    let category = card.dataset.category || "";
    let tags = card.dataset.tags || "";

    let categoryMatch =
      (activeCategory === "all" || category === activeCategory);

    let tagMatch =
      (selectedTags.length === 0 ||
       selectedTags.every(tag => tags.includes(tag)));

    card.style.display = (categoryMatch && tagMatch) ? "block" : "none";
  });

}

</script>