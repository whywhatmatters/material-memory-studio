# Homepage — index.html

Notes for editing the homepage. Full section-by-section spec: `homepage-spec.md`.

## Page role

Introduce Material Memory Studio, four pillars, and current offerings. Primary CTAs: Instagram (hero + Connect), Border Crossing Sessions detail, whywhatmatters.com, jayartmaking.com/works.

## Section order

1. Nav (fixed) — Logo, About, Offerings, Connect, EN/KR.
2. Hero (#hero) — Eyebrow, title, subtitle, body, hero image (assets/images/studio-hero.jpg), Instagram CTA, BCS link.
3. About (#about) — Label, heading, body, detail row (Location, Format, Access).
4. Four Pillars (#pillars) — Intro, four cards (Artist Studio, Salon, Coaching, Material Research).
5. Offerings (#offerings) — Header, intro lines, list 01–06 (Coaching, Original Works, Studio Conversations, Material Research Archive, Workshops, Salons).
6. Note (#note) — Quote block, attribution.
7. Connect (#connect) — Heading, body, Instagram link + handle.
8. Footer — Studio name, host, year.

## Bilingual

- Most copy uses `data-en` / `data-ko`. Exceptions: coaching link note, BCS link, artist link use separate `.xxx-en` / `.xxx-ko` blocks toggled by language.
- Internal link to border-crossing-sessions.html gets `?lang=` via script.

## Tracking

Tracked links use `data-track` and `data-location`. See homepage-spec.md for CTA hierarchy and event names. Do not remove these attributes when editing links.
