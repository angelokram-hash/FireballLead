<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
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
