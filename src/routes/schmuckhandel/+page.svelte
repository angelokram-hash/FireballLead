<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const steps = [
    {
      timing: 'Tag 1',
      title: 'Produktivitätsrechner anfordern',
      active: true,
      description: 'Füllen Sie das Formular aus. Wir senden Ihnen unseren interaktiven Produktivitätsrechner, mit dem Sie den möglichen Jahresumsatz für Ihren Standort berechnen.',
      tasks: [
        'Formular mit Geschäftsname, Standort und Kontaktdaten ausfüllen',
        'Sie erhalten: Interaktiven Produktivitätsrechner (Excel oder Online-Tool)',
        'Eingabe Ihrer Kundenfrequenz → sofortige Umsatz-Hochrechnung (konservativ + optimistisch)',
        'Factsheet: Warum der FIREBALL Ihr Kernsortiment ergänzt, nicht ersetzt',
        'Farbkatalog: Alle 21+ Display-Farben mit Kristallstein-Details',
        'Preisliste mit WS-Konditionen und Staffel-Rabatten für den Fachhandel',
      ],
      tip: 'Der Rechner zeigt: Selbst bei nur 1 Verkauf pro Tag generiert das Display ca. 15.000€ Jahresumsatz auf 0,2m².'
    },
    {
      timing: 'Tag 3–5',
      title: 'Fachgespräch unter Schmuck-Profis',
      active: true,
      description: 'Telefonat oder persönlicher Besuch (20 Minuten). Von Schmuck-Fachleuten für Schmuck-Fachleute.',
      tasks: [
        'Durchsprache Ihres Sortiments: Wo liegt der FIREBALL preislich und stilistisch?',
        'FIREBALL als Impulsware auf der Theke — nicht als Konkurrenz im Schaufenster',
        'Design-Details: Kristallsteine, Messingbasis, Handarbeit, Patina-Qualität',
        'Die 2 Größen erklären: Classic (21mm, 49,90€) und Small (16mm, 39,90€)',
        'Die 2 Finishes: Brass (matt) und Shiny Golden (glänzend, limitierte Farben)',
        'Cross-Selling Pipeline vorstellen: Ketten, Ringe, Armbänder im FIREBALL-Design',
        'Konditionen und Erstbestell-Optionen besprechen',
      ],
      tip: 'Für Juweliere empfehlen wir oft den Start mit dem D18 in gedeckten Farbtönen — das passt besser zum gehobenen Schmuck-Umfeld als knallige Farben.'
    },
    {
      timing: 'Woche 2',
      title: 'Muster-Sticks zum Anfassen',
      active: true,
      description: 'Wir senden Ihnen 3–5 Muster-Sticks in ausgewählten Farben, damit Sie Qualität und Verarbeitung persönlich prüfen können.',
      tasks: [
        '3–5 Muster-Sticks in verschiedenen Farben und Finishes per Express',
        'Haptik-Test: Gewicht, Kristallqualität, Verschluss-Mechanismus prüfen',
        'Stick-Verpackung testen: Öffnen, entnehmen, wieder einsetzen',
        'Zeigen Sie die Muster 5–10 Stammkundinnen und fragen Sie nach Feedback',
        'Vergleich mit Ihrem bestehenden Sortiment: Passt der Stil?',
        'Rückmeldung an uns: Welche Farben und welches Finish für Ihr Display?',
      ],
      tip: 'Professionelle Juweliere schätzen besonders die Shiny Golden Varianten — sie wirken hochwertiger und passen zu goldenem Schmuck in der Vitrine.'
    },
    {
      timing: 'Woche 3',
      title: 'Display aufstellen & Sortiment integrieren',
      active: false,
      description: 'Das fertig bestückte Display wird geliefert. Sie platzieren es auf der Theke — als Impulszone für jeden Kundenbesuch.',
      tasks: [
        'Fertig bestücktes Display geliefert — auspacken, auf die Theke stellen, fertig',
        'Ideale Position: Neben der Kasse, dort wo Kundinnen beim Bezahlen warten',
        'Preisschild anbringen: „Handgefertigter Designerschmuck · ab 39,90€"',
        'Optional: Farbkarte daneben legen — „Finden Sie Ihre Farbe"',
        'Team-Briefing: „Der FIREBALL ergänzt — jede Kundin, die Schmuck kauft, ist potenzielle FIREBALL-Käuferin"',
        'Tipp für Ihr Team: Nach dem Hauptverkauf fragen: „Kennen Sie schon unseren FIREBALL?"',
        'In Ihre Warenwirtschaft aufnehmen: EAN-Codes und Artikelnummern beiliegen',
      ],
      tip: 'Platzieren Sie 2–3 offene Sticks neben dem Display — Kundinnen greifen eher zu, wenn sie die Ohrringe ohne Verpackung sehen können.'
    },
    {
      timing: 'Woche 4–8',
      title: 'Testphase mit Verkaufs-Tracking',
      active: false,
      description: 'Vier Wochen Testbetrieb. Sie tracken die Verkäufe, wir liefern Benchmarks und Optimierungstipps.',
      tasks: [
        'Woche 4: Start — Beobachten Sie, ob Kundinnen das Display selbstständig entdecken',
        'Woche 5: Erstes Check-in — Verkaufszahlen, Farbtrends, Team-Feedback',
        'Woche 6: Optimierung — Bestseller nachbestellen, langsame Farben austauschen',
        'Woche 7–8: Abschluss-Auswertung mit Vergleich zum Benchmark (Ø 2/Tag)',
        'Beobachten: Kaufen Kundinnen spontan oder kommen sie gezielt wegen FIREBALL?',
        'Dokumentieren: Wie viele Kundinnen kaufen beim zweiten Besuch eine weitere Farbe?',
        'Feedback Ihres Teams: Empfehlen sie den FIREBALL aktiv?',
      ],
      tip: 'Die Magie passiert oft beim zweiten Besuch: Kundinnen, die einmal gekauft haben, kommen gezielt für eine neue Farbe.'
    },
    {
      timing: 'Laufend',
      title: 'Feste Partnerschaft & Cross-Selling',
      active: false,
      description: 'Nach erfolgreicher Testphase: Reguläre Partnerschaft mit Nachbestellung, Neuheiten und der Cross-Selling Pipeline.',
      tasks: [
        'Festbestellung mit Ihrem individuellen Farbsortiment',
        'Nachbestellung per App, E-Mail oder Telefon — einzelne Farben oder Sets',
        'Quartalsweise neue Farbkollektionen passend zur Schmuck-Saison',
        'Cross-Selling Schritt 1: FIREBALL Ketten (gleiche Kristallstein-Designs)',
        'Cross-Selling Schritt 2: FIREBALL Ringe (verstellbar, gleiche Ästhetik)',
        'Cross-Selling Schritt 3: FIREBALL Armbänder (Charm-Stil)',
        'Stammkunden-Aktion: „Sammle 10 Farben, die 11. gibt es zum halben Preis"',
        'Partner-Exklusiv: Limitierte Farben nur für den Fachhandel',
        'Staffelkonditionen: Bessere WS-Preise ab 10 Nachbestellungen/Jahr',
      ],
      tip: 'Top-Juweliere berichten: Der FIREBALL wird zum „Gesprächsöffner" — Kundinnen kommen wegen der neuen Farben und bleiben für das Hauptsortiment.'
    },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Juweliere — Display-Partnerschaft</title>
  <meta name="description" content="FIREBALL Display für Schmuck-Fachhandel & Juweliere. 30 Jahre Bestseller, Cross-Selling Pipeline, Produktivitätsrechner." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Schmuck-Fachhandel & Juweliere
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        30 Jahre Bestseller.<br/>
        <span style="color:var(--gold);">Jetzt auf Ihrer Theke.</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        Der FIREBALL ist seit über 30 Jahren der meistverkaufte Designerschmuck Deutschlands.
        280+ Farben, handgefertigt, mit Kristallsteinen — und eine Cross-Selling Pipeline
        aus Ketten, Ringen und Armbändern.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">30+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Jahre #1 Bestseller</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">2 Größen</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">21 / 16 mm</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">Pipeline</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Ketten · Ringe · Armband</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Produktivitätsrechner erhalten</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Berechnen Sie den möglichen Jahresumsatz basierend auf Ihrer Kundenfrequenz.</p>
      <LeadForm channel="schmuckhandel" ctaText="Produktivitätsrechner anfordern" brancheOptions={['Juwelier (inhabergeführt)', 'Schmuck-Fachgeschäft', 'Fashion-Schmuck-Spezialist', 'Schmuck-Kette']} />
    </div>
  </div>
</section>

<!-- CREDIBILITY -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:1000px; margin:0 auto;">
    <h2 style="font-size:1.8rem; margin:0 0 2.5rem; text-align:center;">Glaubwürdigkeit im Schmuck-Kontext</h2>
    <div style="display:grid; grid-template-columns:repeat(2, 1fr); gap:2rem;">
      <div class="card" style="border-left:4px solid #6B5B73;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Designer-Herkunft</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Entworfen von Miranda Konstantinidou — kein anonymes Massenprodukt, sondern ein Stück mit Designergeschichte und 30+ Jahren Bewährung.
        </p>
      </div>
      <div class="card" style="border-left:4px solid #6B5B73;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Impulsware am Kassentisch</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Das Display auf der Theke ergänzt Ihr Kernsortiment als Zusatzverkauf bei jedem Kundenbesuch — ohne Konkurrenz zu Ihrem Hauptangebot.
        </p>
      </div>
      <div class="card" style="border-left:4px solid #6B5B73;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Cross-Selling Pipeline</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Neben Ohrringen kommen Ketten, Ringe und Armbänder im gleichen Design. Ihr Sortiment wächst organisch mit der Nachfrage.
        </p>
      </div>
      <div class="card" style="border-left:4px solid #6B5B73;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Sammeleffekt = Stammkunden</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Kundinnen sammeln den FIREBALL — bis zu 100+ Farben. Das bedeutet garantierten Wiederkauf und Stammkundschaft.
        </p>
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
      Vom Produktivitätsrechner bis zur Cross-Selling Pipeline — Ihr kompletter Fahrplan.
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
              background:var(--white); border:1px solid var(--gray-200);
              border-left:3px solid {step.active ? '#6B5B73' : 'var(--gray-200)'};
              padding:1.5rem;
            ">
              <span style="font-size:0.7rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#6B5B73; text-transform:uppercase;">{step.timing}</span>
              <h3 style="font-size:1.1rem; color:var(--teal); margin:0.25rem 0 0.5rem;">{step.title}</h3>
              <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">{step.description}</p>
              <div style="display:flex; flex-direction:column; gap:0.5rem;">
                {#each step.tasks as task}
                  <div style="display:flex; align-items:flex-start; gap:0.5rem;">
                    <span style="color:#6B5B73; font-size:0.85rem; margin-top:2px;">✓</span>
                    <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{task}</span>
                  </div>
                {/each}
              </div>
              {#if step.tip}
                <div style="margin-top:1rem; padding:0.75rem 1rem; background:rgba(107,91,115,0.05); border-left:2px solid #6B5B73;">
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
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Wie viel Umsatz steckt in 0,2m²?</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Fordern Sie unseren Produktivitätsrechner an — maßgeschneidert auf Ihre Frequenz.</p>
  <a href="#" onclick="window.scrollTo({top:0,behavior:'smooth'})" class="btn-primary">Produktivitätsrechner anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(2"] { grid-template-columns: 1fr !important; }
  }
</style>
