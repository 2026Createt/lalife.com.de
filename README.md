<!doctype html>
<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>La'Lifes Studios | Premium FiveM Scripts</title>
  <meta name="description" content="La'Lifes Studios — performante und realistische FiveM Scripts" />

  <style>
    /* Modernes, klares Dark-Theme mit Glas-Effekt */
    :root{
      --bg:#0f1115;
      --card:#121418;
      --glass: rgba(255,255,255,0.04);
      --accent:#ff7a59; /* warme Akzentfarbe */
      --muted:#9aa4b2;
      --text:#e6eef6;
      --radius:12px;
      --glass-border: rgba(255,255,255,0.06);
      --shadow: 0 8px 30px rgba(2,6,23,0.6);
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Courier New", monospace;
      --sans: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:var(--sans);
      background:
        radial-gradient(1200px 500px at 10% 10%, rgba(255,122,89,0.06), transparent 8%),
        radial-gradient(1000px 450px at 90% 90%, rgba(91,143,185,0.03), transparent 8%),
        var(--bg);
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      padding:2rem;
      display:flex;
      flex-direction:column;
      gap:2.5rem;
      align-items:center;
    }

    /* Header / Hero */
    .hero{
      width:100%;
      max-width:1200px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:var(--radius);
      padding:2rem;
      display:flex;
      gap:1.5rem;
      align-items:center;
      box-shadow:var(--shadow);
      border:1px solid var(--glass-border);
      backdrop-filter: blur(6px) saturate(120%);
    }
    .logo {
      width:84px;
      height:84px;
      border-radius:14px;
      display:flex;
      align-items:center;
      justify-content:center;
      background: linear-gradient(135deg, rgba(255,122,89,0.12), rgba(91,143,185,0.08));
      border: 1px solid rgba(255,255,255,0.04);
      flex-shrink:0;
      font-weight:700;
      color:var(--text);
      font-family:var(--mono);
      font-size:20px;
      letter-spacing:0.6px;
    }
    .hero-content h1{
      margin:0 0 .25rem 0;
      font-size:1.6rem;
      letter-spacing:0.6px;
    }
    .hero-content p{
      margin:0;
      color:var(--muted);
      font-size:0.98rem;
    }
    .hero-actions{
      margin-left:auto;
      display:flex;
      gap:.75rem;
    }
    .btn{
      padding:.6rem .95rem;
      border-radius:10px;
      border:1px solid transparent;
      background:linear-gradient(180deg,var(--accent), #ff6b44);
      color:white;
      font-weight:600;
      text-decoration:none;
      display:inline-flex;
      align-items:center;
      gap:.6rem;
      box-shadow: 0 6px 18px rgba(255,122,89,0.12);
      transition:transform .15s ease, box-shadow .15s;
      font-size:0.95rem;
    }
    .btn.secondary{
      background:transparent;
      border:1px solid var(--glass-border);
      color:var(--text);
      box-shadow:none;
    }
    .btn:active{transform:translateY(1px)}
    .btn.secondary:hover{background:rgba(255,255,255,0.02)}

    /* Info card */
    .intro{
      width:100%;
      max-width:1200px;
      display:grid;
      grid-template-columns: 1fr;
      gap:1.25rem;
    }
    .about{
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid var(--glass-border);
      padding:1.25rem;
      border-radius:12px;
      display:flex;
      gap:1rem;
      align-items:flex-start;
      color:var(--muted);
    }
    .about h2{
      margin:0 0 .25rem 0;
      color:var(--accent);
      font-size:1rem;
    }
    .about p{margin:0;color:var(--muted)}

    /* Projects grid */
    .projects{
      width:100%;
      max-width:1200px;
    }
    .projects h3{
      margin:0 0 1rem 0;
      font-size:1.25rem;
    }
    .grid{
      display:grid;
      grid-template-columns: repeat(auto-fit,minmax(260px,1fr));
      gap:1rem;
    }
    .card{
      background: linear-gradient(180deg, rgba(255,255,255,0.012), rgba(255,255,255,0.008));
      border-radius:12px;
      padding:1rem;
      border:1px solid var(--glass-border);
      box-shadow: 0 6px 22px rgba(2,6,23,0.55);
      transition: transform .18s ease, box-shadow .18s ease;
      display:flex;
      flex-direction:column;
      gap:.6rem;
    }
    .card:hover{ transform: translateY(-6px); box-shadow: 0 16px 40px rgba(2,6,23,0.6) }
    .card .top{
      display:flex;
      align-items:center;
      gap:.6rem;
    }
    .icon{
      width:44px;
      height:44px;
      border-radius:8px;
      display:grid;
      place-items:center;
      background: linear-gradient(135deg, rgba(255,122,89,0.08), rgba(91,143,185,0.06));
      color:var(--text);
      font-weight:700;
      font-family:var(--mono);
    }
    .card h4{
      margin:0;
      font-size:1.02rem;
      color:var(--text);
    }
    .tag{
      margin-left:auto;
      background:rgba(255,255,255,0.02);
      color:var(--muted);
      padding:.25rem .5rem;
      border-radius:999px;
      font-size:.78rem;
      border:1px solid rgba(255,255,255,0.02);
    }
    .card p{
      margin:0;
      color:var(--muted);
      font-size:.95rem;
      flex:1;
    }
    .small{
      font-size:.82rem;
      color:var(--muted);
    }

    /* Footer */
    footer{
      width:100%;
      max-width:1200px;
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:1rem;
      color:var(--muted);
      font-size:.9rem;
    }
    footer a{ color:var(--accent); text-decoration:none; font-weight:600 }
    footer a:hover{text-decoration:underline}

    /* Responsive tweaks */
    @media (max-width:720px){
      .hero{flex-direction:column;align-items:flex-start}
      .hero-actions{margin-left:0;width:100%;justify-content:stretch}
      .btn{width:100%}
      .hero-content h1{font-size:1.3rem}
    }
  </style>
</head>
<body>

  <header class="hero" role="banner">
    <div class="logo" aria-hidden="true">LL</div>
    <div class="hero-content">
      <h1>La'Lifes Studios</h1>
      <p>Premium & realismus-fokussierte FiveM Scripts — performant, modular & ready-to-use.</p>
    </div>

    <div class="hero-actions" role="navigation" aria-label="Aktionen">
      <a class="btn" href="mailto:kontakt@lalifes.studio?subject=Anfrage%20LaLifes%20Scripts">Anfrage senden</a>
      <a class="btn secondary" href="#projekte">Projekte ansehen</a>
    </div>
  </header>

  <section class="intro" aria-labelledby="ueber-heading">
    <article class="about" id="ueber-heading">
      <div style="min-width:60px">
        <svg width="56" height="56" viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <rect x="1" y="1" width="22" height="22" rx="6" fill="rgba(255,255,255,0.02)"/>
          <path d="M6 12h12M12 6v12" stroke="rgba(255,122,89,0.9)" stroke-width="1.6" stroke-linecap="round"/>
        </svg>
      </div>
      <div>
        <h2>Über den Entwickler</h2>
        <p>
          Willkommen bei La'Lifes Studios! Ich bin La'Life (16 Jahre) und entwickle hochwertige FiveM Scripts mit Fokus auf Performance und
          Realismus. Jedes Script ist modular aufgebaut und lässt sich an deine Serverbedürfnisse anpassen. Support und Anpassungen sind auf Anfrage möglich.
        </p>
      </div>
    </article>
  </section>

  <main class="projects" id="projekte" aria-labelledby="projekte-heading">
    <h3 id="projekte-heading">Ausgewählte Projekte</h3>

    <div class="grid" role="list">
      <section class="card" role="listitem" aria-labelledby="ads-title">
        <div class="top">
          <div class="icon">AD</div>
          <h4 id="ads-title">Ads System <span class="small" style="margin-left:8px;color:var(--muted)">UI · Command</span></h4>
          <div class="tag">Konfigurierbar</div>
        </div>
        <p>
          Modernes Anzeigen-System für Server-Jobs: nutze <code>/ads</code> mit ansprechendem Interface. Berechtigte Jobs und Inhalte werden serverseitig in der Konfiguration gepflegt.
        </p>
      </section>

      <section class="card" role="listitem" aria-labelledby="bus-title">
        <div class="top">
          <div class="icon">BD</div>
          <h4 id="bus-title">Busdriver <span class="small" style="margin-left:8px;color:var(--muted)">Job · UI</span></h4>
          <div class="tag">Interaktiv</div>
        </div>
        <p>
          Interaktives Bedienteil für Busse plus spaßigem Minijob. Fahrpläne, Belohnungen und einfache Integration in vorhandene Job-Systeme.
        </p>
      </section>

      <section class="card" role="listitem" aria-labelledby="dj-title">
        <div class="top">
          <div class="icon">DJ</div>
          <h4 id="dj-title">DJ Pult <span class="small" style="margin-left:8px;color:var(--muted)">Interaktiv · FX</span></h4>
          <div class="tag">Club-Atmosphäre</div>
        </div>
        <p>
          Realistisches DJ-Interface mit Nebel- und Licht-Effekten, Sound-Triggern und Steuerung per UI — ideal für Events und Clubs.
        </p>
      </section>

      <section class="card" role="listitem" aria-labelledby="elec-title">
        <div class="top">
          <div class="icon">EL</div>
          <h4 id="elec-title">Electrican <span class="small" style="margin-left:8px;color:var(--muted)">Minijob</span></h4>
          <div class="tag">Realismus</div>
        </div>
        <p>
          Durchdachter Elektriker-Minijob mit eigenem Interaktions-Design für Stromkästen und Reparaturmechaniken.
        </p>
      </section>

      <section class="card" role="listitem" aria-labelledby="lift-title">
        <div class="top">
          <div class="icon">ELV</div>
          <h4 id="lift-title">Elevator <span class="small" style="margin-left:8px;color:var(--muted)">System</span></h4>
          <div class="tag">Flexibel</div>
        </div>
        <p>
          Modernes Aufzug-System: flexibel konfigurierbar für Jobs oder freie Nutzung, einstellbar für beliebige Koordinaten und mehrere Etagen.
        </p>
      </section>

      <section class="card" role="listitem" aria-labelledby="key-title">
        <div class="top">
          <div class="icon">KC</div>
          <h4 id="key-title">KeyCabinet <span class="small" style="margin-left:8px;color:var(--muted)">Hardcore RP</span></h4>
          <div class="tag">Authentisch</div>
        </div>
        <p>
          Interaktiver Schlüsselkasten zum Spawnen von Fahrzeugen mit Fokus auf hardcore-realistische Bedienung und Immersion.
        </p>
      </section>
    </div>
  </main>

  <footer>
    <div>&copy; 2026 La'Lifes Studios</div>
    <div>
      <a href="mailto:kontakt@lalifes.studio">kontakt@lalifes.studio</a>
      <span style="color:var(--muted)"> · </span>
      <a href="#projekte">Projekte</a>
    </div>
  </footer>

</body>
</html>
