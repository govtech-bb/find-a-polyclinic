# Find a Polyclinic — Alpha prototype

A mobile-first directory of Barbados' nine polyclinics. Citizens can:

- See their nearest polyclinic sorted by distance
- Check today's opening status at a glance
- Filter by service (Dental, Pregnancy Care, Pharmacy, Fast Track, 24/7)
- Get directions via Google Maps
- Call the right department directly (each polyclinic exposes its full phone directory)
- View all 9 polyclinics on a Leaflet + OpenStreetMap map

**Live demo:** drop `index.html` on [app.netlify.com/drop](https://app.netlify.com/drop) to deploy in 10 seconds.

## What it is

This is an **Alpha prototype** — a single self-contained `index.html` (~74 KB). No build step, no backend, no framework. Open the file in any modern browser and the whole app runs locally.

Built to match the [alpha.gov.bb](https://alpha.gov.bb) design language: navy/yellow government scaffolding, Figtree wordmark, teal primary buttons, the GovBB colour tokens.

## Data sources

| Field | Source |
|---|---|
| Phone numbers, addresses, opening hours | [health.gov.bb Healthcare Locator](https://www.health.gov.bb/Healthcare-Locator) — every clinic record has a `source` URL pointing to its official institution page |
| 24/7 status, Fast Track service | health.gov.bb |
| GPS coordinates | OpenStreetMap (`nominatim.openstreetmap.org`) — 8 of 9 are OSM-mapped clinic features, the 9th is hand-corrected |
| Services list (Pregnancy Care, Immunisation) | Inferred from standard polyclinic offerings — flagged for SMO verification before launch |

Every clinic detail page links back to its source page on health.gov.bb so users can verify.

## The nine polyclinics

| # | Name | Parish | Notable |
|---|---|---|---|
| 1 | Randal Phillips | Christ Church | Has Pharmacy |
| 2 | Edgar Cochrane | St. Michael (Wildey) | |
| 3 | **Winston Scott** | St. Michael (Bridgetown) | **Open 24/7** · Fast Track Doctor & Nurse |
| 4 | Branford Taitt | St. Michael (Black Rock) | |
| 5 | Eunice Gibson | St. Michael (Warrens) | |
| 6 | Frederick "Freddie" Miller | St. George (The Glebe) | Has Pharmacy |
| 7 | St. Philip | St. Philip (Six Roads) | Direct department lines only (no main switchboard) |
| 8 | David Thompson Health & Social Services Complex | St. John | Social Services |
| 9 | Maurice Byer | St. Peter (Station Hill) | Dental · Pharmacy |

All open **Mon–Fri 8:30 AM – 4:30 PM** except Winston Scott (24/7).

## Demo controls

There's a purple/yellow striped bar at the top of the prototype labelled **"Prototype only — not visible in live service"**. Use the **View as** dropdown to fake the current time:

- **Thursday 3:00 PM** — typical weekday, all 9 polyclinics open
- **Tuesday 10:00 PM** — only Winston Scott open → "Most polyclinics closed" banner with QEH A&E fallback
- **Saturday 9:00 AM** — only Winston Scott open
- **Sunday 11:00 AM** — only Winston Scott open

Useful for showing MoH reviewers what the status pills look like outside business hours without waiting for the clock.

## Deploying

**Quickest — Netlify Drop:**
1. Open https://app.netlify.com/drop
2. Drag `index.html` onto the drop zone
3. Done — Netlify gives you a public URL

**Or — git-based with auto-deploy:**
1. Connect this repo to a Netlify site
2. Build command: *(none)*
3. Publish directory: `.` (repo root)
4. Every push to `main` auto-deploys

## Stack

- Plain HTML / CSS / vanilla JS (no framework, no build)
- Figtree from Google Fonts CDN
- Leaflet 1.9.4 from unpkg CDN (with SRI hashes)
- OpenStreetMap tiles
- Google Maps deep links for "Get directions" / "Open in Maps" (no API key needed for deep links)

## Open questions

- Named MoH content owner for ongoing verification (Senior Medical Officer of Health?)
- Should "Symptom checker →" handoff link out to the digital triage service?
- Are service lists (Pregnancy Care, Immunisation) accurate per clinic, or do they vary?
- Is there a canonical Barbados public-holidays calendar we can pull, or does MoH maintain it manually?

## Licence

Crown copyright — Government of Barbados.
