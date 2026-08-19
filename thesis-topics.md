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

  /* --- STATS BAR STYLES --- */
  .stats-container {
    display: flex;
    gap: 1.5rem;
    margin-bottom: 3rem;
    margin-top: 1rem;
  }

  .stat-card {
    flex: 1;
    background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
    border: 1px solid #bfdbfe;
    border-radius: 16px;
    padding: 1.5rem 2rem;
    display: flex;
    align-items: center;
    gap: 1.5rem;
    box-shadow: 0 4px 6px rgba(15, 23, 42, 0.03);
    transition: transform 0.2s ease;
  }
  
  .stat-card:hover {
    transform: translateY(-2px);
  }

  .stat-icon {
    width: 55px;
    height: 55px;
    background: #2563eb;
    color: white;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .stat-content {
    display: flex;
    flex-direction: column;
  }

  .stat-content h4 {
    margin: 0;
    font-size: 0.9rem;
    color: #475569;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05rem;
  }

  .stat-content .stat-value {
    margin: 0.2rem 0 0;
    font-size: 2.2rem;
    font-weight: 800;
    color: #1e3a8a;
    line-height: 1;
  }
  
  @media (max-width: 768px) {
    .stats-container {
      flex-direction: column;
    }
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
    height: 100%; 
  }

  .supervisor-card:hover {
    transform: translateY(-4px);
    border-color: #93c5fd;
    box-shadow: 0 12px 22px rgba(15, 23, 42, 0.10);
  }

  .supervisor-top {
    display: flex;
    flex-direction: column;
    padding: 1.25rem;
    border-bottom: 1px solid #f1f5f9;
    min-height: 175px; 
    box-sizing: border-box;
  }

  .supervisor-header {
    display: flex;
    gap: 1rem;
    align-items: flex-start;
    margin-bottom: 0.8rem;
  }

  .supervisor-photo {
    width: 82px;
    height: 82px;
    border-radius: 999px;
    object-fit: cover;
    object-position: center 15%; 
    border: 2px solid #e2e8f0;
    flex-shrink: 0;
    background: #f8fafc;
  }
  
  .supervisor-meta {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  .supervisor-meta h3 {
    margin: 0 0 0.25rem;
    font-size: 1.15rem;
    color: #0f172a;
    min-height: 2.7rem; 
  }

  .supervisor-role {
    margin: 0;
    color: #475569;
    font-size: 0.92rem;
  }

  .supervisor-contact {
    display: block;
    font-size: 0.9rem;
    text-decoration: none;
    color: #1d4ed8;
    word-break: break-all; 
    margin-top: auto; 
  }
  
  .supervisor-contact:hover {
    text-decoration: underline;
  }

  .supervisor-body {
    padding: 1rem 1.25rem 1.2rem;
    display: flex;
    flex-direction: column;
    flex-grow: 1; 
    gap: 1.2rem;
  }

  .topics-wrapper, .bachelor-section, .master-section {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .topics-wrapper { 
    min-height: 150px; 
  }
  
  .bachelor-section { 
    min-height: 140px; 
  }

  .label {
    display: inline-block;
    margin-bottom: 0.45rem;
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

  .chip.toggle-btn {
    cursor: pointer;
    background: #e0f2fe;
    border-color: #bae6fd;
    transition: background 0.2s ease;
  }
  .chip.toggle-btn:hover { background: #bae6fd; }

  .bullets {
    margin: 0;
    padding-left: 1rem;
    color: #334155;
    line-height: 1.55;
    font-size: 0.93rem;
  }

  .toggle-text {
    font-size: 0.85rem;
    color: #1d4ed8;
    text-decoration: none;
    font-weight: 600;
    margin-top: 0.4rem;
    display: inline-block;
    cursor: pointer;
  }
  .toggle-text:hover { text-decoration: underline; }

  .hidden { display: none !important; }

  .empty-text {
    font-size: 0.85rem;
    color: #94a3b8;
    margin: 0;
    font-style: italic;
  }

  .accordion-section { margin-top: 2.5rem; }
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
  .accordion-header:hover { box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
  .accordion-label {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 1.08rem;
    font-weight: 700;
    color: #166534;
  }
  .accordion-count { font-size: 0.85rem; font-weight: 500; opacity: 0.8; }
  .accordion-icon { color: #166534; transition: transform 0.3s ease; }
  .accordion-section.collapsed .accordion-icon { transform: rotate(-90deg); }
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
    display: flex;
    flex-direction: column;
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
    width: fit-content;
  }
  .thesis-title {
    margin: 0 0 0.6rem;
    font-size: 1.06rem;
    line-height: 1.35;
    color: #111827;
  }
  .thesis-desc { margin: 0 0 0.8rem; font-size: 0.92rem; color: #4b5563; line-height: 1.55; }
  
  .thesis-meta { 
    font-size: 0.86rem; 
    color: #334155; 
    margin-top: auto; 
  }

  /* --- NEW: REPOSITUM BUTTON STYLES --- */
  .repo-link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    margin-top: 0.8rem;
    font-size: 0.82rem;
    font-weight: 700;
    color: #166534;
    background: #dcfce7;
    padding: 0.4rem 0.9rem;
    border-radius: 6px;
    text-decoration: none;
    transition: background 0.2s ease, color 0.2s ease;
    border: 1px solid #bbf7d0;
  }
  .repo-link:hover {
    background: #bbf7d0;
    color: #14532d;
    text-decoration: none;
  }
</style>

{% assign supervisors = site.data.supervisors %}
{% assign finished_topics = site.data.thesis | where: "status", "finished" %}

<!-- STATS BAR ROW -->
<div class="stats-container">
  <div class="stat-card">
    <div class="stat-icon">
      <!-- Checkmark Icon -->
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"></path>
      </svg>
    </div>
    <div class="stat-content">
      <h4>Finished Theses (Since 2023)</h4>
      <p class="stat-value" id="stat-finished-count">-</p>
    </div>
  </div>

  <div class="stat-card">
    <div class="stat-icon">
      <!-- Clock Icon -->
      <svg width="28" height="28" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
      </svg>
    </div>
    <div class="stat-content">
      <h4>Avg. Master Thesis Duration</h4>
      <p class="stat-value" id="stat-avg-duration">-</p>
    </div>
  </div>
</div>

<div class="supervisor-grid">
  {% for s in supervisors %}
  <article class="supervisor-card">
    <div class="supervisor-top">
      <div class="supervisor-header">
        <img class="supervisor-photo" src="{{ s.image }}" alt="{{ s.name }} portrait">
        <div class="supervisor-meta">
          <h3>{{ s.name }}</h3>
          <p class="supervisor-role">{{ s.role }}</p>
        </div>
      </div>
      <a class="supervisor-contact" href="mailto:{{ s.contact }}">
        {{ s.contact }}
      </a>
    </div>

    <div class="supervisor-body">
      <!-- Offers Topics In Section -->
      <div class="topics-wrapper">
        <span class="label">Offered Topics</span>
        <div class="chip-list">
          {% for area in s.offer_topics %}
            {% if forloop.first %}
              <span class="chip">{{ area }}</span>
            {% else %}
              <span class="chip more-chip-{{ s.name | slugify }} hidden">{{ area }}</span>
            {% endif %}
          {% endfor %}
          {% if s.offer_topics.size > 1 %}
            <span class="chip toggle-btn" onclick="toggleChips('{{ s.name | slugify }}', this, {{ s.offer_topics.size | minus: 1 }})">
              + {{ s.offer_topics.size | minus: 1 }} more
            </span>
          {% endif %}
        </div>
      </div>

      <!-- Open Bachelor Theses Section -->
      <div class="bachelor-section">
        <span class="label">Open Bachelor Theses</span>
        {% if s.open_bachelor and s.open_bachelor.size > 0 %}
          <ul class="bullets">
            {% for b in s.open_bachelor %}
              {% if forloop.first %}
                <li>{{ b }}</li>
              {% else %}
                <li class="more-bullet-{{ s.name | slugify }}-bac hidden">{{ b }}</li>
              {% endif %}
            {% endfor %}
          </ul>
          {% if s.open_bachelor.size > 1 %}
            <a class="toggle-text" onclick="toggleBullets('{{ s.name | slugify }}-bac', this, {{ s.open_bachelor.size | minus: 1 }})">
              Show {{ s.open_bachelor.size | minus: 1 }} more...
            </a>
          {% endif %}
        {% else %}
          <p class="empty-text">None currently available</p>
        {% endif %}
      </div>

      <!-- Open Master Theses Section -->
      <div class="master-section">
        <span class="label">Open Master Theses</span>
        {% if s.open_master and s.open_master.size > 0 %}
          <ul class="bullets">
            {% for m in s.open_master %}
              {% if forloop.first %}
                <li>{{ m }}</li>
              {% else %}
                <li class="more-bullet-{{ s.name | slugify }}-mas hidden">{{ m }}</li>
              {% endif %}
            {% endfor %}
          </ul>
          {% if s.open_master.size > 1 %}
            <a class="toggle-text" onclick="toggleBullets('{{ s.name | slugify }}-mas', this, {{ s.open_master.size | minus: 1 }})">
              Show {{ s.open_master.size | minus: 1 }} more...
            </a>
          {% endif %}
        {% else %}
          <p class="empty-text">None currently available</p>
        {% endif %}
      </div>
    </div>
  </article>
  {% endfor %}
</div>

<!-- FINISHED THESES SECTION -->
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
          {% if topic.student %}
            <strong>Student:</strong> {{ topic.student }}<br>
          {% endif %}
          <strong>Supervisors:</strong> {{ topic.supervisor }}<br>
          <a href="mailto:{{ topic.contact }}">Contact Supervisor</a>
          
          <!-- NEW: REPOSITUM BUTTON -->
          {% if topic.repo_link %}
            <br>
            <a href="{{ topic.repo_link }}" target="_blank" rel="noopener noreferrer" class="repo-link">
              View in reposiTUm 
              <svg width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path>
              </svg>
            </a>
          {% endif %}
        </div>

      </div>
      {% endfor %}
    </div>
  </div>
</div>

<script>
// --- UI TOGGLES ---
function toggleAccordion(sectionId) {
  var section = document.getElementById(sectionId);
  section.classList.toggle('collapsed');
}

function toggleChips(id, btn, count) {
  var elements = document.querySelectorAll('.more-chip-' + id);
  var isHidden = elements[0].classList.contains('hidden');
  
  elements.forEach(function(el) { el.classList.toggle('hidden'); });
  
  if (isHidden) {
    btn.innerText = "Show less";
  } else {
    btn.innerText = "+ " + count + " more";
  }
}

function toggleBullets(id, btn, count) {
  var elements = document.querySelectorAll('.more-bullet-' + id);
  var isHidden = elements[0].classList.contains('hidden');
  
  elements.forEach(function(el) { el.classList.toggle('hidden'); });
  
  if (isHidden) {
    btn.innerText = "Show less";
  } else {
    btn.innerText = "Show " + count + " more...";
  }
}

// --- DYNAMIC STATS CALCULATOR ---
document.addEventListener("DOMContentLoaded", function() {
  
  const thesesData = [
    {% for t in site.data.thesis %}
    {
      type: {{ t.type | default: '' | jsonify }},
      status: {{ t.status | default: '' | jsonify }},
      start_date: {{ t.start_date | default: '' | jsonify }},
      finish_date: {{ t.finish_date | default: '' | jsonify }}
    }{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ];

  let finishedSince2023 = 0;
  let totalMonths = 0;
  let validDurationsCount = 0;

  thesesData.forEach(function(t) {
    
    // 1. Count finished theses since 2023
    if (t.status === 'finished') {
      if (t.finish_date) {
        const fYear = new Date(t.finish_date).getFullYear();
        if (fYear >= 2023) finishedSince2023++;
      } else {
        finishedSince2023++;
      }
    }

    // 2. Calculate average Master Thesis duration
    if (t.type === 'Master Thesis' && t.start_date && t.finish_date) {
      const start = new Date(t.start_date);
      const end = new Date(t.finish_date);
      
      if (!isNaN(start) && !isNaN(end)) {
        const diffTime = Math.abs(end - start);
        const diffMonths = diffTime / (1000 * 60 * 60 * 24 * 30.44);
        
        totalMonths += diffMonths;
        validDurationsCount++;
      }
    }
  });

  // Render Finished Count
  document.getElementById('stat-finished-count').innerText = finishedSince2023;

  // Render Average Duration
  const durationEl = document.getElementById('stat-avg-duration');
  if (validDurationsCount > 0) {
    const avg = Math.round(totalMonths / validDurationsCount);
    durationEl.innerText = avg + " Months";
  } else {
    durationEl.innerText = "N/A";
  }

});
</script>
