<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>La'Lifes Studios | Premium FiveM Development</title>
  <meta name="description" content="Fortschrittliche und performante FiveM Scripts für authentisches Roleplay." />

  <style>
    /* Premium Tech-Startup Theme */
    :root {
      --bg: #090a0f;
      --surface: rgba(22, 27, 34, 0.4);
      --border: rgba(255, 255, 255, 0.08);
      --border-hover: rgba(47, 129, 247, 0.4);
      --accent: #2f81f7;
      --accent-glow: rgba(47, 129, 247, 0.15);
      --text-main: #f0f6fc;
      --text-muted: #8b949e;
      --radius: 12px;
      --font-sans: "Inter", system-ui, -apple-system, sans-serif;
      --font-mono: "JetBrains Mono", "Fira Code", ui-monospace, monospace;
    }

    * { box-sizing: border-box; }
    
    body {
      margin: 0;
      font-family: var(--font-sans);
      background-color: var(--bg);
      color: var(--text-main);
      -webkit-font-smoothing: antialiased;
      line-height: 1.6;
      padding: 4rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5rem;
      position: relative;
      overflow-x: hidden;
    }

    /* Das gewisse Extra: Feines Hintergrund-Raster (Blueprint Vibe) */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0; width: 100vw; height: 100vh;
      background-image: 
        linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
      background-size: 32px 32px;
      mask-image: radial-gradient(ellipse 80% 50% at 50% 0%, black 40%, transparent 100%);
      -webkit-mask-image: radial-gradient(ellipse 80% 50% at 50% 0%, black 40%, transparent 100%);
      z-index: -2;
    }

    /* Subtiler Glow im Hintergrund oben Mitte */
    body::after {
      content: "";
      position: absolute;
      top: -150px; left: 50%;
      transform: translateX(-50%);
      width: 600px; height: 400px;
      background: radial-gradient(circle, rgba(47,129,247,0.15) 0%, transparent 70%);
      z-index: -1;
      filter: blur(40px);
    }

    /* Fade-In Animation für die Elemente */
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

    /* Container */
    .container {
      width: 100%;
      max-width: 1000px;
    }

    /* Hero Section */
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
      font-size: 0.85rem;
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
      margin: 0;
      font-size: 3.5rem;
      font-weight: 700;
      letter-spacing: -1px;
      line-height: 1.1;
      /* Edler Text-Gradient */
      background: linear-gradient(180deg, #ffffff 0%, #a2b0c1 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      margin: 0 auto;
      color: var(--text-muted);
      font-size: 1.15rem;
      max-width: 600px;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      margin-top: 1.5rem;
    }

    .btn {
      padding: 0.8rem 1.5rem;
      border-radius: 8px;
      font-weight: 500;
      text-decoration: none;
      font-size: 0.95rem;
      transition: all 0.3s ease;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }

    .btn-primary {
      background-color: var(--accent);
      color: #ffffff;
      box-shadow: 0 4px 14px 0 rgba(47, 129, 247, 0.39);
    }

    .btn-primary:hover {
      background-color: #1f6feb;
      box-shadow: 0 6px 20px rgba(47, 129, 247, 0.23);
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

    /* About Section */
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
      margin: 0;
      font-size: 1.3rem;
      font-weight: 500;
      color: var(--text-main);
    }

    .about-content p {
      margin: 0 0 1.2rem 0;
      color: var(--text-muted);
    }
    .about-content p:last-child { margin-bottom: 0; }

    /* Projects Section */
    .section-header {
      margin-bottom: 2.5rem;
    }

    .section-header h2 {
      margin: 0;
      font-size: 1.75rem;
      font-weight: 600;
      letter-spacing: -0.5px;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    /* Interaktive Cards */
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

    /* Subtiler Glow-Punkt in der Karte beim Hover */
    .card::before {
      content: "";
      position: absolute;
      top: 0; left: 0; width: 100%; height: 100%;
      background: radial-gradient(800px circle at var(--mouse-x, 50%) var(--mouse-y, 0%), rgba(47, 129, 247, 0.06), transparent 40%);
      z-index: 0;
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
    }
    .card:hover::before { opacity: 1; }

    .card > * { position: relative; z-index: 1; }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
    }

    .card-title {
      margin: 0;
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

    /* Pulsierender Live-Indikator */
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
      margin: 0;
      color: var(--text-muted);
      font-size: 0.95rem;
      flex-grow: 1;
      line-height: 1.6;
    }

    /* Footer */
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

    /* Responsive */
    @media (max-width: 768px) {
      body { padding: 2rem 1.5rem; gap: 4rem; }
      .about-grid { grid-template-columns: 1fr; gap: 1.5rem; padding: 1.5rem; }
      .hero h1 { font-size: 2.2rem; }
      .hero-actions { flex-direction: column; width: 100%; }
      .btn { width: 100%; }
    }
  </style>
