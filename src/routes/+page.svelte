<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  let authenticated = $state(false);
  let pw = $state('');
  let pwError = $state(false);
  let activeTab = $state('overview');

  function login() {
    if (pw === 'fire') { authenticated = true; pwError = false; }
    else { pwError = true; pw = ''; }
  }

  const channels = [
    { slug: '/boutiquen', title: 'Modeboutiquen & Concept Stores', icon: '👗', color: '#8B5E3C', cta: 'Probedisplay', status: 'Live' },
    { slug: '/parfuemerien', title: 'Parfümerien & Beauty-Fachhandel', icon: '💄', color: '#9B4D6E', cta: 'Muster-Paket', status: 'Live' },
    { slug: '/kaufhaeuser', title: 'Kaufhäuser & Department Stores', icon: '🏬', color: '#2C5F7C', cta: 'ROI-Kalkulation', status: 'Live' },
    { slug: '/museumsshops', title: 'Museumsshops & Hotel-Boutiquen', icon: '🏛️', color: '#5C6B4E', cta: 'Lookbook', status: 'Live' },
    { slug: '/schmuckhandel', title: 'Schmuck-Fachhandel & Juweliere', icon: '💎', color: '#6B5B73', cta: 'Produktivitätsrechner', status: 'Live' },
  ];
  const docs = [
    { name: 'Kontaktschreiben (alle Kanäle)', file: '/docs/ALLE_KONTAKTSCHREIBEN.md', desc: '15 Texte: Erst-, Zweit- & Drittkontakt pro Kanal' },
    { name: 'Sales Navigator Guide', file: '/docs/SALES_NAVIGATOR_GUIDE.md', desc: 'Filter, Boolean Strings, Tagesroutine, InMail-Regeln' },
    { name: 'LinkedIn-Profil Ina Bunt', file: '/docs/LINKEDIN_PROFIL_INA_BUNT.md', desc: 'Headline, About, Featured, Settings — Copy-Paste-fertig' },
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
    { phase: 'Foundation', weeks: 'Woche 1–4', color: '#C8A951', items: ['Landing Pages deployen (Vercel) + Tracking (GA4, Pixel)', 'CRM aufsetzen (HubSpot Free) + Lead-Scoring', 'Sales-Materialien: Factsheets, ROI-Rechner, Lookbook', 'E-Mail-Automatisierung: Welcome-Sequenz', 'Kontaktschreiben finalisieren pro Kanal'] },
    { phase: 'Launch', weeks: 'Woche 5–8', color: '#8B5E3C', items: ['LinkedIn: 50–100 Approaches/Woche', 'Google Ads: 3–5 Ad Groups pro Zielgruppe', 'Instagram: 20–30 DMs/Woche', '10 Muster-Displays an Top-Leads', 'Wöchentliches Performance-Review'] },
    { phase: 'Optimierung', weeks: 'Woche 9–16', color: '#2C5F7C', items: ['Bester CPA-Kanal → Budget verdoppeln', 'Case Studies von ersten Partnern', 'Landing Page A/B-Tests', '2–3 Sales-Reps rekrutieren (8–12%)', 'Messevorbereitung INHORGENTA/TrendSet'] },
    { phase: 'Skalierung', weeks: 'Ab Monat 5', color: '#5C6B4E', items: ['Nachbestell-Automatisierung (EDI/App)', 'Cross-Selling Pipeline aktivieren', 'Neue Märkte: AT, CH, Benelux', 'Partner-Programm mit Staffelkonditionen', 'Monatliche Reports an alle Partner'] },
  ];
  const schreiben = [
    { ch: 'Modeboutiquen', b1: 'Schmuck, den Ihre Kundinnen sammeln — Testdisplay für [Store]?', b2: 'Kurz nachgehakt — Testdisplay für [Store]', b3: 'Letzte Frage — dann halte ich die Füße still', cta: 'Probedisplay 4 Wochen', t1: 'Tag 0', t2: 'Tag 7', t3: 'Tag 17', c: '#8B5E3C', channels: 'E-Mail + LinkedIn InMail' },
    { ch: 'Parfümerien', b1: 'Neues Impulssortiment im Stick-Format — wie ein Lippenstift', b2: 'Ihre 3 Muster-Sticks — soll ich sie losschicken?', b3: '', cta: '3 Muster-Sticks', t1: 'Tag 0', t2: 'Tag 10', t3: '', c: '#9B4D6E', channels: 'E-Mail + LinkedIn InMail' },
    { ch: 'Kaufhäuser', b1: '50.000€ Jahresumsatz auf 0,2m² — FIREBALL Display', b2: 'ROI-Kalkulation für [Kaufhaus] — bereits vorbereitet', b3: 'Kurze Frage zum Timing', cta: 'ROI-Kalkulation', t1: 'Tag 0', t2: 'Tag 14', t3: 'Tag 28', c: '#2C5F7C', channels: 'E-Mail an Einkauf' },
    { ch: 'Museumsshops', b1: 'Handgefertigter Designerschmuck mit Geschichte', b2: 'Die Geschichte hinter dem FIREBALL — für [Museum]', b3: '', cta: 'Lookbook + Story', t1: 'Tag 0', t2: 'Tag 10', t3: '', c: '#5C6B4E', channels: 'E-Mail' },
    { ch: 'Schmuckhandel', b1: 'Der #1 Bestseller seit 30 Jahren — als Impulsware', b2: 'Produktivitätsrechner für [Geschäft] — Ihre Zahlen', b3: 'Kurze Frage — Impulssortiment auf Ihrer Theke', cta: 'Produktivitätsrechner', t1: 'Tag 0', t2: 'Tag 10', t3: 'Tag 20', c: '#6B5B73', channels: 'E-Mail / Brief' },
  ];

  // LinkedIn Lead Gen Process
  const linkedinSteps = [
    { nr: '1', title: 'Sales Navigator Konto einrichten', tool: 'LinkedIn Sales Navigator Core', toolUrl: 'https://business.linkedin.com/sales-solutions', price: '79,99€/Mo', time: '30 Min (einmalig)', tasks: [
      'linkedin.com/sales → „Kostenlos testen" (30 Tage gratis)',
      'Sales Navigator Core wählen (79,99€/Mo, 50 InMails/Mo)',
      'Settings → Sales Preferences: Geography = Deutschland, Industry = Retail + Luxury + Fashion + Hospitality',
      'Settings → CRM → HubSpot verbinden → Authorize',
      'Chrome-Extension „LinkedIn Sales Navigator" installieren',
      'Alerts aktivieren: Job Changes + News Mentions',
    ]},
    { nr: '2', title: 'LinkedIn-Profil von Ina Bunt optimieren', tool: 'LinkedIn (kostenlos)', toolUrl: 'https://linkedin.com', price: 'Free', time: '2 Stunden (einmalig)', tasks: [
      'Profilfoto: Professionelles Headshot MIT FIREBALL Ohrringen',
      'Banner: Display-Foto links + FIREBALL Branding rechts (1584×396px, Canva Pro)',
      'Headline: „Head of Retail Partnerships bei FIREBALL | 280+ Farben, 30+ Jahre, Ø 2 Verkäufe/Tag | Ich suche Boutiquen, Parfümerien & Kaufhäuser"',
      'About: 2.600 Zeichen mit Value Props + kanalspezifischen Angeboten (→ Dokument downloaden)',
      'Featured: 2 Landing Page Links + Factsheet PDF + Top-Post',
      'Experience: Aktuelle Position mit allen FIREBALL-Kennzahlen',
      'Skills: Retail Partnerships, B2B Sales, Key Account Management, POS, Business Development',
      'Creator Mode aktivieren → Topics: #Retail #Schmuck #B2B #POS',
      'Open Profile in Sales Navigator aktivieren',
    ]},
    { nr: '3', title: 'Lead-Listen anlegen (5 Kanäle)', tool: 'Sales Navigator → Lead Lists', toolUrl: 'https://business.linkedin.com/sales-solutions', price: 'Inkl.', time: '2 Stunden (einmalig)', tasks: [
      'Liste „FIREBALL — Boutiquen": Lead Filters → Job Title: Inhaberin/Owner/Gründerin → Industry: Retail/Fashion → Headcount: 1–50 → Keywords: Boutique/Concept Store',
      'Liste „FIREBALL — Parfümerien": Job Title: Inhaberin/Geschäftsführerin → Keywords: Parfümerie/Beauty/Kosmetik → Headcount: 1–50',
      'Liste „FIREBALL — Kaufhäuser": Job Title: Einkauf/Buyer/Category Manager → Keywords: Kaufhaus/Department Store → Headcount: 201–10.000',
      'Liste „FIREBALL — Kultur & Hotels": Job Title: Shop Manager/Boutique Manager → Keywords: Museum Shop/Hotel Boutique → Industry: Museums/Hospitality',
      'Liste „FIREBALL — Juweliere": Job Title: Inhaberin/Juwelier → Keywords: Juwelier/Schmuck/Goldschmiede → Industry: Luxury Goods',
      'Pro Liste: 30–50 Leads recherchieren, nach „Recently posted" sortieren, nur aktive Profile speichern',
    ]},
    { nr: '4', title: 'Kontaktschreiben in Templates laden', tool: 'Sales Navigator + Lemlist', toolUrl: 'https://lemlist.com', price: 'Lemlist 59€/Mo', time: '1 Stunde (einmalig)', tasks: [
      'Alle 15 Kontaktschreiben (→ Dokument downloaden) als InMail-Templates speichern',
      'In Lemlist: 5 Sequenzen anlegen (1 pro Kanal), je 2–3 Schritte',
      'Schritt 1: Erstkontakt-E-Mail (personalisiert mit Store-Name + individuellem Detail)',
      'Schritt 2: Follow-up nach 7–14 Tagen (kanalspezifisch)',
      'Schritt 3: Letzter Kontakt nach weiteren 10 Tagen (nur Boutiquen, Kaufhäuser, Schmuckhandel)',
      'Personalisierungs-Variablen definieren: {{firstName}}, {{company}}, {{customLine}}',
      'Test-E-Mails an eigene Adresse senden → Formatierung und Links prüfen',
    ]},
    { nr: '5', title: 'Tägliche Outreach-Routine starten', tool: 'Sales Navigator + HubSpot CRM', toolUrl: 'https://app.hubspot.com', price: 'HubSpot Free', time: '1,5–2h täglich', tasks: [
      'MORGENS (30 Min): Alerts prüfen → 5–10 neue Leads recherchieren → Website/Instagram jedes Leads anschauen (1 Min) → Personalisierungsnotiz speichern',
      'MITTAGS (45 Min): 8–12 personalisierte InMails senden → Jede InMail individuell anpassen → Connection Requests an nicht-InMail-erreichbare Leads → Jeden Lead in HubSpot loggen (Stage: „Kontaktiert")',
      'NACHMITTAGS (30 Min): Antworten beantworten (Priorität!) → Leads, die Profil angesehen haben, proaktiv anschreiben → 3–5 Posts von Leads liken/kommentieren',
      'InMail-Regeln: Max. 300 Wörter, immer nur 1 CTA, Di–Do versenden, 8:30–10:00 oder 16:00–17:30',
      'Wochenziel: 40–60 InMails, 20–30 Connection Requests, 3–5 Calls gebucht',
    ]},
    { nr: '6', title: 'Social Selling Content posten', tool: 'LinkedIn + Canva Pro', toolUrl: 'https://canva.com', price: 'Canva 12€/Mo', time: '30 Min, 3x/Woche', tasks: [
      'MONTAG: Produkt-Insight → Foto aus Manufaktur + kurzer Text (z.B. „280 Farben — und es werden nicht weniger")',
      'MITTWOCH: Partner-Erfolg → Anonymisierter Case (z.B. „Boutique in München: 12 Paar in 5 Tagen")',
      'FREITAG: Branchen-Insight → Artikel teilen + eigener Kommentar (z.B. Lipstick Effect, Retail Trends)',
      'Bilder in Canva Pro erstellen: FIREBALL Fotos + Text-Overlay im Brand-Design (Teal + Gold)',
      'Hashtags: #Retail #Schmuck #Impulssortiment #POS #B2B #Designerschmuck #Einzelhandel',
      'Engagement: Täglich 3–5 Posts von Leads substantiell kommentieren (nicht nur „Toll!")',
    ]},
    { nr: '7', title: 'Pipeline in HubSpot tracken', tool: 'HubSpot CRM (Free)', toolUrl: 'https://app.hubspot.com', price: 'Free', time: '15 Min täglich', tasks: [
      'Pipeline-Stufen: Recherchiert → Kontaktiert → Reagiert → Meeting → Muster versendet → Testphase → Partner → Lost',
      'Jeden Lead nach jedem Kontakt updaten (Stage + Notiz + nächste Aktion)',
      'Wöchentlich: Pipeline-Report ziehen → Wie viele Leads pro Stage? → Wo stockt es?',
      'Monatlich: Conversion Rates berechnen → Kontaktiert→Reagiert sollte >15% sein',
      'Lead-Scoring: +10 für aktives LinkedIn-Profil, +20 für Antwort, +30 für Meeting, +50 für Muster',
      'Automatisierung: HubSpot Workflow → Wenn Stage = „Kontaktiert" + 7 Tage kein Update → Erinnerung Follow-up',
    ]},
    { nr: '8', title: 'Monatliche Optimierung', tool: 'Sales Navigator + Looker Studio', toolUrl: 'https://lookerstudio.google.com', price: 'Free', time: '1 Stunde, 1x/Monat', tasks: [
      'SSI-Score prüfen (linkedin.com/sales/ssi) → Ziel: >70',
      'InMail Response Rate prüfen → Ziel: >15% → Unter 10%? Betreffzeilen ändern',
      'Bester Kanal identifizieren → Mehr Budget/Zeit zuweisen',
      'Schlechtester Kanal → Texte anpassen oder pausieren',
      'Nicht-Responder nach 3 Kontakten archivieren (Lead-Liste sauber halten)',
      'Neue Boolean Search Strings testen für frische Leads',
      'Looker Studio Dashboard: InMails gesendet, Response Rate, Meetings, Neue Partner pro Monat',
    ]},
  ];
