<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let blur = $derived(unlocked ? '' : 'filter:blur(5px);user-select:none;');
  const steps = [
    { t: 'Tag 1', title: 'Lookbook & Konditionen anfordern', desc: 'Formular ausfüllen → Lookbook mit Designer-Story, Manufaktur-Fotos und Sonderkonditionen.', tasks: ['Lookbook mit hochauflösenden Lifestyle-Fotos', 'Designer-Story von Miranda Konstantinidou', 'Manufaktur-Bilder: Handarbeit in Cebu', 'Sonderkonditionen für Kultureinrichtungen'], tip: 'Erwähnen Sie den thematischen Kontext — wir empfehlen Farben passend zu Ihrer Ausstellung.' },
    { t: 'Tag 3–5', title: 'Beratung: Das richtige Konzept', desc: 'Call (15–20 Min): FIREBALL als Design-Souvenir oder Geschenk-Sortiment? Display, Farben, Story-Karte.', tasks: ['Analyse: Besucherprofil, Durchschnittsbon, Sortiment', 'Konzept: Souvenir oder Geschenk-Sortiment?', 'Story-Karte A5: Designer- und Manufaktur-Geschichte', 'QR-Code für Manufaktur-Video (optional)'], tip: 'Shops mit guter Produkt-Story verkaufen bis zu 40% mehr.' },
    { t: 'Woche 2', title: 'Display & Story-Material einrichten', desc: 'Fertig bestücktes Display + Story-Karten + Team-Briefing mit 3 Story-Elementen.', tasks: ['Display auspacken und nahe der Kasse platzieren', 'Story-Karten für Kunden zum Mitnehmen', '„Jeder FIREBALL wird von Hand gefertigt"', '„Über 280 Farben — seit 30 Jahren jedes Jahr neue"', '„Stick = Präsentation und Geschenk-Etui in einem"'], tip: 'Besucher kaufen Mitbringsel beim Hinausgehen — Display nahe Ausgang/Kasse.' },
    { t: 'Woche 3–8', title: 'Testphase & Besucherreaktionen', desc: '6 Wochen testen. Welche Farben zuerst? Wird geschenkt oder selbst getragen?', tasks: ['Woche 3–4: Greifen Besucher zum Display?', 'Woche 5: Verkaufszahlen, beliebteste Farben', 'Woche 6: Nachbestellung Top-Seller', 'Woche 7–8: Abschlussbewertung'], tip: 'Hotels: FIREBALL-Karte ins Zimmer — „Entdecken Sie Designerschmuck in unserer Boutique."' },
    { t: 'Ab Woche 9', title: 'Partnerschaft & Storytelling', desc: 'Feste Partnerschaft mit saisonalen Updates, Geschenk-Sets und optionalen Exklusiv-Farben.', tasks: ['Saisonale Farben passend zu Ausstellungswechseln', 'Geschenk-Sets: Weihnachten, Muttertag, Valentinstag', 'Exklusiv-Farbe nur für Ihre Einrichtung (ab 5 Displays)', 'Cross-Selling: Ketten als „großes Geschenk"'], tip: 'Besonders erfolgreich: Eine Signature-Farbe, die es nur bei Ihnen gibt.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Museumsshops — Handgefertigt. Mit Geschichte. Das perfekte Mitbringsel.</title>
  <meta name="description" content="FIREBALL Designerschmuck: Handgefertigt, 30+ Jahre Geschichte, geschenkfertige Stick-Verpackung. Lookbook anfordern." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/12.jpeg" alt="FIREBALL Manufaktur" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(135deg, rgba(26,60,64,0.92) 0%, rgba(26,60,64,0.7) 50%, rgba(26,60,64,0.35) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="display:grid; grid-template-columns:1fr 420px; gap:4rem; align-items:center;">
      <div>
        <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">Für Museumsshops & Hotel-Boutiquen</p>
        <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem,4vw,3rem); font-weight:700; color:var(--white); line-height:1.1; margin:0 0 1.5rem;">Handgefertigt. Mit Geschichte. Das perfekte <span style="color:var(--gold);">Mitbringsel.</span></h1>
        <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.7); line-height:1.7; margin-bottom:2rem;">Vor mehr als 30 Jahren von Miranda Konstantinidou entworfen. Jedes Stück von Hand gefertigt in unserer Manufaktur. Über 280 Farben. Geschenkfertig im Stick.</p>
        <div class="animate-fade-up delay-300" style="display:flex; gap:2.5rem;">
          <div><div class="stat-number" style="font-size:2rem;">30+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Jahre Design</div></div>
          <div><div class="stat-number" style="font-size:2rem;">280+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Farben</div></div>
          <div><div class="stat-number" style="font-size:2rem;">Handmade</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Manufaktur</div></div>
        </div>
      </div>
      <div class="animate-fade-up delay-300" style="background:rgba(255,255,255,0.06); backdrop-filter:blur(8px); border:1px solid rgba(255,255,255,0.1); padding:2rem;">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Lookbook mit Designer-Story</h3>
        <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Fotos, Geschichte, Manufaktur — für Ihre Produktpräsentation.</p>
        <LeadForm channel="museumsshops" ctaText="Lookbook anfordern" brancheOptions={['Museumsshop', 'Hotel-Boutique', 'Galerie-Shop', 'Concept Store (Kultur)']} />
      </div>
    </div>
  </div>
