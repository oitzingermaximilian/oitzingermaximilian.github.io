---
layout: page
title: Our Team
permalink: /team/
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/academicons/1.9.4/css/academicons.min.css">

<div class="team-list">
  {% for member in site.data.team %}
  <div class="team-row">
    <img src="{{ member.image }}" class="team-photo-left" alt="{{ member.name }}">
    
    <div class="team-info">
      <h3 class="team-name">{{ member.name }}</h3>
      <p class="team-role">{{ member.role }}</p>
      
      <p class="team-bio">{{ member.bio }}</p>
      
      {% if member.email %}
      <p class="team-meta" style="font-size: 0.9em; margin-top: 0.5rem;">
        📧 <a href="mailto:{{ member.email }}">{{ member.email }}</a>
      </p>
      {% endif %}

      {% if member.social_links %}
      <div class="team-social">
        {% for link in member.social_links %}
          <a href="{{ link.url }}" target="_blank" title="{{ link.platform }}" class="social-btn">
            <i class="{{ link.icon }}"></i>
          </a>
        {% endfor %}
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
