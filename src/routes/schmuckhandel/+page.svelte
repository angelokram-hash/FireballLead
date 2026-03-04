<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let showPwModal = $state(false);
  const faqs = [
    { q: 'Konkurriert der FIREBALL mit meinem Sortiment?', a: 'Nein. FIREBALL ist Impulsware auf der Theke, nicht Schmuck in der Vitrine. Preispunkt 39,90–49,90€ spricht auch Begleitpersonen an. Er ergänzt, konkurriert nicht.' },
    { q: 'Wirkt das nicht wie Modeschmuck?', a: 'Nein. Echte Kristallsteine, Messing-Basis, Handarbeit, 30 Jahre Designgeschichte. Besonders die Shiny Golden Varianten passen auch in ein gehobenes Umfeld.' },
    { q: 'Was bringt der Sammelcharakter?', a: 'Kundinnen kommen wegen der neuen Farben — und bleiben für Ihr Hauptsortiment. Der FIREBALL ist ein Gesprächsöffner und Stammkunden-Generator.' },
    { q: 'Wie funktioniert die Cross-Selling Pipeline?', a: 'Über die Ohrstecker hinaus: FIREBALL Ketten, Ringe, Armbänder im gleichen Kristallstein-Design. Schrittweise Sortimentserweiterung.' },
    { q: 'Welches Finish empfehlen Sie für Juweliere?', a: 'Shiny Golden für gehobenes Umfeld. Brass für trendigere Sortimente. Beides verfügbar — wir beraten individuell.' },
  ];
</script>
<svelte:head><title>FIREBALL für Juweliere — 30 Jahre Bestseller für Ihre Theke</title><meta name="description" content="FIREBALL: Handgefertigt, Kristallsteine, 30+ Jahre Bestseller. Produktivitätsrechner für Ihren Standort anfordern." /></svelte:head>
<PriceGate bind:unlocked bind:showInput={showPwModal} />
<Navbar dark={true} />

<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;"><img src="/img/8.jpeg" alt="FIREBALL Ohrring" style="width:100%; height:100%; object-fit:cover;" /><div style="position:absolute; inset:0; background:linear-gradient(160deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.8) 40%, rgba(26,60,64,0.4) 100%);"></div></div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;"><div style="max-width:640px;">
    <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1.5rem;">Für Schmuck-Fachhandel & Juweliere</p>
    <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.2rem,4.5vw,3.2rem); font-weight:700; color:var(--white); line-height:1.08; margin:0 0 1.5rem;">30 Jahre Bestseller. Jetzt als <span style="color:var(--gold);">Impulsware</span> auf Ihrer Theke.</h1>
    <p class="animate-fade-up delay-200" style="font-size:1.15rem; color:rgba(255,255,255,0.75); line-height:1.7; margin-bottom:2.5rem;">Echte Kristallsteine, Handarbeit, 280+ Farben. Ergänzt Ihr Kernsortiment ohne Konkurrenz. Der Sammelcharakter macht aus Laufkundschaft Stammkunden — die wegen der Farben kommen und für Ihr Hauptsortiment bleiben.</p>
    <a href="#kontakt" class="animate-fade-up delay-300 btn-primary" style="font-size:1rem; padding:1rem 2.5rem;">Produktivitätsrechner anfordern →</a>
    <p class="animate-fade-up delay-300" style="color:rgba(255,255,255,0.35); font-size:0.8rem; margin-top:0.75rem;">Ihre Frequenz → Ihr möglicher Jahresumsatz</p>
  </div></div>
</section>

<section style="background:var(--teal); padding:1.5rem 2rem; border-bottom:1px solid rgba(255,255,255,0.08);"><div style="max-width:900px; margin:0 auto; display:flex; justify-content:center; gap:3rem; flex-wrap:wrap;">
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">30+</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Jahre Bestseller</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">21+</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Display-Farben</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">2 Finishes</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Brass / Shiny Gold</span></div>
  <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Handmade</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem;">Kristallsteine</span></div>
</div></section>

<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
  <img src="/img/8.jpeg" alt="FIREBALL Sammlung" style="width:100%;" />
  <div>
    <h2 style="font-size:1.8rem; color:var(--teal); margin:0 0 1.5rem;">Sammelschmuck = Stammkunden</h2>
    <div style="display:flex; flex-direction:column; gap:1.25rem;">
      <div style="padding-left:1.25rem; border-left:3px solid #6B5B73;"><p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Sammelcharakter:</strong> Kundinnen besitzen 30–100+ Farben. Einmalkäuferinnen werden Stammkundinnen.</p></div>
      <div style="padding-left:1.25rem; border-left:3px solid #6B5B73;"><p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Empfehlungs-Effekt:</strong> Kommunikativ ohne laut zu sein. Komplimente führen zu Geschenken führen zu Neukundinnen.</p></div>
      <div style="padding-left:1.25rem; border-left:3px solid #6B5B73;"><p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Täglicher Begleiter:</strong> Für viele wird der FIREBALL zum Alltagsschmuck — wie ein Lippenstift, immer dabei.</p></div>
    </div>
  </div>
</div></section>

<section style="padding:0;"><img src="/img/3.jpeg" alt="Varianten" style="width:100%; display:block;" /></section>

