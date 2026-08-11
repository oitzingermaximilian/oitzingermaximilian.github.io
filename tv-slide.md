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
      background: #f8fafc;
      color: #333;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .slide-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      width: 90%;
      max-width: 1600px;
      background: #ffffff;
      border: 1px solid #e5e7eb;
      border-radius: 30px;
      padding: 4rem 5rem;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.08);
      position: relative;
      overflow: hidden; /* Keeps the watermark inside the box */
    }

    /* Massive Background Watermark */
    .slide-container::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 80%;
      height: 80%;
      background-image: url('/assets/images/ES3M_Logo.jpg');
      background-repeat: no-repeat;
      background-position: center;
      background-size: contain;
      opacity: 0.04; /* Very faint so text is still readable */
      z-index: 0;
      pointer-events: none;
    }

    /* Ensures content stays above the watermark */
    .header-section, .content-section {
      position: relative;
      z-index: 1;
    }

    /* Top Centered Logo Section */
    .header-section {
      text-align: center;
      width: 100%;
      margin-bottom: 3.5rem;
    }

    .brand-logo {
      max-height: 240px; /* MASSIVELY INCREASED */
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
      font-size: 6rem;
      line-height: 1.1;
      margin: 0 0 2.5rem 0;
      font-weight: 800;
      color: #111827;
    }

    .text-accent {
      color: #1e90ff;
    }

    .highlights {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin-bottom: 4rem;
    }

    .highlight-chip {
      background: #f0f7ff;
      border: 2px solid #1e90ff;
      color: #1e90ff;
      padding: 1.2rem 2.5rem;
      border-radius: 999px;
      font-size: 1.8rem;
      font-weight: 700;
    }

    /* Team Avatars Section */
    .team-section {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }

    .team-title {
      font-size: 1.6rem;
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

    .avatar {
      width: 110px;
      height: 110px;
      border-radius: 50%;
      object-fit: cover;
      border: 6px solid #ffffff;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      margin-left: -25px; 
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
      70% { transform: scale(1.02); box-shadow: 0 0 0 35px rgba(30, 144, 255, 0); }
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
        
        <div class="highlights">
          <span class="highlight-chip">Bachelor Theses</span>
          <span class="highlight-chip">Master Theses</span>
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
          <img src="/assets/images/qr-code.png" alt="Scan to see open thesis topics">
        </div>
        <p class="qr-text">Scan for Open Topics</p>
        <div class="qr-subtext">Point your camera here</div>
      </div>
    </div>

  </div>

</body>
</html>
