<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';

  const channels = [
    {
      slug: '/boutiquen',
      title: 'Modeboutiquen & Concept Stores',
      icon: '👗',
      tagline: 'Der perfekte Impulskauf für Ihre modebewusste Kundschaft',
      color: '#8B5E3C',
      stats: '49,90€ RPR · Sofort-Impulskauf'
    },
    {
      slug: '/parfuemerien',
      title: 'Parfümerien & Beauty-Fachhandel',
      icon: '💄',
      tagline: 'Wie ein Lippenstift — immer dabei, immer anders',
      color: '#9B4D6E',
      stats: 'Stick-Verpackung · Beauty-Kontext'
    },
    {
      slug: '/kaufhaeuser',
      title: 'Kaufhäuser & Department Stores',
      icon: '🏬',
      tagline: 'Maximale Flächenproduktivität auf minimaler Fläche',
      color: '#2C5F7C',
      stats: 'EDI-fähig · Skalierbar'
    },
    {
      slug: '/museumsshops',
      title: 'Museumsshops & Hotel-Boutiquen',
      icon: '🏛️',
      tagline: 'Handgefertigt — das perfekte Mitbringsel mit Geschichte',
      color: '#5C6B4E',
      stats: 'Designer-Story · Geschenkfertig'
    },
    {
      slug: '/schmuckhandel',
      title: 'Schmuck-Fachhandel & Juweliere',
      icon: '💎',
      tagline: '30 Jahre Bestseller — jetzt als Display-Konzept für Ihre Theke',
      color: '#6B5B73',
      stats: '280+ Farben · Cross-Selling Pipeline'
    }
  ];
</script>

<svelte:head>
  <title>FIREBALL — Display-Partnerprogramm</title>
  <meta name="description" content="Werden Sie FIREBALL Display-Partner. 17.000–50.000€ Jahresumsatz auf 0,2m² — der meistverkaufte Designerschmuck Deutschlands." />
</svelte:head>

<Navbar />

<!-- HERO -->
<section class="section-dark noise-overlay" style="
  position:relative;
  min-height:100vh;
  display:flex;
  align-items:center;
  padding:8rem 2rem 6rem;
">
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; width:100%;">
    <div style="max-width:720px;">
      <p class="animate-fade-up" style="
        font-family:'Josefin Sans',sans-serif;
        color:var(--gold);
        font-size:0.85rem;
        letter-spacing:0.2em;
        text-transform:uppercase;
        margin-bottom:1.5rem;
      ">Display-Partnerprogramm 2026</p>

      <h1 class="animate-fade-up delay-100" style="
        font-size:clamp(2.2rem, 5vw, 3.5rem);
        font-weight:700;
        color:var(--white);
        line-height:1.1;
        margin:0 0 1.5rem;
      ">
        17.000–50.000€<br/>
        <span style="color:var(--gold);">Jahresumsatz</span><br/>
        auf 0,2m².
      </h1>

      <p class="animate-fade-up delay-200" style="
        font-size:1.15rem;
        color:rgba(255,255,255,0.7);
        line-height:1.7;
        margin-bottom:2rem;
        max-width:560px;
      ">
        Der meistverkaufte Designerschmuck Deutschlands — seit über 30 Jahren.
        Jetzt als fertiges Display-Konzept für Ihren Point of Sale.
      </p>

      <div class="animate-fade-up delay-300" style="display:flex; gap:1rem; flex-wrap:wrap;">
        <a href="#branchen" class="btn-primary">Ihre Branche finden →</a>
        <a href="#kontakt" class="btn-secondary">Direkt Kontakt aufnehmen</a>
      </div>
    </div>

    <!-- Stats -->
    <div class="animate-fade-up delay-400" style="
      display:grid;
      grid-template-columns:repeat(4, 1fr);
      gap:2rem;
      margin-top:5rem;
      padding-top:3rem;
      border-top:1px solid rgba(255,255,255,0.1);
    ">
      <div>
        <div class="stat-number">30+</div>
        <div class="stat-label" style="color:rgba(255,255,255,0.5);">Jahre Marktpräsenz</div>
      </div>
      <div>
        <div class="stat-number">280+</div>
        <div class="stat-label" style="color:rgba(255,255,255,0.5);">Farbvarianten</div>
      </div>
      <div>
        <div class="stat-number">~2/Tag</div>
        <div class="stat-label" style="color:rgba(255,255,255,0.5);">Ø Verkäufe pro Display</div>
      </div>
      <div>
        <div class="stat-number">0,2m²</div>
        <div class="stat-label" style="color:rgba(255,255,255,0.5);">Platzbedarf Display</div>
      </div>
    </div>
  </div>
</section>

