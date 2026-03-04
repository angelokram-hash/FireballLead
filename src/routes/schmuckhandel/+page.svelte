<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
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
