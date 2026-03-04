# 🔥 FIREBALL Lead — B2B Display-Vertrieb

> Landing Pages, Lead-Generierung & Kontaktschreiben für das FIREBALL Display-Partnerprogramm.

## Übersicht

Dieses Projekt enthält:

- **6 Landing Pages** (SvelteKit 5 + Tailwind CSS): 1 zentrale Hub-Seite + 5 kanalspezifische Seiten
- **10 Kontaktschreiben**: Erst- und Zweitkontakt für jeden der 5 B2B-Kanäle
- **Software-Tools Guide**: Vollständige Übersicht aller Tools für Lead-Generierung

## 🎯 Die 5 B2B-Kanäle

| # | Kanal | Landing Page | CTA |
|---|-------|-------------|-----|
| 1 | Modeboutiquen & Concept Stores | `/boutiquen` | Kostenloses Probedisplay |
| 2 | Parfümerien & Beauty-Fachhandel | `/parfuemerien` | Muster-Paket bestellen |
| 3 | Kaufhäuser & Department Stores | `/kaufhaeuser` | ROI-Kalkulation anfordern |
| 4 | Museumsshops & Hotel-Boutiquen | `/museumsshops` | Lookbook anfordern |
| 5 | Schmuck-Fachhandel & Juweliere | `/schmuckhandel` | Produktivitätsrechner |

## 🏗️ Tech Stack

- **Framework:** SvelteKit 5 (Runes)
- **Styling:** Tailwind CSS 4 + Custom CSS Properties
- **Fonts:** Josefin Sans (Brand) + DM Sans (Body)
- **Deployment:** Vercel / Netlify / Node.js

## 🚀 Setup & Entwicklung

```bash
# Dependencies installieren
npm install

# Entwicklungsserver starten
npm run dev

# Production Build
npm run build

# Preview
npm run preview
```

## 📁 Projektstruktur

```
FireballLead/
├── src/
│   ├── routes/
│   │   ├── +page.svelte           # Hub / Zentrale Seite
│   │   ├── +layout.svelte         # Root Layout
│   │   ├── boutiquen/+page.svelte # Kanal 1
│   │   ├── parfuemerien/+page.svelte # Kanal 2
│   │   ├── kaufhaeuser/+page.svelte  # Kanal 3
│   │   ├── museumsshops/+page.svelte # Kanal 4
│   │   └── schmuckhandel/+page.svelte # Kanal 5
│   ├── lib/
│   │   └── components/
│   │       ├── LeadForm.svelte     # Shared Lead-Formular
│   │       └── Navbar.svelte       # Navigation
│   ├── app.html                    # HTML Template
│   └── app.css                     # Global Styles
├── docs/
│   ├── kontaktschreiben/
│   │   └── ALLE_KONTAKTSCHREIBEN.md  # 10 Schreiben (5×2)
│   └── SOFTWARE_TOOLS.md             # Tool-Übersicht
├── static/                         # Statische Assets
├── svelte.config.js
├── vite.config.ts
└── package.json
```

## 📧 Kontaktschreiben

Für jeden der 5 Kanäle gibt es:
- **Erstkontakt**: Vorstellung des Konzepts + kanalspezifischer Lead-Magnet
- **Zweitkontakt**: Follow-up nach 7–14 Tagen mit konkretem Angebot

→ Siehe `docs/kontaktschreiben/ALLE_KONTAKTSCHREIBEN.md`

## 🛠️ Software-Tools

Vollständige Übersicht von 40+ Tools in 10 Kategorien:
- CRM & Lead-Management
- Landing Page & Website
- E-Mail-Marketing & Automatisierung
- LinkedIn & Social Selling
- Anzeigen & Paid Ads
- und mehr...

Inklusive **Minimal-Stack** (~150€/Mo) und **Premium-Stack** (~500€/Mo).

→ Siehe `docs/SOFTWARE_TOOLS.md`

## 🎨 Brand Guidelines

- **Name:** Immer in GROSSBUCHSTABEN: FIREBALL
- **Font:** Josefin Sans Semibold
- **Farben:** Weiß auf Schwarz/Teal
- **Logo:** Keine Animationen, keine Effekte — clean und simpel

## 📊 KPIs (Ziele)

| KPI | 3 Monate | 12 Monate |
|-----|----------|-----------|
| Qualifizierte Leads/Monat | 30–50 | 80–150 |
| Neue Display-Partner/Monat | 5–10 | 15–30 |
| Cost per Lead | < 50€ | < 30€ |
| Landing Page Conversion | > 3% | > 5% |
| Nachbestellrate | > 60% | > 75% |

## Deployment

### Vercel (empfohlen)
```bash
npm i -D @sveltejs/adapter-vercel
vercel deploy
```

### Docker
```bash
npm run build
docker build -t fireball-lead .
docker run -p 3000:3000 fireball-lead
```

---

© 2026 VICI Vertrieb Deutschland GmbH — FIREBALL
