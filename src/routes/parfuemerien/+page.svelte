<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const steps = [
    {
      timing: 'Tag 1',
      title: 'Muster-Paket anfordern',
      active: true,
      description: 'Füllen Sie das Formular aus. Wir senden Ihnen 3 Muster-Sticks in verschiedenen Farben — kostenlos und unverbindlich.',
      tasks: [
        'Formular mit Geschäftsname, Standort und Kontaktdaten ausfüllen',
        'Sie erhalten per E-Mail: Factsheet mit Beauty-spezifischen Verkaufsargumenten',
        'Bildmaterial der Stick-Verpackung in Lifestyle-Kontext (neben Lippenstiften, Parfums)',
        'Preisliste und WS-Konditionen speziell für den Beauty-Fachhandel',
        'Übersicht: Welche Farben passen zu welcher Beauty-Saison?',
      ],
      tip: 'Erwähnen Sie Ihre Sortimentsstruktur — wir empfehlen Farben, die zu Ihrem bestehenden Beauty-Sortiment passen.'
    },
    {
      timing: 'Tag 2–4',
      title: '3 Muster-Sticks erhalten',
      active: true,
      description: 'Per DHL Express erhalten Sie 3 FIREBALL Sticks in unterschiedlichen Farben zum Anfassen und Testen.',
      tasks: [
        'Stick auspacken und in die Hand nehmen — das Format spricht für sich',
        'Legen Sie einen Stick neben Ihre Lippenstifte: Passt er ins Bild?',
        'Zeigen Sie den Stick 2–3 Stammkundinnen und beobachten Sie die Reaktion',
        'Öffnen Sie den Stick: Ohrring herausnehmen, anschauen, zurücklegen — zero waste',
        'Beiliegend: Kurzanleitung für Ihr Team (1 Seite) zum Verkaufsstart',
      ],
      tip: 'Die häufigste Reaktion: Kundinnen greifen instinktiv zum Stick, weil das Format so vertraut ist wie ein Lippenstift.'
    },
    {
      timing: 'Tag 5–7',
      title: 'Beratungsgespräch & Display-Empfehlung',
      active: true,
      description: 'Unser Partnermanagement bespricht mit Ihnen die optimale Display-Lösung für Ihre Parfümerie.',
      tasks: [
        'Feedback zu den Muster-Sticks besprechen: Wie war die Kundenreaktion?',
        'Display-Auswahl: D18 (kompakt, passt neben Kasse) oder D21 (Standalone)',
        'Platzierungs-Beratung: Neben Lippenstiften? Am Kassentresen? Im Schaufenster?',
        'Farbkonzept: Welche 9–15 Farben passen zu Ihrer Kundschaft?',
        'Konditionen besprechen: Erstbestellung, Mindestmenge, Zahlungsbedingungen',
        'Optional: Individuelles Display in Ihrer CI-Farbe (ab 10 Displays)',
      ],
      tip: 'Beste Platzierung in Parfümerien: Direkt neben Lippen- oder Nagelprodukten. Die Farbauswahl ist geübtes Verhalten Ihrer Kundinnen.'
    },
    {
      timing: 'Woche 2',
      title: 'Display aufstellen & Team schulen',
      active: false,
      description: 'Das fertig bestückte Display wird geliefert. Ihr Team bekommt ein 5-Minuten-Briefing.',
      tasks: [
        'Display kommt fertig bestückt — auspacken, hinstellen, fertig',
        'Platzierung an der vereinbarten Stelle (Kassenbereich empfohlen)',
        'Team-Briefing (5 Min Video oder PDF): Die 3 wichtigsten Verkaufsargumente',
        'Argument 1: „Wie ein Lippenstift — immer dabei, immer anders"',
        'Argument 2: „Handgefertigt mit echten Kristallsteinen, über 280 Farben"',
        'Argument 3: „Die Verpackung ist gleichzeitig das Etui — kein Abfall"',
        'POS-Material aufstellen: Aufsteller mit Preis und Markenname',
      ],
      tip: 'Bitten Sie Ihr Team, den FIREBALL bei jedem Kundenbesuch einmal zu erwähnen: „Kennen Sie schon unseren FIREBALL?" reicht oft aus.'
    },
    {
      timing: 'Woche 2–6',
      title: 'Testphase & Begleitung',
      active: false,
      description: '4 Wochen Testbetrieb mit regelmäßigen Check-ins. Wir analysieren gemeinsam, was funktioniert.',
      tasks: [
        'Woche 2: Start-Check — Display steht, Team ist informiert, erste Tage beobachten',
        'Woche 3: Erstes Feedback — Welche Farben gehen am besten? Wie reagieren Kundinnen?',
        'Woche 4: Nachbestell-Check — Müssen einzelne Farben nachgefüllt werden?',
        'Woche 5: Zwischenbilanz — Stückzahl, Umsatz, beliebteste Farben',
        'Woche 6: Abschlussbewertung — Performance-Vergleich mit Benchmark (Ø 2/Tag)',
        'Dokumentieren Sie Kundenfeedback: „Wie süß!" / „Wo gibt es mehr Farben?"',
      ],
      tip: 'In Parfümerien funktioniert besonders gut: Kundinnen, die einen Lippenstift kaufen, nehmen häufig auch einen farblich passenden FIREBALL mit.'
    },
    {
      timing: 'Ab Woche 7',
      title: 'Partnerschaft & Ausbau',
      active: false,
      description: 'Nach erfolgreicher Testphase starten Sie die reguläre Partnerschaft mit automatischer Nachbestellung.',
      tasks: [
        'Festbestellung des Displays in optimierter Farbzusammenstellung',
        'Nachbestellung per App oder E-Mail — einzelne Farben oder komplette Nachfüll-Sets',
        'Saisonale Neuheiten: Neue Farben passend zu den Beauty-Trends jeder Saison',
        'Cross-Selling: FIREBALL Ketten und Ringe als Erweiterung Ihres Schmucksortiments',
        'Exklusive Aktionen: Muttertag-Sets, Weihnachts-Specials, Valentinstag-Bundles',
        'Partner-Marketing: Instagram-Posts, Schaufenster-Material, Kundinnen-Flyer',
      ],
      tip: 'Erstellen Sie ein „Farbe des Monats"-Highlight in Ihrem Schaufenster — das generiert Neugier und Wiederkäufe.'
    },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Parfümerien — Display-Partnerschaft</title>
  <meta name="description" content="FIREBALL Schmuck-Display für Parfümerien & Beauty-Fachhandel. Die Stick-Verpackung passt perfekt ins Beauty-Sortiment." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Parfümerien & Beauty-Fachhandel
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        „Wie mein Lippenstift,<br/>
        <span style="color:var(--gold);">immer dabei."</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        Der FIREBALL Ohrring in der Stick-Verpackung fügt sich nahtlos ins Beauty-Sortiment ein.
        Ihre Kundinnen kennen das Ritual: vor der Farbauswahl stehen, eintauchen, die eigene Farbe finden.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">280+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Farbvarianten</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">Stick</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Verpackung = Case</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">0 Abfall</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Nachhaltig</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Muster-Paket bestellen</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Wir senden Ihnen 3 Muster-Sticks + Factsheet direkt in Ihre Parfümerie.</p>
      <LeadForm channel="parfuemerien" ctaText="Muster-Paket anfordern" brancheOptions={['Parfümerie (inhabergeführt)', 'Douglas Franchise', 'Kosmetikinstitut mit Retail', 'Beauty Concept Store']} />
    </div>
  </div>
</section>

<!-- LIPSTICK ANALOGY -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto; text-align:center;">
    <h2 style="font-size:1.8rem; margin:0 0 1rem;">Der „Lipstick Effect" — wissenschaftlich belegt</h2>
    <p style="color:var(--gray-500); max-width:640px; margin:0 auto 2.5rem; line-height:1.7;">
      Wenn die Konjunktur ins Stocken gerät, steigt der Absatz für weibliche Schönheitsprodukte.
      Der FIREBALL ist eine Affordable Luxury — konjunkturresistent und impulsstark.
    </p>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:2rem;">
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Vertrautes Format</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Die Stick-Verpackung fühlt sich an wie ein Lippenstift — die Kundin nimmt ihn instinktiv in die Hand.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Farbauswahl als Erlebnis</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Genau wie bei einem Nagellack-Regal: Kundinnen tauchen ein, vergleichen, entscheiden — und kommen wieder.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Kassennah platzierbar</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Das kompakte Display passt neben die Kasse oder ins Schaufenster — überall dort, wo der Impulskauf entsteht.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- ROI SECTION -->
<section class="section-white" style="padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 2.5rem;">Ihre Rechnung — konkret</h2>
    <div style="background:var(--teal); padding:2.5rem; color:var(--white);">
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Ihr Invest (D18 Display)</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">931,50€ WS</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">RRP im Display</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">2.424,60€</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Ø Tagesverkauf</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">2 Paar</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Hochrechnung / Jahr</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">17.000–50.000€</p>
        </div>
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
      Von der ersten Anfrage bis zum laufenden Beauty-Sortiment — Ihr kompletter Fahrplan.
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
              border-left:3px solid {step.active ? '#9B4D6E' : 'var(--gray-200)'};
              padding:1.5rem;
            ">
              <span style="font-size:0.7rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#9B4D6E; text-transform:uppercase;">{step.timing}</span>
              <h3 style="font-size:1.1rem; color:var(--teal); margin:0.25rem 0 0.5rem;">{step.title}</h3>
              <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">{step.description}</p>
              <div style="display:flex; flex-direction:column; gap:0.5rem;">
                {#each step.tasks as task}
                  <div style="display:flex; align-items:flex-start; gap:0.5rem;">
                    <span style="color:#9B4D6E; font-size:0.85rem; margin-top:2px;">✓</span>
                    <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{task}</span>
                  </div>
                {/each}
              </div>
              {#if step.tip}
                <div style="margin-top:1rem; padding:0.75rem 1rem; background:rgba(155,77,110,0.06); border-left:2px solid #9B4D6E;">
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

<!-- CTA BOTTOM -->
<section class="section-dark" style="padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">3 Muster-Sticks. Kostenlos. Unverbindlich.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Legen Sie die Sticks neben Ihre Lippenstifte — der Rest passiert von allein.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Muster-Paket anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(3"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:1fr 1fr"][style*="gap:2rem"] { grid-template-columns: 1fr !important; }
  }
</style>
