---
title: "Meet the Team"
layout: splash
permalink: /team/
header:
  overlay_color: "#fff"
  overlay_filter: 0
---

<style>
  /* 1. HIDE DEFAULT TITLES */
  .page__title { display: none !important; }
  
  /* 2. LAYOUT FIXES */
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1200px !important;
    margin: 0 auto !important;
    padding: 0 !important;
  }
  
  .page__content {
    width: 100% !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* 3. MAIN LIST CONTAINER */
  .team-list { 
    display: flex; 
    flex-direction: column; 
    /* Gap between different team members */
    gap: 3rem; 
    width: 100%;
    margin-top: 3rem;
    padding-bottom: 3rem;
  }
  
  /* 4. THE ROW (Image + Card Wrapper) */
  .team-row {
    display: flex;
    align-items: center; 
    justify-content: center;
    
    /* This creates the space between the Picture and the Box */
    gap: 3rem; 
    
    max-width: 100%; 
    margin: 0 auto;
    scroll-margin-top: 100px; 
  }

  /* 5. THE IMAGE */
  /* 5. THE IMAGE WRAPPER (Enforces Circle) */
  .team-photo-wrapper {
    width: 180px;        
    height: 180px;
    border-radius: 50%;
    flex-shrink: 0; 
    
    background-color: #fff;
    /* Clean border, no overlap shadows */
    border: 5px solid #fff; 
    box-shadow: 0 0 0 1px rgba(0,0,0,0.1), 0 4px 10px rgba(0,0,0,0.1); 
    
    /* MASKING: This cuts off anything outside the circle */
    overflow: hidden;
    position: relative;
    
    /* Removed negative margin - Image stands alone now */
    margin: 0; 
  }

  /* The actual image inside */
  .team-photo-img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Crucial: crops to fill */
    object-position: center;
    display: block;
  }

  /* 6. THE TEXT CARD */
  .team-info { 
    flex: 1; 
    min-width: 0; /* Prevents flexbox issues */
    background: #fff;
    
    /* RESTORED STANDARD PADDING (No need to push text for image) */
    padding: 2.5rem;       
    
    border-radius: 12px; 
    border: 1px solid #e5e7eb;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    position: relative;
    
    /* RESTORED LEFT ALIGNMENT */
    text-align: left; 
  }

  /* Typography */
  .team-name { margin-top: 0; margin-bottom: 0.25rem; font-size: 1.75em; line-height: 1.2; }
  .team-role { color: #1e90ff; font-weight: 700; margin-bottom: 1rem; text-transform: uppercase; font-size: 0.85em; letter-spacing: 0.5px; }
  
  .team-bio { 
    margin-bottom: 1.5rem; 
    line-height: 1.7; 
    color: #4b5563; 
    font-size: 1.05rem;
    /* Back to Left Align */
    text-align: left; 
  }
  
  /* Email Styling */
  .team-email {
    margin-bottom: 1.25rem;
    font-size: 0.95em;
    padding-top: 1rem;
    border-top: 1px solid #f0f0f0; 
    display: flex;
    align-items: center;
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
      gap: 1.5rem; /* Vertical gap on mobile */
      margin-bottom: 3rem;
    }
    
    .team-photo-wrapper {
      width: 140px; 
      height: 140px;
    }
    
    .team-info { 
      width: 100%; 
      padding: 2rem; 
      text-align: center; 
    }

    .team-bio { text-align: center; }
    .team-social { justify-content: center; }
    .team-email { justify-content: center; } 
  }
</style>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/academicons/1.9.4/css/academicons.min.css">

<div class="team-list">
  {% for member in site.data.team %}
  <div class="team-row" id="{{ member.id }}">
    <div class="team-photo-wrapper">
      <img src="{{ member.image }}" class="team-photo-img" style="object-position: {{ member.object_position | default: 'center' }};" alt="{{ member.name }}" onerror="this.style.display='none'">
    </div>
    
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
