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
      background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%);
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .slide-container {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 90%;
      max-width: 1600px;
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 30px;
      padding: 5rem;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
    }

    .text-content {
      max-width: 60%;
    }

    .logo {
      font-size: 2rem;
      font-weight: bold;
      color: #93c5fd;
      text-transform: uppercase;
      letter-spacing: 2px;
      margin-bottom: 2rem;
      display: inline-block;
      border-bottom: 2px solid #3b82f6;
      padding-bottom: 0.5rem;
    }

    h1 {
      font-size: 5.5rem;
      line-height: 1.1;
      margin: 0 0 1.5rem 0;
      font-weight: 800;
    }

    p {
      font-size: 2.2rem;
      color: #bfdbfe;
      margin: 0 0 2.5rem 0;
      line-height: 1.4;
    }

    .highlights {
      display: flex;
      gap: 1.5rem;
      flex-wrap: wrap;
    }

    .highlight-chip {
      background: rgba(59, 130, 246, 0.2);
      border: 1px solid #3b82f6;
      padding: 1rem 2rem;
      border-radius: 999px;
      font-size: 1.5rem;
      font-weight: 600;
    }

    .qr-section {
      background: white;
      padding: 2.5rem;
      border-radius: 24px;
      text-align: center;
      box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.2);
      /* Subtle pulse animation to draw the eye */
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
      color: #0f172a;
      font-size: 1.8rem;
      font-weight: 800;
      margin: 0;
    }
    
    .qr-subtext {
      color: #64748b;
      font-size: 1.2rem;
      margin-top: 0.5rem;
      font-weight: 600;
    }

    @keyframes pulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(255,255,255, 0.4); }
      70% { transform: scale(1.02); box-shadow: 0 0 0 25px rgba(255,255,255, 0); }
      100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(255,255,255, 0); }
    }
  </style>
</head>
<body>

  <div class="slide-container">
    <div class="text-content">
      <div class="logo">TU Wien | ES3M</div>
      <h1>Write your Thesis<br>with us.</h1>
      <p>Join the "From Minerals to Megawatts" team to research the future of clean energy, supply chains, and market design.</p>
      
      <div class="highlights">
        <span class="highlight-chip">Bachelor Theses</span>
        <span class="highlight-chip">Master Theses</span>
        <span class="highlight-chip">Energy Modeling</span>
      </div>
    </div>

    <div class="qr-section">
      <div class="qr-code">
        <!-- REPLACE THIS WITH YOUR GENERATED QR CODE IMAGE -->
        <img src="/assets/images/qr-code-placeholder.png" alt="Scan to see open thesis topics">
      </div>
      <p class="qr-text">Scan for Open Topics</p>
      <div class="qr-subtext">Point your camera here</div>
    </div>
  </div>

</body>
</html>
