---
layout: none
permalink: /tv-display/
---
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ES3M - Thesis Topics</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      /* Soft off-white background so the white card pops */
      background: #f8fafc;
      color: #333;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .slide-container {
      display: flex;
      flex-direction: column; /* Stack header and content vertically */
      align-items: center;
      justify-content: center;
      width: 90%;
      max-width: 1600px;
      background: #ffffff;
      border: 1px solid #e5e7eb;
      border-radius: 30px;
      padding: 4rem 5rem;
      /* Soft, elegant shadow */
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.08);
    }

    /* Top Centered Logo Section */
    .header-section {
      text-align: center;
      width: 100%;
      margin-bottom: 3.5rem;
    }

    .brand-logo {
      max-height: 160px; /* Made the logo larger for more impact */
      border-radius: 8px;
    }

    /* Bottom Split Content (Text + QR) */
    .content-section {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100%;
      gap: 4rem;
    }

    .text-content {
      max-width: 60%;
    }

    h1 {
      font-size: 5.5rem;
      line-height: 1.1;
      margin: 0 0 1.5rem 0;
      font-weight: 800;
      color: #111827;
    }

    /* Accent color for specific text */
    .text-accent {
      color: #1e90ff;
    }

    p {
      font-size: 2.2rem;
      color: #555;
      margin: 0 0 2.5rem 0;
      line-height: 1.4;
    }

    .highlights {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin-bottom: 3.5rem;
    }

    .highlight-chip {
      background: #f0f7ff;
      border: 2px solid #1e90ff;
      color: #1e90ff;
      padding: 1rem 2.2rem;
      border-radius: 999px;
      font-size: 1.5rem;
      font-weight: 700;
    }

    /* Team Avatars Section */
    .team-section {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .team-title {
      font-size: 1.4rem;
      color: #666;
      margin: 0;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1.5px;
    }

    .avatar-group {
      display: flex;
      align-items: center;
    }

    /* Overlapping circular photos */
    .avatar {
      width: 95px;
      height: 95px;
      border-radius: 50%;
      object-fit: cover;
      /* Thick white border to separate overlapping images */
      border: 5px solid #ffffff;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      margin-left: -20px; 
      background: #f0f0f0;
    }
    
    .avatar:first-child {
      margin-left: 0;
    }

    /* QR Code Section */
    .qr-section {
      background: #ffffff;
      padding: 2.5rem;
      border-radius: 24px;
      text-align: center;
      /* Blue pulse border/shadow */
      border: 3px solid #1e90ff;
      box-shadow: 0 20px 25px -5px rgba(30, 144, 255, 0.15);
      animation: pulse 3s infinite; 
    }

    .qr-code {
      width: 350px;
      height: 350px;
      background: #f1f5f9;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 1.5rem;
      border-radius: 12px;
      overflow: hidden;
    }
    
    .qr-code img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .qr-text {
      color: #1e90ff;
      font-size: 1.9rem;
      font-weight: 800;
      margin: 0;
    }
    
    .qr-subtext {
      color: #666;
      font-size: 1.25rem;
      margin-top: 0.5rem;
      font-weight: 600;
    }

    @keyframes pulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(30, 144, 255, 0.3); }
      70% { transform: scale(1.02); box-shadow: 0 0 0 25px rgba(30, 144, 255, 0); }
      100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(30, 144, 255, 0); }
    }
  </style>
</head>
<body>

  <div class="slide-container">
    
    <!-- Prominent Centered Logo -->
    <div class="header-section">
      <img src="/assets/images/ES3M_Logo.jpg" alt="ES3M Logo" class="brand-logo">
    </div>

    <!-- Main Content Row -->
    <div class="content-section">
      <div class="text-content">
        <h1>Write your Thesis<br><span class="text-accent">with us.</span></h1>
        <p>Join the "From Minerals to Megawatts" team to research the future of clean energy, supply chains, and market design.</p>
        
        <div class="highlights">
          <span class="highlight-chip">Bachelor Theses</span>
          <span class="highlight-chip">Master Theses</span>
          <span class="highlight-chip">Energy Modeling</span>
        </div>

        <div class="team-section">
          <p class="team-title">Meet your supervisors:</p>
          <div class="avatar-group">
            {% for member in site.data.team %}
              <img src="{{ member.image }}" class="avatar" style="object-position: {{ member.object_position | default: 'center' }};" alt="{{ member.name }}">
            {% endfor %}
          </div>
        </div>
      </div>

      <div class="qr-section">
        <div class="qr-code">
          <!-- Replace this source with your actual QR code image -->
          <img src="/assets/images/qr-code-placeholder.png" alt="Scan to see open thesis topics">
        </div>
        <p class="qr-text">Scan for Open Topics</p>
        <div class="qr-subtext">Point your camera here</div>
      </div>
    </div>

  </div>

</body>
</html>
