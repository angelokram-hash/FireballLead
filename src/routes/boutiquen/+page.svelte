<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  const steps = [
    { t: 'Tag 1', title: 'Info-Paket anfordern', desc: 'Formular ausfüllen → Factsheet, Lookbook, Preisliste und Farbkatalog per E-Mail innerhalb 24h.', tasks: ['Factsheet mit Produktivitätszahlen und ROI', 'Hochauflösende Produktfotos und Display-Bilder', 'Preisliste mit WS-Konditionen', 'Übersicht 21+ Farbvarianten für Displays'], tip: 'Je mehr wir über Ihren Store wissen, desto besser schneiden wir das Display zu.' },
    { t: 'Tag 2–3', title: 'Persönliches Beratungsgespräch', desc: '15-Minuten Call: Store-Situation, Display-Auswahl, Farbkonzept, Platzierung.', tasks: ['D18 (kompakt, 18 SKU) oder D21 (voll, 21 SKU)?', 'Farbauswahl passend zu Kundschaft und Saison', 'Platzierung: Kasse, Schaufenster oder freistehend?', 'Testphase-Bedingungen besprechen'], tip: 'Senden Sie vorab ein Foto Ihres Kassenbereichs — sofortige Platzierungsempfehlung.' },
    { t: 'Tag 4–7', title: 'Probedisplay aufstellen', desc: 'Fertig bestücktes Display per Express. Aufstellen: 5 Minuten. Team-Schulung per Video.', tasks: ['Display fertig bestückt — kein Zusammenbauen', 'Kurze Team-Schulung (5 Min Video)', 'POS-Material: Aufsteller, Farbkarte, Preisschilder', 'Stick-Verpackung = Präsentation + Verpackung + Case'], tip: 'Erfolgsfaktor: Höchste Frequenzstelle + Team-Commitment.' },
    { t: 'Woche 1–4', title: '4-Wochen-Testphase', desc: 'Testen mit regelmäßigen Check-ins. Wir begleiten Sie mit Feedback und Nachbestell-Check.', tasks: ['Woche 1: Erstes Feedback — läuft das Display?', 'Woche 2: Erste Verkaufszahlen besprechen', 'Woche 3: Farb-Nachbestellung prüfen', 'Woche 4: Abschlussgespräch und Zahlen'], tip: 'Erfolgsfaktoren: Frequenz (Lage) und Engagement des Teams.' },
    { t: 'Danach', title: 'Auswertung & Partnerschaft', desc: 'Gemeinsame Auswertung. Bei Erfolg: Festbestellung. Bei Nicht-Erfolg: Display kostenlos zurück.', tasks: ['Benchmark: Ø 2 Paar/Tag = 17.000–50.000€/Jahr', 'Farbsortiment optimieren nach Bestsellern', 'Nachbestellung per App oder E-Mail', 'Cross-Selling Pipeline: Ketten, Ringe, Armbänder'], tip: 'Stammkundinnen kaufen im Schnitt 5–10 Farben pro Jahr.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Modeboutiquen — Impulskauf-Display für Ihre Kundschaft</title>
  <meta name="description" content="FIREBALL Schmuck-Display: 49,90€ RPR, Sammelcharakter, 17.000–50.000€ Jahresumsatz auf 0,2m². Jetzt Probedisplay anfordern." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO with lifestyle image -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/1.jpeg" alt="FIREBALL Lifestyle" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(135deg, rgba(26,60,64,0.92) 0%, rgba(26,60,64,0.7) 50%, rgba(26,60,64,0.4) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="display:grid; grid-template-columns:1fr 420px; gap:4rem; align-items:center;">
      <div>
        <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">Für Modeboutiquen & Concept Stores</p>
        <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.2rem,4.5vw,3.2rem); font-weight:700; color:var(--white); line-height:1.1; margin:0 0 1.5rem;">Der Impulskauf, den Ihre Kundinnen <span style="color:var(--gold);">sammeln.</span></h1>
        <p class="animate-fade-up delay-200" style="font-size:1.1rem; color:rgba(255,255,255,0.7); line-height:1.7; margin-bottom:2.5rem;">280+ Farben, handgefertigt, 39,90–49,90€. Kundinnen besitzen 30, 50, manchmal über 100 verschiedene Paare. Das bedeutet: garantierter Wiederkauf.</p>
        <div class="animate-fade-up delay-300" style="display:flex; gap:2.5rem;">
          <div><div class="stat-number" style="font-size:2rem;">49,90€</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">RPR Classic</div></div>
          <div><div class="stat-number" style="font-size:2rem;">~2/Tag</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Ø Verkäufe</div></div>
          <div><div class="stat-number" style="font-size:2rem;">0,2m²</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Platzbedarf</div></div>
        </div>
      </div>
      <div class="animate-fade-up delay-300" style="background:rgba(255,255,255,0.06); backdrop-filter:blur(8px); border:1px solid rgba(255,255,255,0.1); padding:2rem;">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Kostenloses Probedisplay sichern</h3>
        <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">4 Wochen testen — ohne Risiko, ohne Mindestvertrag.</p>
        <LeadForm channel="boutiquen" ctaText="Probedisplay anfordern" brancheOptions={['Modeboutique', 'Concept Store', 'Multi-Brand Store', 'Flagship Store']} />
      </div>
    </div>
  </div>
</section>

<!-- MODEL + WHY -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <img src="/img/13.jpeg" alt="Model mit FIREBALL Ohrring" style="width:100%; border:1px solid var(--gray-200);" />
    <div>
      <h2 style="font-size:1.8rem; margin:0 0 1.5rem; color:var(--teal);">Warum FIREBALL in Ihre Boutique gehört</h2>
      <div style="display:flex; flex-direction:column; gap:1.25rem;">
        <div style="padding-left:1rem; border-left:3px solid var(--gold);">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Stammkunden-Maschine</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Kundinnen sammeln 30–100+ Farben. Der FIREBALL macht aus Laufkundschaft Stammkundinnen.</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid var(--gold);">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Null Beratungsaufwand</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Das Display verkauft sich selbst. Die Frage ist nicht „ob?", sondern „welche Farbe?"</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid var(--gold);">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Empfehlungs-Wachstum</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Kundinnen bekommen Komplimente und verschenken den FIREBALL. Organisches Wachstum.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- POS COLOR ROW IMAGE -->
<section style="padding:0;"><img src="/img/9.jpeg" alt="FIREBALL POS Farbauswahl" style="width:100%; display:block;" /></section>

<!-- DISPLAYS -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 1rem;">Zwei Display-Optionen — offen für Anpassungen</h2>
    <p style="color:var(--gray-500); text-align:center; margin-bottom:2rem;">Individuell an Ihren POS anpassbar in Form und Farbe.</p>
    <img src="/img/5.jpeg" alt="FIREBALL Displays D21 und D18" style="width:100%; border:1px solid var(--gray-200);" />
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem; margin-top:2rem;">
      <div style="background:var(--teal); padding:2rem; color:var(--white);">
        <h3 style="color:var(--gold); font-size:1.2rem; margin:0 0 1rem;">D21 Display Black</h3>
        <p style="opacity:0.7; font-size:0.9rem; margin:0 0 0.25rem;">45 × 35 × 35 cm · 21 SKU / 63 Stück · 15 Farben / 2 Größen</p>
        <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 1.174€ · RRP 3.054€</p>
      </div>
      <div style="background:var(--cream); padding:2rem;">
        <h3 style="color:var(--teal); font-size:1.2rem; margin:0 0 1rem;">D18 Display White</h3>
        <p style="color:var(--gray-500); font-size:0.9rem; margin:0 0 0.25rem;">34 × 34 × 21 cm · 18 SKU / 45 Stück · 9 Farben / 2 Größen</p>
        <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 931,50€ · RRP 2.424,60€</p>
      </div>
    </div>
  </div>
</section>

<!-- VARIANTS IMAGE -->
<section style="padding:0;"><img src="/img/3.jpeg" alt="FIREBALL Varianten" style="width:100%; display:block;" /></section>

<!-- STEP BY STEP -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 0.5rem;">So starten Sie — Schritt für Schritt</h2>
    <p style="color:var(--gray-500); text-align:center; margin-bottom:3rem;">Vom ersten Kontakt bis zum laufenden Umsatz.</p>
    {#each steps as step, i}
      <div style="display:grid; grid-template-columns:56px 1fr; gap:1.25rem; margin-bottom:0;">
        <div style="display:flex; flex-direction:column; align-items:center;">
          <div style="width:44px; height:44px; border-radius:50%; background:var(--gold); display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:var(--teal); font-size:1rem; z-index:2;">{i+1}</div>
          {#if i < steps.length - 1}<div style="width:2px; flex:1; background:var(--gray-200);"></div>{/if}
        </div>
        <div style="padding-bottom:2rem;">
          <div style="background:var(--white); border:1px solid var(--gray-200); border-left:3px solid var(--gold); padding:1.25rem;">
            <span style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:var(--gold); text-transform:uppercase;">{step.t}</span>
            <h3 style="font-size:1.05rem; color:var(--teal); margin:0.2rem 0 0.4rem;">{step.title}</h3>
            <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin-bottom:0.75rem;">{step.desc}</p>
            {#each step.tasks as task}<div style="display:flex; gap:0.4rem; margin-bottom:0.3rem;"><span style="color:var(--gold); font-size:0.8rem;">✓</span><span style="font-size:0.8rem; color:var(--gray-700); line-height:1.4;">{task}</span></div>{/each}
            {#if step.tip}<div style="margin-top:0.75rem; padding:0.6rem 0.75rem; background:rgba(200,169,81,0.08); border-left:2px solid var(--gold);"><p style="font-size:0.75rem; color:var(--teal); margin:0;"><strong>Tipp:</strong> {step.tip}</p></div>{/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<!-- CTA BOTTOM -->
<section style="background:var(--teal); padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">Bereit für den Test?</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">4 Wochen testen. Kein Risiko. Kein Mindestvertrag.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Probedisplay anfordern →</a>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) {
    section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; }
  }
</style>
