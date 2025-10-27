---
title: "Team"
permalink: /team/
layout: page
---

<style>
.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill,minmax(220px,1fr));
  gap: 1.25rem;
  margin-top: 1rem;
}
.team-card {
  padding: 1rem;
  border-radius: 8px;
  background: var(--color-canvas, #fff);
  box-shadow: var(--shadow-depth-1, 0 1px 3px rgba(0,0,0,0.08));
  text-align: center;
}
.team-photo {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: 50%;
  margin-bottom: 0.5rem;
}
.team-links a { margin: 0 0.25rem; font-size: 0.95rem; }
.role { color: var(--type-muted); margin-top: 0.25rem; font-weight:600; }
</style>

<div class="team-grid">
{% for member in site.data.team %}
  <article class="team-card" id="{{ member.id }}">
    <img src="{{ member.image }}" alt="{{ member.name }}" class="team-photo" />
    <h3>{{ member.name }}</h3>
    <div class="role">{{ member.role }}</div>
    <p>{{ member.bio }}</p>
    <p class="team-links">
      {% if member.github %}<a href="https://github.com/{{ member.github }}" target="_blank">GitHub</a>{% endif %}
      {% if member.twitter %}<a href="https://twitter.com/{{ member.twitter }}" target="_blank">Twitter</a>{% endif %}
      {% if member.orcid %}<a href="https://orcid.org/{{ member.orcid }}" target="_blank">ORCID</a>{% endif %}
      {% if member.email %}<a href="mailto:{{ member.email }}">Email</a>{% endif %}
    </p>
  </article>
{% endfor %}
</div>
