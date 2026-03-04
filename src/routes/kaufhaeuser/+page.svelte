<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const steps = [
    {
      timing: 'Tag 1',
      title: 'ROI-Kalkulation anfordern',
      active: true,
      description: 'Füllen Sie das Formular aus. Wir erstellen eine individuelle Produktivitätsrechnung für Ihre spezifische Fläche und Frequenz.',
      tasks: [
        'Formular mit Haus-Name, Abteilung und Kontakt des Einkaufs ausfüllen',
        'Angaben zur geschätzten Kundenfrequenz in der Schmuck-/Accessoire-Abteilung',
        'Sie erhalten: Individuelle ROI-Kalkulation (konservativ + optimistisch)',
        'Factsheet mit bewiesenen Produktivitätszahlen aus bestehenden Teststellungen',
        'Übersicht: Display-Optionen, SKU-Struktur, EDI-Anbindung',
        'Case Study von vergleichbaren Standorten als Referenz',
      ],
      tip: 'Je genauer Ihre Frequenzschätzung, desto präziser unsere Kalkulation. Tagesfrequenz in der Abteilung reicht — wir rechnen den Rest.'
    },
    {
      timing: 'Tag 3–5',
      title: 'Präsentation beim Einkauf',
      active: true,
      description: 'Persönliche Präsentation (vor Ort oder Video-Call, 30 Minuten) mit Ihrem Einkaufs-Team.',
      tasks: [
        'Vorstellung des FIREBALL Konzepts: Produkt, Display, Nachbestellung',
        'Durchsprache der individuellen ROI-Kalkulation für Ihr Haus',
        'Display-Optionen im Detail: D18 (kompakt) vs. D21 (Standard) vs. Maßanfertigung',
        'Logistik: EDI-Anbindung, Bestell-App, Lieferzeiten, Mindestmengen',
        'Konditionen: WS-Preise, Zahlungsziele, Rücknahme-Regelung im Pilot',
        'Pilotprogramm besprechen: Anzahl Filialen, Laufzeit, Erfolgskriterien',
        'Klärung interner Prozesse: Warenwirtschaft, Artikelanlage, Regalplanung',
      ],
      tip: 'Bringen Sie Ihren Flächenplaner und Warenwirtschafts-Verantwortlichen mit — wir haben alle technischen Daten für die Artikelanlage vorbereitet.'
    },
    {
      timing: 'Woche 2',
      title: 'Pilotprogramm definieren',
      active: true,
      description: 'Gemeinsam legen wir den Piloten fest: Welche Filialen, welche Displays, welche Erfolgskriterien.',
      tasks: [
        'Auswahl von 1–3 Pilot-Filialen (unterschiedliche Frequenz/Lage empfohlen)',
        'Display-Variante pro Standort festlegen (D18 oder D21)',
        'Farbsortiment pro Display zusammenstellen (Empfehlung basierend auf Region)',
        'Platzierung definieren: Kassentheke, Schmuck-Abteilung oder Eingangsbereich',
        'KPI-Definition: Tagesverkäufe, Umsatz/m², Nachbestellfrequenz',
        'Reporting-Rhythmus vereinbaren: Wöchentlich oder monatlich',
        'Artikelanlage in Ihrem System: Wir liefern alle Stammdaten (EAN, VK, Maße)',
      ],
      tip: 'Wählen Sie eine Filiale mit hoher und eine mit mittlerer Frequenz — so sehen Sie den Frequenz-Hebel direkt in den Zahlen.'
    },
    {
      timing: 'Woche 3–4',
      title: 'Displays aufstellen & Teams briefen',
      active: false,
      description: 'Die Displays werden geliefert und aufgestellt. Jedes Filial-Team erhält ein kompaktes Briefing.',
      tasks: [
        'Fertig bestückte Displays per Paket an jede Pilot-Filiale',
        'Aufstellung am vereinbarten Standort (5 Minuten, kein Werkzeug)',
        'Team-Schulung per Video-Link (5 Minuten): Produkt, Argumente, Nachbestellung',
        'Kernbotschaft für das Team: „Die Frage ist nicht ob, sondern welche Farbe"',
        'POS-Material pro Filiale: Aufsteller, Preisschild, Farbkarte',
        'Ansprechpartner für jede Filiale benennen (für Feedback und Nachbestellung)',
        'Bestell-App oder EDI-Zugang einrichten und testen',
      ],
      tip: 'Idealerweise besucht ein FIREBALL-Mitarbeiter die Pilot-Filialen persönlich zum Aufstellen — das zeigt Commitment und motiviert das Team.'
    },
    {
      timing: 'Monat 1–3',
      title: '3-Monats-Pilot mit Performance-Tracking',
      active: false,
      description: 'Drei Monate datengetriebener Testbetrieb. Wir liefern monatliche Reports, Sie liefern die Verkaufszahlen.',
      tasks: [
        'Monat 1: Startphase — erste Verkaufsdaten, Kalibrierung, Team-Feedback einholen',
        'Monat 2: Optimierung — Farbsortiment anpassen, Platzierung ggf. korrigieren',
        'Monat 3: Skalierungs-Entscheidung — datenbasierte Empfehlung für Roll-out',
        'Monatlicher Performance-Report pro Filiale: Stück, Umsatz, Farb-Ranking',
        'Vergleichsanalyse zwischen den Pilot-Filialen: Was macht den Unterschied?',
        'Nachbestellungen automatisch über EDI oder App tracken',
        'Kundenfeedback dokumentieren: Sammeln Kundinnen? Verschenken sie?',
      ],
      tip: 'Die Erfahrung zeigt: Monat 2 ist meist besser als Monat 1, weil das Team sicherer wird und Stammkundinnen wiederkommen.'
    },
    {
      timing: 'Ab Monat 4',
      title: 'Roll-out & Skalierung',
      active: false,
      description: 'Nach erfolgreichem Pilot: Schrittweises Roll-out auf weitere Filialen mit optimiertem Konzept.',
      tasks: [
        'Auswertung: Welche Filialen, Platzierungen und Farbkonzepte funktionieren am besten?',
        'Roll-out Plan: Phasenweise Ausweitung auf 5, 10, 20+ Filialen',
        'Optimiertes Farbsortiment basierend auf Pilot-Daten',
        'EDI-Vollintegration: Automatische Nachbestellung bei Mindestbestand',
        'Cross-Selling Pipeline aktivieren: Ketten, Ringe, Armbänder als Erweiterung',
        'Quartals-Business-Review: Performance, Trends, Sortimentsplanung',
        'Staffelkonditionen: Bessere WS-Preise bei höherem Volumen',
        'Jahresplanung: Saisonale Farbkollektionen, Aktions-Displays, Promotion-Slots',
      ],
      tip: 'Top-Filialen erreichen 3,8 Verkäufe pro Tag — das sind über 50.000€ Jahresnetto auf 0,2m². Ein Wert, den kaum ein anderes Sortiment schafft.'
    },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Kaufhäuser — Display-Partnerschaft</title>
  <meta name="description" content="FIREBALL Display-Konzept für Kaufhäuser & Department Stores. Skalierbar, EDI-fähig, maximale Flächenproduktivität." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Kaufhäuser & Department Stores
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        50.000€ Jahresumsatz.<br/>
        <span style="color:var(--gold);">Pro 0,2m². Skalierbar.</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        Der FIREBALL ist Deutschlands meistverkaufter Designerschmuck — seit über 30 Jahren.
        Standardisierte Displays, automatisierte Nachbestellung, nachgewiesene Produktivität.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">3,8/Tag</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Best Case Verkäufe</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">EDI</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Nachbestellung</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">21 SKU</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Pro Display</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">ROI-Kalkulation anfordern</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Wir erstellen eine individuelle Produktivitätsrechnung für Ihre Fläche.</p>
      <LeadForm channel="kaufhaeuser" ctaText="ROI-Kalkulation anfordern" brancheOptions={['Kaufhaus / Warenhaus', 'Department Store', 'Schmuck-Abteilung', 'Accessoire-Fläche']} />
    </div>
  </div>
</section>

<!-- SCALE SECTION -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:1000px; margin:0 auto;">
    <h2 style="font-size:1.8rem; margin:0 0 2.5rem; text-align:center;">Warum FIREBALL skaliert</h2>
    <div style="display:grid; grid-template-columns:repeat(2, 1fr); gap:2rem;">
      <div class="card" style="border-left:4px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Standardisierte Displays</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Zwei bewährte Display-Formate (D18 + D21) — schnelles Roll-out über mehrere Standorte. Anpassbar in Form und Farbe.
        </p>
      </div>
      <div class="card" style="border-left:4px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Automatische Nachbestellung</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          EDI-Anbindung oder Bestell-App — Nachlieferung ohne manuellen Aufwand.
        </p>
      </div>
      <div class="card" style="border-left:4px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Cross-Selling Pipeline</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Neben den Ohrringen sind Ketten, Ringe und Armbänder in der Pipeline — Sortimentstiefe ohne Extra-Risiko.
        </p>
      </div>
      <div class="card" style="border-left:4px solid var(--gold);">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Bewiesene Produktivität</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          17.000–50.000€ Jahresnetto-Produktivität pro 0,2m². Erfolgsfaktoren: Frequenz + Team-Commitment.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- PILOT PROGRAM -->
<section class="section-white" style="padding:5rem 2rem;">
  <div style="max-width:700px; margin:0 auto; text-align:center;">
    <h2 style="font-size:1.8rem; margin:0 0 1rem;">Pilotprogramm: 3 Monate Test</h2>
    <p style="color:var(--gray-500); line-height:1.7; margin-bottom:2rem;">
      Starten Sie mit 1–3 Displays in ausgewählten Filialen. Wir liefern monatliche Performance-Reports.
      Nach 3 Monaten entscheiden die Zahlen — nicht Versprechen.
    </p>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:1.5rem;">
      <div style="background:var(--cream); padding:1.5rem;">
        <div style="font-family:'Josefin Sans',sans-serif; font-size:2rem; color:var(--teal); font-weight:700;">1</div>
        <p style="font-size:0.85rem; color:var(--gray-500);">Display aufstellen</p>
      </div>
      <div style="background:var(--cream); padding:1.5rem;">
        <div style="font-family:'Josefin Sans',sans-serif; font-size:2rem; color:var(--teal); font-weight:700;">2</div>
        <p style="font-size:0.85rem; color:var(--gray-500);">3 Monate testen</p>
      </div>
      <div style="background:var(--cream); padding:1.5rem;">
        <div style="font-family:'Josefin Sans',sans-serif; font-size:2rem; color:var(--teal); font-weight:700;">3</div>
        <p style="font-size:0.85rem; color:var(--gray-500);">Skalieren nach Zahlen</p>
      </div>
    </div>
  </div>
</section>

<!-- SCHRITT FÜR SCHRITT -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:0.75rem; text-align:center;">
      Vom Pilot zum Roll-out
    </p>
    <h2 style="font-size:clamp(1.6rem, 3vw, 2rem); margin:0 0 1rem; text-align:center;">
      Schritt für Schritt: Ihr Pilotprogramm
    </h2>
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:0 auto 3rem; line-height:1.7;">
      Datengetrieben und risikofrei — so integrieren Sie FIREBALL in Ihr Sortiment.
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
              border-left:3px solid {step.active ? '#2C5F7C' : 'var(--gray-200)'};
              padding:1.5rem;
            ">
              <span style="font-size:0.7rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#2C5F7C; text-transform:uppercase;">{step.timing}</span>
              <h3 style="font-size:1.1rem; color:var(--teal); margin:0.25rem 0 0.5rem;">{step.title}</h3>
              <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">{step.description}</p>
              <div style="display:flex; flex-direction:column; gap:0.5rem;">
                {#each step.tasks as task}
                  <div style="display:flex; align-items:flex-start; gap:0.5rem;">
                    <span style="color:#2C5F7C; font-size:0.85rem; margin-top:2px;">✓</span>
                    <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{task}</span>
                  </div>
                {/each}
              </div>
              {#if step.tip}
                <div style="margin-top:1rem; padding:0.75rem 1rem; background:rgba(44,95,124,0.05); border-left:2px solid #2C5F7C;">
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
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Lassen Sie die Zahlen entscheiden.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Wir erstellen eine ROI-Kalkulation für Ihre spezifische Fläche und Frequenz.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">ROI-Kalkulation anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(2"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(3"] { grid-template-columns: 1fr !important; }
  }
</style>
