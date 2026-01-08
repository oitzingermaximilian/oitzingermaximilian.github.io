---
title: "Meet the Team"
layout: single
permalink: /team/
---

<style>
    /* Force the main content container to be wider just for this page */
  .page__inner-wrap {
    width: 100% !important;
    max-width: 1200px !important; /* Increases max-width from the default narrow column */
    margin-left: auto;
    margin-right: auto;
  }
  
  /* Sometimes themes use these classes instead, it doesn't hurt to include them */
  .wrapper, .page__content {
    max-width: 1200px !important;
  }
  /* Main Grid Container */
  .team-list { 
    display: flex; 
    flex-direction: column; 
    gap: 2rem; /* Increased gap between people */
    width: 100%;
  }
  
  /* The Container (Transparent now, just holds Image + Card) */
  .team-row {
    display: flex;
    align-items: center; /* Vertically center the image with the card */
    gap: 2rem;           /* Space between the floating image and the text card */
    padding: 0;          /* No padding on the container itself */
    border: none;
    background: transparent;
    box-shadow: none;
  }

  /* The Image - Floating Outside */
  .team-photo-left {
    width: 170px;        /* Big Portrait */
    height: 170px;
    object-fit: cover;
    border-radius: 50%;
    flex-shrink: 0;
    
    /* Make the image pop out */
    background-color: #fff;
    border: 5px solid #fff; /* Thick white border looks pro */
    box-shadow: 0 4px 10px rgba(0,0,0,0.1); /* Shadow for depth */
  }

  /* The Text Card - The "Panel" */
  .team-info { 
    flex: 1; 
    min-width: 0;
    
    /* This creates the White Box look */
    background: #fff;
    padding: 2rem;       /* Spacious padding inside the box */
    border-radius: 12px; /* Smoother corners */
    border: 1px solid #e5e7eb;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    position: relative;  /* Ready for advanced styling */
  }

  /* (Optional) A tiny arrow pointing to the image to make it look like a speech bubble */
  /* Remove this block if you don't like the arrow effect */
  .team-info::before {
    content: "";
    position: absolute;
    left: -10px;         /* Position on the left edge */
    top: 50%;
    transform: translateY(-50%);
    border-width: 10px 10px 10px 0;
    border-style: solid;
    border-color: transparent #e5e7eb transparent transparent; /* Arrow Border color */
  }
  .team-info::after {
    content: "";
    position: absolute;
    left: -9px;          /* Position overlay to hide border */
    top: 50%;
    transform: translateY(-50%);
    border-width: 10px 10px 10px 0;
    border-style: solid;
    border-color: transparent #fff transparent transparent; /* Arrow Fill color */
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
    border-top: 1px solid #f0f0f0; /* Separator line above email */
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
    box-shadow: 0 4px 6px rgba(30, 144, 255, 0.25);
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
      width: 140px; /* Slightly smaller on mobile */
      height: 140px;
      margin-bottom: -40px; /* Pull the image down into the card slightly */
      z-index: 2; /* Ensure image sits on top */
      position: relative;
    }

    .team-info { 
      width: 100%; 
      padding-top: 50px; /* Make room for the overlapping image */
    }
    
    .team-info::before, .team-info::after { display: none; } /* Hide arrow on mobile */
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