</script>

<svelte:head><title>FIREBALL Admin — Lead-Generierung</title></svelte:head>

{#if !authenticated}
<!-- PASSWORD GATE -->
<div style="min-height:100vh; background:var(--teal); display:flex; align-items:center; justify-content:center; padding:2rem;">
  <div style="max-width:380px; width:100%; text-align:center;">
    <p class="fireball-brand" style="color:var(--gold); font-size:1.8rem; margin-bottom:0.5rem;">FIREBALL</p>
    <p style="color:rgba(255,255,255,0.4); font-size:0.85rem; margin-bottom:3rem;">Internes Admin-Dashboard</p>
    <div style="background:rgba(255,255,255,0.05); border:1px solid rgba(255,255,255,0.1); padding:2.5rem;">
      <p style="color:rgba(255,255,255,0.6); font-size:0.85rem; margin-bottom:1.5rem;">Bitte Passwort eingeben:</p>
      <input
        type="password"
        bind:value={pw}
        onkeydown={(e) => { if (e.key === 'Enter') login(); }}
        placeholder="Passwort"
        style="
          width:100%; padding:0.75rem 1rem; border:1px solid {pwError ? '#e74c3c' : 'rgba(255,255,255,0.15)'};
          background:rgba(255,255,255,0.05); color:var(--white); font-size:1rem;
          font-family:'DM Sans',sans-serif; outline:none; box-sizing:border-box;
          margin-bottom:0.75rem;
        "
      />
      {#if pwError}
        <p style="color:#e74c3c; font-size:0.8rem; margin:0 0 0.75rem;">Falsches Passwort.</p>
      {/if}
      <button onclick={login} style="
        width:100%; padding:0.75rem; background:var(--gold); color:var(--teal);
        border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif;
        font-size:0.9rem; letter-spacing:0.1em; font-weight:600;
      ">Einloggen</button>
    </div>
  </div>
</div>

{:else}
<!-- AUTHENTICATED DASHBOARD -->
<Navbar />

<section style="background:var(--teal); padding:6rem 2rem 2rem; color:var(--white);">
  <div style="max-width:1200px; margin:0 auto;">
    <p style="font-family:'Josefin Sans',sans-serif; color:var(--gold); font-size:0.75rem; letter-spacing:0.2em; text-transform:uppercase; margin-bottom:0.5rem;">Internes Dashboard</p>
    <h1 style="font-family:'Josefin Sans',sans-serif; font-size:clamp(1.8rem,3vw,2.5rem); color:var(--white); margin:0 0 0.5rem;">FIREBALL Lead-Generierung</h1>
    <p style="color:rgba(255,255,255,0.5); font-size:0.95rem;">5 Kanäle · Tools · LinkedIn-Prozess · Roadmap · Kontaktschreiben · Dokumente</p>
  </div>
</section>

<!-- TABS -->
<section style="background:var(--teal); padding:0 2rem 1rem; position:sticky; top:52px; z-index:50;">
  <div style="max-width:1200px; margin:0 auto; display:flex; gap:0; border-bottom:1px solid rgba(255,255,255,0.1); overflow-x:auto;">
    {#each [{id:'overview',l:'Kanäle'},{id:'linkedin',l:'LinkedIn'},{id:'tools',l:'Tools'},{id:'roadmap',l:'Roadmap'},{id:'schreiben',l:'Schreiben'},{id:'docs',l:'Dokumente'}] as tab}
      <button onclick={() => activeTab = tab.id} style="padding:0.75rem 1.25rem; background:none; border:none; cursor:pointer; font-family:'Josefin Sans',sans-serif; font-size:0.8rem; letter-spacing:0.05em; color:{activeTab === tab.id ? 'var(--gold)' : 'rgba(255,255,255,0.4)'}; border-bottom:2px solid {activeTab === tab.id ? 'var(--gold)' : 'transparent'}; transition:all 0.2s; white-space:nowrap;">{tab.l}</button>
    {/each}
  </div>
</section>

<main style="max-width:1200px; margin:0 auto; padding:2rem;">

<!-- TAB: KANÄLE -->
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

<!-- TAB: LINKEDIN -->
{:else if activeTab === 'linkedin'}
  <div style="background:var(--cream); padding:1.5rem; border-left:3px solid #0A66C2; margin-bottom:2.5rem;">
    <h2 style="font-size:1.2rem; color:var(--teal); margin:0 0 0.5rem;">LinkedIn Lead-Generierung — Schritt für Schritt</h2>
    <p style="font-size:0.85rem; color:var(--gray-500); margin:0; line-height:1.7;">8 Schritte, jeder mit dem exakten Tool, URL, Preis und konkreten Aufgaben. Von der Konto-Einrichtung bis zur monatlichen Optimierung.</p>
  </div>

  {#each linkedinSteps as step, i}
    <div style="margin-bottom:2rem;">
      <!-- Step Header -->
      <div style="display:grid; grid-template-columns:48px 1fr; gap:1rem; align-items:start;">
        <div style="width:48px; height:48px; border-radius:50%; background:#0A66C2; display:flex; align-items:center; justify-content:center; font-family:'Josefin Sans',sans-serif; font-weight:700; color:white; font-size:1.1rem;">{step.nr}</div>
        <div>
          <h3 style="font-size:1.1rem; color:var(--teal); margin:0 0 0.5rem;">{step.title}</h3>
          <!-- Tool Badge -->
          <div style="display:flex; flex-wrap:wrap; gap:0.5rem; margin-bottom:1rem;">
            <a href={step.toolUrl} target="_blank" style="display:inline-flex; align-items:center; gap:0.4rem; padding:0.3rem 0.75rem; background:#0A66C2; color:white; font-size:0.75rem; font-family:'Josefin Sans',sans-serif; text-decoration:none; letter-spacing:0.03em;">
              🔗 {step.tool}
            </a>
            <span style="padding:0.3rem 0.75rem; background:var(--cream); font-size:0.75rem; color:var(--gray-500); font-family:'Josefin Sans',sans-serif;">{step.price}</span>
            <span style="padding:0.3rem 0.75rem; background:var(--cream); font-size:0.75rem; color:var(--gray-500); font-family:'Josefin Sans',sans-serif;">⏱ {step.time}</span>
          </div>
          <!-- Tasks -->
          <div style="display:flex; flex-direction:column; gap:0.5rem;">
            {#each step.tasks as task}
              <div style="display:flex; align-items:flex-start; gap:0.5rem; padding:0.6rem 0.75rem; background:var(--white); border:1px solid var(--gray-200); border-left:3px solid #0A66C2;">
                <span style="color:#0A66C2; font-size:0.8rem; margin-top:1px; flex-shrink:0;">→</span>
                <span style="font-size:0.8rem; color:var(--gray-700); line-height:1.5;">{task}</span>
              </div>
            {/each}
          </div>
        </div>
      </div>
    </div>
  {/each}

  <!-- Weekly Targets -->
  <div style="background:var(--teal); padding:2rem; margin-top:1rem;">
    <h3 style="color:var(--gold); font-size:1rem; margin:0 0 1.25rem;">Wöchentliche Ziele</h3>
    <div style="display:grid; grid-template-columns:repeat(3, 1fr); gap:1.5rem;">
      <div style="text-align:center;"><div class="stat-number" style="font-size:1.8rem;">40–60</div><div style="color:rgba(255,255,255,0.4); font-size:0.75rem;">InMails/Woche</div></div>
      <div style="text-align:center;"><div class="stat-number" style="font-size:1.8rem;">20–30</div><div style="color:rgba(255,255,255,0.4); font-size:0.75rem;">Connection Requests</div></div>
      <div style="text-align:center;"><div class="stat-number" style="font-size:1.8rem;">3–5</div><div style="color:rgba(255,255,255,0.4); font-size:0.75rem;">Calls gebucht</div></div>
    </div>
  </div>

<!-- TAB: TOOLS -->
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

<!-- TAB: ROADMAP -->
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

<!-- TAB: KONTAKTSCHREIBEN -->
{:else if activeTab === 'schreiben'}
  <div style="background:var(--cream); padding:1rem 1.5rem; border-left:3px solid var(--gold); margin-bottom:2rem;">
    <p style="font-size:0.85rem; color:var(--gray-500); margin:0; line-height:1.7;">Alle Volltexte als Download: <a href="/docs/ALLE_KONTAKTSCHREIBEN.md" download style="color:var(--gold); font-weight:600;">Kontaktschreiben herunterladen →</a></p>
  </div>
  {#each schreiben as s}
    <div style="margin-bottom:1.5rem; border:1px solid var(--gray-200); border-left:4px solid {s.c}; padding:1.25rem; background:var(--white);">
      <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:1rem;">
        <h3 style="font-size:1rem; color:var(--teal); margin:0;">{s.ch}</h3>
        <span style="font-size:0.7rem; color:var(--gray-500); font-family:'Josefin Sans',sans-serif;">{s.channels}</span>
      </div>
      <div style="display:grid; grid-template-columns:{s.b3 ? '1fr 1fr 1fr' : '1fr 1fr'}; gap:0.75rem;">
        <div style="background:var(--cream); padding:0.75rem;">
          <p style="font-size:0.6rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:{s.c}; text-transform:uppercase; margin:0 0 0.3rem;">Erstkontakt ({s.t1})</p>
          <p style="font-size:0.78rem; color:var(--teal); font-weight:600; margin:0 0 0.3rem; line-height:1.4;">{s.b1}</p>
          <p style="font-size:0.7rem; color:var(--gray-500); margin:0;">→ {s.cta}</p>
        </div>
        <div style="background:var(--cream); padding:0.75rem;">
          <p style="font-size:0.6rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:{s.c}; text-transform:uppercase; margin:0 0 0.3rem;">Follow-up ({s.t2})</p>
          <p style="font-size:0.78rem; color:var(--teal); font-weight:600; margin:0 0 0.3rem; line-height:1.4;">{s.b2}</p>
          <p style="font-size:0.7rem; color:var(--gray-500); margin:0;">→ Konkretes Angebot</p>
        </div>
        {#if s.b3}
        <div style="background:var(--cream); padding:0.75rem;">
          <p style="font-size:0.6rem; font-family:'Josefin Sans',sans-serif; letter-spacing:0.1em; color:{s.c}; text-transform:uppercase; margin:0 0 0.3rem;">Letzter Kontakt ({s.t3})</p>
          <p style="font-size:0.78rem; color:var(--teal); font-weight:600; margin:0 0 0.3rem; line-height:1.4;">{s.b3}</p>
          <p style="font-size:0.7rem; color:var(--gray-500); margin:0;">→ Ja/Nein-Frage</p>
        </div>
        {/if}
      </div>
    </div>
  {/each}

<!-- TAB: DOKUMENTE -->
{:else if activeTab === 'docs'}
  <p style="color:var(--gray-500); margin-bottom:2rem; line-height:1.7;">Alle Dokumente als Markdown-Dateien. Können direkt in Notion, Google Docs oder einem Texteditor geöffnet werden.</p>
  <div style="display:flex; flex-direction:column; gap:1rem;">
    {#each docs as doc}
      <a href={doc.file} download style="display:grid; grid-template-columns:1fr auto; gap:2rem; align-items:center; padding:1.5rem; background:var(--white); border:1px solid var(--gray-200); border-left:4px solid var(--gold); text-decoration:none; transition:border-color 0.2s;">
        <div>
          <h3 style="font-size:1rem; color:var(--teal); margin:0 0 0.25rem;">{doc.name}</h3>
          <p style="font-size:0.8rem; color:var(--gray-500); margin:0;">{doc.desc}</p>
        </div>
        <span style="padding:0.5rem 1rem; background:var(--gold); color:var(--teal); font-family:'Josefin Sans',sans-serif; font-size:0.8rem; font-weight:600; white-space:nowrap;">Download ↓</span>
      </a>
    {/each}
  </div>
{/if}
</main>

<footer style="background:var(--teal); border-top:1px solid rgba(255,255,255,0.08); padding:2rem; text-align:center; margin-top:4rem;">
  <p class="fireball-brand" style="color:var(--gold); font-size:1rem; margin-bottom:0.5rem;">FIREBALL</p>
  <p style="font-size:0.75rem; color:rgba(255,255,255,0.35);">© 2026 VICI Vertrieb Deutschland GmbH · Internes Dokument</p>
</footer>
{/if}