</head>
<body>

  <header class="container hero animate-in">
    <div class="logo-badge">Est. 2026 // La'Lifes Studios</div>
    <h1>Premium FiveM<br>Development.</h1>
    <p>Performante, sichere und auf Realismus ausgelegte Scripts. Skalierbare Infrastruktur für ambitionierte Roleplay-Projekte.</p>
    
    <div class="hero-actions">
      <a class="btn btn-primary" href="mailto:kontakt@lalifes.studio?subject=Projektanfrage">Projekt anfragen</a>
      <a class="btn btn-secondary" href="#projects">Portfolio ansehen</a>
    </div>
  </header>

  <section class="container animate-in delay-1">
    <div class="about-grid">
      <div class="about-title">
        <h2>System-Architektur & <br>UI-Design</h2>
      </div>
      <div class="about-content">
        <p>
          Als Lead Developer hinter La'Lifes Studios liegt mein Fokus auf der Entwicklung von performanten Systemen, die weit über Standard-Scripts hinausgehen. Ich arbeite intensiv mit modernen Frameworks (wie ESX, ox_lib und ox_target), um ressourcenschonende und nahtlos integrierte Lösungen zu schaffen.
        </p>
        <p>
          Besonderen Wert lege ich dabei auf authentische, physisch wirkende UI-Elemente im Industrial-Design. Von komplexen Leitständen bis hin zu interaktiven Terminals – jedes System wird modular programmiert und ist für den produktiven Servereinsatz optimiert.
        </p>
      </div>
    </div>
  </section>

  <main class="container animate-in delay-2" id="projects">
    <div class="section-header">
      <h2>Ausgewählte Systeme</h2>
    </div>

    <div class="grid">
      <!-- Projekt 1: NEU - AXON BODYCAM & CAD -->
      <article class="card">
        <div class="card-header">
          <div>
            <h3 class="card-title">Axon Body 3 & CAD Dispatch</h3>
            <div class="card-tech">NUI / CAD-UI / CCTV-SPECTATOR</div>
          </div>
          <span class="status-dot"></span>
        </div>
        <p>Fotorealistisches Axon Body 3 System mit interaktivem Hardware-Gehäuse, OLED-Display und physischem Event-Button. Inklusive robustem Leitstellen-Toughpad (Axon Respond CAD) für nahtlose Live-CCTV-Überwachung im Dispatch.</p>
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
        <p>Ein modulares Anzeigen-System für staatliche und private Fraktionen. Berechtigungen und Inhalte werden vollständig serverseitig konfiguriert, unterstützt von einem cleanen User Interface.</p>
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
        <p>Immersives Schlüsselkasten-System zur Fahrzeugausgabe. Entwickelt für Hardcore-RP mit authentischem, industriellem Interaktions-Design statt simplen Menüs.</p>
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
        <p>Vollwertiges DJ-Interface mit xsound-Integration für dynamisches, positionsbasiertes 3D-Audio. Inklusive synchronisierter Nebel- und Lichteffektsteuerung für Event-Locations.</p>
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
        <p>Leitstand-Simulation und Job-Logik für den ÖPNV. Umfassende Fahrplan-Verwaltung, dynamische Wegpunkte und ein realistisch nachempfundenes Bedienfeld für den Fahrer.</p>
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
        <p>Hochflexibles Aufzug-System für mehrstöckige Gebäude. Etagen, Berechtigungen (Job/Item) und Koordinaten frei justierbar. Bedient über ein physisch wirkendes Tastenfeld.</p>
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
        <p>Komplexes Wartungssystem für Elektriker. Bietet dedizierte Schaltkästen im Industrial-Look, bei denen Spieler realistische Fehlerbehebungen und Reparaturmechaniken durchführen müssen.</p>
      </article>
    </div>
  </main>

  <footer class="container animate-in delay-3">
    <div>&copy; 2026 La'Lifes Studios. All rights reserved.</div>
    <div>
      <a href="mailto:kontakt@lalifes.studio">kontakt@lalifes.studio</a>
    </div>
  </footer>

</body>
</html>
