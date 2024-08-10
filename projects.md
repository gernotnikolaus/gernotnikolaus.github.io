<div class="gallery-container">
  {% for image in site.static_files %}
    {% if image.path contains '/assets/images/projects/' %}
      {% assign img_name = image.path | split: '/' | last %}
      {% assign img_desc = site.data.image_descriptions[img_name] %}
      
      <div class="gallery-item">
        <p>{{ img_name }}</p>  <!-- Output the image name -->
        <p>{{ img_desc }}</p>  <!-- Output the description -->
        <img src="{{ image.path }}" alt="{{ image.name }}" onclick="openModal('{{ image.path }}', '{{ img_desc | escape }}')">
      </div>
      
    {% endif %}
  {% endfor %}
</div>
