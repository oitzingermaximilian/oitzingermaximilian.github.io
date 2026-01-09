---
title: "Meet the Team"
layout: single
permalink: /team/
classes: wide
---

<style>
  /* 1. FORCE WIDE LAYOUT */
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1200px !important;
    margin: 0 auto !important;
    padding-right: 0 !important;
  }
  
  /* HIDE THE PAGE TITLE */
  .page__title { display: none; }

  /* Main Grid Container */
  .team-list { 
    display: flex; 
    flex-direction: column; 
    gap: 2rem; 
    width: 100%;
    margin-top: 2rem;
  }
  
  /* The Container */
  .team-row {
    display: flex;
    align-items: center; 
    gap: 2rem;           
    padding: 0;          
    border: none;
    background: transparent;
    box-shadow: none;
    scroll-margin-top: 100px; 
  }

  /* The Image - Floating Outside */
  .team-photo-left {
    width: 170px;        
    height: 170px;
    object-fit: cover;
    border-radius: 50%;
    flex-shrink: 0;
    background-color: #fff;
    border: 5px solid #fff; 
    box-shadow: 0 4px 10px rgba(0,0,0,0.1); 
  }

  /* The Text Card */
  .team-info { 
    flex: 1; 
    min-width: 0;
    background: #fff;
    padding: 2rem;       
    border-radius: 12px; 
    border: 1px solid #e5e7eb;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    position: relative;
    
    /* --- RESTORED: LEFT ALIGNMENT --- */
    text-align: left; 
  }

  /* Typography */
  .team-name { margin-top: 0; margin-bottom: 0.25rem; font-size: 1.6em; line-height: 1.2; }
  .team-role { color: #1e90ff; font-weight: 700; margin-bottom: 0.75rem; text-transform: uppercase; font-size: 0.85em; letter-spacing: 0.5px; }
  .team-bio { margin-bottom: 1.5rem; line-height: 1.6; color: #4b5563; }
  
  /* Email Styling */
  .team-email {
    margin-bottom: 1.25rem;
    font-size: 0.95em;
    padding-top: 1rem;
    border-top: 1px solid #f0f0f0; 
  }
  .email-label {
    font-weight: 600;
    color: #333;
    margin-right: 5px;
  }

  /* Social Button Styles */
  .team-social {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    /* --- RESTORED: LEFT ALIGNMENT --- */
    justify-content: flex-start;
  }

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
  @media (max-width: 768px) {
    .team-row { 
      flex-direction: column; 
      text-align: center; 
      gap: 1rem;
    }
    .team-photo-left {
      width: 140px; 
      height: 140px;
      margin-bottom: -40px; 
      z-index: 2; 
      position: relative;
    }
    .team-info { width: 100%; padding-top: 50px; text-align: center; }
    
    /* Keep centered on mobile for better look */
    .team-social { justify-content: center; }
    .team-email { justify-content: center; display: flex; } 
  }
</style>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/academicons/1.9.4/css/academicons.min.css">

<div class="team-list">
  {% for member in site.data.team %}
  <div class="team-row" id="{{ member.id }}">
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
