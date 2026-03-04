<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const steps = [
    {
      timing: 'Tag 1',
      title: 'Lookbook & Konditionen anfordern',
      active: true,
      description: 'Füllen Sie das Formular aus. Sie erhalten unser Lookbook mit der vollständigen Designer-Story, Produktfotos und Sonderkonditionen für Kulturinstitutionen.',
      tasks: [
        'Formular mit Einrichtung, Shop-Art und Kontaktdaten ausfüllen',
        'Sie erhalten: Lookbook mit hochauflösenden Lifestyle-Fotos',
        'Designer-Story von Miranda Konstantinidou — für Ihre Produktbeschreibungen nutzbar',
        'Manufaktur-Bilder: Leilanie beim Löten, Josie bei den Kristallen, Erlinda in der QS',
        'Preisliste mit Sonderkonditionen für Museums- und Hotelshops',
        'Übersicht: Welche Farben eignen sich als „Souvenir" und „Geschenk"?',
      ],
      tip: 'Erwähnen Sie den thematischen Kontext Ihres Museums oder Hotels — wir können Farben empfehlen, die zu Ihrer Ausstellung oder Ihrem Branding passen.'
    },
    {
      timing: 'Tag 3–5',
      title: 'Beratung: Das richtige Konzept für Ihren Shop',
      active: true,
      description: 'Telefonat oder Video-Call (15–20 Minuten) zur Erarbeitung eines Shop-Konzepts, das zu Ihrer Einrichtung passt.',
      tasks: [
        'Analyse Ihres Shops: Größe, Sortiment, Besucherprofil, Durchschnittsbon',
        'Konzept-Empfehlung: FIREBALL als „Design-Souvenir" oder als „Geschenk-Sortiment"?',
        'Display-Auswahl: D18 (ideal für kleine Shops) oder D21 (für mehr Platz)',
        'Farbkonzept: Passend zu Ihrer Ausstellung, Ihrem Hotel-Thema oder Ihrer Region',
        'Produktbeschreibung erstellen: Text für Preisschild, Website, Social Media',
        'Story-Karte: A5-Karte mit Designer- und Manufaktur-Geschichte zum Beilegen',
      ],
      tip: 'Museumsshops mit einer guten Produkt-Story verkaufen bis zu 40% mehr. Die FIREBALL-Geschichte (30+ Jahre, eigene Manufaktur, Handarbeit) ist Ihr Verkaufsargument.'
    },
    {
      timing: 'Woche 2',
      title: 'Display bestellen & einrichten',
      active: true,
      description: 'Das Display wird geliefert. Zusätzlich erhalten Sie Story-Karten und POS-Material speziell für Kultureinrichtungen.',
      tasks: [
        'Fertig bestücktes Display geliefert — auspacken und platzieren',
        'Story-Karten beilegen: Jeder Kunde kann die Designer-Geschichte mitnehmen',
        'Preisschild mit „Handgefertigt · Kristallsteine · Design by Miranda Konstantinidou"',
        'Team-Briefing: Die 3 Story-Elemente, die Besucher überzeugen',
        'Element 1: „Jeder FIREBALL wird von Hand in unserer Manufaktur gefertigt"',
        'Element 2: „Über 280 Farben — seit 30 Jahren jedes Jahr neue Farben"',
        'Element 3: „Die Stick-Verpackung ist Präsentation und Geschenk-Etui in einem"',
        'Optional: QR-Code am Display verlinkt auf FIREBALL Manufaktur-Video',
      ],
      tip: 'Platzieren Sie das Display in der Nähe der Kasse — Besucher kaufen Mitbringsel typischerweise beim Hinausgehen.'
    },
    {
      timing: 'Woche 3–8',
      title: 'Testphase & Besucherreaktionen',
      active: false,
      description: 'Sechs Wochen testen, beobachten und optimieren. Wir begleiten Sie mit Check-ins.',
      tasks: [
        'Woche 3–4: Erste Beobachtungen — Greifen Besucher zum Display? Welche Farben zuerst?',
        'Woche 5: Check-in — Verkaufszahlen, beliebteste Farben, Besucherfeedback',
        'Woche 6: Farboptimierung — Nachbestellung der Top-Seller, Austausch von Slow-Movern',
        'Woche 7–8: Abschlussbewertung mit Performance-Zahlen',
        'Dokumentieren: Wird geschenkt oder selbst getragen? Touristen oder Einheimische?',
        'Beobachten: Kommen Besucher gezielt wegen FIREBALL wieder?',
        'Testen: Funktioniert eine Empfehlung des Teams am Eingang oder an der Kasse besser?',
      ],
      tip: 'Hotels mit Boutique-Shop: Legen Sie eine FIREBALL Info-Karte ins Zimmer oder an die Rezeption — „Entdecken Sie handgefertigten Designerschmuck in unserer Boutique."'
    },
    {
      timing: 'Ab Woche 9',
      title: 'Partnerschaft & Storytelling',
      active: false,
      description: 'Nach erfolgreicher Testphase: Feste Partnerschaft mit fortlaufender Story-Unterstützung und saisonalen Highlights.',
      tasks: [
        'Festbestellung mit optimiertem Farbsortiment basierend auf Testdaten',
        'Saisonale Farb-Updates passend zu Ihren Ausstellungswechseln oder Hotel-Saisons',
        'Geschenk-Sets für besondere Anlässe: Weihnachten, Muttertag, Valentinstag',
        'Marketing-Material: Social Media Posts, Website-Texte, Newsletter-Bausteine',
        'Exklusiv-Farben: Ab 5 Displays möglich — eine Farbe nur für Ihre Einrichtung',
        'Cross-Selling: FIREBALL Ketten als „großes Geschenk" neben dem „kleinen Mitbringsel"',
        'Nachbestellung per App oder E-Mail — unkompliziert, schnelle Lieferung',
      ],
      tip: 'Besonders erfolgreich: Eine „Signature-Farbe" für Ihr Museum oder Hotel — ein FIREBALL, den es nur bei Ihnen gibt.'
    },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Museumsshops & Hotels — Display-Partnerschaft</title>
  <meta name="description" content="Handgefertigter Designerschmuck als perfektes Mitbringsel — FIREBALL Display-Konzept für Museumsshops, Hotels und Tourismus-Retail." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Museumsshops, Hotel-Boutiquen & Tourismus-Retail
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        Handgefertigt. Mit Geschichte.<br/>
        <span style="color:var(--gold);">Das perfekte Mitbringsel.</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        Seit über 30 Jahren wird jeder FIREBALL von Hand in unserer Manufaktur gefertigt.
        Die Stick-Verpackung macht ihn geschenkfertig — kein Einpacken nötig.
        Ein Mitbringsel, das nicht in der Schublade verschwindet.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">30+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Jahre Design</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">39,90€</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">ab RPR</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">0,2m²</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Platzbedarf</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Lookbook + Konditionen anfordern</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Inklusive Designer-Story, Produktfotos und spezielle Konditionen für Kulturinstitutionen.</p>
      <LeadForm channel="museumsshops" ctaText="Lookbook anfordern" brancheOptions={['Museumsshop', 'Hotel-Boutique', 'Flughafen-Shop', 'Tourismus-Shop', 'Design-Store']} />
    </div>
  </div>
</section>

<!-- STORY -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <h2 style="font-size:1.8rem; margin:0 0 1rem; text-align:center;">Die Geschichte hinter jedem Stück</h2>
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:0 auto 2.5rem; line-height:1.7;">
      Der FIREBALL wurde von Miranda Konstantinidou entworfen und wird in der eigenen Manufaktur handgefertigt.
      Jedes Stück hat eine Geschichte — perfekt für Shops, die mehr bieten wollen als anonyme Massenware.
    </p>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:2rem;">
      <div class="card" style="border-top:3px solid #5C6B4E; text-align:center;">
        <div style="font-size:2rem; margin-bottom:0.75rem;">🎨</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">280+ Farben</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6;">
          Jedes Jahr neue Farben — Ihre Kunden haben Grund, wiederzukommen.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #5C6B4E; text-align:center;">
        <div style="font-size:2rem; margin-bottom:0.75rem;">🎁</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Geschenkfertig</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6;">
          Die Stick-Verpackung ist Präsentation, Verpackung und Case in einem. Kein Einpacken nötig.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #5C6B4E; text-align:center;">
        <div style="font-size:2rem; margin-bottom:0.75rem;">✋</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Handgemacht</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6;">
          Leilanie lötet, Josie appliziert Kristalle, Erlinda prüft die Qualität — seit über 20 Jahren.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- SCHRITT FÜR SCHRITT -->
<section class="section-white" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:0.75rem; text-align:center;">
      Ihr Weg zum Display-Partner
    </p>
    <h2 style="font-size:clamp(1.6rem, 3vw, 2rem); margin:0 0 1rem; text-align:center;">
      Schritt für Schritt: So starten Sie
    </h2>
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:0 auto 3rem; line-height:1.7;">
      Von der Anfrage bis zum fertigen Shop-Konzept — inklusive Story-Material.
    </p>

    <div style="display:flex; flex-direction:column; gap:0;">
      {#each steps as step, i}
        <div style="display:grid; grid-template-columns:64px 1fr; gap:1.5rem; position:relative;">
          <div style="display:flex; flex-direction:column; align-items:center;">
            <div style="
              width:48px; height:48px; border-radius:50%;
              background:{step.active ? 'var(--gold)' : 'var(--white)'};
              border:2px solid {step.active ? 'var(--gold)' : 'var(--gray-200)'};
              display:flex; align-items:center; justify-content:center;
              font-family:'Josefin Sans',sans-serif; font-weight:700;
              color:{step.active ? 'var(--teal)' : 'var(--gray-500)'};
              font-size:1.1rem; z-index:2;
            ">{i + 1}</div>
            {#if i < steps.length - 1}
              <div style="width:2px; flex:1; background:var(--gray-200); min-height:20px;"></div>
            {/if}
          </div>
          <div style="padding-bottom:2.5rem;">
            <div style="
              background:var(--cream); border:1px solid var(--gray-200);
              border-left:3px solid {step.active ? '#5C6B4E' : 'var(--gray-200)'};
              padding:1.5rem;
            ">
              <span style="font-size:0.7rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#5C6B4E; text-transform:uppercase;">{step.timing}</span>
              <h3 style="font-size:1.1rem; color:var(--teal); margin:0.25rem 0 0.5rem;">{step.title}</h3>
              <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">{step.description}</p>
              <div style="display:flex; flex-direction:column; gap:0.5rem;">
                {#each step.tasks as task}
                  <div style="display:flex; align-items:flex-start; gap:0.5rem;">
                    <span style="color:#5C6B4E; font-size:0.85rem; margin-top:2px;">✓</span>
                    <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{task}</span>
                  </div>
                {/each}
              </div>
              {#if step.tip}
                <div style="margin-top:1rem; padding:0.75rem 1rem; background:rgba(92,107,78,0.06); border-left:2px solid #5C6B4E;">
                  <p style="font-size:0.8rem; color:var(--teal); margin:0;"><strong>💡 Tipp:</strong> {step.tip}</p>
                </div>
              {/if}
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- CTA -->
<section class="section-dark" style="padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Ein Mitbringsel, das bleibt.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Fordern Sie unser Lookbook mit Designer-Story und Bildmaterial an.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Lookbook anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(3"] { grid-template-columns: 1fr !important; }
  }
</style>
