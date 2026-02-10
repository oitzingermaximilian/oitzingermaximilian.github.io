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

  /* ── Accordion ── */
  .accordion-section {
    margin-bottom: 2rem;
  }

  .accordion-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 1.5rem;
    border-radius: 10px;
    cursor: pointer;
    user-select: none;
    transition: background 0.2s, box-shadow 0.2s;
  }

  .accordion-header:hover {
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  }

  .accordion-header.ongoing {
    background: linear-gradient(135deg, #e0f2fe 0%, #bae6fd 100%);
    border: 1px solid #7dd3fc;
  }
  .accordion-header.finished {
    background: linear-gradient(135deg, #dcfce7 0%, #bbf7d0 100%);
    border: 1px solid #86efac;
  }

  .accordion-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.2rem;
    font-weight: 700;
  }
  .accordion-header.ongoing .accordion-label { color: #0369a1; }
  .accordion-header.finished .accordion-label { color: #166534; }

  .accordion-count {
    font-size: 0.85rem;
    font-weight: 500;
    opacity: 0.7;
  }

  .accordion-icon {
    font-size: 1.2rem;
    transition: transform 0.3s ease;
  }
  .accordion-header.ongoing .accordion-icon { color: #0369a1; }
  .accordion-header.finished .accordion-icon { color: #166534; }

  .accordion-section.collapsed .accordion-icon {
    transform: rotate(-90deg);
  }

  .accordion-body {
    overflow: hidden;
    max-height: 5000px;
    transition: max-height 0.4s ease-in-out, opacity 0.3s ease;
    opacity: 1;
  }
  .accordion-section.collapsed .accordion-body {
    max-height: 0;
    opacity: 0;
  }

  /* ── Grid ── */
  .thesis-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 2rem;
    margin-top: 1.5rem;
  }

  .thesis-card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    transition: transform 0.2s, box-shadow 0.2s, border-color 0.2s;
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
    background-color: #f3f4f6;
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
  .status-dot.ongoing { background-color: #007bff; }
  .thesis-status.ongoing { color: #007bff; }

  .status-dot.finished { background-color: #28a745; }
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
  .thesis-card.finished .supervisor-name {
    color: #28a745;
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

<!-- ═══ Ongoing Theses (expanded by default) ═══ -->
{% assign ongoing_topics = site.data.thesis | where: "status", "ongoing" %}
{% assign finished_topics = site.data.thesis | where: "status", "finished" %}

<div class="accordion-section" id="ongoing-section">
  <div class="accordion-header ongoing" onclick="toggleAccordion('ongoing-section')">
    <div class="accordion-label">
      <span class="status-dot ongoing" style="width:12px;height:12px;"></span>
      Ongoing Theses
      <span class="accordion-count">({{ ongoing_topics.size }})</span>
    </div>
    <span class="accordion-icon">▼</span>
  </div>
  <div class="accordion-body">
    <div class="thesis-grid">
      {% for topic in ongoing_topics %}
      <div class="thesis-card ongoing">
        <div class="thesis-header">
          <span class="thesis-type">{{ topic.type }}</span>
          <div class="thesis-status ongoing">
            <span class="status-dot ongoing"></span>
            Ongoing
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
  </div>
</div>

<!-- ═══ Finished Theses (collapsed by default) ═══ -->
<div class="accordion-section collapsed" id="finished-section">
  <div class="accordion-header finished" onclick="toggleAccordion('finished-section')">
    <div class="accordion-label">
      <span class="status-dot finished" style="width:12px;height:12px;"></span>
      Finished Theses
      <span class="accordion-count">({{ finished_topics.size }})</span>
    </div>
    <span class="accordion-icon">▼</span>
  </div>
  <div class="accordion-body">
    <div class="thesis-grid">
      {% for topic in finished_topics %}
      <div class="thesis-card finished">
        <div class="thesis-header">
          <span class="thesis-type">{{ topic.type }}</span>
          <div class="thesis-status finished">
            <span class="status-dot finished"></span>
            Finished
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
  </div>
</div>

<script>
function toggleAccordion(sectionId) {
  var section = document.getElementById(sectionId);
  section.classList.toggle('collapsed');
}
</script>
