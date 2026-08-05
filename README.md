<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pauls' Studios | Custom FiveM Scripts</title>
    <style>
        :root {
            --bg-dark: #121212;
            --bg-card: #1e1e24;
            --text-main: #e0e0e0;
            --text-muted: #a0a0a0;
            --accent: #5b8fb9; /* Funktionales, kühles Blau */
            --border-color: #333;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            line-height: 1.6;
        }

        /* Header Bereich */
        header {
            background-color: #0a0a0c;
            padding: 3rem 1rem;
            text-align: center;
            border-bottom: 3px solid var(--accent);
        }

        header h1 {
            font-size: 2.8rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 0.5rem;
            color: #ffffff;
        }

        header p {
            color: var(--text-muted);
            font-size: 1.1rem;
        }

        /* Info-Box (Über den Entwickler) */
        .info-section {
            max-width: 900px;
            margin: 3rem auto 1rem auto;
            padding: 0 1.5rem;
        }

        .info-box {
            background-color: #1a1a20;
            border-left: 4px solid var(--accent);
            padding: 1.5rem 2rem;
            border-radius: 0 6px 6px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }

        .info-box h2 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--accent);
        }

        /* Script-Grid */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            color: #ffffff;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
        }

        /* Einzelne Script-Karten */
        .card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 1.8rem;
            transition: transform 0.2s ease, border-color 0.2s ease;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: 0 8px 20px rgba(0,0,0,0.5);
        }

        .card h3 {
            font-size: 1.4rem;
            color: var(--accent);
            margin-bottom: 1rem;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 0.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card p {
            color: var(--text-muted);
            flex-grow: 1;
        }

        .tag {
            background-color: #2a2a35;
            color: var(--text-main);
            font-size: 0.75rem;
            padding: 0.2rem 0.6rem;
            border-radius: 4px;
            font-family: monospace;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            border-top: 1px solid var(--border-color);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        footer a {
            color: var(--accent);
            text-decoration: none;
        }
        
        footer a:hover {
            text-decoration: underline;
        }

        /* Code-Highlighting im Text */
        code {
            background-color: #2b2b36;
            padding: 2px 5px;
            border-radius: 4px;
            font-family: 'Courier New', Courier, monospace;
            color: #dcdcaa;
        }
    </style>
</head>
<body>

    <header>
        <h1>Pauls' Studios</h1>
        <p>Premium & Realismus-fokussierte FiveM Scripts</p>
    </header>

    <section class="info-section">
        <div class="info-box">
            <h2>Über den Entwickler</h2>
            <p>
                Willkommen bei Pauls' Studios! Ich bin Paul, 16 Jahre alt, und jedes Script, das du auf dieser Seite siehst, 
                wurde von mir komplett alleine entwickelt. Mein Fokus liegt auf performanten, realistischen und funktionalen Systemen. 
                Alle hier vorgestellten Scripts stelle ich auf Anfrage gerne zur Verfügung.
            </p>
        </div>
    </section>

    <main class="container">
        <h2 class="section-title">Meine Projekte</h2>
        
        <div class="grid">
            <!-- Ads System -->
            <div class="card">
                <h3>Ads System <span class="tag">UI / Command</span></h3>
                <p>
                    Ein System, das es jedem beliebigen Beruf ermöglicht, den Command <code>/ads</code> mit einem eigenen, 
                    modernen Design zu nutzen. Die berechtigten Jobs können ganz einfach direkt in der <code>server.lua</code> 
                    konfiguriert werden.
                </p>
            </div>

            <!-- Busdriver -->
            <div class="card">
                <h3>Busdriver <span class="tag">Job / UI</span></h3>
                <p>
                    Dieses Script verleiht jedem Bus ein zusätzliches interaktives Bedienteil. 
                    Es bietet zudem einen spaßigen und funktionalen Minijob, der für jede Person auf dem Server zugänglich ist.
                </p>
            </div>

            <!-- DJ Pult -->
            <div class="card">
                <h3>DJ Pult <span class="tag">Interaktiv / FX</span></h3>
                <p>
                    Ein hochrealistisches DJ-Pult, das nicht nur gut aussieht, sondern auch durch integrierte Nebelmaschinen 
                    und dynamische Disco-Lights-Effekte die perfekte Club-Atmosphäre schafft.
                </p>
            </div>

            <!-- Electrican -->
            <div class="card">
                <h3>Electrican <span class="tag">Minijob</span></h3>
                <p>
                    Ein durchdachter Minijob als Elektriker. Beinhaltet ein völlig eigenes und realistisch gestaltetes 
                    Design für die Interaktion mit den Stromkästen.
                </p>
            </div>

            <!-- Elevator -->
            <div class="card">
                <h3>Elevator <span class="tag">System</span></h3>
                <p>
                    Das modernste Aufzug-Script. Völlig flexibel einsetzbar: Konfigurierbar für jeden Beruf 
                    und anwendbar auf absolut jede Koordinate (Coord) auf der Map.
                </p>
            </div>

            <!-- KeyCabinet -->
            <div class="card">
                <h3>KeyCabinet <span class="tag">Hardcore RP</span></h3>
                <p>
                    Einer meiner besten Entwürfe: Ein interaktiver Schlüsselkasten, über den Fahrzeuge gespawnt werden können. 
                    Das Extra-Design ist speziell auf Hardcore-Realismus und eine authentische Bedienung ausgelegt.
                </p>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 Pauls' Studios. Alle Rechte vorbehalten. | <a href="mailto:kontakt@deinedomain.de">Anfrage senden</a></p>
    </footer>

</body>
</html>
