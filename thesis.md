---
title: "Available Thesis Topics"
layout: splash
permalink: /thesis/
header:
  overlay_color: "#fff"
---
<style>
  /* Makes all headings (H1, H2) blue */
  h1, h2, h3 {
    color: #1e90ff !important;
  }
</style>

<style>
  /* Reuse the wide layout from your team page */
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1200px !important;
    margin: 0 auto !important;
  }
  
  .page__title {
    text-align: center;
    color: #1e90ff;
    margin-bottom: 2rem;
  }

  .thesis-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
  }

  .thesis-card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    transition: transform 0.2s;
    display: flex;
    flex-direction: column;
  }

  .thesis-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    border-color: #1e90ff;
  }

  .thesis-type {
    display: inline-block;
    background-color: #e0f2fe;
    color: #0369a1;
    padding: 0.25rem 0.75rem;
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    margin-bottom: 1rem;
    align-self: flex-start;
  }

  .thesis-title {
    font-size: 1.25rem;
    margin: 0 0 1rem 0;
    color: #111;
    line-height: 1.4;
  }

  .thesis-desc {
    color: #666;
    font-size: 0.95rem;
    line-height: 1.6;
    margin-bottom: 1.5rem;
    flex-grow: 1;
  }

  .thesis-footer {
    border-top: 1px solid #f3f4f6;
    padding-top: 1rem;
    font-size: 0.9rem;
  }

  .supervisor-label {
    font-weight: 600;
    color: #4b5563;
    display: block;
    margin-bottom: 0.25rem;
  }

  .supervisor-name {
    color: #1e90ff;
    font-weight: 500;
  }
  
  .contact-btn {
    display: inline-block;
    margin-top: 1rem;
    text-decoration: none;
    color: #666;
    font-size: 0.85rem;
  }
  .contact-btn:hover { text-decoration: underline; color: #1e90ff; }
</style>

<div class="thesis-grid">
  {% for topic in site.data.thesis %}
  <div class="thesis-card">
    <span class="thesis-type">{{ topic.type }}</span>
    <h3 class="thesis-title">{{ topic.title }}</h3>
    <p class="thesis-desc">{{ topic.description }}</p>
    
    <div class="thesis-footer">
      <span class="supervisor-label">Supervisor:</span>
      <span class="supervisor-name">{{ topic.supervisor }}</span>
      <br>
      <a href="mailto:{{ topic.contact }}" class="contact-btn">
        <i class="fas fa-envelope"></i> Contact Supervisor
      </a>
    </div>
  </div>
  {% endfor %}
</div>