</section>

<!-- DER OHRRING -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <div>
      <h2 style="font-size:1.6rem; color:var(--teal); margin:0 0 1.5rem;">Der Ohrring mit Geschichte</h2>
      <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.8; margin-bottom:1.5rem;">Der FIREBALL wurde vor mehr als 30 Jahren von Miranda Konstantinidou für Konplott entworfen. Jedes Jahr kommen neue Farben hinzu — insgesamt nun mehr als 280. Seit wir den FIREBALL machen, gibt es kein Jahr, in dem er nicht unser meistverkaufter Artikel ist. Mit Abstand.</p>
      <div style="padding-left:1rem; border-left:3px solid #5C6B4E;">
        <p style="font-size:0.9rem; color:var(--teal); line-height:1.6; margin:0;">Wir kennen nicht den Hersteller — <strong>wir sind der Hersteller.</strong> Und wir kennen die Menschen, die die Schmuckstücke von Hand fertigen. Leilanie, Josie, Erlinda — seit Jahren Teil unseres Teams.</p>
      </div>
    </div>
    <img src="/img/6.jpeg" alt="Der FIREBALL Ohrring" style="width:100%; border:1px solid var(--gray-200);" />
  </div>
</section>

<!-- MANUFAKTUR -->
<section style="padding:0;"><img src="/img/12.jpeg" alt="FIREBALL Manufaktur Handarbeit" style="width:100%; display:block;" /></section>

<!-- DER STICK -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <img src="/img/10.jpeg" alt="FIREBALL Stick" style="width:100%; border:1px solid var(--gray-200);" />
    <div>
      <h2 style="font-size:1.5rem; color:var(--teal); margin:0 0 1rem;">Geschenkfertig im Stick</h2>
      <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.7; margin-bottom:1rem;">Die Stick-Verpackung ist gleichzeitig Präsentation, Verpackung und Reise-Etui. Kein zusätzliches Geschenkpapier nötig. Kein Abfall.</p>
      <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.7;">Ideal als Mitbringsel: kompakt, elegant, mit einer Geschichte, die man weitererzählen kann.</p>
    </div>
  </div>
</section>

<!-- STEPS -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 3rem;">So starten Sie — Schritt für Schritt</h2>
    {#each steps as step, i}
      <div style="display:grid; grid-template-columns:56px 1fr; gap:1.25rem;">
        <div style="display:flex; flex-direction:column; align-items:center;">
          <div style="width:44px; height:44px; border-radius:50%; background:#5C6B4E; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1rem; z-index:2;">{i+1}</div>
          {#if i < steps.length - 1}<div style="width:2px; flex:1; background:var(--gray-200);"></div>{/if}
        </div>
        <div style="padding-bottom:2rem;">
          <div style="background:var(--white); border:1px solid var(--gray-200); border-left:3px solid #5C6B4E; padding:1.25rem;">
            <span style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#5C6B4E; text-transform:uppercase;">{step.t}</span>
            <h3 style="font-size:1.05rem; color:var(--teal); margin:0.2rem 0 0.4rem;">{step.title}</h3>
            <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin-bottom:0.75rem;">{step.desc}</p>
            {#each step.tasks as task}<div style="display:flex; gap:0.4rem; margin-bottom:0.3rem;"><span style="color:#5C6B4E; font-size:0.8rem;">✓</span><span style="font-size:0.8rem; color:var(--gray-700); line-height:1.4;{task.includes('€') ? blur : ''}">{task}</span></div>{/each}
            {#if step.tip}<div style="margin-top:0.75rem; padding:0.6rem; background:rgba(92,107,78,0.06); border-left:2px solid #5C6B4E;"><p style="font-size:0.75rem; color:var(--teal); margin:0;{step.tip?.includes('€') ? blur : ''}"><strong>Tipp:</strong> {step.tip}</p></div>{/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<!-- CTA -->
<section style="background:var(--teal); padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Ein Mitbringsel, das bleibt.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Fordern Sie unser Lookbook mit Designer-Story und Bildmaterial an.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Lookbook anfordern →</a>
</section>

<PriceGate bind:unlocked />

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }
</style>
