<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let showPwModal = $state(false);
  const faqs = [
    { q: 'Wie funktioniert das Pilotprogramm?', a: '1–3 Filialen, 3 Monate, monatliche Reports. Wir liefern Displays + Stammdaten für Ihre WaWi. Sie liefern Verkaufszahlen. Datenbasierte Entscheidung für Roll-out.' },
    { q: 'Ist eine EDI-Anbindung möglich?', a: 'Ja. Wir unterstützen EDI und bieten zusätzlich eine Bestell-App. Alle Stammdaten (EAN, VK, Maße) werden von uns bereitgestellt.' },
    { q: 'Welche Flächenproduktivität ist realistisch?', a: 'Konservativ: 1 Paar/Tag = ca. 15.200€/Jahr auf 0,2m². Optimistisch: 2,5 Paar/Tag = ca. 38.000€/Jahr. Top-Filialen: 3,8/Tag = 50.000€+.' },
    { q: 'Brauchen wir Fachpersonal für FIREBALL?', a: 'Nein. Das Display verkauft sich über die Farbauswahl. Ein 5-Minuten-Briefing pro Filiale reicht.' },
    { q: 'Wie wird nachbestellt?', a: 'EDI, Bestell-App oder E-Mail. Einzelne Farben oder Nachfüll-Sets. Auto-Nachbestellung bei Mindestbestand möglich.' },
  ];
</script>
<svelte:head><title>FIREBALL für Kaufhäuser — Pilotprogramm mit ROI-Kalkulation</title><meta name="description" content="FIREBALL Display: Standardisiert, EDI-fähig, getestete Produktivität. 3-Monats-Pilot für Ihre Filialen." /></svelte:head>
<PriceGate bind:unlocked bind:showInput={showPwModal} />
<Navbar dark={true} />

<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;"><img src="/img/5.jpeg" alt="FIREBALL Displays" style="width:100%; height:100%; object-fit:cover;" /><div style="position:absolute; inset:0; background:linear-gradient(160deg, rgba(26,60,64,0.96) 0%, rgba(26,60,64,0.85) 40%, rgba(26,60,64,0.5) 100%);"></div></div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;"><div style="max-width:640px;">
    <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1.5rem;">Für Kaufhäuser & Department Stores</p>
    <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.2rem,4.5vw,3.2rem); font-weight:700; color:var(--white); line-height:1.08; margin:0 0 1.5rem;">Standardisiert. Skalierbar. <span style="color:var(--gold);">Datengetrieben.</span></h1>
    <p class="animate-fade-up delay-200" style="font-size:1.15rem; color:rgba(255,255,255,0.75); line-height:1.7; margin-bottom:2.5rem;">0,2m² Kassentheke, Ø 2 Verkäufe pro Tag, EDI-fähig. Vom 3-Monats-Pilot in 1–3 Filialen zum datenbasierten Roll-out — ohne Risiko.</p>
    <a href="#kontakt" class="animate-fade-up delay-300 btn-primary" style="font-size:1rem; padding:1rem 2.5rem;">Individuelle ROI-Kalkulation anfordern →</a>
    <p class="animate-fade-up delay-300" style="color:rgba(255,255,255,0.35); font-size:0.8rem; margin-top:0.75rem;">Ihre Frequenz → Ihre Zahlen. In 24 Stunden.</p>
  </div></div>
</section>

<section style="background:var(--teal); padding:1.5rem 2rem; border-bottom:1px solid rgba(255,255,255,0.08);"><div style="max-width:900px; margin:0 auto; display:flex; justify-content:center; gap:3rem; flex-wrap:wrap;">
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Ø 2/Tag</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Verkäufe/Display</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Max 3,8</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Spitzenwert/Tag</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">EDI</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Anbindung möglich</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">0,2m²</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Platzbedarf</span></div>
</div></section>

<!-- PROBLEM → SOLUTION -->
<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
  <div>
    <h2 style="font-size:1.8rem; color:var(--teal); margin:0 0 1.5rem;">Getestete Produktivität auf 0,2m²</h2>
    <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.75; margin-bottom:1.5rem;">In ersten Tests: Ø 2 Ohrringe pro Tag pro Display. Maximum: 3,8. Das ergibt Jahresnetto-Produktivitäten, die schwer zu schlagen sind.</p>
    <div style="display:flex; flex-direction:column; gap:0.75rem;">
      <div style="padding-left:1.25rem; border-left:3px solid #2C5F7C;"><p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Erfolgsfaktor 1:</strong> Frequenz (Lage im Shop)</p></div>
      <div style="padding-left:1.25rem; border-left:3px solid #2C5F7C;"><p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Erfolgsfaktor 2:</strong> Commitment des Teams</p></div>
      <div style="padding-left:1.25rem; border-left:3px solid #2C5F7C;"><p style="font-size:0.9rem; color:var(--teal); margin:0;"><strong>Positionierung:</strong> Kassentheke oder vergleichbar</p></div>
    </div>
  </div>
  <img src="/img/7.jpeg" alt="FIREBALL Ziele" style="width:100%;" />
