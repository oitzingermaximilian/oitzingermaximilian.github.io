---
title: "Meet the Team"
permalink: /team/
layout: page
---

<div class="team-list">
{% for member in site.data.team %}
  <section class="team-row" id="{{ member.id }}">
    <img src="{{ member.image }}" alt="{{ member.name }}" class="team-photo-left" />
    <div class="team-info">
      <h3 class="team-name">{{ member.name }}</h3>
      {% if member.role %}<p class="team-role">{{ member.role }}</p>{% endif %}
      <ul class="team-meta">
        {% if member.email %}<li>Email: <a href="mailto:{{ member.email }}">{{ member.email }}</a></li>{% endif %}
        {% if member.github %}<li>GitHub: <a href="https://github.com/{{ member.github }}" target="_blank">@{{ member.github }}</a></li>{% endif %}
        {% if member.twitter %}<li>Twitter/X: <a href="https://twitter.com/{{ member.twitter }}" target="_blank">@{{ member.twitter }}</a></li>{% endif %}
        {% if member.orcid %}<li>ORCID: <a href="https://orcid.org/{{ member.orcid }}" target="_blank">{{ member.orcid }}</a></li>{% endif %}
      </ul>
      {% if member.bio %}<p class="team-bio">{{ member.bio }}</p>{% endif %}
    </div>
  </section>
{% endfor %}
</div>