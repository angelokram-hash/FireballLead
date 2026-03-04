<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  let activeTab = $state('overview');
  const channels = [
    { slug: '/boutiquen', title: 'Modeboutiquen & Concept Stores', icon: '👗', color: '#8B5E3C', cta: 'Probedisplay', status: 'Live' },
    { slug: '/parfuemerien', title: 'Parfümerien & Beauty-Fachhandel', icon: '💄', color: '#9B4D6E', cta: 'Muster-Paket', status: 'Live' },
    { slug: '/kaufhaeuser', title: 'Kaufhäuser & Department Stores', icon: '🏬', color: '#2C5F7C', cta: 'ROI-Kalkulation', status: 'Live' },
    { slug: '/museumsshops', title: 'Museumsshops & Hotel-Boutiquen', icon: '🏛️', color: '#5C6B4E', cta: 'Lookbook', status: 'Live' },
    { slug: '/schmuckhandel', title: 'Schmuck-Fachhandel & Juweliere', icon: '💎', color: '#6B5B73', cta: 'Produktivitätsrechner', status: 'Live' },
  ];
  const toolStack = [
    { category: 'CRM & Leads', tools: [
      { name: 'HubSpot CRM', price: 'Free–45€', use: 'Lead-Erfassung, Pipeline, E-Mail-Automatisierung', p: 'Pflicht' },
      { name: 'Pipedrive', price: '14–99€', use: 'Sales-fokussiertes CRM (Alternative)', p: 'Optional' },
    ]},
    { category: 'Outreach & E-Mail', tools: [
      { name: 'Lemlist', price: '59–99€', use: 'Kalt-E-Mail Outreach mit Personalisierung', p: 'Empfohlen' },
      { name: 'Brevo', price: 'Free–25€', use: 'Newsletter & E-Mail-Marketing', p: 'Optional' },
    ]},
    { category: 'LinkedIn & Social', tools: [
      { name: 'Sales Navigator', price: '79–139€', use: 'Lead-Suche, InMail, Filter nach Branche', p: 'Pflicht' },
      { name: 'Waalaxy', price: 'Free–80€', use: 'LinkedIn-Outreach automatisieren', p: 'Empfohlen' },
    ]},
    { category: 'Paid Ads', tools: [
      { name: 'Google Ads', price: 'CPC', use: 'Intent-basiert: "Impulssortiment Einzelhandel"', p: 'Pflicht' },
      { name: 'Meta Ads', price: 'CPC', use: 'Instagram/Facebook: Awareness + Retargeting', p: 'Empfohlen' },
    ]},
    { category: 'Tracking', tools: [
      { name: 'GA4', price: 'Free', use: 'Traffic, Conversions, Landing Page Performance', p: 'Pflicht' },
      { name: 'Hotjar', price: 'Free–32€', use: 'Heatmaps, Session Recordings', p: 'Empfohlen' },
      { name: 'Looker Studio', price: 'Free', use: 'Dashboards & Performance-Reports', p: 'Empfohlen' },
    ]},
    { category: 'Hosting & Termine', tools: [
      { name: 'Vercel', price: 'Free–20$', use: 'Hosting dieser Landing Pages', p: 'Pflicht' },
      { name: 'Cal.com', price: 'Free–15$', use: 'Terminbuchung auf Landing Pages', p: 'Empfohlen' },
    ]},
    { category: 'Content & Design', tools: [
      { name: 'Canva Pro', price: '12€', use: 'Factsheets, Social Media, Flyer', p: 'Empfohlen' },
      { name: 'Loom', price: 'Free–13$', use: 'Personalisierte Video-Messages', p: 'Optional' },
    ]},
    { category: 'Datenbanken', tools: [
      { name: 'Dealfront', price: 'Ab 99€', use: 'DACH B2B-Datenbank: Firmendaten', p: 'Empfohlen' },
      { name: 'IHK-Verzeichnis', price: 'Free', use: 'Grundrecherche regionale Händler', p: 'Optional' },
    ]},
  ];
  const roadmap = [
    { phase: 'Foundation', weeks: 'Woche 1–4', color: '#C8A951', items: [
      'Landing Pages deployen (Vercel) + Tracking (GA4, Pixel)',
      'CRM aufsetzen (HubSpot Free) + Lead-Scoring',
      'Sales-Materialien: Factsheets, ROI-Rechner, Lookbook',
      'E-Mail-Automatisierung: Welcome-Sequenz',
      'Kontaktschreiben finalisieren pro Kanal',
    ]},
    { phase: 'Launch', weeks: 'Woche 5–8', color: '#8B5E3C', items: [
      'LinkedIn: 50–100 Approaches/Woche',
      'Google Ads: 3–5 Ad Groups pro Zielgruppe',
      'Instagram: 20–30 DMs/Woche',
      '10 Muster-Displays an Top-Leads',
      'Wöchentliches Performance-Review',
    ]},
    { phase: 'Optimierung', weeks: 'Woche 9–16', color: '#2C5F7C', items: [
      'Bester CPA-Kanal → Budget verdoppeln',
      'Case Studies von ersten Partnern',
      'Landing Page A/B-Tests',
      '2–3 Sales-Reps rekrutieren (8–12%)',
      'Messevorbereitung INHORGENTA/TrendSet',
    ]},
    { phase: 'Skalierung', weeks: 'Ab Monat 5', color: '#5C6B4E', items: [
      'Nachbestell-Automatisierung (EDI/App)',
      'Cross-Selling Pipeline aktivieren',
      'Neue Märkte: AT, CH, Benelux',
      'Partner-Programm mit Staffelkonditionen',
      'Monatliche Reports an alle Partner',
    ]},
  ];
  const schreiben = [
    { ch: 'Modeboutiquen', b1: 'Impulskauf-Schmuck für Ihre Boutique — 0,2m², bis 50.000€/Jahr', b2: 'Kurze Rückfrage — FIREBALL Display für [Store]', cta: 'Probedisplay 4 Wochen', t: '7 Tage', c: '#8B5E3C' },
    { ch: 'Parfümerien', b1: 'Wie ein Lippenstift — neues Impulssortiment für Ihre Parfümerie', b2: 'Ihre 3 kostenlosen Muster-Sticks', cta: '3 Muster-Sticks', t: '10 Tage', c: '#9B4D6E' },
    { ch: 'Kaufhäuser', b1: '50.000€ Jahresumsatz auf 0,2m² — FIREBALL Display-Konzept', b2: 'ROI-Kalkulation für [Kaufhaus]', cta: 'ROI-Kalkulation', t: '14 Tage', c: '#2C5F7C' },
    { ch: 'Museumsshops', b1: 'Handgefertigter Designerschmuck — geschenkfertig, mit Geschichte', b2: 'Lookbook + Designer-Story', cta: 'Lookbook', t: '10 Tage', c: '#5C6B4E' },
    { ch: 'Schmuckhandel', b1: 'Der #1 Bestseller seit 30 Jahren — als Display für Ihre Theke', b2: 'Produktivitätsrechner für [Geschäft]', cta: 'Produktivitätsrechner', t: '10 Tage', c: '#6B5B73' },
  ];
