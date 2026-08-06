
<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>La'Lifes Studios | Premium FiveM Development</title>
  <meta name="description" content="Fortschrittliche und performante FiveM Scripts für authentisches Roleplay." />

  <style>
    /* Professionelles, technisches Dark-Theme (Industrial / Clean) */
    :root {
      --bg: #0d1117;
      --surface: #161b22;
      --border: #30363d;
      --border-hover: #8b949e;
      --accent: #2f81f7;
      --accent-hover: #1f6feb;
      --text-main: #e6edf3;
      --text-muted: #8b949e;
      --radius: 6px;
      --font-sans: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
      --font-mono: "JetBrains Mono", "Fira Code", ui-monospace, Menlo, Monaco, monospace;
    }

    * { 
      box-sizing: border-box; 
    }
    
    body {
      margin: 0;
      font-family: var(--font-sans);
      background-color: var(--bg);
      color: var(--text-main);
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      line-height: 1.6;
      padding: 3rem 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4rem;
    }

    /* Container */
    .container {
      width: 100%;
      max-width: 1000px;
    }

    /* Header / Hero */
    .hero {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      border-bottom: 1px solid var(--border);
      padding-bottom: 3rem;
    }
    
    .logo-badge {
      display: inline-flex;
      align-items: center;
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--accent);
      background: rgba(47, 129, 247, 0.1);
      padding: 0.4rem 0.8rem;
      border-radius: 4px;
      border: 1px solid rgba(47, 129, 247, 0.2);
      width: fit-content;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .hero h1 {
      margin: 0;
      font-size: 2.5rem;
      font-weight: 600;
      letter-spacing: -0.5px;
    }

    .hero p {
      margin: 0;
      color: var(--text-muted);
      font-size: 1.1rem;
      max-width: 600px;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      margin-top: 1rem;
    }

    .btn {
      padding: 0.75rem 1.25rem;
      border-radius: var(--radius);
      font-weight: 500;
      text-decoration: none;
      font-size: 0.95rem;
      transition: all 0.2s ease;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }

    .btn-primary {
      background-color: var(--accent);
      color: #ffffff;
      border: 1px solid var(--accent);
    }

    .btn-primary:hover {
      background-color: var(--accent-hover);
      border-color: var(--accent-hover);
    }

    .btn-secondary {
      background-color: transparent;
      color: var(--text-main);
      border: 1px solid var(--border);
    }

    .btn-secondary:hover {
      border-color: var(--border-hover);
      background-color: var(--surface);
    }

    /* Info Section */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 2fr;
      gap: 2rem;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 2rem;
    }

    .about-title h2 {
      margin: 0;
      font-size: 1.2rem;
      font-weight: 500;
    }

    .about-content p {
      margin: 0 0 1rem 0;
      color: var(--text-muted);
    }
    
    .about-content p:last-child {
      margin-bottom: 0;
    }

    /* Projects */
    .section-header {
      margin-bottom: 2rem;
      display: flex;
      align-items: baseline;
      justify-content: space-between;
    }

    .section-header h2 {
      margin: 0;
      font-size: 1.5rem;
      font-weight: 600;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      transition: border-color 0.2s ease;
    }

    .card:hover {
      border-color: var(--border-hover);
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
    }

    .card-title {
      margin: 0;
      font-size: 1.1rem;
      font-weight: 500;
      color: var(--text-main);
    }

    .card-tech {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--accent);
      margin-top: 0.25rem;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      background-color: var(--accent);
      border-radius: 50%;
      display: inline-block;
    }

    .card p {
      margin: 0;
      color: var(--text-muted);
      font-size: 0.95rem;
      flex-grow: 1;
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
    }

    footer a {
      color: var(--text-main);
      text-decoration: none;
      transition: color 0.2s;
    }

    footer a:hover {
      color: var(--accent);
    }

    /* Responsive */
    @media (max-width: 768px) {
      body { padding: 2rem 1.5rem; gap: 3rem; }
      .about-grid { grid-template-columns: 1fr; gap: 1rem; }
      .hero h1 { font-size: 2rem; }
      .hero-actions { flex-direction: column; }
    }
  </style>
</head>
<body>

  <header class="container hero">
    <div class="logo-badge">Est. 2026 // La'Lifes Studios</div>
    <h1>Premium FiveM Development.</h1>
    <p>Performante, sichere und auf Realismus ausgelegte Scripts. Skalierbare Infrastruktur für ambitionierte Roleplay-Projekte.</p>
    
    <div class="hero-actions">
      <a class="btn btn-primary" href="mailto:kontakt@lalifes.studio?subject=Projektanfrage">Projekt anfragen</a>
      <a class="btn btn-secondary" href="#projects">Portfolio ansehen</a>
    </div>
  </header>

  <section class="container">
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

  <main class="container" id="projects">
    <div class="section-header">
      <h2>Ausgewählte Systeme</h2>
    </div>

    <div class="grid">
      <!-- Projekt 1 -->
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

      <!-- Projekt 2 -->
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

      <!-- Projekt 3 -->
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

      <!-- Projekt 4 -->
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

      <!-- Projekt 5 -->
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

      <!-- Projekt 6 -->
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

  <footer class="container">
    <div>&copy; 2026 La'Lifes Studios. All rights reserved.</div>
    <div>
      <a href="mailto:kontakt@lalifes.studio">kontakt@lalifes.studio</a>
    </div>
  </footer>

</body>
</html>
