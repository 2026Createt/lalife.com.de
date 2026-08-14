<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>La'Lifes Studios | Raw FiveM Development</title>
  <meta name="description" content="FiveM Scripts ohne Bullshit. Entwickelt von Paul." />
  
  <style>
    /* ==========================================
        1. THEME & VARIABLES (Raw Developer Vibe)
        ========================================== */
    :root {
      --bg: #050505;
      --surface: #111111;
      --surface-border: #222222;
      --accent: #f03e3e; /* Ein aggressiveres, klares Rot für Akzente */
      --accent-glow: rgba(240, 62, 62, 0.2);
      --text-main: #f8f9fa;
      --text-muted: #868e96;
      --terminal-header: #1a1a1a;
      --font-sans: "Inter", -apple-system, sans-serif;
      --font-mono: "JetBrains Mono", "Fira Code", monospace;
    }

    * { 
      box-sizing: border-box; 
      margin: 0;
      padding: 0;
    }
    
    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: var(--font-sans);
      background-color: var(--bg);
      color: var(--text-main);
      -webkit-font-smoothing: antialiased;
      line-height: 1.6;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 0 1.5rem;
      overflow-x: hidden;
    }

    /* Subtiles Grid im Hintergrund */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0; width: 100vw; height: 100vh;
      background-image: 
        linear-gradient(rgba(255, 255, 255, 0.015) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.015) 1px, transparent 1px);
      background-size: 40px 40px;
      z-index: -2;
    }

    .container {
      width: 100%;
      max-width: 900px; /* Etwas schmaler für besseren Lesefluss */
      margin: 0 auto;
    }

    /* ==========================================
        2. HERO SECTION
        ========================================== */
    .hero {
      margin-top: 10vh;
      margin-bottom: 5rem;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      border-left: 4px solid var(--accent);
      padding-left: 2rem;
    }
    
    .hero h1 {
      font-size: 4rem;
      font-weight: 800;
      letter-spacing: -2px;
      line-height: 1;
      text-transform: uppercase;
    }

    .hero h1 span {
      color: var(--accent);
    }

    .hero p {
      color: var(--text-muted);
      font-size: 1.25rem;
      max-width: 600px;
      font-weight: 400;
    }

    /* ==========================================
        3. ABOUT ME (Terminal Style)
        ========================================== */
    .about-section {
      margin-bottom: 6rem;
    }

    .terminal-window {
      background: var(--surface);
      border: 1px solid var(--surface-border);
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }

    .terminal-header {
      background: var(--terminal-header);
      padding: 0.8rem 1rem;
      border-bottom: 1px solid var(--surface-border);
      display: flex;
      gap: 0.5rem;
      align-items: center;
    }

    .terminal-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
    }
    .dot-1 { background: #ff5f56; }
    .dot-2 { background: #ffbd2e; }
    .dot-3 { background: #27c93f; }

    .terminal-title {
      margin-left: 1rem;
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .terminal-body {
      padding: 2rem;
      font-family: var(--font-mono);
      font-size: 0.95rem;
      color: #d1d5db;
    }

    .terminal-body p {
      margin-bottom: 1.5rem;
    }
    .terminal-body p:last-child { margin-bottom: 0; }
    
    .highlight { color: var(--accent); }

    /* ==========================================
        4. SCRIPTS SECTION
        ========================================== */
    .section-title {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 2rem;
      text-transform: uppercase;
      letter-spacing: -1px;
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .section-title::after {
      content: "";
      height: 1px;
      flex-grow: 1;
      background: var(--surface-border);
    }

    .scripts-grid {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      margin-bottom: 6rem;
    }

    .script-card {
      background: transparent;
      border: 1px solid var(--surface-border);
      padding: 2rem;
      border-radius: 8px;
      transition: all 0.2s ease;
      position: relative;
    }

    .script-card:hover {
      border-color: var(--accent);
      background: rgba(240, 62, 62, 0.02);
    }

    .script-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 1rem;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .script-title {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--text-main);
    }

    .script-tech {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      color: var(--accent);
      padding: 0.2rem 0.6rem;
      border: 1px solid var(--accent-glow);
      border-radius: 4px;
      background: rgba(240, 62, 62, 0.05);
    }

    .script-card p {
      color: var(--text-muted);
      font-size: 1rem;
      max-width: 800px;
    }

    /* ==========================================
        5. FOOTER & DISCORD CALL
        ========================================== */
    .cta-section {
      text-align: center;
      padding: 4rem 0;
      border-top: 1px solid var(--surface-border);
      margin-top: 2rem;
    }

    .btn-discord {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--text-main);
      color: var(--bg);
      padding: 1rem 2rem;
      font-weight: 700;
      font-family: var(--font-mono);
      text-decoration: none;
      border-radius: 4px;
      text-transform: uppercase;
      transition: transform 0.2s;
    }

    .btn-discord:hover {
      transform: translateY(-3px);
    }

    footer {
      text-align: center;
      padding-bottom: 2rem;
      color: var(--text-muted);
      font-family: var(--font-mono);
      font-size: 0.8rem;
    }

    @media (max-width: 768px) {
      .hero h1 { font-size: 2.8rem; }
      .hero { padding-left: 1rem; border-left-width: 2px; }
      .terminal-body { padding: 1.5rem; font-size: 0.85rem; }
    }
  </style>
</head>
<body>

  <main class="container">
    
    <!-- HERO SECTION -->
    <header class="hero">
      <h1>La'Lifes<br><span>Studios.</span></h1>
      <p>Dein wahrscheinlich erhlichster FiveM Scripte Shop</p>
    </header>

    <!-- ABOUT ME / DIE WAHRHEIT -->
    <section class="about-section">
      <div class="terminal-window">
        <div class="terminal-header">
          <div class="terminal-dot dot-1"></div>
          <div class="terminal-dot dot-2"></div>
          <div class="terminal-dot dot-3"></div>
          <div class="terminal-title">paul@lalifes-studios: ~/about_me</div>
        </div>
        <div class="terminal-body">
          <p>
            <span class="highlight">> Wer steckt dahinter?</span><br>
            Ich bin Paul, 16 Jahre alt. Keine große Agentur, kein riesiges Team, nur ich. Ich entwickle FiveM-Scripte, weil mich der Standard-Kram auf den meisten Servern einfach nur genervt hat.
          </p>
          <p>
            <span class="highlight">> Warum dieses Projekt?</span><br>
            Ich habe gemerkt, dass viele Server mit halbfertigen, schlecht performenden Scripts rumlaufen. Ich will Systeme bauen, die einzigartig sind, gut aussehen und dem Server echten Mehrwert bieten.
          </p>
          <p>
            <span class="highlight">> Der Qualitätsanspruch</span><br>
            Ich habe vor kurzem kräftig ausgemistet. Ich verkaufe keinen Müll mehr, nur um ein paar Leute auf den Discord zu locken. Was du hier auf der Seite siehst, ist das gute Zeug. Sachen, in die ich Zeit und Nerven gesteckt habe und die wirklich funktionieren. Punkt.
          </p>
        </div>
      </div>
    </section>

    <!-- SCRIPTS SECTION -->
    <section class="scripts-section">
      <h2 class="section-title">Die Systeme</h2>
      
      <div class="scripts-grid">
        
        <!-- Script: BMA -->
        <article class="script-card">
          <div class="script-header">
            <h3 class="script-title">BMA-System (Brandmeldeanlage)</h3>
            <span class="script-tech">ESX / QB / NUI</span>
          </div>
          <p>Kein simples "/feuer"-Command. Eine realistische Brandmeldeanlage. Scheibe einschlagen, Knopf drücken – physisch bedienbar. Dazu gibt es ein durchdachtes Admin-Panel und ein Tablet (MDT) für die echte Feuerwehr-Koordination. So funktioniert ordentliches RP.</p>
        </article>

        <!-- Script: HUD -->
        <article class="script-card">
          <div class="script-header">
            <h3 class="script-title">Ultimate Glassmorphism HUD</h3>
            <span class="script-tech">HTML / CSS / JS / NUI</span>
          </div>
          <p>Vergiss klobige Anzeigen, die den halben Bildschirm verdecken. Das hier ist ein High-End HUD im cleanen Glas-Design. Alles ist drin: Dynamischer Puls, Waffen-Modul, PMA-Voice Reichweite, Gänge, Schaltblitz, Anschnaller und Blinker. Sieht verdammt gut aus und zieht keine Leistung.</p>
        </article>

        <!-- Script: BODYCAM -->
        <article class="script-card">
          <div class="script-header">
            <h3 class="script-title">Axon Body 3 & CAD Dispatch</h3>
            <span class="script-tech">NUI / CCTV</span>
          </div>
          <p>Die meisten Bodycams sind nur ein billiges Overlay. Das hier ist ein fotorealistisches Axon Body 3 System. Interaktives Gehäuse, funktionierendes OLED-Display und ein physischer Event-Button. Der Dispatch kann live über ein Leitstellen-Toughpad zuschauen. Für Fraktionen, die es ernst meinen.</p>
        </article>

        <!-- Script: KEY CABINET -->
        <article class="script-card">
          <div class="script-header">
            <h3 class="script-title">KeyCabinet</h3>
            <span class="script-tech">OX_TARGET / HARDCORE RP</span>
          </div>
          <p>Fahrzeuge per Dropdown-Menü ausparken ist langweilig. Dieses Script bringt einen physischen, interaktiven Schlüsselkasten ins Spiel. Im industriellen Look. Du willst ein Auto? Hol dir den Schlüssel. Gemacht für Hardcore-RP.</p>
        </article>

        <!-- Script: ELEVATOR -->
        <article class="script-card">
          <div class="script-header">
            <h3 class="script-title">Elevator Control</h3>
            <span class="script-tech">OX_LIB / CONFIG</span>
          </div>
          <p>Ein simples, aber extrem effektives Aufzug-System für mehrstöckige Gebäude. Über die Config kannst du Etagen, Berechtigungen (Job oder Items) und Koordinaten völlig frei anpassen. Die Bedienung läuft über ein realistisches Tastenfeld. Tut genau das, was es soll.</p>
        </article>

      </div>
    </section>

    <!-- DISCORD CTA -->
    <section class="cta-section">
      <p style="margin-bottom: 1.5rem; color: var(--text-muted); font-size: 1.1rem;">Interesse an den Systemen oder Fragen? Meld dich direkt bei mir.</p>
      <a href="https://discord.gg/hHCtR4T8wN" class="btn-discord" target="_blank" rel="noopener">
        > Join the Discord
      </a>
    </section>

  </main>

  <footer>
    &copy; 2026 La'Lifes Studios. Developed by Paul.
  </footer>

</body>
</html>
