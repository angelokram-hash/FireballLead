<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let showPwModal = $state(false);
  const faqs = [
    { q: 'Passt der FIREBALL wirklich ins Beauty-Regal?', a: 'Ja — der Stick sieht aus und fühlt sich an wie ein Lippenstift. Ihre Kundinnen greifen instinktiv danach. Das Format ist vertraut, das Produkt neu.' },
    { q: 'Funktioniert das ohne Schmuck-Beratung?', a: 'Absolut. Die Farbauswahl ist geübtes Verhalten Ihrer Kundinnen — sie wählen selbstständig. Ihr Team muss nur zeigen, nicht erklären.' },
    { q: 'Was ist der "Lipstick Effect"?', a: 'In wirtschaftlich unsicheren Zeiten steigt der Absatz für Beauty-Produkte und erschwingliche Luxusartikel. FIREBALL passt mit 39,90–49,90€ perfekt in diese Kategorie.' },
    { q: 'Wie funktioniert die Nachbestellung?', a: 'Per App oder E-Mail. Einzelne Farben oder komplette Sets. Lieferung in 3–5 Werktagen.' },
    { q: 'Gibt es saisonale Neuheiten?', a: 'Jedes Quartal neue Farben, passend zu Beauty-Trends. Plus Geschenk-Sets für Muttertag, Valentinstag, Weihnachten.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Parfümerien — Wie mein Lippenstift, immer dabei</title>
  <meta name="description" content="FIREBALL im Stick-Format: Handgefertigter Designerschmuck, der ins Beauty-Regal passt. 3 kostenlose Muster-Sticks anfordern." />
</svelte:head>
<PriceGate bind:unlocked bind:showInput={showPwModal} />
<Navbar dark={true} />

<!-- HERO -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;"><img src="/img/14.jpeg" alt="FIREBALL Lifestyle" style="width:100%; height:100%; object-fit:cover;" /><div style="position:absolute; inset:0; background:linear-gradient(160deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.8) 40%, rgba(26,60,64,0.35) 100%);"></div></div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="max-width:640px;">
      <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1.5rem;">Für Parfümerien & Beauty-Fachhandel</p>
      <h1 class="animate-fade-up delay-100" style="font-size:clamp(2.4rem,5vw,3.5rem); font-weight:700; color:var(--white); line-height:1.08; margin:0 0 1.5rem;">Wie mein Lippenstift, <span style="color:var(--gold);">immer dabei.</span></h1>
      <p class="animate-fade-up delay-200" style="font-size:1.15rem; color:rgba(255,255,255,0.75); line-height:1.7; margin-bottom:2.5rem;">Der FIREBALL Stick passt ins Beauty-Regal wie ein Lippenstift. Vertrautes Format, neues Produkt. Ihre Kundinnen greifen danach, bevor Sie ein Wort sagen müssen.</p>
      <a href="#kontakt" class="animate-fade-up delay-300 btn-primary" style="font-size:1rem; padding:1rem 2.5rem;">3 kostenlose Muster-Sticks anfordern →</a>
      <p class="animate-fade-up delay-300" style="color:rgba(255,255,255,0.35); font-size:0.8rem; margin-top:0.75rem;">Anfassen · Neben Lippenstifte legen · Kundinnen zeigen</p>
    </div>
  </div>
</section>

<!-- TRUST BAR -->
<section style="background:var(--teal); padding:1.5rem 2rem; border-bottom:1px solid rgba(255,255,255,0.08);">
  <div style="max-width:900px; margin:0 auto; display:flex; justify-content:center; gap:3rem; flex-wrap:wrap;">
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">280+</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Farben</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">0 Abfall</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Stick = Verpackung + Etui</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Ø 2/Tag</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Verkäufe pro Display</span></div>
    <div style="text-align:center;"><span class="stat-number" style="font-size:1.4rem;">Handmade</span><span style="display:block; color:rgba(255,255,255,0.35); font-size:0.7rem; margin-top:0.2rem;">Echte Kristallsteine</span></div>
  </div>
</section>

<!-- PROBLEM → SOLUTION -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:center;">
    <img src="/img/10.jpeg" alt="FIREBALL Stick Verpackung" style="width:100%;" />
    <div>
      <h2 style="font-size:1.8rem; color:var(--teal); margin:0 0 1.5rem;">Der Stick = Präsentation + Verpackung + Case</h2>
      <div style="display:flex; flex-direction:column; gap:1.25rem;">
        <div style="padding-left:1.25rem; border-left:3px solid #9B4D6E;">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Für die Kundin:</strong> Form und Handling sind neu, aber vertraut. Wie der Lippenstift — immer dabei. Und vielleicht eine zweite Farbe in der Handtasche.</p>
        </div>
        <div style="padding-left:1.25rem; border-left:3px solid #9B4D6E;">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Für Sie als Partner:</strong> Leichtes Handling am POS und in der Logistik. Kein Umverpacken.</p>
        </div>
        <div style="padding-left:1.25rem; border-left:3px solid #9B4D6E;">
          <p style="font-size:0.9rem; color:var(--gray-700); line-height:1.6; margin:0;"><strong>Für uns alle:</strong> Kein Abfall. Der Stick ist alles in einem.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- LIPSTICK EFFECT -->
<section style="padding:0;"><img src="/img/11.jpeg" alt="Lipstick Effect" style="width:100%; display:block;" /></section>

<!-- POS FARBAUSWAHL -->
<section style="background:var(--white); padding:4rem 2rem;">
  <div style="max-width:900px; margin:0 auto; text-align:center;">
    <h2 style="font-size:1.6rem; color:var(--teal); margin:0 0 1rem;">Vom „ob?" zu „welche?"</h2>
    <p style="color:var(--gray-500); max-width:600px; margin:0 auto 2rem; line-height:1.7;">Kundinnen möchten ihre Farbe suchen, jagen, entdecken und finden. Die Farbauswahl ist geübtes Verhalten — genau wie bei Nagellack oder Lippenstift.</p>
    <img src="/img/9.jpeg" alt="FIREBALL POS Farbauswahl" style="width:100%;" />
  </div>
</section>

<!-- PRICING — BLURRED -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.5rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Displays & Konditionen</h2>
    <div style="position:relative;">
      <div style="{unlocked ? '' : 'filter:blur(6px);user-select:none;pointer-events:none;'}transition:filter 0.4s;">
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:2rem;">
          <div style="background:var(--teal); padding:2rem; color:var(--white);"><h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">D21 Display Black</h3><p style="opacity:0.7; font-size:0.85rem; margin:0;">45×35×35cm · 21 SKU / 63 PCS</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 1.174€ · RRP 3.054€</p></div>
          <div style="background:var(--white); padding:2rem; border:1px solid var(--gray-200);"><h3 style="color:var(--teal); font-size:1.1rem; margin:0 0 0.5rem;">D18 Display White</h3><p style="color:var(--gray-500); font-size:0.85rem; margin:0;">34×34×21cm · 18 SKU / 45 PCS</p><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.2rem; margin:1rem 0 0;">WS 931,50€ · RRP 2.424,60€</p></div>
        </div>
      </div>
      {#if !unlocked}<div style="position:absolute; inset:0; display:flex; align-items:center; justify-content:center; z-index:10;"><button onclick={() => showPwModal = true} style="padding:1rem 2.5rem; background:var(--gold); color:var(--teal); border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif; font-size:1rem; font-weight:700; box-shadow:0 8px 32px rgba(0,0,0,0.2); display:flex; align-items:center; gap:0.6rem;">🔒 Preise freischalten</button></div>{/if}
    </div>
  </div>
</section>

<!-- FAQ -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:700px; margin:0 auto;">
    <h2 style="font-size:1.4rem; text-align:center; color:var(--teal); margin:0 0 2.5rem;">Häufige Fragen</h2>
    {#each faqs as faq}<details style="margin-bottom:1rem; background:var(--cream); border:1px solid var(--gray-200);"><summary style="padding:1rem 1.25rem; cursor:pointer; font-weight:600; font-size:0.95rem; color:var(--teal); list-style:none; display:flex; justify-content:space-between; align-items:center;">{faq.q}<span style="color:var(--gold); font-size:1.2rem; flex-shrink:0; margin-left:1rem;">+</span></summary><div style="padding:0 1.25rem 1.25rem;"><p style="font-size:0.9rem; color:var(--gray-500); line-height:1.7; margin:0;">{faq.a}</p></div></details>{/each}
  </div>
</section>

<!-- FINAL CTA -->
<section id="kontakt" style="background:var(--teal); padding:5rem 2rem;">
  <div style="max-width:520px; margin:0 auto; text-align:center;">
    <p class="fireball-brand" style="color:var(--gold); font-size:1.4rem; margin-bottom:1rem;">FIREBALL</p>
    <h2 style="color:var(--white); font-size:1.8rem; margin:0 0 0.75rem;">3 Sticks. Kostenlos. Sofort testen.</h2>
    <p style="color:rgba(255,255,255,0.5); margin-bottom:2rem;">Anfassen, neben Ihre Lippenstifte legen, Kundinnen zeigen.</p>
    <LeadForm channel="parfuemerien" ctaText="Muster-Sticks anfordern" brancheOptions={['Parfümerie (Einzelhandel)', 'Parfümerie-Kette', 'Beauty-Fachhandel', 'Kosmetikinstitut']} />
  </div>
</section>
<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;"><p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 FIREBALL by VICI Vertrieb Deutschland GmbH</p></footer>
<style>details[open] summary span { transform: rotate(45deg); } details summary span { transition: transform 0.2s; display:inline-block; } @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }</style>
