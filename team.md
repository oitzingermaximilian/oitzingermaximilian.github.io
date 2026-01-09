---
title: "Meet the Team"
layout: single
permalink: /team/
classes: wide
---

<style>
  /* --- 1. FORCE FULL WIDTH (The Fix) --- */
  
  /* 1. Delete the invisible sidebar that is pushing everything right */
  .sidebar, .page__sidebar {
    display: none !important;
    width: 0 !important;
  }

  /* 2. Force the page container to be wide and centered */
  .page__inner-wrap {
    width: 100% !important;
    max-width: 1600px !important; /* Increased width to match your drawing */
    margin: 0 auto !important;
    padding: 0 2rem !important;   /* Adds a little safety space on the sides */
  }

  /* 3. Allow content to fill the new wide container */
  .page__content {
    width: 100% !important;
    max-width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
    float: none !important;
  }

  /* --- 2. ROW LAYOUT (Photo Left, Text Wide) --- */

  .team-list {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    width: 100%;
  }

  .team-row {
    display: flex;
    flex-direction: row; /* Forces side-by-side layout */
    align-items: center; /* Vertically centers the photo with the text */
    gap: 3rem;           /* Gap between photo and text */
    width: 100%;
  }

  /* Photo Styles */
  .team-photo-left {
    width: 200px;        /* Made slightly bigger to match wide layout */
    height: 200px;
    object-fit: cover;
    border-radius: 50%;
    flex-shrink: 0;      /* Prevents photo from getting squished */
    
    background-color: #fff;
    border: 5px solid #fff;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }

  /* Text Card Styles */
  .team-info {
    flex: 1;             /* This is key: tells text to fill ALL remaining space */
    min-width: 0;        /* Prevents overflow issues */
    
    background: #fff;
    padding: 2.5rem;     /* More padding for the wider look */
    border-radius: 12px;
    border: 1px solid #e5e7eb;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    position: relative;
  }

  /* Arrow pointing to photo */
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

  /* Typography */
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

  /* Mobile Adjustments */
  @media (max-width: 900px) {
    .team-row { 
      flex-direction: column; 
      text-align: center; 
      gap: 1.5rem;
    }
    .team-photo-left {
      width: 150px; 
      height: 150px;
      margin-bottom: -40px; 
      z-index: 2; 
      position: relative;
    }
    .team-info { 
      width: 100%; 
      padding-top: 50px; 
    }
    .team-info::before, .team-info::after { display: none; }
    .team-social { justify-content: center; }
  }
</style>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/academicons/1.9.4/css/academicons.min.css">

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
