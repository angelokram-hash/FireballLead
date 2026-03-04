<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let showPwModal = $state(false);

  const faqs = [
    { q: 'Was passiert nach der Testphase?', a: 'Sie entscheiden datenbasiert. Funktioniert das Display? Festbestellung. Nicht? Kostenlose Rücksendung. Kein Vertrag, kein Risiko.' },
    { q: 'Wie viel Platz braucht das Display?', a: 'Das D18 ist 34×34 cm — passt auf jede Kassentheke. Das D21 ist 45×35 cm für mehr Farbauswahl. Beides auf 0,2m².' },
    { q: 'Muss mein Team geschult werden?', a: 'Ein 5-Minuten-Video reicht. Der FIREBALL verkauft sich über die Farbauswahl — Ihr Team muss ihn nicht erklären, nur zeigen.' },
    { q: 'Was, wenn bestimmte Farben schnell ausgehen?', a: 'Nachbestellung per App oder E-Mail. Einzelne Farben oder komplette Nachfüll-Sets. Lieferung in 3–5 Werktagen.' },
    { q: 'Konkurriert der FIREBALL mit meinem Schmuck-Sortiment?', a: 'Nein. Der FIREBALL ist Impulskauf am POS, nicht Schmuck in der Vitrine. Preispunkt 39,90–49,90€ spricht auch Begleitpersonen an.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Modeboutiquen — Der Impulskauf, den Kundinnen sammeln</title>
  <meta name="description" content="FIREBALL Display für Ihre Boutique: 0,2m², handgefertigter Designerschmuck, 280+ Farben. 4 Wochen kostenlos testen." />
</svelte:head>

<PriceGate bind:unlocked bind:showInput={showPwModal} />
<Navbar dark={true} />

<!-- ███ 1. HERO: PROBLEM-CENTRIC + CLEAR VALUE PROP ███ -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/1.jpeg" alt="FIREBALL Lifestyle" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(160deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.8) 40%, rgba(26,60,64,0.35) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="max-width:640px;">
      <!-- Pain validation first -->
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1.5rem;">Für Modeboutiquen & Concept Stores</p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.4rem,5vw,3.5rem); font-weight:700; color:var(--white); line-height:1.08; margin:0 0 1.5rem;">
        Ein Impulskauf, den Ihre Kundinnen <span style="color:var(--gold);">immer wieder</span> machen.
      </h1>
      <!-- Outcome-focused subheadline, not feature description -->
      <p class="animate-fade-up delay-200" style="font-size:1.15rem; color:rgba(255,255,255,0.75); line-height:1.7; margin-bottom:2.5rem;">
        Kundinnen kaufen nicht ein Paar — sie sammeln 30, 50, über 100 verschiedene Farben. Ein Display auf 0,2m² Ihrer Kassentheke verwandelt Laufkundschaft in Stammkundinnen. Ohne Beratungsaufwand.
      </p>
      <!-- Single CTA — friction reduction -->
      <a href="#kontakt" class="animate-fade-up delay-300 btn-primary" style="font-size:1rem; padding:1rem 2.5rem;">
        Kostenloses Probedisplay anfordern →
      </a>
      <p class="animate-fade-up delay-300" style="color:rgba(255,255,255,0.35); font-size:0.8rem; margin-top:0.75rem;">4 Wochen testen · Kein Vertrag · Kein Risiko</p>
    </div>
  </div>
</section>

<!-- ███ 2. TRUST BAR: QUANTIFIED PROOF ███ -->
<section style="background:var(--teal); padding:1.5rem 2rem; border-bottom:1px solid rgba(255,255,255,0.08);">
  <div style="max-width:900px; margin:0 auto; display:flex; justify-content:center; gap:3rem; flex-wrap:wrap;">
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">30+</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Jahre am Markt</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">280+</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Farbvarianten</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Ø 2/Tag</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Verkäufe pro Display</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">0,2m²</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Platzbedarf</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Handmade</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Eigene Manufaktur</span></div>
  </div>
</section>

<!-- ███ 3. PROBLEM → SOLUTION (Feature-to-Benefit) ███ -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <div>
      <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.15em; text-transform:uppercase; margin-bottom:0.75rem;">Das Problem</p>
      <h2 style="font-size:clamp(1.5rem,3vw,2rem); color:var(--teal); margin:0 0 1rem; line-height:1.2;">Ihre Kassenzone verkauft unter Wert.</h2>
      <p style="font-size:0.95rem; color:var(--gray-500); line-height:1.75; margin-bottom:2rem;">
        Die wertvollsten Quadratmeter Ihres Stores — direkt an der Kasse — werden oft mit Kleingeld-Artikeln oder gar nichts bespielt. Dabei ist genau hier der Moment, in dem Kundinnen offen für einen letzten Impuls sind.
      </p>
      <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.15em; text-transform:uppercase; margin-bottom:0.75rem;">Die Lösung</p>
      <h3 style="font-size:1.3rem; color:var(--teal); margin:0 0 1rem;">Ein Produkt, das sich selbst verkauft — und Kundinnen zurückbringt.</h3>
      <div style="display:flex; flex-direction:column; gap:1rem;">
        <div style="padding-left:1.25rem; border-left:3px solid var(--gold);">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Stammkunden-Effekt:</strong> Kundinnen sammeln 30–100+ Farben. Wer einmal kauft, kommt wieder. Garantiert.</p>
        </div>
        <div style="padding-left:1.25rem; border-left:3px solid var(--gold);">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Null Aufwand:</strong> Die Frage ist nicht „ob?", sondern „welche Farbe?". Kein Erklären, kein Beraten.</p>
        </div>
        <div style="padding-left:1.25rem; border-left:3px solid var(--gold);">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Empfehlungs-Wachstum:</strong> Kundinnen bekommen Komplimente und verschenken den FIREBALL. Organische Neukundinnen.</p>
        </div>
      </div>
    </div>
    <img src="/img/13.jpeg" alt="Model mit FIREBALL Ohrring" style="width:100%;" />
  </div>
</section>

<!-- ███ 4. SOCIAL PROOF (Quantified) ███ -->
<section style="background:var(--white); padding:4rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.15em; text-transform:uppercase; text-align:center; margin-bottom:0.75rem;">Getestete Ergebnisse</p>
    <h2 style="font-size:1.6rem; color:var(--teal); text-align:center; margin:0 0 2.5rem;">Was bisherige Partner berichten</h2>
    <div style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:2rem;">
      <div style="background:var(--cream); padding:2rem; text-align:center;">
        <div class="stat-number" style="font-size:2.2rem; margin-bottom:0.5rem;">Ø 2/Tag</div>
        <p style="font-size:0.85rem; color:var(--gray-500); margin:0; line-height:1.5;">Durchschnittliche Verkäufe pro Display in Teststellungen</p>
      </div>
      <div style="background:var(--cream); padding:2rem; text-align:center;">
        <div class="stat-number" style="font-size:2.2rem; margin-bottom:0.5rem;">3,8 max</div>
        <p style="font-size:0.85rem; color:var(--gray-500); margin:0; line-height:1.5;">Spitzenwert Verkäufe/Tag bei optimaler Platzierung</p>
      </div>
      <div style="background:var(--cream); padding:2rem; text-align:center;">
        <div class="stat-number" style="font-size:2.2rem; margin-bottom:0.5rem;">30+ Jahre</div>
        <p style="font-size:0.85rem; color:var(--gray-500); margin:0; line-height:1.5;">Jedes Jahr der meistverkaufte Artikel. Mit Abstand.</p>
      </div>
    </div>
    <p style="color:var(--gray-500); text-align:center; font-size:0.85rem; font-style:italic; margin-top:2rem; line-height:1.6;">
      „Erfolgsfaktoren sind Frequenz (Lage im Shop) und Commitment des Teams. Positionierung: Kassentheke."
    </p>
  </div>
</section>

<!-- ███ 5. PRODUCT SHOWCASE (Workflow visual) ███ -->
<section style="padding:0;"><img src="/img/9.jpeg" alt="FIREBALL POS Farbauswahl" style="width:100%; display:block;" /></section>

<section style="background:var(--teal); padding:4rem 2rem;">
  <div style="max-width:900px; margin:0 auto; text-align:center;">
    <h2 style="color:var(--white); font-size:1.6rem; margin:0 0 1rem;">Vom „ob?" zu „welche Farbe?"</h2>
    <p style="color:rgba(255,255,255,0.6); font-size:1rem; line-height:1.7; max-width:650px; margin:0 auto;">
      Es ist geübtes Verhalten, vor einer großen Farbauswahl zu stehen und einzutauchen. Kundinnen möchten ihre Farbe suchen, jagen, entdecken und finden. Nur dann wird der FIREBALL ein Lieblingsstück.
    </p>
  </div>
</section>

<!-- ███ 6. PRICING — BLURRED WITH INLINE UNLOCK ███ -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.15em; text-transform:uppercase; text-align:center; margin-bottom:0.5rem;">Displays & Konditionen</p>
    <h2 style="font-size:1.6rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Zwei Optionen — offen für Anpassungen</h2>

    <!-- Price content wrapper with blur + overlay -->
    <div style="position:relative;">
      <!-- The actual price content -->
      <div style="{unlocked ? '' : 'filter:blur(6px);user-select:none;pointer-events:none;'}transition:filter 0.4s ease;">
        <img src="/img/5.jpeg" alt="FIREBALL Displays" style="width:100%; margin-bottom:2rem;" />
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
          <div style="background:var(--teal); padding:2rem; color:var(--white);">
            <h3 style="color:var(--gold); font-size:1.2rem; margin:0 0 1rem;">D21 Display Black</h3>
            <p style="opacity:0.7; font-size:0.9rem; margin:0 0 0.5rem;">45 × 35 × 35 cm</p>
            <p style="opacity:0.7; font-size:0.9rem; margin:0 0 0.5rem;">21 SKU / 63 Stück · 15 Farben / 2 Größen</p>
            <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.3rem; margin:1.5rem 0 0;">WS 1.174€ · RRP 3.054€</p>
          </div>
          <div style="background:var(--white); padding:2rem; border:1px solid var(--gray-200);">
            <h3 style="color:var(--teal); font-size:1.2rem; margin:0 0 1rem;">D18 Display White</h3>
            <p style="color:var(--gray-500); font-size:0.9rem; margin:0 0 0.5rem;">34 × 34 × 21 cm</p>
            <p style="color:var(--gray-500); font-size:0.9rem; margin:0 0 0.5rem;">18 SKU / 45 Stück · 9 Farben / 2 Größen</p>
            <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.3rem; margin:1.5rem 0 0;">WS 931,50€ · RRP 2.424,60€</p>
          </div>
        </div>
      </div>

      <!-- Unlock overlay — positioned ON the blurred content -->
      {#if !unlocked}
        <div style="position:absolute; inset:0; display:flex; align-items:center; justify-content:center; z-index:10;">
          <button onclick={() => showPwModal = true} style="
            padding:1rem 2.5rem; background:var(--gold); color:var(--teal);
            border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif;
            font-size:1rem; font-weight:700; letter-spacing:0.05em;
            box-shadow:0 8px 32px rgba(0,0,0,0.2);
            display:flex; align-items:center; gap:0.6rem;
            transition:transform 0.2s, box-shadow 0.2s;
          ">
            🔒 Preise freischalten
          </button>
        </div>
      {/if}
    </div>
  </div>
</section>

<!-- ███ 7. VARIANTEN VISUAL ███ -->
<section style="padding:0;"><img src="/img/3.jpeg" alt="FIREBALL Varianten Übersicht" style="width:100%; display:block;" /></section>

<!-- ███ 8. HOW IT WORKS (Simplified steps) ███ -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:900px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.15em; text-transform:uppercase; text-align:center; margin-bottom:0.5rem;">So funktioniert es</p>
    <h2 style="font-size:1.6rem; text-align:center; color:var(--teal); margin:0 0 3rem;">In 3 Schritten zum Display-Partner</h2>
    <div style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:2rem;">
      <div style="text-align:center;">
        <div style="width:56px; height:56px; border-radius:50%; background:var(--gold); display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:var(--teal); font-size:1.2rem; margin:0 auto 1rem;">1</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Anfragen</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin:0;">Formular ausfüllen. In 24h erhalten Sie Factsheet, Farbkatalog und Preisliste.</p>
      </div>
      <div style="text-align:center;">
        <div style="width:56px; height:56px; border-radius:50%; background:var(--gold); display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:var(--teal); font-size:1.2rem; margin:0 auto 1rem;">2</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Testen</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin:0;">Fertig bestücktes Display auf Ihre Theke. 4 Wochen testen. Wir begleiten Sie.</p>
      </div>
      <div style="text-align:center;">
        <div style="width:56px; height:56px; border-radius:50%; background:var(--gold); display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:var(--teal); font-size:1.2rem; margin:0 auto 1rem;">3</div>
        <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.5rem;">Entscheiden</h4>
        <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin:0;">Zahlen auswerten. Funktioniert? Festbestellung. Nicht? Display zurück — kostenlos.</p>
      </div>
    </div>
  </div>
</section>

<!-- ███ 9. OBJECTION HANDLING (FAQ) ███ -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:700px; margin:0 auto;">
    <h2 style="font-size:1.4rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Häufige Fragen</h2>
    {#each faqs as faq}
      <details style="margin-bottom:1rem; background:var(--white); border:1px solid var(--gray-200);">
        <summary style="padding:1rem 1.25rem; cursor:pointer; font-weight:600; font-size:0.95rem; color:var(--teal); list-style:none; display:flex; justify-content:space-between; align-items:center;">
          {faq.q}
          <span style="color:var(--gold); font-size:1.2rem; flex-shrink:0; margin-left:1rem;">+</span>
        </summary>
        <div style="padding:0 1.25rem 1.25rem;">
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin:0;">{faq.a}</p>
        </div>
      </details>
    {/each}
  </div>
</section>

<!-- ███ 10. FINAL CTA + MINIMAL FORM ███ -->
<section id="kontakt" style="background:var(--teal); padding:5rem 2rem;">
  <div style="max-width:520px; margin:0 auto; text-align:center;">
    <p class="fireball-brand" style="color:var(--gold); font-size:1.4rem; margin-bottom:1rem;">FIREBALL</p>
    <h2 style="color:var(--white); font-size:clamp(1.5rem,3vw,2rem); margin:0 0 0.75rem;">Probedisplay anfordern</h2>
    <p style="color:rgba(255,255,255,0.5); margin-bottom:2rem; font-size:0.95rem;">4 Wochen testen. Kein Vertrag. Kein Risiko. Passt nicht? Wir holen es zurück.</p>
    <LeadForm channel="boutiquen" ctaText="Probedisplay anfordern" brancheOptions={['Modeboutique', 'Concept Store', 'Multi-Brand Store', 'Flagship Store']} />
  </div>
</section>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 FIREBALL by VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  details[open] summary span { transform: rotate(45deg); }
  details summary span { transition: transform 0.2s; display:inline-block; }
  @media (max-width: 768px) {
    section > div[style*="grid-template-columns: 1fr 1fr 1fr"] { grid-template-columns: 1fr !important; }
    section > div[style*="grid-template-columns:1fr 1fr 1fr"] { grid-template-columns: 1fr !important; }
    section > div > div[style*="grid-template-columns:1fr 1fr"] { grid-template-columns: 1fr !important; }
    section > div[style*="grid-template-columns:1fr 1fr;"] { grid-template-columns: 1fr !important; }
  }
</style>
