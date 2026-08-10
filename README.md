<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>La'Lifes Studios | Premium FiveM Development</title>
  <meta name="description" content="Fortschrittliche, performante und immersive FiveM Scripts für anspruchsvolle Roleplay-Server." />
  
  <!-- FontAwesome für HUD Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <!-- Google Site Verification -->
  <meta name="google-site-verification" content="q9aucXo06qaGu6ts-PvlUEnvwP1NcldxJqcdHY231J0" />

  <style>
    /* ==========================================
        1. THEME & VARIABLES (Premium Tech-Startup)
        ========================================== */
    :root {
      --bg: #090a0f;
      --surface: rgba(22, 27, 34, 0.45);
      --surface-solid: #0f141c;
      --border: rgba(255, 255, 255, 0.08);
      --border-hover: rgba(47, 129, 247, 0.4);
      --accent: #2f81f7;
      --accent-glow: rgba(47, 129, 247, 0.15);
      --discord: #5865F2;
      --discord-hover: #4752c4;
      --text-main: #f0f6fc;
      --text-muted: #8b949e;
      --radius: 12px;
      --font-sans: "Inter", system-ui, -apple-system, sans-serif;
      --font-mono: "JetBrains Mono", "Fira Code", ui-monospace, monospace;
      --nav-height: 70px;
    }

    * { 
      box-sizing: border-box; 
      margin: 0;
      padding: 0;
    }
    
    html {
      scroll-behavior: smooth;
      scroll-padding-top: calc(var(--nav-height) + 20px);
    }

    body {
      font-family: var(--font-sans);
      background-color: var(--bg);
      color: var(--text-main);
      -webkit-font-smoothing: antialiased;
      line-height: 1.6;
      padding: calc(var(--nav-height) + 3rem) 2rem 4rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5rem;
      position: relative;
      overflow-x: hidden;
    }

    /* Hintergrund-Raster (Blueprint Vibe) */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0; width: 100vw; height: 100vh;
      background-image: 
        linear-gradient(rgba(255, 255, 255, 0.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.025) 1px, transparent 1px);
      background-size: 32px 32px;
      mask-image: radial-gradient(ellipse 80% 50% at 50% 0%, black 40%, transparent 100%);
      -webkit-mask-image: radial-gradient(ellipse 80% 50% at 50% 0%, black 40%, transparent 100%);
      z-index: -2;
    }

    /* Subtiler Glow oben Mitte */
    body::after {
      content: "";
      position: absolute;
      top: -100px; left: 50%;
      transform: translateX(-50%);
      width: 700px; height: 450px;
      background: radial-gradient(circle, rgba(47,129,247,0.18) 0%, transparent 70%);
      z-index: -1;
      filter: blur(50px);
      pointer-events: none;
    }

    /* ==========================================
        2. NAVIGATION
        ========================================== */
    .navbar {
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: var(--nav-height);
      background: rgba(9, 10, 15, 0.75);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
      padding: 0 2rem;
    }

    .nav-container {
      width: 100%;
      max-width: 1000px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .nav-brand {
      font-weight: 700;
      font-size: 1.1rem;
      letter-spacing: -0.5px;
      color: var(--text-main);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .nav-brand span {
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--text-muted);
      text-decoration: none;
      font-size: 0.95rem;
      font-weight: 500;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--text-main);
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    /* Sprach-Toggle-Button */
    .lang-toggle {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--border);
      color: var(--text-main);
      font-family: var(--font-mono);
      font-size: 0.75rem;
      padding: 0.45rem 0.8rem;
      border-radius: 6px;
      cursor: pointer;
      transition: all 0.2s;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .lang-toggle:hover {
      background: rgba(255, 255, 255, 0.1);
      border-color: var(--border-hover);
    }

    /* ==========================================
        3. BUTTONS & UI-ELEMENTE
        ========================================== */
    .btn {
      padding: 0.8rem 1.5rem;
      border-radius: 8px;
      font-weight: 500;
      text-decoration: none;
      font-size: 0.95rem;
      transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
    }

    .btn-sm {
      padding: 0.5rem 1rem;
      font-size: 0.85rem;
      border-radius: 6px;
    }

    .btn-discord {
      background-color: var(--discord);
      color: #ffffff;
      box-shadow: 0 4px 14px 0 rgba(88, 101, 242, 0.35);
    }

    .btn-discord:hover {
      background-color: var(--discord-hover);
      box-shadow: 0 6px 20px rgba(88, 101, 242, 0.25);
      transform: translateY(-2px);
    }

    .btn-secondary {
      background-color: rgba(255,255,255,0.03);
      color: var(--text-main);
      border: 1px solid var(--border);
      backdrop-filter: blur(10px);
    }

    .btn-secondary:hover {
      background-color: rgba(255,255,255,0.08);
      border-color: rgba(255,255,255,0.2);
      transform: translateY(-2px);
    }

    /* Container */
    .container {
      width: 100%;
      max-width: 1000px;
    }

    /* Fade-In Animation */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .animate-in {
      animation: fadeUp 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
      opacity: 0;
    }
    .delay-1 { animation-delay: 0.1s; }
    .delay-2 { animation-delay: 0.2s; }
    .delay-3 { animation-delay: 0.3s; }

    /* ==========================================
        4. HERO SECTION
        ========================================== */
    .hero {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      align-items: center;
      text-align: center;
    }
    
    .logo-badge {
      display: inline-flex;
      align-items: center;
      font-family: var(--font-mono);
      font-size: 0.8rem;
      color: var(--accent);
      background: rgba(47, 129, 247, 0.1);
      padding: 0.5rem 1rem;
      border-radius: 64px;
      border: 1px solid rgba(47, 129, 247, 0.2);
      text-transform: uppercase;
      letter-spacing: 1px;
      box-shadow: 0 0 20px rgba(47,129,247,0.1);
    }

    .hero h1 {
      font-size: 3.5rem;
      font-weight: 700;
      letter-spacing: -1px;
      line-height: 1.1;
      background: linear-gradient(180deg, #ffffff 0%, #a2b0c1 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      color: var(--text-muted);
      font-size: 1.15rem;
      max-width: 640px;
      line-height: 1.7;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      margin-top: 0.5rem;
    }

    /* ==========================================
        5. ABOUT / ARCHITEKTUR SECTION
        ========================================== */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 3rem;
      background: linear-gradient(145deg, var(--surface), rgba(13, 17, 23, 0.2));
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 2.5rem;
      backdrop-filter: blur(12px);
    }

    .about-title h2 {
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--text-main);
      line-height: 1.3;
    }

    .about-content p {
      margin-bottom: 1.2rem;
      color: var(--text-muted);
    }
    .about-content p:last-child { margin-bottom: 0; }

    /* ==========================================
        6. PROJECTS SECTION
        ========================================== */
    .section-header {
      margin-bottom: 2.5rem;
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
    }

    .section-header h2 {
      font-size: 1.75rem;
      font-weight: 600;
      letter-spacing: -0.5px;
    }

    .section-header p {
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.8rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(10px);
      transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), 
                  border-color 0.3s ease, 
                  box-shadow 0.4s ease;
    }

    .card:hover {
      transform: translateY(-6px);
      border-color: var(--border-hover);
      box-shadow: 0 10px 30px -10px rgba(0,0,0,0.5), 0 0 20px var(--accent-glow);
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
    }

    .card-title {
      font-size: 1.15rem;
      font-weight: 600;
      color: var(--text-main);
    }

    .card-tech {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--accent);
      margin-top: 0.4rem;
      letter-spacing: 0.5px;
    }

    @keyframes pulse {
      0% { box-shadow: 0 0 0 0 rgba(47, 129, 247, 0.4); }
      70% { box-shadow: 0 0 0 6px rgba(47, 129, 247, 0); }
      100% { box-shadow: 0 0 0 0 transparent; }
    }
    
    .status-dot {
      width: 8px;
      height: 8px;
      background-color: var(--accent);
      border-radius: 50%;
      display: inline-block;
      animation: pulse 2s infinite;
    }

    .card p {
      color: var(--text-muted);
      font-size: 0.95rem;
      flex-grow: 1;
      line-height: 1.6;
    }

    /* ==========================================
        7. PARTNER & NETWORK SECTION
        ========================================== */
    .partners-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .partner-card {
      background: var(--surface);
      border: 1px dashed var(--border);
      border-radius: var(--radius);
      padding: 2rem 1.5rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      gap: 0.8rem;
      backdrop-filter: blur(10px);
      transition: all 0.3s ease;
      min-height: 180px;
      text-decoration: none;
      color: var(--text-main);
    }

    .partner-card:hover {
      border-style: solid;
      border-color: var(--border-hover);
      transform: translateY(-4px);
      box-shadow: 0 8px 24px -8px rgba(0,0,0,0.4);
    }

    .partner-badge {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--text-muted);
      background: rgba(255, 255, 255, 0.04);
      padding: 0.35rem 0.8rem;
      border-radius: 20px;
      border: 1px solid rgba(255, 255, 255, 0.06);
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .partner-card h3 {
      font-size: 1.1rem;
      font-weight: 500;
      color: var(--text-main);
    }

    .partner-card p {
      color: var(--text-muted);
      font-size: 0.9rem;
      max-width: 250px;
    }

    /* ==========================================
        8. FIVEM ULTIMATE HUD STYLES (EINGEFÜGT)
        ========================================== */
    /* OBEN RECHTS (Bereits im Seiten-Design integriert via .top-right) */
    .top-right {
      position: fixed;
      top: 85px;
      right: 20px;
      display: flex;
      gap: 10px;
      z-index: 999;
    }

    .hud-pill {
      background: rgba(15, 15, 18, 0.78);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 6px;
      padding: 6px 14px;
      display: flex;
      align-items: center;
      gap: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
      color: #fff;
    }

    .hud-pill .icon {
      font-size: 15px;
      color: rgba(255, 255, 255, 0.6);
    }

    .hud-text-box {
      display: flex;
      flex-direction: column;
    }

    .hud-label {
      font-size: 9px;
      letter-spacing: 0.8px;
      color: rgba(255, 255, 255, 0.4);
      font-weight: 700;
    }

    .hud-value {
      font-size: 13px;
      font-weight: 600;
      color: #ffffff;
    }

    /* WAFFEN-MODUL */
    .weapon-container {
      position: fixed;
      top: 135px;
      right: 20px;
      z-index: 999;
    }
    .weapon-pill {
      border-left: 3px solid #f59e0b;
    }
    .firemode-badge {
      background: rgba(245, 158, 11, 0.2);
      color: #f59e0b;
      font-size: 10px;
      font-weight: 800;
      padding: 3px 6px;
      border-radius: 4px;
      letter-spacing: 0.5px;
    }

    /* UNTEN LINKS: Status-Reihe */
    .bottom-left {
      position: fixed;
      bottom: 25px;
      left: 25px; 
      display: flex;
      align-items: center;
      gap: 8px;
      z-index: 999;
    }

    .status-circle {
      width: 36px;
      height: 36px;
      border-radius: 50%;
      background: rgba(15, 15, 18, 0.78);
      border: 1px solid rgba(255, 255, 255, 0.08);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 14px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
      transition: all 0.2s ease;
      position: relative;
    }

    .voice-tooltip {
      position: absolute;
      top: -25px;
      background: rgba(15, 15, 18, 0.9);
      color: #fff;
      font-size: 9px;
      padding: 2px 6px;
      border-radius: 4px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.2s;
      white-space: nowrap;
    }
    .status-circle:hover .voice-tooltip { opacity: 1; }

    .status-circle.voice-whisper { color: #10b981; border-color: rgba(16, 185, 129, 0.5); }
    .status-circle.voice-normal { color: #3b82f6; border-color: rgba(59, 130, 246, 0.5); }
    .status-circle.voice-shout { color: #ef4444; border-color: rgba(239, 68, 68, 0.6); }

    .status-pill {
      background: rgba(15, 15, 18, 0.78);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 20px;
      padding: 6px 12px;
      display: flex;
      align-items: center;
      gap: 8px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
      color: #fff;
    }
    .status-pill i { font-size: 12px; }

    .bar-bg {
      width: 45px;
      height: 5px;
      background: rgba(255, 255, 255, 0.12);
      border-radius: 10px;
      overflow: hidden;
    }
    .bar {
      height: 100%;
      width: 100%;
      border-radius: 10px;
      transition: width 0.3s ease;
    }

    .health i { color: #ff4a4a; }
    .health .bar { background: #ff4a4a; }
    .pulse i { color: #ec4899; }
    
    @keyframes heartBeat {
      0% { transform: scale(1); }
      15% { transform: scale(1.25); }
      30% { transform: scale(1); }
      45% { transform: scale(1.15); }
      60% { transform: scale(1); }
    }
    .pulse-anim { animation: heartBeat 0.8s infinite ease-in-out; }

    .armor i { color: #3b82f6; }
    .armor .bar { background: #3b82f6; }
    .hunger i { color: #f59e0b; }
    .hunger .bar { background: #f59e0b; }
    .thirst i { color: #06b6d4; }
    .thirst .bar { background: #06b6d4; }

    /* UNTEN RECHTS: Supercar Digital-Tacho */
    .speedo-container {
      position: fixed;
      bottom: 25px;
      right: 25px;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 8px;
      z-index: 999;
    }

    .street-capsule {
      background: rgba(15, 15, 18, 0.85);
      border: 1px solid rgba(255, 255, 255, 0.08);
      padding: 5px 12px;
      border-radius: 20px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 11px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.4);
      color: #fff;
    }
    .street-capsule .compass {
      background: rgba(59, 130, 246, 0.2);
      color: #60a5fa;
      font-weight: 800;
      padding: 2px 6px;
      border-radius: 4px;
      letter-spacing: 1px;
    }
    .street-capsule .street { color: rgba(255,255,255,0.85); font-weight: 600; }

    .speedo-main {
      background: rgba(15, 15, 18, 0.85);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-left: 4px solid #3b82f6;
      padding: 10px 18px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      gap: 15px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.5);
    }

    .gear-display {
      background: rgba(59, 130, 246, 0.15);
      border: 1px solid rgba(59, 130, 246, 0.4);
      width: 32px; height: 32px;
      border-radius: 6px;
      display: flex; align-items: center; justify-content: center;
    }
    #gear-val { font-size: 16px; font-weight: 800; color: #60a5fa; }

    .speed-display { display: flex; align-items: baseline; gap: 6px; }
    #speed-val { font-size: 34px; font-weight: 800; color: #ffffff; letter-spacing: -1px; }
    .kmh { font-size: 11px; font-weight: 700; color: rgba(255,255,255,0.4); letter-spacing: 1px; }

    .vehicle-indicators { display: flex; gap: 10px; align-items: center; }
    .ind-icon { font-size: 13px; color: rgba(255, 255, 255, 0.2); }
    .ind-icon.active-green { color: #2ecc71; text-shadow: 0 0 8px rgba(46, 204, 113, 0.6); }
    .ind-icon.active-red { color: #ff4747; text-shadow: 0 0 8px rgba(255, 71, 71, 0.6); }

    @keyframes pulseWarning {
      0% { transform: scale(1); opacity: 0.8; }
      50% { transform: scale(1.15); opacity: 1; text-shadow: 0 0 12px rgba(255, 71, 71, 0.9); }
      100% { transform: scale(1); opacity: 0.8; }
    }
    .warning-pulse { color: #ff4747 !important; animation: pulseWarning 1s infinite ease-in-out; }

    .rpm-container { width: 100%; height: 4px; background: rgba(255, 255, 255, 0.1); border-radius: 2px; overflow: hidden; }
    .rpm-fill { height: 100%; width: 45%; background: #3b82f6; }

    .speedo-bars { display: flex; gap: 8px; width: 100%; }
    .v-bar {
      flex: 1; background: rgba(15, 15, 18, 0.85); border: 1px solid rgba(255, 255, 255, 0.08);
      padding: 5px 10px; border-radius: 6px; display: flex; align-items: center; gap: 8px; color: #fff;
    }
    .v-bar i { font-size: 11px; }
    .v-bar .bar-bg { width: 100%; height: 4px; }
    .fuel i { color: #10b981; } .fuel .bar { background: #10b981; }
    .engine i { color: #f97316; } .engine .bar { background: #f97316; }

    .hidden { display: none !important; }

    /* ==========================================
        9. FOOTER
        ========================================== */
    footer {
      border-top: 1px solid var(--border);
      padding-top: 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--text-muted);
      font-size: 0.9rem;
      width: 100%;
      margin-top: 2rem;
    }

    footer a {
      color: var(--text-main);
      text-decoration: none;
      transition: color 0.2s;
    }
    footer a:hover { color: var(--accent); }

    /* Responsive Design */
    @media (max-width: 768px) {
      body { padding: calc(var(--nav-height) + 2rem) 1.25rem 4rem 1.25rem; gap: 4rem; }
      .nav-links { display: none; }
      .about-grid { grid-template-columns: 1fr; gap: 1.5rem; padding: 1.5rem; }
      .hero h1 { font-size: 2.3rem; }
      .hero-actions { flex-direction: column; width: 100%; }
      .btn { width: 100%; }
    }
  </style>
</head>
<body>

  <!-- ==========================================
       FIVEM HUD OVERLAY (DEMO-SICHTBAR AUF WEBSEITE)
       ========================================== -->

  <!-- OBEN RECHTS: Slots (Beruf, Geld, ID) -->
  <div class="top-right">
      <div class="hud-pill">
          <i class="fa-solid fa-briefcase icon"></i>
          <div class="hud-text-box">
              <span class="hud-label">BERUF</span>
              <span id="job-value" class="hud-value">Lead Dev - Admin</span>
          </div>
      </div>
      <div class="hud-pill">
          <i class="fa-solid fa-wallet icon"></i>
          <div class="hud-text-box">
              <span class="hud-label">BARGELD</span>
              <span id="money-value" class="hud-value">$24,500</span>
          </div>
      </div>
      <div class="hud-pill">
          <i class="fa-solid fa-id-card icon"></i>
          <div class="hud-text-box">
              <span class="hud-label">ID</span>
              <span id="id-value" class="hud-value">1</span>
          </div>
      </div>
  </div>

  <!-- WAFFEN-MODUL -->
  <div id="weapon-module" class="weapon-container">
      <div class="hud-pill weapon-pill">
          <i class="fa-solid fa-gun icon"></i>
          <div class="hud-text-box">
              <span id="weapon-name" class="hud-label">GEWEHR</span>
              <span id="ammo-value" class="hud-value">30 / 120</span>
          </div>
          <div class="firemode-badge" id="firemode-val">AUTO</div>
      </div>
  </div>

  <!-- UNTEN LINKS: Status-Reihe, Voice & Puls -->
  <div class="bottom-left">
      <div id="voice-indicator" class="status-circle voice-normal">
          <i id="mic-icon" class="fa-solid fa-microphone"></i>
          <span id="voice-range-label" class="voice-tooltip">Normal</span>
      </div>

      <div class="status-pill health">
          <i class="fa-solid fa-heart"></i>
          <div class="bar-bg"><div id="health-bar" class="bar" style="width: 100%;"></div></div>
      </div>

      <div class="status-pill pulse">
          <i class="fa-solid fa-heart-pulse id-pulse-icon pulse-anim"></i>
          <div class="hud-text-box">
              <span class="hud-label">PULS</span>
              <span id="bpm-value" class="hud-value">72 BPM</span>
          </div>
      </div>

      <div id="armor-pill" class="status-pill armor">
          <i class="fa-solid fa-shield-halved"></i>
          <div class="bar-bg"><div id="armor-bar" class="bar" style="width: 80%;"></div></div>
      </div>

      <div class="status-pill hunger">
          <i class="fa-solid fa-burger"></i>
          <div class="bar-bg"><div id="hunger-bar" class="bar" style="width: 90%;"></div></div>
      </div>

      <div class="status-pill thirst">
          <i class="fa-solid fa-droplet"></i>
          <div class="bar-bg"><div id="thirst-bar" class="bar" style="width: 85%;"></div></div>
      </div>
  </div>

  <!-- UNTEN RECHTS: Supercar Digital-Tacho (Demo aktiv) -->
  <div id="speedometer" class="speedo-container">
      <div class="street-capsule">
          <span id="compass-val" class="compass">N</span>
          <span id="street-val" class="street">Vinewood Boulevard</span>
      </div>

      <div class="speedo-main" id="speedo-main-box">
          <div class="gear-display">
              <span id="gear-val">3</span>
          </div>
          <div class="speed-display">
              <span id="speed-val">145</span>
              <span class="kmh">KM/H</span>
          </div>

          <div class="vehicle-indicators">
              <i id="blinker-left" class="fa-solid fa-arrow-left ind-icon"></i>
              <i id="seatbelt-icon" class="fa-solid fa-user-shield ind-icon active-green"></i>
              <i id="engine-icon" class="fa-solid fa-wrench ind-icon"></i>
              <i id="blinker-right" class="fa-solid fa-arrow-right ind-icon active-green"></i>
          </div>
      </div>

      <div class="rpm-container">
          <div id="rpm-bar" class="rpm-fill" style="width: 65%;"></div>
      </div>

      <div class="speedo-bars">
          <div class="v-bar fuel">
              <i class="fa-solid fa-gas-pump"></i>
              <div class="bar-bg"><div id="fuel-bar" class="bar" style="width: 75%;"></div></div>
          </div>
          <div class="v-bar engine">
              <i class="fa-solid fa-car-burst"></i>
              <div class="bar-bg"><div id="engine-bar" class="bar" style="width: 95%;"></div></div>
          </div>
      </div>
  </div>

  <!-- ==========================================
       ORIGINALE WEBSITE INHALTE
       ========================================== -->

  <!-- NACH OBEN FIXIERTE NAVIGATION -->
  <nav class="navbar">
    <div class="nav-container">
      <a href="#" class="nav-brand">LA'LIFES <span>STUDIOS</span></a>
      <ul class="nav-links">
        <li><a href="#about" data-i18n="nav_about">System-Architektur</a></li>
        <li><a href="#projects" data-i18n="nav_projects">Systeme</a></li>
        <li><a href="#partners" data-i18n="nav_partners">Netzwerk</a></li>
      </ul>
      <div class="nav-actions">
        <button class="lang-toggle" id="langToggle" title="Sprache ändern / Change Language">
          🌐 <span id="currentLangLabel">DE</span>
        </button>
        <a class="btn btn-discord btn-sm" href="https://discord.gg/hHCtR4T8wN" target="_blank" rel="noopener noreferrer" data-i18n="nav_discord">
          Discord beitreten
        </a>
      </div>
    </div>
  </nav>

  <!-- HERO SECTION -->
  <header class="container hero animate-in">
    <div class="logo-badge" data-i18n="hero_badge">Est. 2026 // La'Lifes Studios</div>
    <h1 data-i18n="hero_title">Premium FiveM<br>Development.</h1>
    <p data-i18n="hero_sub">
      Performante, hochgradig optimierte Scripts für authentisches Roleplay. Skalierbare Infrastruktur und maßgeschneidertes NUI-Design für ambitionierte Server-Projekte.
    </p>
    
    <div class="hero-actions">
      <a class="btn btn-discord" href="https://discord.gg/hHCtR4T8wN" target="_blank" rel="noopener noreferrer" data-i18n="btn_discord_main">
        Auf Discord anfragen
      </a>
      <a class="btn btn-secondary" href="#projects" data-i18n="btn_portfolio">
        Systeme ansehen
      </a>
    </div>
  </header>

  <!-- ABOUT SECTION -->
  <section class="container animate-in delay-1" id="about">
    <div class="about-grid">
      <div class="about-title">
        <h2 data-i18n="about_title">System-Architektur & <br>UI-Design</h2>
      </div>
      <div class="about-content">
        <p data-i18n="about_p1">
          Als Lead Developer hinter La'Lifes Studios liegt mein Fokus auf der Entwicklung von performanten Systemen, die weit über Standard-Scripts hinausgehen. Ich arbeite intensiv mit modernen Frameworks (wie ESX, ox_lib und ox_target), um ressourcenschonende und nahtlos integrierte Lösungen zu schaffen.
        </p>
        <p data-i18n="about_p2">
          Besonderen Wert lege ich dabei auf authentische, physisch wirkende UI-Elemente im Industrial-Design. Von komplexen Leitständen bis hin zu interaktiven Terminals – jedes System wird modular programmiert und ist für den produktiven Servereinsatz unter hoher Last optimiert.
        </p>
      </div>
    </div>
  </section>

  <!-- PROJECTS SECTION -->
  <main class="container animate-in delay-2" id="projects">
    <div class="section-header">
      <div>
        <h2 data-i18n="projects_title">Ausgewählte Systeme</h2>
      </div>
      <p data-i18n="projects_sub">Für produktiven Einsatz optimiert</p>
    </div>

    <div class="grid">
      <!-- Projekt 1 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Axon Body 3 & CAD Dispatch</h3>
            <div class="card-tech">NUI / CAD-UI / CCTV-SPECTATOR</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p1_desc">Fotorealistisches Axon Body 3 System mit interaktivem Hardware-Gehäuse, OLED-Display und physischem Event-Button. Inklusive robustem Leitstellen-Toughpad (Axon Respond CAD) für nahtlose Live-CCTV-Überwachung im Dispatch.</p>
      </article>

      <!-- Projekt 2 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Ads System</h3>
            <div class="card-tech">ESX / UI / COMMAND</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p2_desc">Ein modulares Anzeigen-System für staatliche und private Fraktionen. Berechtigungen und Inhalte werden vollständig serverseitig konfiguriert, unterstützt von einem cleanen User Interface.</p>
      </article>

      <!-- Projekt 3 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">KeyCabinet</h3>
            <div class="card-tech">OX_TARGET / HARDCORE RP</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p3_desc">Immersives Schlüsselkasten-System zur Fahrzeugausgabe. Entwickelt für Hardcore-RP mit authentischem, industriellem Interaktions-Design statt simplen Menüs.</p>
      </article>

      <!-- Projekt 4 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">DJ Pult</h3>
            <div class="card-tech">XSOUND / FX / UI</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p4_desc">Vollwertiges DJ-Interface mit xsound-Integration für dynamisches, positionsbasiertes 3D-Audio. Inklusive synchronisierter Nebel- und Lichteffektsteuerung für Event-Locations.</p>
      </article>

      <!-- Projekt 5 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Busdriver Dispatch</h3>
            <div class="card-tech">JOB-SYSTEM / LOGIC</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p5_desc">Leitstand-Simulation und Job-Logik für den ÖPNV. Umfassende Fahrplan-Verwaltung, dynamische Wegpunkte und ein realistisch nachempfundenes Bedienfeld für den Fahrer.</p>
      </article>

      <!-- Projekt 6 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Elevator Control</h3>
            <div class="card-tech">OX_LIB / CONFIG</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p6_desc">Hochflexibles Aufzug-System für mehrstöckige Gebäude. Etagen, Berechtigungen (Job/Item) und Koordinaten frei justierbar. Bedient über ein physisch wirkendes Tastenfeld.</p>
      </article>

      <!-- Projekt 7 -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Electrician Mechanics</h3>
            <div class="card-tech">MINIJOB / INTERACTION</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p data-i18n="p7_desc">Komplexes Wartungssystem für Elektriker. Bietet dedizierte Schaltkästen im Industrial-Look, bei denen Spieler realistische Fehlerbehebungen und Reparaturmechaniken durchführen müssen.</p>
      </article>
    </div>
  </main>

  <!-- PARTNER & NETWORK SECTION -->
  <section class="container animate-in delay-3" id="partners">
    <div class="section-header">
      <div>
        <h2 data-i18n="partners_title">Partner & Netzwerk</h2>
      </div>
      <p data-i18n="partners_sub">Zusammenarbeit & Server-Netzwerk</p>
    </div>

    <div class="partners-grid">
      <!-- Partner Slot #01 -->
      <a href="https://discord.gg/VgHFdNEqu3" target="_blank" rel="noopener noreferrer" class="partner-card">
        <span class="partner-badge" data-i18n="partner1_badge">Offizieller Beta-Server</span>
        <h3>HohenWald Roleplay</h3>
        <p data-i18n="partner_p1">Ein enger Partner im La'Lifes-Entwicklungsnetzwerk. Ausgewählte neue Scripts und Systeme werden hier exklusiv im Live-Betrieb als Beta getestet.</p>
      </a>

      <!-- Partner Slot #02 -->
      <a href="https://discord.gg/ssla" target="_blank" rel="noopener noreferrer" class="partner-card">
        <span class="partner-badge" data-i18n="partner2_badge">Partner Server</span>
        <h3>South Side Los Angeles</h3>
        <p data-i18n="partner_p2">Offizieller Partner von La'Lifes Studios. Das Projekt setzt im Live-Betrieb auf ausgewählte, performante Scripts aus unserer Entwicklung.</p>
      </a>

      <!-- Partner Slot #03 -->
      <div class="partner-card">
        <span class="partner-badge">Partner Slot #03</span>
        <h3 data-i18n="partner_free">Platz frei</h3>
        <p data-i18n="partner_p3">Raum für gemeinsame FiveM-Infrastruktur und Development-Kooperationen.</p>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="container animate-in delay-3">
    <div>&copy; 2026 La'Lifes Studios. <span data-i18n="footer_rights">Alle Rechte vorbehalten.</span></div>
    <div>
      <a href="https://discord.gg/hHCtR4T8wN" target="_blank" rel="noopener noreferrer">Discord Community</a>
    </div>
  </footer>

  <!-- ==========================================
       AUTOMATISCHE SPRACHERKENNUNG (I18N)
       ========================================== -->
  <script>
    const translations = {
      de: {
        nav_about: "System-Architektur",
        nav_projects: "Systeme",
        nav_partners: "Netzwerk",
        nav_discord: "Discord beitreten",
        hero_badge: "Est. 2026 // La'Lifes Studios",
        hero_title: "Premium FiveM<br>Development.",
        hero_sub: "Performante, hochgradig optimierte Scripts für authentisches Roleplay. Skalierbare Infrastruktur und maßgeschneidertes NUI-Design für ambitionierte Server-Projekte.",
        btn_discord_main: "Auf Discord anfragen",
        btn_portfolio: "Systeme ansehen",
        about_title: "System-Architektur & <br>UI-Design",
        about_p1: "Als Lead Developer hinter La'Lifes Studios liegt mein Fokus auf der Entwicklung von performanten Systemen, die weit über Standard-Scripts hinausgehen. Ich arbeite intensiv mit modernen Frameworks (wie ESX, ox_lib und ox_target), um ressourcenschonende und nahtlos integrierte Lösungen zu schaffen.",
        about_p2: "Besonderen Wert lege ich dabei auf authentische, physisch wirkende UI-Elemente im Industrial-Design. Von komplexen Leitständen bis hin zu interaktiven Terminals – jedes System wird modular programmiert und ist für den produktiven Servereinsatz unter hoher Last optimiert.",
        projects_title: "Ausgewählte Systeme",
        projects_sub: "Für produktiven Einsatz optimiert",
        p1_desc: "Fotorealistisches Axon Body 3 System mit interaktivem Hardware-Gehäuse, OLED-Display und physischem Event-Button. Inklusive robustem Leitstellen-Toughpad (Axon Respond CAD) für nahtlose Live-CCTV-Überwachung im Dispatch.",
        p2_desc: "Ein modulares Anzeigen-System für staatliche und private Fraktionen. Berechtigungen und Inhalte werden vollständig serverseitig konfiguriert, unterstützt von einem cleanen User Interface.",
        p3_desc: "Immersives Schlüsselkasten-System zur Fahrzeugausgabe. Entwickelt für Hardcore-RP mit authentischem, industriellem Interaktions-Design statt simplen Menüs.",
        p4_desc: "Vollwertiges DJ-Interface mit xsound-Integration für dynamisches, positionsbasiertes 3D-Audio. Inklusive synchronisierter Nebel- und Lichteffektsteuerung für Event-Locations.",
        p5_desc: "Leitstand-Simulation und Job-Logik für den ÖPNV. Umfassende Fahrplan-Verwaltung, dynamische Wegpunkte und ein realistisch nachempfundenes Bedienfeld für den Fahrer.",
        p6_desc: "Hochflexibles Aufzug-System für mehrstöckige Gebäude. Etagen, Berechtigungen (Job/Item) und Koordinaten frei justierbar. Bedient über ein physisch wirkendes Tastenfeld.",
        p7_desc: "Komplexes Wartungssystem für Elektriker. Bietet dedizierte Schaltkästen im Industrial-Look, bei denen Spieler realistische Fehlerbehebungen und Reparaturmechaniken durchführen müssen.",
        partners_title: "Partner & Netzwerk",
        partners_sub: "Zusammenarbeit & Server-Netzwerk",
        partner1_badge: "Offizieller Beta-Server",
        partner_p1: "Ein enger Partner im La'Lifes-Entwicklungsnetzwerk. Ausgewählte neue Scripts und Systeme werden hier exklusiv im Live-Betrieb als Beta getestet.",
        partner2_badge: "Partner Server",
        partner_p2: "Offizieller Partner von La'Lifes Studios. Das Projekt setzt im Live-Betrieb auf ausgewählte, performante Scripts aus unserer Entwicklung.",
        partner_free: "Platz frei",
        partner_p3: "Raum für gemeinsame FiveM-Infrastruktur und Development-Kooperationen.",
        footer_rights: "Alle Rechte vorbehalten."
      },
      en: {
        nav_about: "Architecture",
        nav_projects: "Systems",
        nav_partners: "Network",
        nav_discord: "Join Discord",
        hero_badge: "Est. 2026 // La'Lifes Studios",
        hero_title: "Premium FiveM<br>Development.",
        hero_sub: "High-performance, optimized scripts for authentic roleplay. Scalable infrastructure and bespoke NUI design for ambitious server projects.",
        btn_discord_main: "Inquire on Discord",
        btn_portfolio: "View Systems",
        about_title: "System Architecture & <br>UI Design",
        about_p1: "As the lead developer behind La'Lifes Studios, my focus lies on engineering performant systems that go far beyond standard scripts. I work extensively with modern frameworks (such as ESX, ox_lib, and ox_target) to deliver highly optimized, seamlessly integrated solutions.",
        about_p2: "I place great value on authentic, physically tactile UI elements with an industrial design aesthetic. From complex dispatch rooms to interactive terminals – every system is modularly coded and optimized for production server environments under heavy load.",
        projects_title: "Featured Systems",
        projects_sub: "Engineered for production environments",
        p1_desc: "Photorealistic Axon Body 3 system featuring an interactive hardware casing, OLED display, and physical event button. Includes a rugged dispatch toughpad (Axon Respond CAD) for seamless live CCTV monitoring.",
        p2_desc: "A modular announcement system for public and private factions. Permissions and content are entirely server-side configured, backed by a clean user interface.",
        p3_desc: "Immersive key cabinet system for vehicle dispatching. Tailored for hardcore roleplay with an authentic, industrial interaction design instead of basic menus.",
        p4_desc: "Full-featured DJ interface with xsound integration for dynamic, positional 3D audio. Includes synchronized fog and stage lighting controls for event venues.",
        p5_desc: "Control center simulation and job logic for public transit. Extensive schedule management, dynamic waypoints, and a realistically recreated control panel for drivers.",
        p6_desc: "Highly flexible elevator system for multi-story buildings. Floors, permissions (job/item), and coordinates are fully customizable. Controlled via a physically tactile keypad.",
        p7_desc: "Complex maintenance system for electricians. Features dedicated switchboxes in an industrial style where players must perform realistic troubleshooting and repairs.",
        partners_title: "Partners & Network",
        partners_sub: "Collaborations & Server Network",
        partner1_badge: "Official Beta Server",
        partner_p1: "A close partner in the La'Lifes development network. Selected new scripts and systems are exclusively beta-tested here in a live production environment.",
        partner2_badge: "Partner Server",
        partner_p2: "Official partner of La'Lifes Studios. This project utilizes selected, high-performance scripts from our development in their live environment.",
        partner_free: "Open Slot",
        partner_p3: "Space for shared FiveM infrastructure and development collaborations.",
        footer_rights: "All rights reserved."
      }
    };

    let currentLang = 'de';

    function detectLanguage() {
      const userLang = navigator.language || navigator.userLanguage || 'de';
      if (!userLang.toLowerCase().startsWith('de')) {
        currentLang = 'en';
      } else {
        currentLang = 'de';
      }
      applyLanguage(currentLang);
    }

    function applyLanguage(lang) {
      currentLang = lang;
      document.documentElement.lang = lang;
      document.getElementById('currentLangLabel').textContent = lang.toUpperCase();

      const elements = document.querySelectorAll('[data-i18n]');
      elements.forEach(el => {
        const key = el.getAttribute('data-i18n');
        if (translations[lang] && translations[lang][key]) {
          el.innerHTML = translations[lang][key];
        }
      });
    }

    document.getElementById('langToggle').addEventListener('click', () => {
      const nextLang = currentLang === 'de' ? 'en' : 'de';
      applyLanguage(nextLang);
    });

    window.addEventListener('DOMContentLoaded', detectLanguage);
  </script>
</body>
</html>
