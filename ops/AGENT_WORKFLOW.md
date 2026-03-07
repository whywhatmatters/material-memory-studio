# Agent workflow — Material Memory Studio

Practical guide for AI agents (and humans) doing website edits. Use this for the usual sequence and for common tasks. (This file lives in **ops/**; brand/website reference lives in **docs/**.)

---

## How to work on this repo

1. **Read context first** — `/docs` and `.cursor/rules/` before touching HTML.
2. **Inspect the file** you will edit — confirm structure, IDs, bilingual pattern, and tracked links.
3. **Apply minimal edits** — change only what’s needed; keep EN/KR in sync when changing copy.
4. **Check parity and tracking** — Ensure no broken bilingual behavior and no missing or wrong tracking attributes.
5. **Summarize** — What changed, which files, tracking impact, bilingual parity.

---

## Recommended sequence

| Step | Action |
|------|--------|
| 1 | Read `docs/brand/voice.md`, `docs/website/site-rules.md`, and the spec for the page you’re editing (`homepage-spec.md` or `border-crossing-sessions-spec.md`). |
| 2 | Open the relevant HTML file and locate the section(s) or strings to change. Note whether copy uses `data-en`/`data-ko` or separate `.xxx-en`/`.xxx-ko` blocks. |
| 3 | Propose or apply the edit. Prefer patch-style changes (exact string or block replacement) over full-file rewrites. |
| 4 | **Check EN/KR parity** — If you changed user-facing copy, update both languages in the same edit. |
| 5 | **Check tracking** — If you changed a link that has `data-track`/`data-location`, leave them in place. If you added a new CTA that should be tracked, add attributes and extend the page’s tracking script (see `.cursor/rules/tracking-rules.md`). |
| 6 | **Summarize** — What changed, which files, whether tracking or bilingual parity was affected. Update specs in `/docs` if you changed structure or key content. |

---

## Common tasks

### Update homepage copy

- Identify the section (hero, about, pillars, offerings, note, connect) and whether the text lives in `data-en`/`data-ko` or in separate EN/KR elements.
- Replace the EN string and the KR string. Do not remove section IDs or nav anchors.
- If the change affects offerings or CTAs, update `docs/website/homepage-spec.md`.

### Update Border Crossing Sessions page

- Identify the block (e.g. intro, pilot note, session details, pricing, flow, takeaways, CTAs).
- Apply EN and KR changes. For **session flow**, remember there are two column sets (60 min / 90 min) and both EN and KR versions (`.flow-col-en` / `.flow-col-ko`); update all four if you change steps or times.
- Respect the "Do not accidentally change" checklist in `docs/website/border-crossing-sessions-spec.md` (location, day, pricing, booking URL, etc.).
- Update `docs/website/border-crossing-sessions-spec.md` if you changed format, pricing, flow, or CTAs.

### Add a CTA

- Decide if it’s internal (e.g. to another page) or outbound. Use the correct URL; do not repurpose whywhatmatters.com, jayartmaking.com/works, or the Cal.com booking URL for something else.
- Add the link. If it’s a primary or outbound CTA, add `data-track` and `data-location` and extend the tracking script on that page (see tracking-rules.md).
- If the CTA is bilingual, add both EN and KR link text (or use data-en/data-ko if it’s a single element).
- Update the relevant spec doc.

### Add a new tracked outbound link

- Add `data-track="snake_case_key"` and `data-location="short_description"` to the `<a>`.
- In the **same page’s** `<script>` that defines `GA4_EVENTS` and `META_EVENTS`, add the key and the event names (GA4: e.g. `key_click`, Meta: e.g. `KeyClick`).
- Do not duplicate an existing key on that page; keep naming consistent with existing keys.
- Document the new event in the relevant spec (homepage-spec or border-crossing-sessions-spec).

### Adjust bilingual text

- Find every place that string appears: both `data-en`/`data-ko` and any duplicate `.xxx-en`/`.xxx-ko` blocks (e.g. hero BCS link, coaching link, BCS flow columns).
- Update all EN and all KR instances so the site stays in parity. Do not leave one language outdated.

---

## Do not break

- **Language toggle** — EN · KR buttons, `setLang`, `applyLang`, `updateCrossLinks`, `localStorage['mms-lang']`, `?lang=` on internal links.
- **Relative page links** — index.html ↔ border-crossing-sessions.html and the script that appends `?lang=` to them.
- **Analytics scripts** — GA4 and Meta Pixel blocks; do not remove them or change measurement IDs unless explicitly asked.
- **Tracked CTA attributes** — `data-track` and `data-location` on existing tracked links; do not remove or rename without updating the script and docs.
- **Brand tone** — Minimal, elegant, reflective, non-commercial; AI as supporting tool only. See `.cursor/rules/content-rules.md` and `docs/brand/voice.md`.
- **Fixed link roles** — Instagram, Cal.com booking, whywhatmatters.com (coaching/essays/newsletter), jayartmaking.com/works (art archive). Do not swap or repurpose.
- **Private address** — Do not add studio street address unless explicitly instructed.
- **Section IDs** — `#hero`, `#about`, `#pillars`, `#offerings`, `#note`, `#connect`; nav and in-page links depend on them.

---

## Before deploy

- [ ] All user-facing copy changes have both EN and KR where applicable.
- [ ] No removal or unintended change to GA4/Meta scripts or measurement IDs.
- [ ] Existing tracked links still have correct `data-track` and `data-location`; any new CTA has tracking added and script updated.
- [ ] Internal links between index.html and border-crossing-sessions.html still work and pass `?lang=`.
- [ ] No private address or sensitive data added.
- [ ] Border Crossing Sessions still described as in-person, Seoul; link roles unchanged.
- [ ] Specs in `/docs` updated if structure or key content changed.
- [ ] Tone remains consistent with brand (minimal, elegant, non-commercial; AI as support only).
