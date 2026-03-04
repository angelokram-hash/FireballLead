<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let blur = $derived(unlocked ? '' : 'filter:blur(5px);user-select:none;');
  const steps = [
    { t: 'Tag 1', title: 'ROI-Kalkulation anfordern', desc: 'Formular ausfüllen → individuelle Produktivitätsrechnung für Ihre Fläche und Frequenz.', tasks: ['Individuelle ROI-Kalkulation (konservativ + optimistisch)', 'Factsheet mit bewiesenen Produktivitätszahlen', 'Display-Optionen, SKU-Struktur, EDI-Anbindung', 'Case Study von vergleichbaren Standorten'], tip: 'Tagesfrequenz in der Abteilung reicht — wir rechnen den Rest.' },
    { t: 'Tag 3–5', title: 'Präsentation beim Einkauf', desc: 'Persönliche Präsentation (30 Min) mit ROI-Kalkulation, Display-Optionen und Pilotprogramm.', tasks: ['FIREBALL Konzept: Produkt, Display, Nachbestellung', 'Logistik: EDI-Anbindung, Bestell-App, Lieferzeiten', 'Konditionen: WS-Preise, Zahlungsziele, Rücknahme', 'Pilotprogramm: Filialen, Laufzeit, Erfolgskriterien'], tip: 'Bringen Sie Flächenplaner und WaWi-Verantwortlichen mit — alle Stammdaten liegen bereit.' },
    { t: 'Woche 2', title: 'Pilotprogramm definieren', desc: '1–3 Pilot-Filialen auswählen. Display, Farben, Platzierung und KPIs festlegen.', tasks: ['1–3 Filialen mit unterschiedlicher Frequenz', 'Display-Variante und Farbsortiment pro Standort', 'KPIs: Tagesverkäufe, Umsatz/m², Nachbestellfrequenz', 'Artikelanlage: Alle Stammdaten (EAN, VK, Maße) von uns'], tip: 'Eine High- und eine Mid-Frequency-Filiale wählen — zeigt den Frequenz-Hebel direkt.' },
    { t: 'Monat 1–3', title: '3-Monats-Pilot mit Tracking', desc: 'Datengetriebener Testbetrieb. Monatliche Reports pro Filiale. Optimierung nach Monat 1.', tasks: ['Monat 1: Startphase, Kalibrierung', 'Monat 2: Farbsortiment anpassen, Platzierung korrigieren', 'Monat 3: Skalierungs-Entscheidung datenbasiert', 'Vergleichsanalyse zwischen Pilot-Filialen'], tip: 'Monat 2 ist meist besser — Team wird sicherer, Stammkundinnen kommen wieder.' },
    { t: 'Ab Monat 4', title: 'Roll-out & Skalierung', desc: 'Schrittweises Roll-out auf 5, 10, 20+ Filialen. EDI-Vollintegration. Cross-Selling.', tasks: ['Phasenweise Ausweitung auf weitere Filialen', 'EDI-Vollintegration: Auto-Nachbestellung bei Mindestbestand', 'Cross-Selling: Ketten, Ringe, Armbänder', 'Quartals-Business-Review und Staffelkonditionen'], tip: 'Top-Filialen: 3,8 Verkäufe/Tag = über 50.000€/Jahr auf 0,2m².' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Kaufhäuser — 50.000€ Jahresumsatz auf 0,2m²</title>
  <meta name="description" content="FIREBALL Display-Konzept für Kaufhäuser: Standardisierte Displays, EDI-fähig, 3-Monats-Pilot. ROI-Kalkulation anfordern." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/5.jpeg" alt="FIREBALL Displays" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(135deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.8) 50%, rgba(26,60,64,0.5) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="display:grid; grid-template-columns:1fr 420px; gap:4rem; align-items:center;">
      <div>
        <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">Für Kaufhäuser & Department Stores</p>
        <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem,4vw,3rem); font-weight:700; color:var(--white); line-height:1.1; margin:0 0 1.5rem;"><span style="color:var(--gold);{blur}">50.000€</span> Jahresumsatz.<br/>Pro 0,2m². Skalierbar.</h1>
        <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.7); line-height:1.7; margin-bottom:2rem;">Standardisierte Displays, EDI-fähig, 3-Monats-Pilotprogramm mit datengetriebener Auswertung. Vom Pilot zum Roll-out — risikofrei und skalierbar.</p>
        <div class="animate-fade-up delay-300" style="display:flex; gap:2.5rem;">
          <div><div class="stat-number" style="font-size:2rem;">Ø 2/Tag</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Verkäufe</div></div>
          <div><div class="stat-number" style="font-size:2rem;{blur}">17–50T€</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Jahresnetto/Display</div></div>
          <div><div class="stat-number" style="font-size:2rem;">EDI</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Anbindung</div></div>
        </div>
      </div>
      <div class="animate-fade-up delay-300" style="background:rgba(255,255,255,0.06); backdrop-filter:blur(8px); border:1px solid rgba(255,255,255,0.1); padding:2rem;">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Individuelle ROI-Kalkulation</h3>
        <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Ihre Frequenz → Ihre Zahlen. Konservativ & optimistisch.</p>
        <LeadForm channel="kaufhaeuser" ctaText="ROI-Kalkulation anfordern" brancheOptions={['Kaufhaus (Einzelstandort)', 'Kaufhaus-Gruppe', 'Department Store', 'Warenhaus-Kette']} />
      </div>
    </div>
  </div>
