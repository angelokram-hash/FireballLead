<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
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

<!-- CTA -->
<section class="section-dark" style="padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Lassen Sie die Zahlen entscheiden.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Wir erstellen eine ROI-Kalkulation für Ihre spezifische Fläche und Frequenz.</p>
  <a href="#" onclick="window.scrollTo({top:0,behavior:'smooth'})" class="btn-primary">ROI-Kalkulation anfordern →</a>
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