</div></section>

<section style="padding:0;"><img src="/img/3.jpeg" alt="FIREBALL Varianten" style="width:100%; display:block;" /></section>

<!-- CROSS SELLING -->
<section style="background:var(--white); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto;">
  <h2 style="font-size:1.5rem; text-align:center; color:var(--teal); margin:0 0 2rem;">Cross-Selling Pipeline</h2>
  <img src="/img/4.jpeg" alt="Cross-Selling" style="width:100%;" />
  <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:1.5rem auto 0; line-height:1.7;">Ketten, Ohrhänger, Ringe, Armbänder — das FIREBALL-Design als komplettes Sortiment.</p>
</div></section>

<!-- PRICING — BLURRED -->
<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto;">
  <h2 style="font-size:1.5rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Displays & Konditionen</h2>
  <div style="position:relative;">
    <div style="{unlocked ? '' : 'filter:blur(6px);user-select:none;pointer-events:none;'}transition:filter 0.4s;">
      <img src="/img/5.jpeg" alt="Displays" style="width:100%; margin-bottom:2rem;" />
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
        <div style="background:var(--teal); padding:2rem; color:var(--white);"><h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">D21 Display Black</h3><p style="opacity:0.7; font-size:0.85rem; margin:0;">21 SKU / 63 PCS · 15 Farben</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 1.174€ · RRP 3.054€</p></div>
        <div style="background:var(--white); padding:2rem; border:1px solid var(--gray-200);"><h3 style="color:var(--teal); font-size:1.1rem; margin:0 0 0.5rem;">D18 Display White</h3><p style="color:var(--gray-500); font-size:0.85rem; margin:0;">18 SKU / 45 PCS · 9 Farben</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 931,50€ · RRP 2.424,60€</p></div>
      </div>
    </div>
    {#if !unlocked}<div style="position:absolute; inset:0; display:flex; align-items:center; justify-content:center; z-index:10;"><button onclick={() => showPwModal = true} style="padding:1rem 2.5rem; background:var(--gold); color:var(--teal); border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif; font-size:1rem; font-weight:700; box-shadow:0 8px 32px rgba(0,0,0,0.2); display:flex; align-items:center; gap:0.6rem;">🔒 Preise freischalten</button></div>{/if}
  </div>
</div></section>

<!-- 3 STEPS -->
<section style="background:var(--white); padding:5rem 2rem;"><div style="max-width:900px; margin:0 auto;">
  <h2 style="font-size:1.6rem; text-align:center; color:var(--teal); margin:0 0 3rem;">In 3 Schritten zum Pilot</h2>
  <div style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:2rem;">
    {#each [{n:'1',t:'ROI anfordern',d:'Formular → individuelle Kalkulation in 24h. Konservativ + optimistisch.'},{n:'2',t:'Pilot starten',d:'1–3 Filialen, fertig bestückte Displays, Stammdaten für Ihre WaWi.'},{n:'3',t:'Daten entscheiden',d:'3 Monate tracken. Zahlen gut? Roll-out. Nicht? Displays zurück.'}] as s}
      <div style="text-align:center;"><div style="width:56px; height:56px; border-radius:50%; background:#2C5F7C; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1.2rem; margin:0 auto 1rem;">{s.n}</div><h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">{s.t}</h4><p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin:0;">{s.d}</p></div>
    {/each}
  </div>
</div></section>

<!-- FAQ -->
<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:700px; margin:0 auto;">
  <h2 style="font-size:1.4rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Häufige Fragen</h2>
  {#each faqs as faq}<details style="margin-bottom:1rem; background:var(--white); border:1px solid var(--gray-200);"><summary style="padding:1rem 1.25rem; cursor:pointer; font-weight:600; font-size:0.95rem; color:var(--teal); list-style:none; display:flex; justify-content:space-between; align-items:center;">{faq.q}<span style="color:var(--gold); font-size:1.2rem; flex-shrink:0; margin-left:1rem;">+</span></summary><div style="padding:0 1.25rem 1.25rem;"><p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin:0;">{faq.a}</p></div></details>{/each}
</div></section>

<section id="kontakt" style="background:var(--teal); padding:5rem 2rem;"><div style="max-width:520px; margin:0 auto; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1.4rem; margin-bottom:1rem;">FIREBALL</p>
  <h2 style="color:var(--white); font-size:1.8rem; margin:0 0 0.75rem;">ROI-Kalkulation anfordern</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:2rem;">Ihre Frequenz → Ihre Zahlen. Datengetrieben, risikofrei, skalierbar.</p>
  <LeadForm channel="kaufhaeuser" ctaText="ROI-Kalkulation anfordern" brancheOptions={['Kaufhaus (Einzelstandort)', 'Kaufhaus-Gruppe', 'Department Store', 'Warenhaus-Kette']} />
</div></section>
<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;"><p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 FIREBALL by VICI Vertrieb Deutschland GmbH</p></footer>
<style>details[open] summary span { transform: rotate(45deg); } details summary span { transition: transform 0.2s; display:inline-block; } @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }</style>
