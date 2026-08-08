---
layout: splash
permalink: /thesis-topics/
title: "Thesis Topics & Supervision"
header:
  overlay_color: "#fff"
---

<style>
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1250px !important;
    margin: 0 auto !important;
  }

  .page__title {
    display: none !important;
  }

  .intro-box {
    display: none !important;
  }

  .section-title {
    display: none !important;
  }

  .supervisor-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
    gap: 1.5rem;
    margin: 1rem 0 2rem;
  }

  .supervisor-card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 14px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(15, 23, 42, 0.05);
    transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
    display: flex;
    flex-direction: column;
  }

  .supervisor-card:hover {
    transform: translateY(-4px);
    border-color: #93c5fd;
    box-shadow: 0 12px 22px rgba(15, 23, 42, 0.10);
  }

  .supervisor-top {
    display: flex;
    gap: 1rem;
    padding: 1.25rem 1.25rem 1rem;
    align-items: center;
    border-bottom: 1px solid #f1f5f9;
  }

  .supervisor-photo {
    width: 82px;
    height: 82px;
    border-radius: 999px;
    object-fit: cover;
    border: 2px solid #e2e8f0;
    flex-shrink: 0;
    background: #f8fafc;
  }

  .supervisor-meta h3 {
    margin: 0 0 0.25rem;
    font-size: 1.15rem;
    color: #0f172a;
  }

  .supervisor-role {
    margin: 0;
    color: #475569;
    font-size: 0.92rem;
  }

  .supervisor-contact {
    margin-top: 0.4rem;
    display: inline-block;
    font-size: 0.88rem;
    text-decoration: none;
    color: #1d4ed8;
  }
  .supervisor-contact:hover {
    text-decoration: underline;
  }

  .supervisor-body {
    padding: 1rem 1.25rem 1.2rem;
    display: grid;
    gap: 1rem;
  }

  .label {
    display: inline-block;
    margin-bottom: 0.35rem;
    font-weight: 700;
    color: #1e293b;
    font-size: 0.9rem;
  }

  .chip-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.45rem;
  }

  .chip {
    display: inline-block;
    padding: 0.3rem 0.62rem;
    border-radius: 999px;
    font-size: 0.78rem;
    font-weight: 600;
    border: 1px solid #dbeafe;
    background: #eff6ff;
    color: #1e3a8a;
  }

  .bullets {
    margin: 0;
    padding-left: 1rem;
    color: #334155;
    line-height: 1.55;
    font-size: 0.93rem;
  }

  .accordion-section {
    margin-top: 2.5rem;
  }

  .accordion-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.9rem 1.2rem;
    border-radius: 10px;
    cursor: pointer;
    user-select: none;
    transition: box-shadow 0.2s ease;
    background: linear-gradient(135deg, #dcfce7 0%, #bbf7d0 100%);
    border: 1px solid #86efac;
  }
  .accordion-header:hover {
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  }

  .accordion-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.08rem;
    font-weight: 700;
    color: #166534;
  }

  .accordion-count {
    font-size: 0.85rem;
    font-weight: 500;
    opacity: 0.8;
  }

  .accordion-icon {
    color: #166534;
    transition: transform 0.3s ease;
  }

  .accordion-section.collapsed .accordion-icon {
    transform: rotate(-90deg);
  }

  .accordion-body {
    overflow: hidden;
    max-height: 5000px;
    opacity: 1;
    transition: max-height 0.4s ease-in-out, opacity 0.3s ease;
  }

  .accordion-section.collapsed .accordion-body {
    max-height: 0;
    opacity: 0;
  }

  .thesis-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 1.5rem;
    margin-top: 1.2rem;
  }

  .thesis-card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 1.35rem;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.04);
  }

  .thesis-type {
    display: inline-block;
    padding: 0.2rem 0.65rem;
    background: #f3f4f6;
    border-radius: 999px;
    font-size: 0.72rem;
    font-weight: 700;
    color: #475569;
    text-transform: uppercase;
    margin-bottom: 0.7rem;
  }

  .thesis-title {
    margin: 0 0 0.6rem;
    font-size: 1.06rem;
    line-height: 1.35;
    color: #111827;
  }

  .thesis-desc {
    margin: 0 0 0.8rem;
    font-size: 0.92rem;
    color: #4b5563;
    line-height: 1.55;
  }

  .thesis-meta {
    font-size: 0.86rem;
    color: #334155;
  }

  @media (max-width: 520px) {
    .supervisor-top {
      align-items: flex-start;
      flex-direction: column;
    }
  }
</style>

{% assign supervisors = site.data.supervisors %}
{% assign finished_topics = site.data.thesis | where: "status", "finished" %}

<div class="supervisor-grid">
  {% for s in supervisors %}
  <article class="supervisor-card">
    <div class="supervisor-top">
      <img class="supervisor-photo" src="{{ s.image }}" alt="{{ s.name }} portrait">
      <div class="supervisor-meta">
        <h3>{{ s.name }}</h3>
        <p class="supervisor-role">{{ s.role }}</p>
        <a class="supervisor-contact" href="mailto:{{ s.contact }}">
          <i class="fas fa-envelope"></i> {{ s.contact }}
        </a>
      </div>
    </div>

    <div class="supervisor-body">
      <div>
        <span class="label">Offers Topics In</span>
        <div class="chip-list">
          {% for area in s.offer_topics %}
          <span class="chip">{{ area }}</span>
          {% endfor %}
        </div>
      </div>

      <div>
        <span class="label">Possible Directions</span>
        <ul class="bullets">
          {% for d in s.directions %}
          <li>{{ d }}</li>
          {% endfor %}
        </ul>
      </div>
    </div>
  </article>
  {% endfor %}
</div>

<div class="accordion-section collapsed" id="finished-section">
  <div class="accordion-header" onclick="toggleAccordion('finished-section')">
    <div class="accordion-label">
      <span style="width:12px;height:12px;border-radius:50%;background:#16a34a;display:inline-block;"></span>
      Finished Theses
      <span class="accordion-count">({{ finished_topics.size }})</span>
    </div>
    <span class="accordion-icon">▼</span>
  </div>

  <div class="accordion-body">
    <div class="thesis-grid">
      {% for topic in finished_topics %}
      <div class="thesis-card">
        <span class="thesis-type">{{ topic.type }}</span>
        <h3 class="thesis-title">{{ topic.title }}</h3>
        <p class="thesis-desc">{{ topic.description }}</p>
        <div class="thesis-meta">
          <strong>Supervisors:</strong> {{ topic.supervisor }}<br>
          <a href="mailto:{{ topic.contact }}">Contact Supervisor</a>
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