</script>

<svelte:head><title>FIREBALL Admin — Lead-Generierung</title></svelte:head>
<Navbar />

<section style="background:var(--teal); padding:6rem 2rem 2rem; color:var(--white);">
  <div style="max-width:1200px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:0.5rem;">Internes Dashboard</p>
    <h1 style="font-family:'Josefin Sans',sans-serif; font-size:clamp(1.8rem,3vw,2.5rem); color:var(--white); margin:0 0 0.5rem;">FIREBALL Lead-Generierung</h1>
    <p style="color:rgba(255,255,255,0.5); font-size:0.95rem;">5 Kanäle · 5 Landing Pages · Tools · Roadmap · Kontaktschreiben</p>
  </div>
</section>

<section style="background:var(--teal); padding:0 2rem 1rem; position:sticky; top:52px; z-index:50;">
  <div style="max-width:1200px; margin:0 auto; display:flex; gap:0; border-bottom:1px solid rgba(255,255,255,0.1); overflow-x:auto;">
    {#each [{id:'overview',l:'Kanäle'},{id:'tools',l:'Tools'},{id:'roadmap',l:'Roadmap'},{id:'schreiben',l:'Kontaktschreiben'}] as tab}
      <button onclick={() => activeTab = tab.id} style="padding:0.75rem 1.5rem; background:none; border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif; font-size:0.85rem; letter-spacing:0.05em; color:{activeTab === tab.id ? 'var(--gold)' : 'rgba(255,255,255,0.4)'}; border-bottom:2px solid {activeTab === tab.id ? 'var(--gold)' : 'transparent'}; transition:all 0.2s; white-space:nowrap;">{tab.l}</button>
    {/each}
  </div>
</section>

<main style="max-width:1200px; margin:0 auto; padding:2rem;">
{#if activeTab === 'overview'}
  <div style="display:flex; flex-direction:column; gap:1rem;">
    {#each channels as ch}
      <div style="display:grid; grid-template-columns:1fr auto; gap:2rem; align-items:center; padding:1.5rem; background:var(--white); border:1px solid var(--gray-200); border-left:4px solid {ch.color};">
        <div>
          <div style="display:flex; align-items:center; gap:0.75rem; margin-bottom:0.5rem;">
            <span style="font-size:1.5rem;">{ch.icon}</span>
            <h3 style="font-size:1.1rem; color:var(--teal); margin:0;">{ch.title}</h3>
          </div>
          <p style="font-size:0.85rem; color:var(--gray-500); margin:0;">CTA: <strong>{ch.cta}</strong> · <span style="color:green;">● {ch.status}</span></p>
        </div>
        <a href={ch.slug} target="_blank" style="padding:0.5rem 1rem; background:var(--teal); color:var(--white); font-family:'Josefin Sans',sans-serif; font-size:0.8rem; text-decoration:none;">Öffnen →</a>
      </div>
    {/each}
  </div>
  <div style="margin-top:3rem;">
    <h2 style="font-size:1.3rem; color:var(--teal); margin:0 0 1.5rem;">Ziel-KPIs</h2>
    <div style="display:grid; grid-template-columns:1fr 1fr; gap:1.5rem;">
      <div style="background:var(--cream); padding:1.5rem;"><h4 style="font-family:'Josefin Sans',sans-serif; color:var(--teal); font-size:0.95rem; margin:0 0 1rem;">3-Monats-Ziele</h4><div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;"><div><div class="stat-number" style="font-size:1.5rem;">30–50</div><div class="stat-label">Leads/Mo</div></div><div><div class="stat-number" style="font-size:1.5rem;">5–10</div><div class="stat-label">Partner/Mo</div></div><div><div class="stat-number" style="font-size:1.5rem;">&lt;50€</div><div class="stat-label">CPL</div></div><div><div class="stat-number" style="font-size:1.5rem;">&gt;3%</div><div class="stat-label">CVR</div></div></div></div>
      <div style="background:var(--cream); padding:1.5rem;"><h4 style="font-family:'Josefin Sans',sans-serif; color:var(--teal); font-size:0.95rem; margin:0 0 1rem;">12-Monats-Ziele</h4><div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;"><div><div class="stat-number" style="font-size:1.5rem;">80–150</div><div class="stat-label">Leads/Mo</div></div><div><div class="stat-number" style="font-size:1.5rem;">15–30</div><div class="stat-label">Partner/Mo</div></div><div><div class="stat-number" style="font-size:1.5rem;">&lt;30€</div><div class="stat-label">CPL</div></div><div><div class="stat-number" style="font-size:1.5rem;">&gt;5%</div><div class="stat-label">CVR</div></div></div></div>
    </div>
  </div>
{:else if activeTab === 'tools'}
  <div style="display:grid; grid-template-columns:1fr 1fr; gap:1.5rem; margin-bottom:3rem;">
    <div style="background:var(--cream); padding:1.5rem; border-left:3px solid var(--gold);"><h3 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">Minimal-Stack</h3><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.3rem; margin:0 0 1rem;">~150€/Mo + Ads</p><p style="font-size:0.8rem; color:var(--gray-500); margin:0; line-height:1.8;">HubSpot Free · Vercel Free · Sales Navigator 79€ · Canva 12€ · Lemlist 59€ · GA4 + Cal.com Free</p></div>
    <div style="background:var(--teal); padding:1.5rem; color:var(--white); border-left:3px solid var(--gold);"><h3 style="font-size:1rem; color:var(--gold); margin:0 0 0.25rem;">Premium-Stack</h3><p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:1.3rem; margin:0 0 1rem;">~470€/Mo + Ads</p><p style="font-size:0.8rem; color:rgba(255,255,255,0.6); margin:0; line-height:1.8;">+ HubSpot Starter 45€ · Waalaxy 80€ · Dealfront 99€ · Hotjar 32€ · Loom 13€</p></div>
  </div>
  {#each toolStack as cat}
    <div style="margin-bottom:2rem;"><h3 style="font-size:1rem; color:var(--teal); margin:0 0 0.75rem; padding-bottom:0.5rem; border-bottom:1px solid var(--gray-200);">{cat.category}</h3>
      {#each cat.tools as t}
        <div style="display:grid; grid-template-columns:150px 80px 1fr 75px; gap:1rem; align-items:center; padding:0.6rem 1rem; background:var(--white); border:1px solid var(--gray-200); margin-bottom:0.5rem;">
          <span style="font-weight:600; font-size:0.85rem; color:var(--teal);">{t.name}</span>
          <span style="font-size:0.75rem; color:var(--gray-500);">{t.price}</span>
          <span style="font-size:0.8rem; color:var(--gray-500);">{t.use}</span>
          <span style="font-size:0.65rem; text-align:center; padding:0.2rem 0.4rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.05em; background:{t.p === 'Pflicht' ? '#1A3C40' : t.p === 'Empfohlen' ? '#C8A951' : '#eee'}; color:{t.p === 'Pflicht' ? 'white' : t.p === 'Empfohlen' ? '#1A3C40' : '#888'};">{t.p}</span>
        </div>
      {/each}
    </div>
  {/each}
{:else if activeTab === 'roadmap'}
  {#each roadmap as phase, i}
    <div style="display:grid; grid-template-columns:180px 1fr; gap:2rem; padding-bottom:2.5rem;">
      <div><div style="width:12px; height:12px; border-radius:50%; background:{phase.color}; margin-bottom:0.5rem;"></div><h3 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">{phase.phase}</h3><p style="font-size:0.8rem; color:var(--gray-500); margin:0;">{phase.weeks}</p></div>
      <div style="display:flex; flex-direction:column; gap:0.5rem;">
        {#each phase.items as item, j}
          <div style="display:flex; align-items:flex-start; gap:0.75rem; padding:0.6rem 1rem; background:var(--white); border:1px solid var(--gray-200); border-left:3px solid {phase.color};">
            <span style="font-family:'Josefin Sans',sans-serif; font-size:0.75rem; color:{phase.color}; min-width:16px;">{j+1}.</span>
            <span style="font-size:0.85rem; color:var(--gray-700); line-height:1.5;">{item}</span>
          </div>
        {/each}
      </div>
    </div>
  {/each}
{:else if activeTab === 'schreiben'}
  <p style="color:var(--gray-500); margin-bottom:2rem; line-height:1.7;">Für jeden Kanal: Erst- und Zweitkontakt. Vor Versand personalisieren. Volltext: <code>docs/kontaktschreiben/</code></p>
  {#each schreiben as s}
    <div style="margin-bottom:1.5rem; border:1px solid var(--gray-200); border-left:4px solid {s.c}; padding:1.25rem; background:var(--white);">
      <h3 style="font-size:1rem; color:var(--teal); margin:0 0 1rem;">{s.ch}</h3>
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;">
        <div style="background:var(--cream); padding:0.75rem;">
          <p style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:{s.c}; text-transform:uppercase; margin:0 0 0.4rem;">Erstkontakt</p>
          <p style="font-size:0.8rem; color:var(--teal); font-weight:600; margin:0 0 0.4rem;">{s.b1}</p>
          <p style="font-size:0.75rem; color:var(--gray-500); margin:0;">Lead-Magnet: {s.cta}</p>
        </div>
        <div style="background:var(--cream); padding:0.75rem;">
          <p style="font-size:0.65rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:{s.c}; text-transform:uppercase; margin:0 0 0.4rem;">Follow-up ({s.t})</p>
          <p style="font-size:0.8rem; color:var(--teal); font-weight:600; margin:0 0 0.4rem;">{s.b2}</p>
          <p style="font-size:0.75rem; color:var(--gray-500); margin:0;">Konkretes Angebot nachfassen</p>
        </div>
      </div>
    </div>
  {/each}
{/if}
</main>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center; margin-top:4rem;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH · Internes Dokument</p>
</footer>
