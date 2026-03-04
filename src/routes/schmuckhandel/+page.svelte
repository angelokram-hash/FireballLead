<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import LeadForm from '$lib/components/LeadForm.svelte';
  import PriceGate from '$lib/components/PriceGate.svelte';
  let unlocked = $state(false);
  let blur = $derived(unlocked ? '' : 'filter:blur(5px);user-select:none;');
  const steps = [
    { t: 'Tag 1', title: 'Produktivitätsrechner anfordern', desc: 'Formular ausfüllen → interaktiver Rechner: Ihre Frequenz = Ihr Jahresumsatz.', tasks: ['Interaktiver Produktivitätsrechner (Excel/Online)', 'Factsheet: FIREBALL ergänzt, ersetzt nicht', 'Farbkatalog mit Kristallstein-Details', 'Preisliste mit Staffel-Rabatten für Fachhandel'], tip: 'Schon 1 Verkauf/Tag = ca. 15.000€ Jahresumsatz auf 0,2m².' },
    { t: 'Tag 3–5', title: 'Fachgespräch unter Profis', desc: 'Telefonat oder Besuch (20 Min). Sortiment-Einordnung, Größen, Finishes, Cross-Selling.', tasks: ['Wo liegt der FIREBALL preislich und stilistisch?', 'FIREBALL als Impulsware auf der Theke, nicht im Schaufenster', 'Classic (21mm, 49,90€) und Small (16mm, 39,90€)', 'Brass (matt) vs. Shiny Golden (glänzend, limitiert)', 'Cross-Selling Pipeline: Ketten, Ringe, Armbänder'], tip: 'Für Juweliere: Start mit D18 in gedeckten Farbtönen passt zum gehobenen Umfeld.' },
    { t: 'Woche 2', title: 'Muster-Sticks zum Anfassen', desc: '3–5 Muster-Sticks per Express. Haptik, Kristallqualität, Verschluss prüfen. Stammkundinnen zeigen.', tasks: ['Haptik-Test: Gewicht, Kristallqualität, Verschluss', 'Stick-Verpackung testen: Öffnen, entnehmen, einsetzen', '5–10 Stammkundinnen zeigen und Feedback sammeln', 'Rückmeldung: Welche Farben und welches Finish?'], tip: 'Juweliere schätzen besonders die Shiny Golden Varianten — wirken hochwertiger.' },
    { t: 'Woche 3–8', title: 'Display aufstellen & testen', desc: 'Display auf die Theke. 4 Wochen Testbetrieb mit Benchmarks. Team: „Kennen Sie schon unseren FIREBALL?"', tasks: ['Ideale Position: Neben der Kasse, beim Warten', 'Farbkarte daneben: „Finden Sie Ihre Farbe"', 'Team: Nach Hauptverkauf → „Kennen Sie FIREBALL?"', 'Beobachten: Spontankauf oder gezielter Wiederkauf?'], tip: '2–3 offene Sticks neben dem Display — Kundinnen greifen eher zu.' },
    { t: 'Laufend', title: 'Partnerschaft & Cross-Selling', desc: 'Feste Partnerschaft mit Nachbestellung, neuen Farben, und der vollen Cross-Selling Pipeline.', tasks: ['Quartalsweise neue Farbkollektionen', 'Cross-Selling: Ketten, Ringe, Armbänder', 'Stammkunden-Aktion: „10 Farben → 11. zum halben Preis"', 'Partner-Exklusiv: Limitierte Farben nur für Fachhandel', 'Staffelkonditionen ab 10 Nachbestellungen/Jahr'], tip: 'Der FIREBALL wird zum Gesprächsöffner — Kundinnen kommen wegen der Farben und bleiben fürs Hauptsortiment.' },
  ];
</script>

<svelte:head>
  <title>FIREBALL für Juweliere — 30 Jahre Bestseller für Ihre Theke</title>
  <meta name="description" content="FIREBALL Designerschmuck: Handgefertigt, Kristallsteine, 30+ Jahre Bestseller. Produktivitätsrechner für Ihren Standort anfordern." />
