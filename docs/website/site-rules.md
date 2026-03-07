# Site maintenance rules — Material Memory Studio

Rules for AI agents, developers, and future editors. Follow these when editing the site (index.html, border-crossing-sessions.html, or any new pages).

---

## Bilingual parity

- The site is **bilingual: English (EN) and Korean (KR).**
- **Preserve parity:** When you change any user-facing copy, update **both** EN and KR. Use `data-en` and `data-ko` where the site uses attribute-based switching; use separate `.xxx-en` / `.xxx-ko` elements where the implementation uses duplicate blocks.
- Do not remove the language toggle (EN · KR) or the logic that applies language (e.g. `applyLang`, `setLang`, `updateCrossLinks`, `localStorage['mms-lang']`, `?lang=` query).
- Internal links to `border-crossing-sessions.html` and `index.html` should carry the current `lang` query param so the user’s language choice persists across pages.

---

## Analytics

- **Do not remove** the Google Analytics (gtag) or Meta Pixel scripts from any page.
- **Do not change** the GA4 measurement ID or Meta Pixel ID unless the site owner explicitly instructs you to.
  - Current GA4 ID: `G-9ZTW6LK4WY`
  - Current Meta Pixel ID: `2119949305436798`
- **Preserve** existing `data-track` and `data-location` attributes on links that are used for outbound/link tracking. The tracking script relies on these; removing or renaming them will break or change events.
- If you add a **new** outbound or important internal CTA, add appropriate `data-track` and `data-location` values and extend the tracking script’s event mapping (GA4 and Meta) so the new link is measured.

---

## Brand and tone

- Keep copy consistent with **Material Memory Studio** brand: elegant, restrained, reflective, minimal. See [voice.md](../brand/voice.md).
- **Avoid** overly commercial language (e.g. "Sign up now", "Don’t miss out", countdowns).
- **Avoid** making **AI the center** of the experience. The studio and Border Crossing Sessions are human-led; AI is a supporting tool (e.g. for reflection print). Do not position the site or offerings as an "AI product" or "AI-powered" experience.
- Keep the site **minimal, elegant, and text-led.** Avoid cluttered layouts or unnecessary UI.

---

## Key facts (do not change unless instructed)

- **Border Crossing Sessions** are **in-person in Seoul** (at Material Memory Studio). Do not describe them as remote or in another city unless explicitly changed.
- **whywhatmatters.com** is for **coaching essays, reflections, and newsletter.** Do not repurpose this link for something else (e.g. booking or art).
- **jayartmaking.com/works** is for **selected works and extended archive** (art/prints). Do not repurpose this link.
- **Private address** must not be exposed on the public site unless the site owner explicitly asks for it. The site only states "Seoul", "Material Memory Studio in Seoul", "By Appointment."

---

## Destinations and links

- **Instagram:** `https://www.instagram.com/materialmemorystudio/`
- **Booking (Border Crossing Sessions):** `https://cal.com/material-memory-studio-672ghg`
- **Coaching / essays / newsletter:** `https://whywhatmatters.com` or `https://www.whywhatmatters.com/`
- **Art / works archive:** `https://www.jayartmaking.com/works`

Do not swap these roles (e.g. do not use the booking URL for "coaching essays" or the art URL for booking).

---

## Structure and docs

- When adding or removing **sections** on the homepage, update [homepage-spec.md](homepage-spec.md) so the spec stays accurate.
- When changing **Border Crossing Sessions** page content, format, pricing, or CTAs, update [border-crossing-sessions-spec.md](border-crossing-sessions-spec.md) and respect the "Do not accidentally change" checklist there.
- For **tone and vocabulary**, follow [voice.md](../brand/voice.md).

---

## Summary checklist

Before shipping edits:

- [ ] EN and KR copy updated together where applicable.
- [ ] Analytics scripts and IDs unchanged unless explicitly requested.
- [ ] `data-track` and `data-location` preserved (or correctly added for new CTAs).
- [ ] No private address or sensitive data added.
- [ ] Border Crossing Sessions still described as in-person, Seoul; whywhatmatters.com = coaching/essays; jayartmaking.com/works = works/archive.
- [ ] Tone remains minimal, elegant, non-commercial; AI is not centered as the product.
- [ ] Spec docs updated if you changed structure or key content.
