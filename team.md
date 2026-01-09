---
title: "Meet the Team"
layout: splash
permalink: /team/
header:
  overlay_color: "#fff"
---

<style>
  /* --- 1. LAYOUT & WIDTH FIXES --- */
  
  /* Make the container MASSIVE (Wide!) */
  .page__inner-wrap {
    float: none !important;
    margin: 0 auto !important;
    width: 95% !important;       /* Uses 95% of the screen */
    max-width: 1900px !important; /* Cap it at 1900px (very wide) */
    padding-right: 0 !important;
  }

  .page__content {
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    float: none !important;
  }
  
  /* HIDE the theme's default duplicate title (The white one) */
  .page__title, .page__hero-caption, .page__hero-title {
    display: none !important;
  }

  /* --- 2. TEAM CARD STYLING --- */
  .team-list {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    width: 100%;
    margin-top: 2rem;
  }

  .team-row {
    display: flex;
    flex-direction: row; 
    align-items: center; 
    gap: 3rem;           
    width: 100%;
  }

  /* PHOTO: Fixed width */
  .team-photo-left {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 50%;
    flex-shrink: 0;
    background-color: #fff;
    border: 5px solid #fff;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }

  /* INFO BOX: Fills the rest of the row */
  .team-info {
    flex: 1;             
    background: #fff;
    padding: 3rem;       /* Increased padding slightly */
    border-radius: 12px;
    border: 1px solid #e5e7eb;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    position: relative;
  }

  /* Speech Bubble Arrow */
  .team-info::before {
    content: "";
    position: absolute;
    left: -10px;
    top: 50%;
    transform: translateY(-50%);
    border-width: 10px 10px 10px 0;
    border-style: solid;
    border-color: transparent #e5e7eb transparent transparent;
  }
  .team-info::after {
    content: "";
    position: absolute;
    left: -9px;
    top: 50%;
    transform: translateY(-50%);
    border-width: 10px 10px 10px 0;
    border-style: solid;
    border-color: transparent #fff transparent transparent;
  }

  /* TEXT STYLES */
  .team-name { margin-top: 0; margin-bottom: 0.25rem; font-size: 1.8em; line-height: 1.2; }
  .team-role { color: #1e90ff; font-weight: 700; margin-bottom: 0.75rem; text-transform: uppercase; font-size: 0.9em; letter-spacing: 0.5px; }
  .team-bio { margin-bottom: 1.5rem; line-height: 1.6; color: #4b5563; font-size: 1.05em; }
  
  .team-email {
    margin-bottom: 1.25rem;
    font-size: 0.95em;
    padding-top: 1rem;
    border-top: 1px solid #f0f0f0;
  }
  .email-label { font-weight: 600; color: #333; margin-right: 5px; }

  /* SOCIAL ICONS */
  .team-social { display: flex; gap: 10px; flex-wrap: wrap; }
  .social-btn {
    display: inline-flex !important;
    align-items: center;
    justify-content: center;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    background-color: #f8f9fa;
    color: #555 !important;
    text-decoration: none !important;
    border: 1px solid #e9ecef;
    transition: all 0.2s ease;
  }
  .social-btn:hover {
    background-color: #1e90ff !important;
    border-color: #1e90ff !important;
    color: white !important;
    transform: translateY(-3px);
  }
  .social-btn i { font-size: 16px; }

  /* MOBILE: Stack vertically */
  @media (max-width: 900px) {
    .team-row { flex-direction: column; text-align: center; gap: 1.5rem; }
    .team-photo-left { margin-bottom: -40px; z-index: 2; position: relative; width: 150px; height: 150px; }
    .team-info { width: 100%; padding-top: 50px; }
    .team-info::before, .team-info::after { display: none; }
    .team-social { justify-content: center; }
  }
</style>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/academicons/1.9.4/css/academicons.min.css">

<h1 style="text-align: center; margin-bottom: 2rem; color: #1e90ff; font-weight: bold;">Meet the Team</h1>

<div class="team-list">
  {% for member in site.data.team %}
  <div class="team-row">
    <img src="{{ member.image }}" class="team-photo-left" alt="{{ member.name }}" onerror="this.style.display='none'">
    
    <div class="team-info">
      <h3 class="team-name">{{ member.name }}</h3>
      <p class="team-role">{{ member.role }}</p>
      
      <p class="team-bio">{{ member.bio }}</p>
      
      {% if member.email %}
      <div class="team-email">
        <span class="email-label">Email:</span>
        <a href="mailto:{{ member.email }}">{{ member.email }}</a>
      </div>
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