</section>

<!-- PERFORMANCE -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <img src="/img/7.jpeg" alt="FIREBALL Ziele Partnerschaft" style="width:100%; border:1px solid var(--gray-200);" />
    <div>
      <h2 style="font-size:1.6rem; color:var(--teal); margin:0 0 1.5rem;">Getestete Produktivität</h2>
      <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.7; margin-bottom:1.5rem;">In ersten Tests: durchschnittlich ca. 2 Ohrringe pro Tag pro Display. Maximum: 3,8. Minimum: knapp 1. Das ergibt <span style="{blur}">17.000–50.000€</span> Jahresnetto-Produktivität auf 0,2m².</p>
      <div style="display:flex; flex-direction:column; gap:0.75rem;">
        <div style="padding-left:1rem; border-left:3px solid #2C5F7C;">
          <p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Erfolgsfaktor 1:</strong> Frequenz (Lage im Shop)</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #2C5F7C;">
          <p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Erfolgsfaktor 2:</strong> Commitment des Teams</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #2C5F7C;">
          <p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Positionierung:</strong> Kassentheke oder vergleichbar</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- VARIANTS IMAGE -->
<section style="padding:0;"><img src="/img/3.jpeg" alt="FIREBALL Varianten" style="width:100%; display:block;" /></section>

<!-- CROSS SELLING -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.5rem; text-align:center; margin:0 0 2rem; color:var(--teal);">Cross-Selling Pipeline</h2>
    <img src="/img/4.jpeg" alt="FIREBALL Cross-Selling Pipeline" style="width:100%; border:1px solid var(--gray-200);" />
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:1.5rem auto 0; line-height:1.7;">Ketten, Ohrhänger, Ringe, Armbänder — alles im FIREBALL-Design. Wachstum über die Ohrstecker hinaus.</p>
  </div>
</section>

<!-- STEPS -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 3rem;">Ihr Pilotprogramm — Schritt für Schritt</h2>
    {#each steps as step, i}
      <div style="display:grid; grid-template-columns:56px 1fr; gap:1.25rem;">
        <div style="display:flex; flex-direction:column; align-items:center;">
          <div style="width:44px; height:44px; border-radius:50%; background:#2C5F7C; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1rem; z-index:2;">{i+1}</div>
          {#if i < steps.length - 1}<div style="width:2px; flex:1; background:var(--gray-200);"></div>{/if}
        </div>
        <div style="padding-bottom:2rem;">
          <div style="background:var(--white); border:1px solid var(--gray-200); border-left:3px solid #2C5F7C; padding:1.25rem;">
            <span style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#2C5F7C; text-transform:uppercase;">{step.t}</span>
            <h3 style="font-size:1.05rem; color:var(--teal); margin:0.2rem 0 0.4rem;">{step.title}</h3>
            <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin-bottom:0.75rem;">{step.desc}</p>
            {#each step.tasks as task}<div style="display:flex; gap:0.4rem; margin-bottom:0.3rem;"><span style="color:#2C5F7C; font-size:0.8rem;">✓</span><span style="font-size:0.8rem; color:var(--gray-700); line-height:1.4;{task.includes('€') ? blur : ''}">{task}</span></div>{/each}
            {#if step.tip}<div style="margin-top:0.75rem; padding:0.6rem; background:rgba(44,95,124,0.05); border-left:2px solid #2C5F7C;"><p style="font-size:0.75rem; color:var(--teal); margin:0;{step.tip?.includes('€') ? blur : ''}"><strong>Tipp:</strong> {step.tip}</p></div>{/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<!-- CTA -->
<section style="background:var(--teal); padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Bereit für den Pilot?</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Datengetrieben, risikofrei, skalierbar. Ihre individuelle ROI-Kalkulation in 24 Stunden.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">ROI-Kalkulation anfordern →</a>
</section>

<PriceGate bind:unlocked />

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }
</style>
