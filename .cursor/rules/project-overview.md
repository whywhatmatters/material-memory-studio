# Project overview — Material Memory Studio

## What this repo is

Static website for **Material Memory Studio**: a private studio and salon in Seoul at the intersection of art, coaching, and material research. The site is minimal, text-led, and bilingual (English / Korean). Deployed on **Vercel**. No build step; plain HTML, CSS, and a small amount of inline JavaScript.

## Primary files

- **index.html** — Homepage: hero, about, four pillars, offerings, quote block, connect, footer.
- **border-crossing-sessions.html** — Detail page for Border Crossing Sessions (coaching format): positioning, format, pricing, booking, session flow, takeaways.
- **assets/images/studio-hero.jpg** — Hero background image (referenced from index.html).
- **docs/** — Brand and website reference: `docs/brand/` (e.g. brand-strategy.md, voice.md), `docs/website/` (site-map.md, page-copy-index.md, page-notes/, homepage-spec.md, border-crossing-sessions-spec.md, site-rules.md).
- **ops/** — Workflow and deployment: AGENT_WORKFLOW.md, COPY_SOURCE_OF_TRUTH.md, DEPLOY_CHECKLIST.md, UPDATE_REQUEST_TEMPLATE.md.

## What the site represents

- A **private** studio and salon (by appointment), not a public venue.
- **Four pillars:** Artist Studio, Salon, Coaching, Material Research.
- **Offerings:** Border Crossing Sessions (pilot), Studio Conversations, original works/prints, and future formats (workshops, salons) — all described as appointment-based or upcoming.
- **Outbound links:** Instagram, Cal.com booking, whywhatmatters.com (coaching/essays/newsletter), jayartmaking.com/works (art archive). Roles of these links are fixed; do not repurpose them.

## Likely audiences

- People interested in **reflective coaching** (especially Border Crossing Sessions).
- Artists, designers, researchers, founders, practitioners looking for studio offerings, works, or dialogue.
- Visitors who want to **follow** the studio (Instagram) or **read** (whywhatmatters.com).

## Most likely future updates

- **Copy tweaks** — Messaging, dates (e.g. "Spring 2026"), or offering descriptions on homepage or BCS page.
- **Bilingual text** — Adding or refining EN/KR strings; must keep parity.
- **New CTAs or links** — If a new outbound link is added, it may need tracking (data-track / data-location) and doc updates.
- **Offerings list** — Adding or updating offerings (e.g. when workshops or salons launch); updating "currently available" line.
- **Pricing or format** — BCS page: pricing, duration, booking URL, or session flow; must stay in sync with docs and "Do not accidentally change" in border-crossing-sessions-spec.md.
- **Analytics** — Only if explicitly asked (e.g. new events); never remove or change IDs without instruction.

No frameworks, no new build systems, and no structural redesign unless explicitly requested. Prefer minimal, patch-style edits.
