---
title: "Our Work"
permalink: /publications/
layout: page
---

<div class="work-list">
{% for pub in site.data.publications %}
  <article class="work-item">
    <h3 class="work-title">
      {{ pub.title }}{% if pub.year %} <span class="work-year">({{ pub.year }})</span>{% endif %}
    </h3>
    {% if pub.authors %}<p class="work-authors">{{ pub.authors }}</p>{% endif %}
    {% if pub.doi %}
      <p class="work-links">DOI: <a href="{{ pub.url | default: 'https://doi.org/' | append: pub.doi }}" target="_blank">{{ pub.doi }}</a></p>
    {% endif %}
    {% if pub.description %}<p class="work-desc">{{ pub.description }}</p>{% endif %}
  </article>
{% endfor %}
</div>
