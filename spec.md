# Fan Page v1 — Spec

## Functional

Fan page topic: **Valorant**.

- Header with the page title and a short tagline describing the game.
- Nav bar with jump links to each section: About, Agents, Maps, Tips.
- **About** section — a couple sentences explaining what Valorant is (5v5 tactical shooter, Agents with abilities, attack/defend rounds).
- **Agents** section — contains two subsections:
  - **Favorite Agents** — a small grid of cards, each with an Agent name and a one-line description (Jett, Sova, Killjoy).
  - **All Agents** — full current roster of all 29 agents, each with role (Duelist/Initiator/Controller/Sentinel), a 1-2 sentence backstory, and their 4 abilities (basic x2, signature, ultimate) with short descriptions. Sourced from a web research pass, not made up.
- **Maps** section — contains two subsections:
  - **Favorite Maps** — a small grid of cards for 2 favorite maps (Ascent, Bind).
  - **All Maps** — all 12 standard competitive maps, each with a short description (theme/setting + a gameplay note) and a real map image (URLs provided by Jake). Clicking an image opens it full-screen in a lightbox with a close button.
- **Pro Tips (2026)** section — a bullet list of real pro tips, pulled from a web search rather than made up:
  - Small, static crosshair (no movement/firing error)
  - Pre-aim at head level
  - Keep sound effects volume up for footstep/gunfire audio
  - Turn V-Sync off, aim for 144Hz+
  - Pick an eDPI and stick with it for 2+ weeks to build muscle memory
- Footer with name/credit.

## Technical

- Mostly HTML + CSS; one small JavaScript file (`script.js`) added for the map image lightbox — a preview of the DOM-events concept Project 2 covers in depth.
- Semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` instead of generic `<div>`s.
- Agents/Maps use nested `<section>`s (outer section + two inner subsections each) to reflect the heading hierarchy (h2 → h3 → h4 on cards).
- Layout: `nav` uses flexbox to lay links out in a row; Favorite Agents/Maps cards use a 3-column CSS grid (`.card-grid`); All Agents/All Maps use a separate 3-column grid (`.agent-grid` / `.map-grid`) that steps down to 2 columns under 900px and 1 column under 600px.
- Map images: each map card has an `<img class="map-image">` pointing at a URL Jake supplied, marked with `data-map="<name>"`. Clicking any `.map-image` triggers `script.js`, which shows a full-screen `#lightbox` overlay (closes via the `×` button, clicking outside the image, or Escape).
- Responsive: media queries collapse grids to fewer columns on smaller screens (2 columns under 900px, 1 column under 600px for the bigger grids; cards go straight to 1 column under 600px).
- Files: `index.html`, `style.css`, and `script.js`, all living in `fan_page_v1/`.
- Deployment: not done yet — last concept, tackled once the page is finished.