<section style="background:var(--white); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto;">
  <h2 style="font-size:1.5rem; text-align:center; color:var(--teal); margin:0 0 2rem;">Cross-Selling Pipeline</h2>
  <img src="/img/4.jpeg" alt="Cross-Selling" style="width:100%;" />
  <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:1.5rem auto 0; line-height:1.7;">Ketten, Ringe, Armbänder — das FIREBALL-Design als komplettes Sortiment für Ihren Fachhandel.</p>
</div></section>

<section style="padding:0;"><img src="/img/13.jpeg" alt="FIREBALL Model" style="width:100%; display:block;" /></section>

<!-- PRICING BLURRED -->
<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:1100px; margin:0 auto;">
  <h2 style="font-size:1.5rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Displays & Konditionen</h2>
  <div style="position:relative;">
    <div style="{unlocked ? '' : 'filter:blur(6px);user-select:none;pointer-events:none;'}transition:filter 0.4s;">
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
        <div style="background:var(--teal); padding:2rem; color:var(--white);"><h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">D21 Display Black</h3><p style="opacity:0.7; font-size:0.85rem; margin:0;">21 SKU / 63 PCS · 15 Farben</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 1.174€ · RRP 3.054€</p></div>
        <div style="background:var(--white); padding:2rem; border:1px solid var(--gray-200);"><h3 style="color:var(--teal); font-size:1.1rem; margin:0 0 0.5rem;">D18 Display White</h3><p style="color:var(--gray-500); font-size:0.85rem; margin:0;">18 SKU / 45 PCS · 9 Farben</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 931,50€ · RRP 2.424,60€</p></div>
      </div>
      <p style="color:var(--gray-500); text-align:center; margin-top:1.5rem; font-size:0.85rem;">Classic 21mm: 49,90€ RPR · Small 16mm: 39,90€ RPR · Brass & Shiny Golden</p>
    </div>
    {#if !unlocked}<div style="position:absolute; inset:0; display:flex; align-items:center; justify-content:center; z-index:10;"><button onclick={() => showPwModal = true} style="padding:1rem 2.5rem; background:var(--gold); color:var(--teal); border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif; font-size:1rem; font-weight:700; box-shadow:0 8px 32px rgba(0,0,0,0.2); display:flex; align-items:center; gap:0.6rem;">🔒 Preise freischalten</button></div>{/if}
  </div>
</div></section>

<!-- 3 STEPS -->
<section style="background:var(--white); padding:5rem 2rem;"><div style="max-width:900px; margin:0 auto;">
  <h2 style="font-size:1.6rem; text-align:center; color:var(--teal); margin:0 0 3rem;">In 3 Schritten zum Display-Partner</h2>
  <div style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:2rem;">
    {#each [{n:'1',t:'Rechner anfordern',d:'Formular → individueller Produktivitätsrechner. Ihre Frequenz = Ihr Jahresumsatz.'},{n:'2',t:'Muster testen',d:'3–5 Sticks per Express. Anfassen, Stammkundinnen zeigen, Feedback sammeln.'},{n:'3',t:'Display aufstellen',d:'Fertig bestückt auf Ihre Theke. 4 Wochen testen. Zahlen entscheiden.'}] as s}
      <div style="text-align:center;"><div style="width:56px; height:56px; border-radius:50%; background:#6B5B73; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1.2rem; margin:0 auto 1rem;">{s.n}</div><h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">{s.t}</h4><p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin:0;">{s.d}</p></div>
    {/each}
  </div>
</div></section>

<section style="background:var(--cream); padding:5rem 2rem;"><div style="max-width:700px; margin:0 auto;">
  <h2 style="font-size:1.4rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Häufige Fragen</h2>
  {#each faqs as faq}<details style="margin-bottom:1rem; background:var(--white); border:1px solid var(--gray-200);"><summary style="padding:1rem 1.25rem; cursor:pointer; font-weight:600; font-size:0.95rem; color:var(--teal); list-style:none; display:flex; justify-content:space-between; align-items:center;">{faq.q}<span style="color:var(--gold); font-size:1.2rem; flex-shrink:0; margin-left:1rem;">+</span></summary><div style="padding:0 1.25rem 1.25rem;"><p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin:0;">{faq.a}</p></div></details>{/each}
</div></section>

<section id="kontakt" style="background:var(--teal); padding:5rem 2rem;"><div style="max-width:520px; margin:0 auto; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1.4rem; margin-bottom:1rem;">FIREBALL</p>
  <h2 style="color:var(--white); font-size:1.8rem; margin:0 0 0.75rem;">Produktivitätsrechner anfordern</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:2rem;">Ihre Frequenz → Ihr möglicher Jahresumsatz. In 24 Stunden.</p>
  <LeadForm channel="schmuckhandel" ctaText="Rechner anfordern" brancheOptions={['Juwelier', 'Schmuck-Fachhandel', 'Schmuck-Atelier', 'Online + Stationär']} />
</div></section>
<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;"><p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 FIREBALL by VICI Vertrieb Deutschland GmbH</p></footer>
<style>details[open] summary span { transform: rotate(45deg); } details summary span { transition: transform 0.2s; display:inline-block; } @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }</style>
