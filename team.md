---
layout: page
title: Meet the Team
permalink: /team/
---

<style>
  /* Container for the icons */
  .team-social {
    display: flex;
    gap: 8px;
    margin-top: 10px;
    flex-wrap: wrap;
  }

  /* The Button Design */
  .social-btn {
    display: inline-flex !important; /* Force flex to align icon center */
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: #f3f4f6; /* Light gray */
    color: #4b5563 !important; /* Dark gray icon */
    text-decoration: none !important; /* No underline */
    border: 1px solid #e5e7eb;
    transition: all 0.2s ease;
    box-shadow: 0 1px 2px rgba(0,0,0,0.05);
  }

  /* Hover Effects */
  .social-btn:hover {
    background-color: #1e90ff !important; /* Blue background */
    border-color: #1e90ff !important;
    color: white !important; /* White icon */
    transform: translateY(-2px);
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  }

  /* Icon Size */
  .social-btn i {
    font-size: 16px;
    line-height: 1; /* Fixes vertical alignment */
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
