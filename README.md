<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Groundbreaking Landscapes | Projects</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #f5f5f3;
      --bg-alt: #ffffff;
      --text: #1f1f1f;
      --muted: #6f6f6f;
      --accent: #446b4b;
      --accent-soft: #dfe8e1;
      --border: #d1d1cd;
      --max-width: 1120px;
      --radius: 10px;
      --shadow-soft: 0 18px 40px rgba(0,0,0,0.06);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",
        "Segoe UI", sans-serif;
      background: radial-gradient(circle at top left, #e7efe9 0, #f5f5f3 40%, #fdfdfb 100%);
      color: var(--text);
      -webkit-font-smoothing: antialiased;
      text-rendering: optimizeLegibility;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    /* Layout shell */

    .page {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    .inner {
      width: 100%;
      max-width: var(--max-width);
      margin: 0 auto;
      padding: 0 20px;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(18px);
      background: color-mix(in srgb, #f7f7f2 85%, transparent);
      border-bottom: 1px solid rgba(0,0,0,0.04);
    }

    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
      padding: 16px 20px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .brand-mark {
      width: 32px;
      height: 32px;
      border-radius: 12px;
      background: radial-gradient(circle at 20% 20%, #88a77f 0, #446b4b 60%, #223824 100%);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      color: #f9fff7;
      font-weight: 700;
      font-size: 16px;
      box-shadow: 0 10px 24px rgba(0,0,0,0.16);
    }

    .brand-text {
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .brand-name {
      font-weight: 640;
      letter-spacing: 0.04em;
      text-transform: uppercase;
      font-size: 13px;
    }

    .brand-tagline {
      font-size: 11px;
      color: var(--muted);
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    nav {
      display: flex;
      align-items: center;
      gap: 20px;
      font-size: 13px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    nav a {
      color: var(--muted);
      position: relative;
      padding-bottom: 3px;
    }

    nav a:hover,
    nav a:focus {
      color: var(--text);
    }

    nav a.active::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 14px;
      height: 2px;
      border-radius: 999px;
      background: var(--accent);
    }

    .nav-cta {
      padding: 6px 14px;
      border-radius: 999px;
      border: 1px solid rgba(68,107,75,0.25);
      background: rgba(255,255,255,0.85);
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 12px;
      color: var(--accent);
      box-shadow: 0 10px 22px rgba(68,107,75,0.12);
    }

    .nav-cta svg {
      width: 14px;
      height: 14px;
    }

    .nav-cta:hover {
      background: #ffffff;
    }

    @media (max-width: 720px) {
      .header-inner {
        flex-wrap: wrap;
        gap: 10px 16px;
      }
      nav {
        flex-wrap: wrap;
        justify-content: flex-end;
        gap: 14px;
      }
      .brand-tagline {
        display: none;
      }
    }

    /* Hero + top area */

    main {
      flex: 1;
    }

    .hero-shell {
      padding: 32px 0 10px;
    }

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 2.1fr) minmax(0, 1.4fr);
      gap: 40px;
      align-items: center;
    }

    @media (max-width: 880px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .eyebrow {
      font-size: 11px;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 14px;
    }

    .hero-title {
      font-size: clamp(32px, 4vw, 40px);
      line-height: 1.05;
      letter-spacing: 0.02em;
      text-transform: uppercase;
      margin: 0 0 14px;
    }

    .hero-highlight {
      display: inline-block;
      padding: 2px 10px;
      margin-left: -10px;
      border-radius: 999px;
      background: var(--accent-soft);
      font-size: 13px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: #223824;
    }

    .hero-body {
      font-size: 15px;
      color: var(--muted);
      max-width: 40rem;
      margin-bottom: 18px;
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 16px 24px;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--muted);
    }

    .hero-meta span {
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .dot {
      width: 6px;
      height: 6px;
      border-radius: 999px;
      background: var(--accent);
    }

    .hero-aside {
      max-width: 360px;
      margin-left: auto;
    }

    .hero-card {
      background: var(--bg-alt);
      border-radius: 22px;
      padding: 18px 18px 18px;
      box-shadow: var(--shadow-soft);
      border: 1px solid rgba(0,0,0,0.03);
      position: relative;
      overflow: hidden;
    }

    .hero-badge {
      position: absolute;
      right: 16px;
      top: 16px;
      padding: 6px 10px;
      border-radius: 999px;
      background: #111;
      color: #f4f4f0;
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .hero-photo {
      border-radius: 16px;
      overflow: hidden;
      margin-bottom: 12px;
      background: #c0d1c5;
      height: 180px;
      display: flex;
      align-items: stretch;
      justify-content: stretch;
      position: relative;
    }

    .hero-photo::after {
      content: "Project preview";
      position: absolute;
      right: 12px;
      bottom: 10px;
      font-size: 10px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      padding: 4px 8px;
      border-radius: 999px;
      background: rgba(0,0,0,0.6);
      color: #f7f7f2;
    }

    .hero-photo-placeholder {
      flex: 1;
      background-image:
        linear-gradient(135deg, rgba(255,255,255,0.24), transparent),
        linear-gradient(120deg, #486b4d, #a2b79d);
      filter: saturate(1.05);
    }

    .hero-card-title {
      font-size: 14px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      margin-bottom: 4px;
    }

    .hero-card-location {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--muted);
      margin-bottom: 10px;
    }

    .hero-card-copy {
      font-size: 13px;
      color: var(--muted);
      margin-bottom: 10px;
    }

    .hero-card-meta {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--muted);
    }

    .hero-card-meta span strong {
      color: var(--accent);
      font-weight: 600;
    }

    /* Section header */

    .section-header {
      padding: 28px 0 10px;
      display: flex;
      justify-content: space-between;
      gap: 20px;
      align-items: flex-end;
      border-top: 1px solid rgba(0,0,0,0.04);
      margin-top: 12px;
    }

    .section-title {
      font-size: 12px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: #999987;
    }

    .section-sub {
      font-size: 13px;
      color: var(--muted);
      max-width: 360px;
    }

    /* Projects grid */

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 26px;
      padding-bottom: 40px;
    }

    .project-card {
      border-radius: var(--radius);
      padding: 14px 14px 12px;
      background: rgba(255,255,255,0.86);
      border: 1px solid rgba(0,0,0,0.04);
      box-shadow: 0 14px 32px rgba(0,0,0,0.03);
      display: flex;
      flex-direction: column;
      gap: 10px;
      transition: transform 150ms ease, box-shadow 150ms ease,
        border-color 150ms ease, background 150ms ease;
      position: relative;
      overflow: hidden;
    }

    .project-card::after {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at top left, rgba(68,107,75,0.12), transparent 55%);
      opacity: 0;
      pointer-events: none;
      transition: opacity 150ms ease;
    }

    .project-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 40px rgba(0,0,0,0.07);
      border-color: rgba(68,107,75,0.38);
      background: #ffffff;
    }

    .project-card:hover::after {
      opacity: 1;
    }

    .project-thumb {
      border-radius: 12px;
      height: 140px;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      background-color: #d0d8d0;
      position: relative;
      overflow: hidden;
    }

    .project-thumb::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(0,0,0,0.22), transparent 40%);
      opacity: 0.0;
      transition: opacity 150ms ease;
    }

    .project-card:hover .project-thumb::before {
      opacity: 1;
    }

    .project-label {
      position: absolute;
      left: 10px;
      bottom: 10px;
      padding: 3px 9px;
      border-radius: 999px;
      background: rgba(255,255,255,0.86);
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: #223824;
    }

    .project-name {
      font-size: 13px;
      font-weight: 600;
      letter-spacing: 0.16em;
      text-transform: uppercase;
    }

    .project-meta {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--muted);
      gap: 10px;
    }

    .project-tags {
      display: inline-flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .chip {
      padding: 2px 8px;
      border-radius: 999px;
      border: 1px solid rgba(0,0,0,0.08);
      background: rgba(248,249,246,0.9);
    }

    .project-link {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--accent);
      padding-top: 6px;
      border-top: 1px dashed rgba(0,0,0,0.08);
      margin-top: 8px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .project-link span {
      transition: transform 150ms ease;
    }

    .project-card:hover .project-link span {
      transform: translateX(3px);
    }

    /* Services + testimonial + contact footer */

    .bottom-sections {
      display: grid;
      grid-template-columns: minmax(0, 2.1fr) minmax(0, 1.5fr);
      gap: 32px;
      padding: 26px 0 40px;
      border-top: 1px solid rgba(0,0,0,0.04);
    }

    @media (max-width: 880px) {
      .bottom-sections {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .panel {
      border-radius: 20px;
      background: #ffffff;
      border: 1px solid rgba(0,0,0,0.04);
      box-shadow: 0 18px 40px rgba(0,0,0,0.05);
      padding: 18px 18px 16px;
    }

    .panel-title {
      font-size: 12px;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: #9a9a89;
      margin-bottom: 10px;
    }

    .panel-body {
      font-size: 14px;
      color: var(--muted);
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 12px;
      margin-top: 12px;
    }

    .service {
      padding: 8px 10px 10px;
      border-radius: 14px;
      background: #f6f7f3;
      border: 1px solid rgba(0,0,0,0.04);
      font-size: 13px;
    }

    .service-title {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      margin-bottom: 4px;
      color: #424232;
    }

    .service-copy {
      font-size: 12px;
      color: var(--muted);
    }

    .quote {
      font-size: 13px;
      line-height: 1.6;
      color: var(--muted);
      margin: 6px 0 8px;
    }

    .quote-mark {
      font-size: 18px;
      color: var(--accent);
      margin-right: 4px;
    }

    .quote-author {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: #555;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
      margin-top: 10px;
      font-size: 12px;
    }

    .contact-label {
      text-transform: uppercase;
      letter-spacing: 0.18em;
      font-size: 10px;
      color: #9b9b8c;
      margin-bottom: 3px;
    }

    .contact-value a {
      color: var(--accent);
    }

    footer {
      border-top: 1px solid rgba(0,0,0,0.06);
      padding: 14px 0 18px;
      font-size: 11px;
      color: var(--muted);
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      flex-wrap: wrap;
    }

    .footer-links {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .footer-links a {
      text-transform: uppercase;
      letter-spacing: 0.16em;
      font-size: 10px;
      color: #999987;
    }

    .footer-links a:hover {
      color: var(--accent);
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div class="inner header-inner">
        <a href="#top" class="brand">
          <div class="brand-mark">G</div>
          <div class="brand-text">
            <span class="brand-name">Groundbreaking Landscapes</span>
            <span class="brand-tagline">Landscape Design · Marin &amp; San Francisco</span>
          </div>
        </a>
        <nav>
          <a href="#projects" class="active">Projects</a>
          <a href="#services">Services</a>
          <a href="#about">About</a>
          <a href="#contact">Contact</a>
          <a href="tel:14156996209" class="nav-cta">
            <svg viewBox="0 0 24 24" aria-hidden="true">
              <path fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"
                d="M5 4h3l2 4-2 1c.6 1.9 2.1 3.4 4 4l1-2 4 2v3c0 .6-.4 1-1 1C10.6 17 7 13.4 7 8c0-.6.4-1 1-1z" />
            </svg>
            (415) 699-6209
          </a>
        </nav>
      </div>
    </header>

    <main id="top">
      <section class="hero-shell">
        <div class="inner hero">
          <div>
            <div class="eyebrow">San Francisco · Marin County</div>
            <h1 class="hero-title">
              Custom landscapes that
              <br />
              extend your living space
            </h1>
            <p class="hero-body">
              Groundbreaking Landscapes designs and builds outdoor spaces that feel tailored to your home:
              quiet gardens, lap pools, roof terraces, and family-friendly backyards — all shaped to the climate
              and character of each site.
            </p>
            <div class="hero-highlight">Selected residential projects</div>
            <div class="hero-meta" style="margin-top: 16px;">
              <span><span class="dot"></span>Design &amp; installation</span>
              <span>Endless pools</span>
              <span>Custom woodwork</span>
            </div>
          </div>

          <aside class="hero-aside">
            <div class="hero-card">
              <div class="hero-badge">Since 2000 · Marin based</div>
              <div class="hero-photo">
                <!-- Replace the placeholder with an actual image from your gallery -->
                <div class="hero-photo-placeholder"></div>
              </div>
              <div class="hero-card-title">San Anselmo residence</div>
              <div class="hero-card-location">Marin County, California</div>
              <div class="hero-card-copy">
                A steep hillside reimagined as layered terraces with a lap pool, wood deck, and low-water planting.
              </div>
              <div class="hero-card-meta">
                <span><strong>Design–build</strong> project</span>
                <span>Groundbreaking Landscapes</span>
              </div>
            </div>
          </aside>
        </div>
      </section>

      <section id="projects">
        <div class="inner">
          <div class="section-header">
            <div class="section-title">Projects</div>
            <p class="section-sub">
              A selection of gardens, terraces, and pools across Marin and San Francisco.
              Click a project to view a dedicated gallery page (link these to your existing galleries).
            </p>
          </div>

          <div class="projects-grid">
            <!-- Example project cards – link to your existing gallery pages -->
            <a class="project-card" href="gallery-bebe-residence.html">
              <div class="project-thumb" style="background-image:url('images/bebe-residence.jpg');">
                <div class="project-label">Bebe Residence</div>
              </div>
              <div class="project-name">Bebe Residence</div>
              <div class="project-meta">
                <span>San Francisco, CA</span>
                <span class="project-tags">
                  <span class="chip">Urban garden</span>
                  <span class="chip">Outdoor living</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-ehrenfeld-residence.html">
              <div class="project-thumb" style="background-image:url('images/ehrenfeld-residence.jpg');">
                <div class="project-label">Ehrenfeld Residence</div>
              </div>
              <div class="project-name">Ehrenfeld Residence</div>
              <div class="project-meta">
                <span>Marin County, CA</span>
                <span class="project-tags">
                  <span class="chip">Family garden</span>
                  <span class="chip">Stonework</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-glenn-park.html">
              <div class="project-thumb" style="background-image:url('images/glenn-park-residence.jpg');">
                <div class="project-label">Glenn Park Residence</div>
              </div>
              <div class="project-name">Glenn Park Residence</div>
              <div class="project-meta">
                <span>San Francisco, CA</span>
                <span class="project-tags">
                  <span class="chip">Hillside</span>
                  <span class="chip">Deck &amp; stairs</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-pirce-roof-garden.html">
              <div class="project-thumb" style="background-image:url('images/pirce-roof-garden.jpg');">
                <div class="project-label">Pirce Roof Garden</div>
              </div>
              <div class="project-name">Pirce Roof Garden</div>
              <div class="project-meta">
                <span>San Francisco, CA</span>
                <span class="project-tags">
                  <span class="chip">Roof terrace</span>
                  <span class="chip">City views</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-richmond-district.html">
              <div class="project-thumb" style="background-image:url('images/richmond-district-garden.jpg');">
                <div class="project-label">Richmond District Garden</div>
              </div>
              <div class="project-name">Richmond District Garden</div>
              <div class="project-meta">
                <span>San Francisco, CA</span>
                <span class="project-tags">
                  <span class="chip">Sheltered patio</span>
                  <span class="chip">Planting design</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-tiburon-residence.html">
              <div class="project-thumb" style="background-image:url('images/tiburon-residence.jpg');">
                <div class="project-label">Tiburon Residence</div>
              </div>
              <div class="project-name">Tiburon Residence</div>
              <div class="project-meta">
                <span>Tiburon, CA</span>
                <span class="project-tags">
                  <span class="chip">Bay views</span>
                  <span class="chip">Terraces</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-lap-pools.html">
              <div class="project-thumb" style="background-image:url('images/lap-pool.jpg');">
                <div class="project-label">Lap Pools</div>
              </div>
              <div class="project-name">Lap Pools &amp; Water</div>
              <div class="project-meta">
                <span>Various locations</span>
                <span class="project-tags">
                  <span class="chip">Endless pools</span>
                  <span class="chip">Water features</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>

            <a class="project-card" href="gallery-misc.html">
              <div class="project-thumb" style="background-image:url('images/misc-gallery.jpg');">
                <div class="project-label">Misc. Gallery</div>
              </div>
              <div class="project-name">Miscellaneous Gardens</div>
              <div class="project-meta">
                <span>San Francisco &amp; Marin</span>
                <span class="project-tags">
                  <span class="chip">Planting</span>
                  <span class="chip">Details</span>
                </span>
              </div>
              <div class="project-link">
                View project <span>↗</span>
              </div>
            </a>
          </div>
        </div>
      </section>

      <section id="services">
        <div class="inner">
          <div class="bottom-sections">
            <div class="panel">
              <div class="panel-title">Services</div>
              <div class="panel-body">
                We handle projects from the first sketch through installation, collaborating with you on plants,
                stone, wood, and other materials that suit your home and micro-climate.
                <div class="services-grid">
                  <div class="service">
                    <div class="service-title">Custom Design</div>
                    <div class="service-copy">
                      Site analysis, concepts, and planting plans tailored to your property and lifestyle.
                    </div>
                  </div>
                  <div class="service">
                    <div class="service-title">Endless &amp; Lap Pools</div>
                    <div class="service-copy">
                      Compact lap pools and swim-in-place installations integrated with decks and terraces.
                    </div>
                  </div>
                  <div class="service">
                    <div class="service-title">Installation</div>
                    <div class="service-copy">
                      Project management, grading, hardscape, planting, lighting, and irrigation.
                    </div>
                  </div>
                  <div class="service">
                    <div class="service-title">Custom Woodwork</div>
                    <div class="service-copy">
                      Fencing, trellises, decks, benches, and other details that complete the space.
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="panel" id="about">
              <div class="panel-title">Client Experience</div>
              <p class="quote">
                <span class="quote-mark">“</span>
                Mike and his crew are knowledgeable, conscientious, and efficient — and remain responsive
                long after the initial installation is complete.
              </p>
              <div class="quote-author">Christine · Residential client</div>

              <div style="margin-top: 14px; border-top: 1px dashed rgba(0,0,0,0.08); padding-top: 10px;">
                <div class="panel-title" style="margin-bottom: 6px;">About</div>
                <div class="panel-body">
                  Based in Marin County, Groundbreaking Landscapes focuses on residential gardens across
                  Marin and San Francisco. Each project begins with a careful study of the site so that plant
                  choices, materials, and details fit both the micro-climate and the way you live outdoors.
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="contact">
        <div class="inner">
          <div class="panel">
            <div class="panel-title">Contact &amp; Availability</div>
            <div class="contact-grid">
              <div>
                <div class="contact-label">Phone</div>
                <div class="contact-value">
                  <a href="tel:14156996209">(415) 699-6209</a>
                </div>
              </div>
              <div>
                <div class="contact-label">Email</div>
                <div class="contact-value">
                  <a href="mailto:mikebovarnick@aol.com">mikebovarnick@aol.com</a>
                </div>
              </div>
              <div>
                <div class="contact-label">Location</div>
                <div class="contact-value">
                  Marin County, CA · Serving San Francisco &amp; Bay Area
                </div>
              </div>
              <div>
                <div class="contact-label">Hours</div>
                <div class="contact-value">
                  Mon–Fri · 9:00am – 5:00pm<br />
                  Sat–Sun · By appointment
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div class="inner footer-inner">
        <div>© <span id="year"></span> Groundbreaking Landscapes. All rights reserved.</div>
        <div class="footer-links">
          <a href="#projects">Projects</a>
          <a href="#services">Services</a>
          <a href="#about">About</a>
          <a href="#contact">Contact</a>
        </div>
      </div>
    </footer>
  </div>

  <script>
    // Simple current year for the footer
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