</svelte:head>

<Navbar dark={true} />

<!-- HERO -->
<section style="position:relative; min-height:100vh; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0;">
    <img src="/img/8.jpeg" alt="FIREBALL Ohrring am Ohr" style="width:100%; height:100%; object-fit:cover;" />
    <div style="position:absolute; inset:0; background:linear-gradient(135deg, rgba(26,60,64,0.95) 0%, rgba(26,60,64,0.75) 50%, rgba(26,60,64,0.4) 100%);"></div>
  </div>
  <div style="position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:8rem 2rem 4rem; width:100%;">
    <div style="display:grid; grid-template-columns:1fr 420px; gap:4rem; align-items:center;">
      <div>
        <p class="animate-fade-up" style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.8rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:1rem;">Für Schmuck-Fachhandel & Juweliere</p>
        <h1 class="animate-fade-up delay-100" style="font-size:clamp(2rem,4vw,3rem); font-weight:700; color:var(--white); line-height:1.1; margin:0 0 1.5rem;">30 Jahre Bestseller. Jetzt auf <span style="color:var(--gold);">Ihrer Theke.</span></h1>
        <p class="animate-fade-up delay-200" style="font-size:1.05rem; color:rgba(255,255,255,0.7); line-height:1.7; margin-bottom:2rem;">Handgefertigte Ohrstecker mit echten Kristallsteinen. Ergänzt Ihr Kernsortiment als Impulsware auf der Theke — ohne Konkurrenz zu schaffen. Die Sammel-Eigenschaft macht aus Laufkundschaft Stammkunden.</p>
        <div class="animate-fade-up delay-300" style="display:flex; gap:2.5rem;">
          <div><div class="stat-number" style="font-size:2rem;">30+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Jahre Bestseller</div></div>
          <div><div class="stat-number" style="font-size:2rem;">21+</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Farbvarianten</div></div>
          <div><div class="stat-number" style="font-size:2rem;">2 Finishes</div><div class="stat-label" style="color:rgba(255,255,255,0.4);">Brass / Shiny Gold</div></div>
        </div>
      </div>
      <div class="animate-fade-up delay-300" style="background:rgba(255,255,255,0.06); backdrop-filter:blur(8px); border:1px solid rgba(255,255,255,0.1); padding:2rem;">
        <h3 style="color:var(--gold); font-size:1.1rem; margin:0 0 0.5rem;">Produktivitätsrechner anfordern</h3>
        <p style="color:rgba(255,255,255,0.5); font-size:0.85rem; margin-bottom:1.5rem;">Ihre Frequenz → Ihr möglicher Jahresumsatz. In 24 Stunden.</p>
        <LeadForm channel="schmuckhandel" ctaText="Rechner anfordern" brancheOptions={['Juwelier', 'Schmuck-Fachhandel', 'Schmuck-Atelier', 'Online + Stationär']} />
      </div>
    </div>
  </div>
</section>

<!-- SAMMELCHARAKTER -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto; display:grid; grid-template-columns:1fr 1fr; gap:3rem; align-items:center;">
    <img src="/img/8.jpeg" alt="FIREBALL Der Ohrring" style="width:100%; border:1px solid var(--gray-200);" />
    <div>
      <h2 style="font-size:1.6rem; color:var(--teal); margin:0 0 1.5rem;">Sammelschmuck = Stammkunden</h2>
      <div style="display:flex; flex-direction:column; gap:1.25rem;">
        <div style="padding-left:1rem; border-left:3px solid #6B5B73;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Sammelcharakter</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Kundinnen besitzen 30–100+ verschiedene Paare. Der FIREBALL ist ein Sammelschmuck, der aus Einmalkäuferinnen Stammkundinnen macht.</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #6B5B73;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Empfehlungs-Effekt</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Der FIREBALL ist kommunikativ ohne laut zu sein. Kundinnen bekommen Komplimente und verschenken ihn gerne.</p>
        </div>
        <div style="padding-left:1rem; border-left:3px solid #6B5B73;">
          <h4 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Täglicher Begleiter</h4>
          <p style="font-size:0.9rem; color:var(--gray-500); line-height:1.6; margin:0;">Für viele Kundinnen wird der FIREBALL zum täglichen Begleiter — wie ein Lippenstift, immer dabei.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- VARIANTEN + DISPLAYS -->
