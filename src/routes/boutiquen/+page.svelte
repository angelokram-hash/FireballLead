<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const steps = [
    {
      timing: 'Tag 1',
      title: 'Info-Paket anfordern',
      active: true,
      description: 'Füllen Sie das Formular auf dieser Seite aus. Innerhalb von 24 Stunden erhalten Sie unser komplettes Info-Paket per E-Mail.',
      tasks: [
        'Formular mit Geschäftsname und Kontaktdaten ausfüllen',
        'Sie erhalten: Factsheet mit allen Zahlen (Produktivität, Marge, ROI)',
        'Lookbook mit hochauflösenden Produktfotos und Display-Bildern',
        'Preisliste mit WS-Konditionen und Staffelpreisen',
        'Übersicht der verfügbaren Farbvarianten (21+ Farben für Displays)',
      ],
      tip: 'Je mehr wir über Ihren Store wissen (Lage, Kundenfrequenz, Sortiment), desto besser können wir das Display auf Sie zuschneiden.'
    },
    {
      timing: 'Tag 2–3',
      title: 'Persönliches Beratungsgespräch',
      active: true,
      description: 'Unser Partnermanagement ruft Sie an (oder per Video-Call) für ein 15-Minuten-Gespräch.',
      tasks: [
        'Wir besprechen Ihre Store-Situation: Kassenbereich, Frequenz, Zielgruppe',
        'Gemeinsame Auswahl: D18 (kompakt, 18 SKU) oder D21 (voll, 21 SKU)?',
        'Farbauswahl passend zu Ihrer Kundschaft und Saison',
        'Klärung: Platzierung an der Kasse, im Schaufenster oder als freistehend',
        'Konditionen und Testphase-Bedingungen besprechen',
      ],
      tip: 'Schicken Sie uns vorab ein Foto Ihres Kassenbereichs — wir können sofort eine Platzierungsempfehlung geben.'
    },
    {
      timing: 'Tag 4–7',
      title: 'Probedisplay erhalten & aufstellen',
      active: true,
      description: 'Wir senden Ihnen ein fertig bestücktes Display per DHL Express. Aufstellen dauert 5 Minuten.',
      tasks: [
        'Display wird fertig bestückt geliefert — kein Zusammenbauen nötig',
        'Platzierung auf der Kassentheke oder an einer hochfrequenten Stelle',
        'Kurze Schulung für Ihr Team per Video (5 Min): Wie verkauft sich FIREBALL?',
        'POS-Material beiliegend: Aufsteller, Farbkarte, Preisschilder',
        'Stick-Verpackung erklären: Präsentation + Verpackung + Case in einem',
      ],
      tip: 'Der wichtigste Erfolgsfaktor: Platzierung an der höchsten Frequenzstelle und Commitment Ihres Teams.'
    },
    {
      timing: 'Woche 1–4',
      title: '4-Wochen-Testphase',
      active: false,
      description: 'Vier Wochen lang testen Sie den FIREBALL in Ihrem Store. Wir begleiten Sie mit regelmäßigen Check-ins.',
      tasks: [
        'Woche 1: Erstes Feedback-Gespräch — läuft das Display? Fragen?',
        'Woche 2: Check-in per E-Mail — erste Verkaufszahlen besprechen',
        'Woche 3: Farb-Nachbestellung prüfen — welche Farben laufen am besten?',
        'Woche 4: Abschlussgespräch — Zahlen auswerten, Entscheidung treffen',
        'Sie beobachten: Welche Farben greifen Kundinnen zuerst? Wer kauft mehrfach?',
      ],
      tip: 'Erfahrungsgemäß sind die Erfolgsfaktoren: Frequenz (Lage im Shop) und Engagement des Teams. Sprechen Sie Kundinnen aktiv an!'
    },
    {
      timing: 'Nach 4 Wochen',
      title: 'Auswertung & Entscheidung',
      active: false,
      description: 'Gemeinsam werten wir die Testphase aus. Die Zahlen sprechen für sich — kein Druck, nur Daten.',
      tasks: [
        'Auswertung: Stückzahl verkauft, Umsatz, meistverkaufte Farben',
        'Vergleich mit Benchmark: Ø 2 Paar/Tag = 17.000–50.000€/Jahr',
        'Bei Erfolg: Festbestellung und reguläre Partnerschaft',
        'Optimierung: Farbsortiment anpassen, ggf. zweites Display testen',
        'Bei Nicht-Erfolg: Display kostenfrei zurücksenden — kein Risiko',
      ],
      tip: null
    },
    {
      timing: 'Laufend',
      title: 'Partnerschaft & Nachbestellung',
      active: false,
      description: 'Als fester Partner profitieren Sie von einfacher Nachbestellung, saisonalen Neuheiten und der Cross-Selling Pipeline.',
      tasks: [
        'Nachbestellung per Bestell-App oder E-Mail — unkompliziert und schnell',
        'Saisonale Farbkollektionen: Neue Farben jedes Quartal',
        'Cross-Selling Pipeline: Ketten, Ringe, Armbänder im FIREBALL-Design',
        'Monatlicher Performance-Report auf Wunsch',
        'Exklusive Partner-Konditionen bei höherem Volumen',
        'Marketing-Unterstützung: Social Media Assets, Schaufenster-Material',
      ],
      tip: 'Nutzen Sie den Sammelcharakter: Stammkundinnen kaufen im Schnitt 5–10 verschiedene Farben pro Jahr.'
    },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Modeboutiquen — Display-Partnerschaft</title>
  <meta name="description" content="FIREBALL Display für Modeboutiquen & Concept Stores. Impulskauf-Schmuck mit 49,90€ RPR und bewiesenem Sammelcharakter." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Modeboutiquen & Concept Stores
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        Der Impulskauf, den<br/>
        <span style="color:var(--gold);">Ihre Kundinnen sammeln.</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        FIREBALL ist Designerschmuck mit Suchtfaktor: 280+ Farben, 39,90–49,90€ RPR,
        und Kundinnen, die wiederkommen. Immer wieder. Für eine neue Farbe.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">49,90€</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">RPR Classic</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">~2/Tag</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Ø Verkäufe</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">0,2m²</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Platzbedarf</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Kostenloses Probedisplay sichern</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Testen Sie FIREBALL 4 Wochen in Ihrer Boutique — ohne Risiko.</p>
      <LeadForm channel="boutiquen" ctaText="Probedisplay anfordern" brancheOptions={['Modeboutique', 'Concept Store', 'Multi-Brand Store', 'Flagship Store']} />
    </div>
  </div>
</section>

<!-- VALUE PROPS -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:1000px; margin:0 auto;">
    <h2 style="font-size:1.8rem; margin:0 0 2.5rem; text-align:center;">Warum FIREBALL in Ihre Boutique gehört</h2>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:2rem;">
      <div class="card" style="border-top:3px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Stammkunden-Maschine</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Kundinnen besitzen 30, 50, manche über 100 Paare. Der FIREBALL macht aus Laufkundschaft Stammkundinnen.
        </p>
      </div>
      <div class="card" style="border-top:3px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Null Beratungsaufwand</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Das Display verkauft sich selbst. Kundinnen stehen vor der Farbauswahl und die Frage ist nicht „ob?", sondern „welche?"
        </p>
      </div>
      <div class="card" style="border-top:3px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Minimaler Platzbedarf</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          0,2m² auf der Kassentheke — für bis zu 50.000€ Jahresumsatz. Kein Sortiment bietet bessere Flächenproduktivität.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- DISPLAY OPTIONS -->
<section class="section-white" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto; text-align:center;">
    <h2 style="font-size:1.8rem; margin:0 0 1rem;">Zwei Display-Optionen</h2>
    <p style="color:var(--gray-500); margin-bottom:3rem;">Offen für Anpassungen — individuell an Ihren POS anpassbar in Form und Farbe.</p>
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:3rem;">
      <div style="background:var(--teal); padding:2.5rem; color:var(--white);">
        <h3 style="color:var(--gold); font-size:1.3rem; margin:0 0 1.5rem;">D21 Display Black</h3>
        <p style="font-size:0.9rem; opacity:0.7;">45 × 35 × 35 cm</p>
        <p style="font-size:0.9rem; opacity:0.7;">21 SKU / 63 Stück</p>
        <p style="font-size:0.9rem; opacity:0.7;">15 Farben / 2 Größen</p>
        <div style="margin-top:1.5rem; padding-top:1.5rem; border-top:1px solid rgba(255,255,255,0.1);">
          <div class="stat-number" style="font-size:1.5rem;">WS 1.174€</div>
          <p style="font-size:0.85rem; opacity:0.5;">RRP 3.054€</p>
        </div>
      </div>
      <div style="background:var(--cream); padding:2.5rem;">
        <h3 style="color:var(--teal); font-size:1.3rem; margin:0 0 1.5rem;">D18 Display White</h3>
        <p style="font-size:0.9rem; color:var(--gray-500);">34 × 34 × 21 cm</p>
        <p style="font-size:0.9rem; color:var(--gray-500);">18 SKU / 45 Stück</p>
        <p style="font-size:0.9rem; color:var(--gray-500);">9 Farben / 2 Größen</p>
        <div style="margin-top:1.5rem; padding-top:1.5rem; border-top:1px solid var(--gray-200);">
          <div class="stat-number" style="font-size:1.5rem;">WS 931,50€</div>
          <p style="font-size:0.85rem; color:var(--gray-500);">RRP 2.424,60€</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SCHRITT FÜR SCHRITT -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:0.75rem; text-align:center;">
      Ihr Weg zum Display-Partner
    </p>
    <h2 style="font-size:clamp(1.6rem, 3vw, 2rem); margin:0 0 1rem; text-align:center;">
      Schritt für Schritt: So starten Sie
    </h2>
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:0 auto 3rem; line-height:1.7;">
      Vom ersten Kontakt bis zum laufenden Umsatz — hier ist Ihr kompletter Fahrplan.
    </p>

    <div style="display:flex; flex-direction:column; gap:0;">
      {#each steps as step, i}
        <div style="display:grid; grid-template-columns:64px 1fr; gap:1.5rem; position:relative;">
          <!-- Timeline -->
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
          <!-- Content -->
          <div style="padding-bottom:2.5rem;">
            <div style="
              background:var(--white); border:1px solid var(--gray-200);
              border-left:3px solid {step.active ? 'var(--gold)' : 'var(--gray-200)'};
              padding:1.5rem;
            ">
              <div style="display:flex; align-items:center; gap:0.5rem; margin-bottom:0.25rem;">
                <span style="font-size:0.7rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:var(--gold); text-transform:uppercase;">{step.timing}</span>
              </div>
              <h3 style="font-size:1.1rem; color:var(--teal); margin:0 0 0.5rem;">{step.title}</h3>
              <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">{step.description}</p>
              <div style="display:flex; flex-direction:column; gap:0.5rem;">
                {#each step.tasks as task}
                  <div style="display:flex; align-items:flex-start; gap:0.5rem;">
                    <span style="color:var(--gold); font-size:0.85rem; margin-top:2px;">✓</span>
                    <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{task}</span>
                  </div>
                {/each}
              </div>
              {#if step.tip}
                <div style="margin-top:1rem; padding:0.75rem 1rem; background:rgba(200,169,81,0.08); border-left:2px solid var(--gold);">
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
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Bereit für den Test?</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">4 Wochen testen. Kein Risiko. Kein Mindestvertrag.</p>
  <a href="#" onclick="window.scrollTo({top:0,behavior:'smooth'})" class="btn-primary">Probedisplay anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] {
      grid-template-columns: 1fr !important;
    }
    div[style*="grid-template-columns:repeat(3"] {
      grid-template-columns: 1fr !important;
    }
    div[style*="grid-template-columns:1fr 1fr"][style*="gap:3rem"] {
      grid-template-columns: 1fr !important;
    }
  }
</style>
