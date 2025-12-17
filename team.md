---
title: "Meet the Team"
layout: single
permalink: /team/
---

<style>
  .team-list { display: grid; gap: 1.5rem; }
  
  .team-row {
    display: flex;
    align-items: flex-start;
    gap: 1.5rem;
    padding: 1.5rem;
    border-radius: 8px;
    background: #fff; /* White card background */
    box-shadow: 0 2px 5px rgba(0,0,0,0.05); /* Soft shadow */
    border: 1px solid #eee;
  }

  .team-photo-left {
    width: 120px;
    height: 120px;
    object-fit: cover;
    border-radius: 50%; /* Circular Image */
    flex-shrink: 0;
  }

  .team-info { flex: 1; }
  .team-name { margin-top: 0; margin-bottom: 0.25rem; font-size: 1.5em; }
  .team-role { color: #666; font-weight: bold; margin-bottom: 0.5rem; }
  .team-bio { margin-bottom: 1rem; }
  
  /* Social Button Styles */
  .team-social {
    display: flex;
    gap: 8px;
    margin-top: 10px;
    flex-wrap: wrap;
  }

  .social-btn {
    display: inline-flex !important;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: #f3f4f6;
    color: #4b5563 !important;
    text-decoration: none !important;
    border: 1px solid #e5e7eb;
    transition: all 0.2s ease;
  }

  .social-btn:hover {
    background-color: #1e90ff !important;
    border-color: #1e90ff !important;
    color: white !important;
    transform: translateY(-2px);
  }

  .social-btn i { font-size: 16px; }

  /* Mobile Adjustments */
  @media (max-width: 600px) {
    .team-row { flex-direction: column; text-align: center; align-items: center; }
    .team-social { justify-content: center; }
  }
</style>

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
      <p class="team-meta" style="font-size: 0.9em; margin-top: 0.5rem; margin-bottom: 0.5rem;">
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