<section style="padding:0;"><img src="/img/3.jpeg" alt="FIREBALL Varianten" style="width:100%; display:block;" /></section>

<!-- CROSS SELLING -->
<section style="background:var(--white); padding:5rem 2rem;">
  <div style="max-width:1100px; margin:0 auto;">
    <h2 style="font-size:1.5rem; text-align:center; margin:0 0 2rem; color:var(--teal);">Cross-Selling Pipeline</h2>
    <img src="/img/4.jpeg" alt="FIREBALL Cross-Selling" style="width:100%; border:1px solid var(--gray-200);" />
    <p style="color:var(--gray-500); text-align:center; max-width:600px; margin:1.5rem auto 0; line-height:1.7;">Ketten, Ohrhänger, Ringe, Armbänder — das FIREBALL-Design als komplettes Sortiment für Ihren Fachhandel.</p>
  </div>
</section>

<!-- MODEL -->
<section style="padding:0;"><img src="/img/13.jpeg" alt="FIREBALL Model" style="width:100%; display:block;" /></section>

<!-- STEPS -->
<section style="background:var(--cream); padding:5rem 2rem;">
  <div style="max-width:800px; margin:0 auto;">
    <h2 style="font-size:1.8rem; text-align:center; margin:0 0 3rem;">So starten Sie — Schritt für Schritt</h2>
    {#each steps as step, i}
      <div style="display:grid; grid-template-columns:56px 1fr; gap:1.25rem;">
        <div style="display:flex; flex-direction:column; align-items:center;">
          <div style="width:44px; height:44px; border-radius:50%; background:#6B5B73; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1rem; z-index:2;">{i+1}</div>
          {#if i < steps.length - 1}<div style="width:2px; flex:1; background:var(--gray-200);"></div>{/if}
        </div>
        <div style="padding-bottom:2rem;">
          <div style="background:var(--white); border:1px solid var(--gray-200); border-left:3px solid #6B5B73; padding:1.25rem;">
            <span style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:#6B5B73; text-transform:uppercase;">{step.t}</span>
            <h3 style="font-size:1.05rem; color:var(--teal); margin:0.2rem 0 0.4rem;">{step.title}</h3>
            <p style="font-size:0.85rem; color:var(--gray-500); line-height:1.6; margin-bottom:0.75rem;">{step.desc}</p>
            {#each step.tasks as task}<div style="display:flex; gap:0.4rem; margin-bottom:0.3rem;"><span style="color:#6B5B73; font-size:0.8rem;">✓</span><span style="font-size:0.8rem; color:var(--gray-700); line-height:1.4;{task.includes('€') ? blur : ''}">{task}</span></div>{/each}
            {#if step.tip}<div style="margin-top:0.75rem; padding:0.6rem; background:rgba(107,91,115,0.05); border-left:2px solid #6B5B73;"><p style="font-size:0.75rem; color:var(--teal); margin:0;{step.tip?.includes('€') ? blur : ''}"><strong>Tipp:</strong> {step.tip}</p></div>{/if}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>

<!-- CTA -->
<section style="background:var(--teal); padding:4rem 2rem; text-align:center;">
  <h2 style="color:var(--white); font-size:1.5rem; margin:0 0 0.75rem;">30 Jahre Bestseller. Bereit für Ihre Theke?</h2>
  <p style="color:rgba(255,255,255,0.5); margin-bottom:1.5rem;">Fordern Sie Ihren individuellen Produktivitätsrechner an.</p>
  <a href="#" onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })} class="btn-primary">Produktivitätsrechner anfordern →</a>
</section>

<PriceGate bind:unlocked />

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH</p>
</footer>

<style>
  @media (max-width: 768px) { section > div[style*="grid-template-columns"] { grid-template-columns: 1fr !important; } }
</style>