<!-- BRANCHEN SECTION -->
<section id="branchen" class="section-cream" style="padding:6rem 2rem;">
  <div style="max-width:1200px; margin:0 auto;">
    <p style="
      font-family:'Josefin Sans',sans-serif;
      color:var(--gold);
      font-size:0.8rem;
      letter-spacing:0.2em;
      text-transform:uppercase;
      margin-bottom:0.75rem;
    ">Finden Sie Ihren Kanal</p>

    <h2 style="font-size:clamp(1.8rem, 3vw, 2.5rem); margin:0 0 1rem;">
      Für welche Branche passt FIREBALL?
    </h2>
    <p style="color:var(--gray-500); max-width:600px; margin-bottom:3rem; line-height:1.7;">
      Wir haben für jede Vertriebsform ein maßgeschneidertes Konzept — mit eigener Landing Page,
      konkreten Zahlen und einem passenden Einstiegsangebot.
    </p>

    <div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(340px, 1fr)); gap:1.5rem;">
      {#each channels as ch, i}
        <a
          href={ch.slug}
          class="card animate-fade-up"
          style="
            text-decoration:none;
            color:inherit;
            animation-delay:{i * 0.1}s;
            border-left:4px solid {ch.color};
          "
        >
          <div style="font-size:2rem; margin-bottom:1rem;">{ch.icon}</div>
          <h3 style="font-size:1.15rem; margin:0 0 0.5rem; color:var(--teal);">{ch.title}</h3>
          <p style="color:var(--gray-500); font-size:0.9rem; line-height:1.6; margin-bottom:1rem;">
            {ch.tagline}
          </p>
          <p style="
            font-family:'Josefin Sans',sans-serif;
            font-size:0.75rem;
            letter-spacing:0.1em;
            color:{ch.color};
          ">{ch.stats}</p>
        </a>
      {/each}
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section class="section-white" style="padding:6rem 2rem;">
  <div style="max-width:1000px; margin:0 auto;">
    <h2 style="font-size:clamp(1.8rem, 3vw, 2.5rem); text-align:center; margin:0 0 3rem;">
      So funktioniert es
    </h2>

    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:3rem; text-align:center;">
      <div>
        <div style="
          width:56px; height:56px;
          background:var(--cream);
          border-radius:50%;
          display:flex; align-items:center; justify-content:center;
          margin:0 auto 1rem;
          font-family:'Josefin Sans',sans-serif;
          font-weight:700;
          color:var(--teal);
          font-size:1.25rem;
        ">1</div>
        <h4 style="font-size:1rem; margin:0 0 0.5rem;">Info-Paket anfordern</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Füllen Sie das Formular aus. Wir senden Ihnen alle Zahlen, Fotos und Konditionen.
        </p>
      </div>
      <div>
        <div style="
          width:56px; height:56px;
          background:var(--cream);
          border-radius:50%;
          display:flex; align-items:center; justify-content:center;
          margin:0 auto 1rem;
          font-family:'Josefin Sans',sans-serif;
          font-weight:700;
          color:var(--teal);
          font-size:1.25rem;
        ">2</div>
        <h4 style="font-size:1rem; margin:0 0 0.5rem;">Test-Display erhalten</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Wir stellen ein passendes Display für Ihren POS zusammen — inklusive Beratung.
        </p>
      </div>
      <div>
        <div style="
          width:56px; height:56px;
          background:var(--cream);
          border-radius:50%;
          display:flex; align-items:center; justify-content:center;
          margin:0 auto 1rem;
          font-family:'Josefin Sans',sans-serif;
          font-weight:700;
          color:var(--teal);
          font-size:1.25rem;
        ">3</div>
        <h4 style="font-size:1rem; margin:0 0 0.5rem;">Verkaufen & nachbestellen</h4>
        <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6;">
          Einfache Nachbestellung per App oder EDI. Wir liefern nach, Sie verkaufen weiter.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT / LEAD FORM -->
<section id="kontakt" class="section-dark" style="padding:6rem 2rem;">
  <div style="max-width:640px; margin:0 auto;">
    <p style="
      font-family:'Josefin Sans',sans-serif;
      color:var(--gold);
      font-size:0.8rem;
      letter-spacing:0.2em;
      text-transform:uppercase;
      text-align:center;
      margin-bottom:0.75rem;
    ">Jetzt starten</p>

    <h2 style="
      font-size:clamp(1.8rem, 3vw, 2.2rem);
      text-align:center;
      color:var(--white);
      margin:0 0 0.75rem;
    ">Kostenloses Info-Paket anfordern</h2>

    <p style="text-align:center; color:rgba(255,255,255,0.6); margin-bottom:2.5rem;">
      Erfahren Sie, wie FIREBALL Displays Ihren Umsatz pro Quadratmeter steigern können.
    </p>

    <div style="background:var(--white); padding:2rem; border-left:4px solid var(--gold);">
      <LeadForm
        channel="hub"
        ctaText="Info-Paket anfordern"
        brancheOptions={['Modeboutique / Concept Store', 'Parfümerie / Beauty', 'Kaufhaus / Department Store', 'Museumsshop / Hotel-Boutique', 'Schmuck-Fachhandel / Juwelier', 'Sonstige']}
      />
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer style="
  background:var(--teal);
  border-top:1px solid rgba(255,255,255,0.08);
  padding:2rem;
  text-align:center;
">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">
    © 2026 VICI Vertrieb Deutschland GmbH · Alle Rechte vorbehalten
  </p>
</footer>

<style>
  @media (max-width: 768px) {
    div[style*="grid-template-columns:repeat(4"] {
      grid-template-columns: repeat(2, 1fr) !important;
    }
    div[style*="grid-template-columns:repeat(3"] {
      grid-template-columns: 1fr !important;
    }
  }
</style>
