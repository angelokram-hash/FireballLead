<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let blur = $derived(unlocked ? '' : 'filter:blur(5px);user-select:none;');
  const steps = [
    { t: 'Tag 1', title: 'Muster-Paket anfordern', desc: 'Formular ausfüllen → 3 Muster-Sticks in verschiedenen Farben kostenlos per Express.', tasks: ['Beauty-spezifisches Factsheet per E-Mail', 'Stick-Lifestyle-Bilder neben Lippenstiften und Parfums', 'Preisliste für Beauty-Fachhandel', 'Saisonale Farbempfehlungen'], tip: 'Erwähnen Sie Ihr Sortiment — wir empfehlen Farben, die zu Ihrem Beauty-Angebot passen.' },
    { t: 'Tag 2–4', title: '3 Muster-Sticks testen', desc: 'Sticks auspacken, anfassen, neben Ihre Lippenstifte legen. Stammkundinnen zeigen und Reaktion beobachten.', tasks: ['Stick-Format neben Lippenstifte legen — passt ins Bild?', '2–3 Stammkundinnen zeigen und Feedback einholen', 'Stick öffnen: Ohrring entnehmen, anschauen, zurücklegen', 'Kurzanleitung für Ihr Team beiliegend (1 Seite)'], tip: 'Häufigste Reaktion: Kundinnen greifen instinktiv zum Stick — das Format ist so vertraut wie ein Lippenstift.' },
    { t: 'Tag 5–7', title: 'Beratung & Display-Empfehlung', desc: 'Call (15 Min): Display-Auswahl, Platzierung neben Lippenstiften, Farbkonzept für Ihre Parfümerie.', tasks: ['D18 (neben Kasse) oder D21 (Standalone)?', 'Platzierung: Neben Lippenstiften, Kassentresen, Schaufenster?', 'Farbkonzept: 9–15 Farben für Ihre Kundschaft', 'Optional: Display in Ihrer CI-Farbe (ab 10 Stück)'], tip: 'Beste Position: direkt neben Lippen- oder Nagelprodukten. Farbauswahl ist geübtes Verhalten.' },
    { t: 'Woche 2–6', title: 'Display aufstellen & Testphase', desc: 'Fertig bestücktes Display + 5-Min Team-Briefing. 4 Wochen testen mit Check-ins.', tasks: ['Display auspacken, hinstellen, fertig', 'Team-Argument: „Wie ein Lippenstift — immer dabei, immer anders"', 'Wöchentliche Check-ins: Farben, Stückzahl, Kundenfeedback', 'Nachbestell-Check nach 3 Wochen'], tip: 'Kundinnen, die Lippenstift kaufen, nehmen häufig auch einen farblich passenden FIREBALL mit.' },
    { t: 'Ab Woche 7', title: 'Partnerschaft & Beauty-Sortiment', desc: 'Festbestellung, saisonale Neuheiten, Cross-Selling mit Ketten und Ringen.', tasks: ['Nachbestellung per App oder E-Mail', 'Saisonale Farben passend zu Beauty-Trends', 'Cross-Selling: Ketten, Ringe im FIREBALL-Design', 'Aktionen: Muttertag-Sets, Valentinstag-Bundles'], tip: '„Farbe des Monats" im Schaufenster generiert Neugier und Wiederkäufe.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Parfümerien — Wie mein Lippenstift, immer dabei</title>
  <meta name="description" content="FIREBALL Schmuck im Stick-Format: Passt ins Beauty-Regal wie ein Lippenstift. 3 kostenlose Muster-Sticks anfordern." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/14.jpeg" alt="FIREBALL Lifestyle" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(135deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.75) 50%, rgba(26,60,64,0.3) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="display:grid; grid-template-columns:1fr 420px; gap:4rem; align-items:center;">
      <div>
        <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">Für Parfümerien & Beauty-Fachhandel</p>
        <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.2rem,4.5vw,3.2rem); font-weight:700; color:var(--white); line-height:1.1; margin:0 0 1.5rem;">Wie mein Lippenstift, <span style="color:var(--gold);">immer dabei.</span></h1>
        <p class="animate-fade-up delay-200" style="font-size:1.1rem; color:rgba(255,255,255,0.7); line-height:1.7; margin-bottom:1rem;">Der FIREBALL Stick passt ins Beauty-Regal wie ein Lippenstift. Vertrautes Format, neues Produkt. Und wenn die Konjunktur stockt, steigt der Absatz für Beauty-Produkte — der „Lipstick Effect".</p>
        <p class="animate-fade-up delay-200" style="font-size:1rem; font-style:italic; color:rgba(255,255,255,0.5); margin-bottom:2rem;">„...wie mein Lippenstift, immer dabei."</p>
        <div class="animate-fade-up delay-300" style="display:flex; gap:2.5rem;">
          <div><div class="stat-number" style="font-size:2rem;{blur}">39,90€</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">RPR Small</div></div>
          <div><div class="stat-number" style="font-size:2rem;">280+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Farben</div></div>
          <div><div class="stat-number" style="font-size:2rem;">0 Abfall</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Stick = Verpackung</div></div>
        </div>
      </div>
      <div class="animate-fade-up delay-300" style="background:rgba(255,255,255,0.06); backdrop-filter:blur(8px); border:1px solid rgba(255,255,255,0.1); padding:2rem;">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">3 Muster-Sticks kostenlos</h3>
        <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Anfassen, testen, Kundinnen zeigen — kein Risiko.</p>
        <LeadForm channel="parfuemerien" ctaText="Muster-Sticks anfordern" brancheOptions={['Parfümerie (Einzelhandel)', 'Parfümerie-Kette', 'Beauty-Fachhandel', 'Kosmetikinstitut']} />
      </div>
    </div>
  </div>
</section>

<!-- DER STICK -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <div>
      <h2 style="font-size:1.8rem; color:var(--teal); margin:0 0 1.5rem;">Der Stick = Präsentation + Verpackung + Case</h2>
      <div style="display:flex; flex-direction:column; gap:1.25rem;">
        <div style="padding-left:1rem; border-left:3px solid #9B4D6E;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Für die Kundin</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Form und Handling sind neu, aber vertraut. Der FIREBALL wird wie der Lippenstift selbstverständlich immer dabei. Und vielleicht noch eine zweite Farbe in der Handtasche.</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #9B4D6E;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Für Sie als Partner</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Leichtes Handling am POS und in der Logistik. Kein Auspacken, kein Umverpacken.</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #9B4D6E;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Für uns alle</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Kein Abfall. Der Stick ist Präsentation, Verpackung und Etui in einem.</p>
        </div>
      </div>
    </div>
    <img src="/img/10.jpeg" alt="FIREBALL Stick Verpackung" style="width:100%; border:1px solid var(--gray-200);" />
  </div>
</section>

<!-- LIPSTICK EFFECT -->
<section style="padding:0;"><img src="/img/11.jpeg" alt="Lipstick Effect" style="width:100%; display:block;" /></section>

<!-- POS FARBAUSWAHL -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 0.5rem; color:var(--teal);">Vom „ob?" zu „welche?"</h2>
    <p style="color:var(--gray-500); text-align:center; max-width:650px; margin:0 auto 2rem; line-height:1.7;">Es ist geübtes Verhalten, vor einer großen Farbauswahl zu stehen: „Für welche Farbe soll ich mich entscheiden?" Kundinnen möchten ihre Farbe suchen, jagen, entdecken und finden.</p>
    <img src="/img/9.jpeg" alt="FIREBALL POS Farbauswahl" style="width:100%; border:1px solid var(--gray-200);" />
  </div>
</section>

<!-- DISPLAYS -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.5rem; text-align:center; margin:0 0 2rem; color:var(--teal);">Displays — offen für Anpassungen</h2>
    <img src="/img/5.jpeg" alt="FIREBALL Displays" style="width:100%; border:1px solid var(--gray-200);" />
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem; margin-top:2rem;">
      <div style="background:var(--teal); padding:1.5rem; color:var(--white);">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">D21 Display Black</h3>
        <p style="opacity:0.7; font-size:0.85rem; margin:0;{blur}">45×35×35cm · 21 SKU / 63 PCS · WS 1.174€</p>
      </div>
      <div style="background:var(--white); padding:1.5rem; border:1px solid var(--gray-200);">
        <h3 style="color:var(--teal); font-size:1.1rem; margin:0 0 0.5rem;">D18 Display White</h3>
        <p style="color:var(--gray-500); font-size:0.85rem; margin:0;{blur}">34×34×21cm · 18 SKU / 45 PCS · WS 931,50€</p>
      </div>
    </div>
  </div>
</section>

<!-- STEPS -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 3rem;">So starten Sie — Schritt für Schritt</h2>
    {#each steps as step, i}
      <div style="display:grid; grid-template-columns:56px 1fr; gap:1.25rem;">
        <div style="display:flex; flex-direction:column; align-items:center;">
          <div style="width:44px; height:44px; border-radius:50%; background:#9B4D6E; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1rem; z-index:2;">{i+1}</div>
          {#if i < steps.length - 1}<div style="width:2px; flex:1; background:var(--gray-200);"></div>{/if}
        </div>
        <div style="padding-bottom:2rem;">
          <div style="background:var(--cream); border:1px solid var(--gray-200); border-left:3px solid #9B4D6E; padding:1.25rem;">
            <span style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#9B4D6E; text-transform:uppercase;">{step.t}</span>
            <h3 style="font-size:1.05rem; color:var(--teal); margin:0.2rem 0 0.4rem;">{step.title}</h3>
            <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin-bottom:0.75rem;">{step.desc}</p>
            {#each step.tasks as task}<div style="display:flex; gap:0.4rem; margin-bottom:0.3rem;"><span style="color:#9B4D6E; font-size:0.8rem;">✓</span><span style="font-size:0.8rem; color:var(--gray-700); line-height:1.4;{task.includes('€') ? blur : ''}">{task}</span></div>{/each}
            {#if step.tip}<div style="margin-top:0.75rem; padding:0.6rem; background:rgba(155,77,110,0.06); border-left:2px solid #9B4D6E;"><p style="font-size:0.75rem; color:var(--teal); margin:0;{step.tip?.includes('€') ? blur : ''}"><strong>Tipp:</strong> {step.tip}</p></div>{/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<!-- CTA -->
<section style="background:var(--teal); padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">3 Sticks. Kostenlos. Sofort testen.</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Anfassen, neben Ihre Lippenstifte legen, Kundinnen zeigen.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Muster-Paket anfordern →</a>
</section>

<PriceGate bind:unlocked />

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }
</style>
