---
permalink: /publications/
layout: single
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

    {% assign abstract = pub.abstract | default: pub.description %}
    {% if abstract %}
      <details class="work-abstract">
        <summary>Abstract</summary>
        <div class="work-abstract-body">
          {{ abstract }}
        </div>
      </details>
    {% endif %}
  </article>
{% endfor %}
</div>
