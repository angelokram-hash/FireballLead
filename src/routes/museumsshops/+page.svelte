<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
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

<!-- CTA -->
<section class="section-dark" style="padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Ein Mitbringsel, das bleibt.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Fordern Sie unser Lookbook mit Designer-Story und Bildmaterial an.</p>
  <a href="#" onclick="window.scrollTo({top:0,behavior:'smooth'})" class="btn-primary">Lookbook anfordern →</a>
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
