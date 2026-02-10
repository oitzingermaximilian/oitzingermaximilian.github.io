---
permalink: /publications/
layout: splash
title: "Our Work"
header:
  overlay_color: "#fff"
---

<style>
  .page__inner-wrap {
    width: 95% !important;
    max-width: 1200px !important;
    margin: 0 auto !important;
  }

  .page__title {
    display: none !important;
  }

  /* ── Accordion ── */
  .pub-accordion-section {
    margin-bottom: 2rem;
  }

  .pub-accordion-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 1.5rem;
    border-radius: 10px;
    cursor: pointer;
    user-select: none;
    transition: background 0.2s, box-shadow 0.2s;
  }

  .pub-accordion-header:hover {
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  }

  .pub-accordion-header.papers {
    background: linear-gradient(135deg, #e0f2fe 0%, #bae6fd 100%);
    border: 1px solid #7dd3fc;
  }
  .pub-accordion-header.activities {
    background: linear-gradient(135deg, #e0f2fe 0%, #bae6fd 100%);
    border: 1px solid #7dd3fc;
  }

  .pub-accordion-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.2rem;
    font-weight: 700;
  }
  .pub-accordion-header.papers .pub-accordion-label { color: #1e90ff; }
  .pub-accordion-header.activities .pub-accordion-label { color: #1e90ff; }

  .pub-accordion-count {
    font-size: 0.85rem;
    font-weight: 500;
    opacity: 0.7;
  }

  .pub-accordion-icon {
    font-size: 1.2rem;
    transition: transform 0.3s ease;
  }
  .pub-accordion-header.papers .pub-accordion-icon { color: #1e90ff; }
  .pub-accordion-header.activities .pub-accordion-icon { color: #1e90ff; }

  .pub-accordion-section.collapsed .pub-accordion-icon {
    transform: rotate(-90deg);
  }

  .pub-accordion-body {
    overflow: hidden;
    max-height: 5000px;
    transition: max-height 0.4s ease-in-out, opacity 0.3s ease;
    opacity: 1;
    padding-top: 1rem;
  }
  .pub-accordion-section.collapsed .pub-accordion-body {
    max-height: 0;
    opacity: 0;
    padding-top: 0;
  }

  /* ── Publication / Activity Items ── */
  .work-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .work-item {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 1.5rem 2rem;
    margin-bottom: 1.25rem;
    box-shadow: 0 2px 6px rgba(0,0,0,0.04);
    transition: transform 0.2s, box-shadow 0.2s, border-color 0.2s;
  }

  .work-item:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 16px rgba(0,0,0,0.08);
  }

  .work-item.paper:hover { border-color: #1e90ff; }
  .work-item.activity:hover { border-color: #1e90ff; }

  .work-title {
    font-size: 1.15rem;
    margin: 0 0 0.5rem 0;
    color: #111;
    line-height: 1.4;
  }

  .work-year {
    color: #888;
    font-weight: 400;
    font-size: 0.95rem;
  }

  .work-authors {
    color: #555;
    font-size: 0.9rem;
    margin: 0 0 0.5rem 0;
  }

  .work-links {
    font-size: 0.85rem;
    margin: 0.25rem 0;
  }
  .work-links a {
    color: #1e90ff;
    text-decoration: none;
  }
  .work-links a:hover {
    text-decoration: underline;
  }

  .work-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    font-size: 0.85rem;
    color: #666;
    margin: 0.5rem 0;
  }

  .work-meta-item {
    display: flex;
    align-items: center;
    gap: 5px;
  }
  .work-meta-item i { color: #1e90ff; font-size: 0.8rem; }

  .work-abstract {
    margin-top: 0.75rem;
  }
  .work-abstract summary {
    cursor: pointer;
    color: #666;
    font-size: 0.85rem;
    font-weight: 600;
  }
  .work-abstract summary:hover { color: #333; }
  .work-abstract-body {
    margin-top: 0.5rem;
    color: #555;
    font-size: 0.9rem;
    line-height: 1.6;
  }


</style>

{% assign papers = site.data.publications | where: "type", "paper" %}
{% assign activities = site.data.publications | where: "type", "activity" %}

<!-- ═══ LinkedIn Carousel ═══ -->
<style>
  .linkedin-carousel-section {
    max-width: 700px;
    margin: 0 auto 2.5rem auto;
    text-align: center;
  }
  .linkedin-carousel-section h3 {
    font-size: 1.4rem;
    color: #1e90ff;
    margin-bottom: 1.5rem;
    font-weight: 700;
    letter-spacing: 0.5px;
  }
  .linkedin-carousel {
    position: relative;
    overflow: hidden;
    border-radius: 12px;
    background: #f9fafb;
    border: 1px solid #e5e7eb;
    min-height: 400px;
  }
  .linkedin-slide {
    display: none;
    width: 100%;
    justify-content: center;
    padding: 1rem;
  }
  .linkedin-slide.active {
    display: flex;
  }
  .linkedin-slide iframe {
    border: none;
    width: 100%;
    max-width: 504px;
    height: 600px;
  }
  .carousel-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    margin-top: 1rem;
  }
  .carousel-btn {
    background: #e5e7eb;
    border: none;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1rem;
    color: #333;
    transition: background 0.2s;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .carousel-btn:hover {
    background: #1e90ff;
    color: #fff;
  }
  .carousel-dots {
    display: flex;
    gap: 8px;
  }
  .carousel-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: #d1d5db;
    border: none;
    cursor: pointer;
    transition: background 0.2s;
    padding: 0;
  }
  .carousel-dot.active {
    background: #1e90ff;
  }
</style>

{% if site.data.linkedin_posts.size > 0 %}
<section class="linkedin-carousel-section">
  <h3>Latest Updates</h3>
  <div class="linkedin-carousel" id="linkedinCarousel">
    {% for post in site.data.linkedin_posts %}
    <div class="linkedin-slide {% if forloop.first %}active{% endif %}">
      <iframe src="{{ post.src }}" height="600" width="504" frameborder="0" allowfullscreen="" title="{{ post.title }}"></iframe>
    </div>
    {% endfor %}
  </div>
  <div class="carousel-controls">
    <button class="carousel-btn" onclick="changeSlide(-1)">&#8249;</button>
    <div class="carousel-dots" id="carouselDots">
      {% for post in site.data.linkedin_posts %}
      <button class="carousel-dot {% if forloop.first %}active{% endif %}" onclick="goToSlide({{ forloop.index0 }})"></button>
      {% endfor %}
    </div>
    <button class="carousel-btn" onclick="changeSlide(1)">&#8250;</button>
  </div>
</section>
{% endif %}

<script>
(function() {
  var currentSlide = 0;
  var slides = document.querySelectorAll('.linkedin-slide');
  var dots = document.querySelectorAll('.carousel-dot');
  var total = slides.length;
  if (total === 0) return;

  var autoTimer = setInterval(function() { changeSlide(1); }, 8000);

  function resetTimer() {
    clearInterval(autoTimer);
    autoTimer = setInterval(function() { changeSlide(1); }, 8000);
  }

  window.changeSlide = function(dir) {
    slides[currentSlide].classList.remove('active');
    dots[currentSlide].classList.remove('active');
    currentSlide = (currentSlide + dir + total) % total;
    slides[currentSlide].classList.add('active');
    dots[currentSlide].classList.add('active');
    resetTimer();
  };

  window.goToSlide = function(idx) {
    slides[currentSlide].classList.remove('active');
    dots[currentSlide].classList.remove('active');
    currentSlide = idx;
    slides[currentSlide].classList.add('active');
    dots[currentSlide].classList.add('active');
    resetTimer();
  };
})();
</script>

<!-- ═══ Peer-Reviewed Publications ═══ -->

<div class="pub-accordion-section" id="papers-section">
  <div class="pub-accordion-header papers" onclick="togglePubAccordion('papers-section')">
    <div class="pub-accordion-label">

      Peer-Reviewed Publications
      <span class="pub-accordion-count">({{ papers.size }})</span>
    </div>
    <span class="pub-accordion-icon">▼</span>
  </div>
  <div class="pub-accordion-body">
    <div class="work-list">
      {% for pub in papers %}
      <article class="work-item paper">
        <h3 class="work-title">
          {{ pub.title }}{% if pub.year %} <span class="work-year">({{ pub.year }})</span>{% endif %}
        </h3>
        {% if pub.authors %}<p class="work-authors">{{ pub.authors }}</p>{% endif %}
        {% if pub.doi %}
          <p class="work-links">DOI: <a href="{{ pub.url | default: 'https://doi.org/' | append: pub.doi }}" target="_blank">{{ pub.doi }}</a></p>
        {% endif %}
        {% assign abstract = pub.abstract | default: pub.description %}
        {% if abstract %}
          <details class="work-abstract">
            <summary>Abstract</summary>
            <div class="work-abstract-body">{{ abstract }}</div>
          </details>
        {% endif %}
      </article>
      {% endfor %}
    </div>
  </div>
</div>

<!-- ═══ Research Activities ═══ -->
<div class="pub-accordion-section" id="activities-section">
  <div class="pub-accordion-header activities" onclick="togglePubAccordion('activities-section')">
    <div class="pub-accordion-label">

      Research Activities
      <span class="pub-accordion-count">({{ activities.size }})</span>
    </div>
    <span class="pub-accordion-icon">▼</span>
  </div>
  <div class="pub-accordion-body">
    <div class="work-list">
      {% for act in activities %}
      <article class="work-item activity">
        <h3 class="work-title">
          {{ act.title }}{% if act.year %} <span class="work-year">({{ act.year }})</span>{% endif %}
        </h3>
        {% if act.authors %}<p class="work-authors">{{ act.authors }}</p>{% endif %}
        <div class="work-meta">
          {% if act.event %}
          <span class="work-meta-item"><i class="fas fa-calendar-alt"></i> {{ act.event }}</span>
          {% endif %}
          {% if act.location %}
          <span class="work-meta-item"><i class="fas fa-map-marker-alt"></i> {{ act.location }}</span>
          {% endif %}
          {% if act.date %}
          <span class="work-meta-item"><i class="fas fa-clock"></i> {{ act.date }}</span>
          {% endif %}
        </div>
        {% if act.description %}
          <details class="work-abstract">
            <summary>Details</summary>
            <div class="work-abstract-body">{{ act.description }}</div>
          </details>
        {% endif %}
      </article>
      {% endfor %}
    </div>
  </div>
</div>

<script>
function togglePubAccordion(sectionId) {
  var section = document.getElementById(sectionId);
  section.classList.toggle('collapsed');
}
</script>
