---
layout: splash
permalink: /
---

<style>
  /* Hero / Intro */
  .home-intro {
    text-align: center;
    max-width: 800px;
    margin: 0 auto 3rem auto;
  }
  .home-intro h2 { font-size: 2.2rem; margin-bottom: 0.5rem; color: #1e90ff; }
  .home-intro p { font-size: 1.2rem; color: #666; line-height: 1.6; }

  /* Team Grid */
  .home-team-section {
    text-align: center;
    padding: 2rem 0;
    border-bottom: 1px solid #eee;
    margin-bottom: 3rem;
  }
  .home-team-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
    margin: 2rem 0;
  }
  .home-member {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 140px;
    text-decoration: none !important;
  }
  .home-member-photo {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
    border: 3px solid #fff;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    transition: all 0.2s ease;
    margin-bottom: 0.75rem;
    background-color: #f0f0f0;
  }
  .home-member:hover .home-member-photo {
    transform: scale(1.1);
    border-color: #1e90ff;
  }
  .home-member-name {
    font-size: 0.95rem;
    font-weight: 700;
    color: #333;
    line-height: 1.2;
    text-align: center;
  }

  /* Publications Preview */
  .home-pubs-section {
    max-width: 800px;
    margin: 0 auto;
    margin-bottom: 3rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid #eee;
  }
  .pub-preview-card {
    background: #fff;
    padding: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 8px;
    border: 1px solid #eee;
    box-shadow: 0 2px 4px rgba(0,0,0,0.03);
    transition: transform 0.2s;
  }
  .pub-preview-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.08);
  }
  .pub-title { font-size: 1.1rem; font-weight: bold; color: #333; margin-bottom: 0.25rem; display: block; }
  .pub-meta { font-size: 0.9rem; color: #777; }

  /* Thesis Section */
  .home-thesis-section {
    text-align: center;
    max-width: 800px;
    margin: 0 auto 3rem auto;
  }

  /* UNIFORM BUTTON STYLE */
  .btn-main {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background-color: #1e90ff;
    color: white !important;
    text-decoration: none;
    border-radius: 50px;
    font-weight: 600;
    margin-top: 1rem;
    transition: background 0.2s;
    border: none;
    cursor: pointer;
  }
  .btn-main:hover { background-color: #0056b3; }
</style>

<section class="home-intro">
  <h2>From Minerals to Megawatts</h2>
  <p>
    We are the Energy System Modeling team (ES3M) at TU Wien. 
    We model the pathways to a climate-neutral future, focusing on supply chains, raw materials, and energy markets.
  </p>
</section>

<section class="home-team-section">
  <div class="home-team-grid">
    {% for member in site.data.team %}
    <a href="/team/#{{ member.id }}" class="home-member">
      <img src="{{ member.image }}" alt="{{ member.name }}" class="home-member-photo" onerror="this.style.display='none'">
      <span class="home-member-name">{{ member.name }}</span>
    </a>
    {% endfor %}
  </div>
  <a href="/team/" class="btn-main">Meet the Team</a>
</section>

<section class="home-thesis-section">
  <h3>Interested in working with us?</h3>
  <p style="color: #666; margin-bottom: 1rem;">
    We are always looking for motivated students for Bachelor and Master theses.
  </p>
  <a href="/thesis/" class="btn-main">View Available Thesis Topics</a>
</section>

<section class="home-pubs-section">
  <h3 style="text-align: center; margin-bottom: 1.5rem;">Recent Research & Publications</h3>
  {% for paper in site.data.papers limit:3 %}
  <div class="pub-preview-card">
    <a href="{{ paper.url }}" target="_blank" class="pub-title">{{ paper.title }}</a>
    <div class="pub-meta">
      {{ paper.year }} • {{ paper.authors }}
    </div>
  </div>
  {% endfor %}
  <div style="text-align: center;">
    <a href="/publications/" class="btn-main">View All Publications</a>
  </div>
</section>
