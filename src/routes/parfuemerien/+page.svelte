<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
</script>

<svelte:head>
  <title>FIREBALL für Parfümerien — Display-Partnerschaft</title>
  <meta name="description" content="FIREBALL Schmuck-Display für Parfümerien & Beauty-Fachhandel. Die Stick-Verpackung passt perfekt ins Beauty-Sortiment." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section class="section-dark noise-overlay" style="position:relative; padding:8rem 2rem 5rem;">
  <div style="position:relative; z-index:2; max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">
        Für Parfümerien & Beauty-Fachhandel
      </p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem, 4vw, 2.8rem); font-weight:700; color:var(--white); line-height:1.15; margin:0 0 1.5rem;">
        „Wie mein Lippenstift,<br/>
        <span style="color:var(--gold);">immer dabei."</span>
      </h1>
      <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.65); line-height:1.7; margin-bottom:2rem;">
        Der FIREBALL Ohrring in der Stick-Verpackung fügt sich nahtlos ins Beauty-Sortiment ein.
        Ihre Kundinnen kennen das Ritual: vor der Farbauswahl stehen, eintauchen, die eigene Farbe finden.
      </p>
      <div class="animate-fade-up delay-300" style="display:flex; gap:2rem; flex-wrap:wrap;">
        <div><div class="stat-number" style="font-size:1.8rem;">280+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Farbvarianten</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">Stick</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Verpackung = Case</div></div>
        <div><div class="stat-number" style="font-size:1.8rem;">0 Abfall</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Nachhaltig</div></div>
      </div>
    </div>
    <div class="animate-fade-up delay-200" style="background:rgba(255,255,255,0.03); border:1px solid rgba(255,255,255,0.08); padding:2rem;">
      <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Muster-Paket bestellen</h3>
      <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Wir senden Ihnen 3 Muster-Sticks + Factsheet direkt in Ihre Parfümerie.</p>
      <LeadForm channel="parfuemerien" ctaText="Muster-Paket anfordern" brancheOptions={['Parfümerie (inhabergeführt)', 'Douglas Franchise', 'Kosmetikinstitut mit Retail', 'Beauty Concept Store']} />
    </div>
  </div>
</section>

<!-- LIPSTICK ANALOGY -->
<section class="section-cream" style="padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto; text-align:center;">
    <h2 style="font-size:1.8rem; margin:0 0 1rem;">Der „Lipstick Effect" — wissenschaftlich belegt</h2>
    <p style="color:var(--gray-500); max-width:640px; margin:0 auto 2.5rem; line-height:1.7;">
      Wenn die Konjunktur ins Stocken gerät, steigt der Absatz für weibliche Schönheitsprodukte.
      Der FIREBALL ist eine Affordable Luxury — konjunkturresistent und impulsstark.
    </p>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:2rem;">
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Vertrautes Format</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Die Stick-Verpackung fühlt sich an wie ein Lippenstift — die Kundin nimmt ihn instinktiv in die Hand.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Farbauswahl als Erlebnis</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Genau wie bei einem Nagellack-Regal: Kundinnen tauchen ein, vergleichen, entscheiden — und kommen wieder.
        </p>
      </div>
      <div class="card" style="border-top:3px solid #9B4D6E;">
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Kassennah platzierbar</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Das kompakte Display passt neben die Kasse oder ins Schaufenster — überall dort, wo der Impulskauf entsteht.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- ROI SECTION -->
<section class="section-white" style="padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 2.5rem;">Ihre Rechnung — konkret</h2>
    <div style="background:var(--teal); padding:2.5rem; color:var(--white);">
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Ihr Invest (D18 Display)</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">931,50€ WS</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">RRP im Display</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">2.424,60€</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Ø Tagesverkauf</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">2 Paar</p>
        </div>
        <div>
          <p style="opacity:0.6; font-size:0.85rem; margin-bottom:0.25rem;">Hochrechnung / Jahr</p>
          <p style="font-family:'Josefin Sans',sans-serif; font-size:1.5rem; color:var(--gold);">17.000–50.000€</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA BOTTOM -->
<section class="section-dark" style="padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">3 Muster-Sticks. Kostenlos. Unverbindlich.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Legen Sie die Sticks neben Ihre Lippenstifte — der Rest passiert von allein.</p>
  <a href="#" onclick="window.scrollTo({top:0,behavior:'smooth'})" class="btn-primary">Muster-Paket anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <a href="/" style="text-decoration:none;"><p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p></a>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section:first-of-type > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:repeat(3"] { grid-template-columns: 1fr !important; }
    div[style*="grid-template-columns:1fr 1fr"][style*="gap:2rem"] { grid-template-columns: 1fr !important; }
  }
</style>
