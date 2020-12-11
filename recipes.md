---
title: Recipes
layout: page
permalink: /recipes/
collection: recipes
entries_layout: list
sort: date
---

{% assign tags =  site.recipes | map: 'tags' | group_by: tag %}

<ul class="taxonomy-index">
  {% for tag in tags %}
    {% assign tag_name = tag.name | replace: "[", "" | replace: "]", "" | replace: '"', '' %}
    <li>
      <a href="#{{ tag.name | slugify }}">
        <strong>{{ tag_name }}</strong> <span class="taxonomy-count">{{ tag.size }}</span>
      </a>
    </li>
  {% endfor %}
</ul>

{% for tag in tags %}
{% assign tag_name = tag.name | replace: "[", "" | replace: "]", "" | replace: '"', '' %}

<section id="{{ tag_name| slugify }}" class="taxonomy-section">
  <h2 class="taxonomy-title">{{ tag_name }}</h2>
  {% for recipe in site.recipes %}
    {% if recipe.tags contains tag_name %}
    {% assign post = recipe %}
      <div class="entries-{{ page.entries_layout | default: 'list' }}">
        {% include entry.html %}
      </div>
      <a href="#page-title" class="back-to-top">{{ site.data.text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
    {% endif %}
  {% endfor %}
</section>
{% endfor %}
