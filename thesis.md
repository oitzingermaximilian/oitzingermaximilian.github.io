---
layout: splash
permalink: /thesis/
title: "Thesis Topic"
header:
  overlay_color: "#fff"
---

<style>
  /* Reuse the wide layout from your team page */
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1200px !important;
    margin: 0 auto !important;
  }
  
  .page__title {
    display: none !important;
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

  /* Hover Border Colors */
  .thesis-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
    border-color: #1e90ff; /* Default Blue */
  }
  .thesis-card.finished:hover {
    border-color: #28a745; /* Green for finished */
  }

  .thesis-type {
    display: inline-block;
    padding: 0.25rem 0.75rem;
    background-color: #f3f4f6; /* Neutral gray */
    color: #4b5563;
    border-radius: 50px;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
  }
  
  .thesis-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  .thesis-status {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    font-weight: 600;
  }

  .status-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    display: inline-block;
  }

  /* Status Colors */
  .status-dot.ongoing { background-color: #007bff; } /* Blue */
  .thesis-status.ongoing { color: #007bff; }

  .status-dot.finished { background-color: #28a745; } /* Green */
  .thesis-status.finished { color: #28a745; }

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
  <div class="thesis-card {{ topic.status | default: 'ongoing' }}">
    <div class="thesis-header">
      <span class="thesis-type">{{ topic.type }}</span>
      <div class="thesis-status {{ topic.status | default: 'ongoing' }}">
        <span class="status-dot {{ topic.status | default: 'ongoing' }}"></span>
        {{ topic.status | capitalize | default: 'Ongoing' }}
      </div>
    </div>
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
