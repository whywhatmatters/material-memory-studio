# Editing rules — Material Memory Studio

Strict rules for editing the site. Follow these unless the user explicitly asks otherwise.

---

## Page structure

- **Preserve existing page structure** unless the user explicitly asks for a redesign.
- Do not remove, rename, or repurpose **section IDs** (e.g. `#hero`, `#about`, `#pillars`, `#offerings`, `#note`, `#connect`) or **nav anchors** — the nav and any in-page links depend on them.
- Do not remove or reorder **offerings** (01–06) without explicit instruction; if you add or change an offering, update `docs/website/homepage-spec.md`.

---

## Bilingual support

- **Preserve full bilingual EN/KR support.** Do not remove the language toggle (EN · KR), `setLang`/`applyLang`, `localStorage['mms-lang']`, or `?lang=` query behavior.
- **When changing copy, update both EN and KR.** Use `data-en` / `data-ko` where the page uses attribute-based switching; use the matching `.xxx-en` / `.xxx-ko` blocks where the page uses duplicate elements (e.g. coaching links, hero BCS link, flow columns and reflection tags on BCS page).
- **Internal links** from index to `border-crossing-sessions.html` and from BCS to `index.html` must continue to receive the current `lang` param via the existing `updateCrossLinks` logic — do not break that.

---

## Links between pages

- **Do not break relative links** between index.html and border-crossing-sessions.html. Links are: logo/back to `index.html`, "Explore Border Crossing Sessions" and similar to `border-crossing-sessions.html`. The script appends `?lang=en` or `?lang=ko`; leave that behavior intact.
- Do not change **outbound URL roles**: Instagram, Cal.com booking, whywhatmatters.com, jayartmaking.com/works — each has a fixed purpose (see docs/website/site-rules.md).

---

## Dependencies and tech

- Keep the site **lightweight and dependency-free.** No new frameworks, no build step, no package.json unless the user explicitly asks.
- Do not add React, Vue, a CSS framework, or a bundler unless explicitly instructed.
- Inline CSS and JS are intentional; prefer minimal edits over introducing new files or build systems.

---

## Edit scope

- **Prefer minimal, targeted edits** over broad rewrites. When asked to change one section or one string, change only that (and the corresponding KR if applicable).
- **Avoid inconsistent terminology.** Use the terms in docs/brand/voice.md and the existing copy (e.g. "Border Crossing Sessions", "BORDER Framework™", "by appointment", "in-person in Seoul").

---

## Private and location

- **Do not expose the private studio address** on the public site unless the user explicitly instructs. The site should only state city (Seoul), venue name (Material Memory Studio in Seoul), and "By Appointment."

---

## After editing

- If you changed **structure or key content**, update the relevant doc: `docs/website/homepage-spec.md` or `docs/website/border-crossing-sessions-spec.md`.
- If you added or changed **tracked links**, extend the tracking script and follow `.cursor/rules/tracking-rules.md`.
