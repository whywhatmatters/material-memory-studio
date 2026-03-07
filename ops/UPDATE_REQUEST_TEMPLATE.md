# Update Request Template

Copy this template when asking Cursor to make a website update. Fill in the sections that apply.

---

## Goal

_Short description of what you want to change._

---

## Page(s)

- [ ] index.html
- [ ] border-crossing-sessions.html
- [ ] both
- [ ] other: ______

---

## Type of change

- [ ] copy only
- [ ] layout / styling
- [ ] new CTA
- [ ] tracking
- [ ] bilingual update
- [ ] section reorder
- [ ] other: ______

---

## Exact section(s)

_Specify the section name, heading, class, or nearby text so the agent can locate it._

Examples: "Hero subtitle (the italic line under the title)", "Offering 01 — Coaching, second paragraph", "BCS page — Session Flow, 60 min column", "#connect section body text".

---

## What should stay unchanged

_List anything that must remain untouched (e.g. "Do not change pricing or booking URL", "Keep section IDs", "Do not touch tracking on existing links")._

---

## New copy / direction

_Paste the desired new copy, messaging, or intent. If EN only, say so and whether KR should follow later._

---

## Tracking impact

- [ ] no tracking change
- [ ] preserve existing tracking on edited links
- [ ] add tracking to new CTA (specify data-track key and data-location)
- [ ] update tracking map (e.g. new event name)

---

## EN / KR handling

- [ ] update both EN and KR
- [ ] update EN only for now
- [ ] update KR only
- [ ] propose KR after EN is approved

---

## Output format I want from the agent

- [ ] apply changes directly
- [ ] show exact patch first (diff or search/replace)
- [ ] propose copy before editing
- [ ] summarize changed lines / sections only

---

## Final checks

- [ ] preserve brand tone (see COPY_SOURCE_OF_TRUTH.md / .cursor/rules/content-rules.md)
- [ ] preserve bilingual behavior (language toggle, ?lang= on internal links)
- [ ] preserve relative links (index.html ↔ border-crossing-sessions.html)
- [ ] preserve GA4 / Meta Pixel scripts and IDs
- [ ] preserve data-track and data-location conventions on existing tracked links

---

# Example 1: Homepage copy update

**Goal:** Update the hero body paragraph to mention that the studio also welcomes people in career transition.

**Page(s):** index.html

**Type of change:** copy only

**Exact section(s):** Hero — the body paragraph after the italic subtitle (starts "A private studio and salon in Seoul for coaching…"). Both `data-en` and `data-ko` on that `<p>`.

**What should stay unchanged:** Hero title, subtitle, eyebrow, image label, both CTAs (Instagram + Border Crossing Sessions link). Section id `#hero`. All tracking attributes on the two hero links.

**New copy / direction:**
- EN: "A private studio and salon in Seoul for coaching, reflection, creative practice, research, prints, and experimental forms of dialogue. It welcomes those in career transition as well as artists and practitioners."
- KR: _[Provide or ask agent to propose after EN is approved.]_

**Tracking impact:** no tracking change

**EN / KR handling:** update both EN and KR (or EN first, then KR in a follow-up)

**Output format:** apply changes directly; then summarize what was changed.

**Final checks:** all checked.

---

# Example 2: Border Crossing Sessions update

**Goal:** Soften the pilot note so it doesn’t say "first paid sessions" and instead says "sessions are now available."

**Page(s):** border-crossing-sessions.html

**Type of change:** copy only

**Exact section(s):** Pilot note block (`.pilot-note`) — the single paragraph inside it. Has `data-en` and `data-ko`.

**What should stay unchanged:** Format, pricing, booking URL, session flow, takeaways, all CTAs and tracking. BORDER Framework™ spelling. "In-person in Seoul" and "Saturdays, by appointment."

**New copy / direction:**
- EN: "Now open in a limited pilot format — sessions are available on Saturdays, by appointment. This is a small, intentional opening, not a large-scale launch."
- KR: _[Agent to propose equivalent.]_

**Tracking impact:** no tracking change

**EN / KR handling:** update both EN and KR

**Output format:** apply changes directly; summarize changed section.

**Final checks:** all checked.

---

# Example 3: Add a new CTA with tracking

**Goal:** Add a text link in the Connect section (homepage) to a new newsletter signup page at example.com/newsletter. The link should be tracked.

**Page(s):** index.html

**Type of change:** new CTA + tracking

**Exact section(s):** #connect — after the Instagram link and handle, add a new line with the newsletter link.

**What should stay unchanged:** Everything else in #connect. Instagram link and its data-track/data-location. Section structure. Language toggle.

**New copy / direction:**
- EN: "Newsletter: [sign up here](https://example.com/newsletter)"
- KR: "뉴스레터: [여기서 가입](https://example.com/newsletter)"  
Use a class that fits existing link styling (e.g. subtle link). Ensure the link is inside elements that are toggled by language (or use data-en/data-ko if it’s a single element).

**Tracking impact:** add tracking to new CTA. Suggest: data-track="newsletter_signup", data-location="connect_section". Add these keys to the GA4_EVENTS and META_EVENTS maps in index.html (e.g. newsletter_signup_click, NewsletterSignupClick).

**EN / KR handling:** update both EN and KR

**Output format:** apply changes; list the new link, new attributes, and the two new script map entries.

**Final checks:** all checked.
