# Deploy Checklist

Use this before, during, and after editing, and before/after deploying to Vercel.

---

## Before editing

- [ ] Read `.cursor/rules/*` (project-overview, editing-rules, content-rules, tracking-rules, workflow-rules).
- [ ] Read `ops/AGENT_WORKFLOW.md`.
- [ ] Inspect current file(s) you will change (section IDs, bilingual pattern, tracked links).
- [ ] Confirm which page(s) should change (index.html, border-crossing-sessions.html, or both).
- [ ] Confirm whether EN and KR both need updates for your change.
- [ ] Confirm whether any link you’re touching has tracking (data-track / data-location) and whether you are adding a new CTA.

---

## During editing

- [ ] Preserve page structure unless the change is an intentional redesign (section IDs, nav anchors, offerings order).
- [ ] Preserve GA4 and Meta Pixel script blocks and measurement IDs (G-9ZTW6LK4WY, 2119949305436798).
- [ ] Preserve data-track and data-location on existing tracked links; if adding a new CTA, add attributes and extend the page’s tracking map.
- [ ] Preserve relative links between index.html and border-crossing-sessions.html and the ?lang= behavior.
- [ ] Preserve language toggle behavior (EN · KR, setLang, applyLang, localStorage, updateCrossLinks).
- [ ] Keep brand tone consistent (see COPY_SOURCE_OF_TRUTH.md and .cursor/rules/content-rules.md).

---

## After editing

- [ ] Verify English and Korean parity for any copy you changed (both data-en/data-ko and any .xxx-en/.xxx-ko blocks).
- [ ] Verify no accidental wording drift in brand terminology (BORDER Framework™, Border Crossing Sessions, in-person Seoul, etc.).
- [ ] Verify new or modified links open correctly and point to the right URLs (Instagram, Cal.com, whywhatmatters.com, jayartmaking.com/works — roles unchanged).
- [ ] Verify tracking keys on tracked links still match the GA4_EVENTS and META_EVENTS maps on that page.
- [ ] Verify no broken internal links (index ↔ border-crossing-sessions; back link on BCS page).
- [ ] Verify no accidental private address or sensitive data added.
- [ ] Verify no unintended structural changes (e.g. removed section, reordered offerings without explicit request).
- [ ] If you changed structure or key content, update the relevant doc in `docs/website/` (homepage-spec.md or border-crossing-sessions-spec.md).

---

## Pre-deploy browser check

Quick manual pass before you consider the deploy done:

- [ ] Homepage loads (index.html or production URL).
- [ ] Border-crossing-sessions page loads from homepage link and from direct URL.
- [ ] Hero CTA (Instagram) works; hero secondary CTA (Border Crossing Sessions) goes to BCS page with ?lang= when applicable.
- [ ] Offerings CTAs work: whywhatmatters.com, jayartmaking.com/works, Border Crossing Sessions detail link.
- [ ] Instagram links work from Connect (homepage) and from BCS page.
- [ ] Language toggle works on both pages (EN/KR switch; copy and link text update; ?lang= persists on cross-navigation).
- [ ] Tracked links still have data-track and data-location attributes (inspect in dev tools if needed).
- [ ] Mobile/narrow layout still looks reasonable (no overflow, nav readable).

---

## Vercel deploy steps

1. **Review git diff** — Confirm only intended files and lines changed; no stray edits or removed scripts.
2. **Commit changes** — Clear commit message (e.g. "Update hero body copy (EN/KR)" or "Add newsletter CTA and tracking").
3. **Deploy with Vercel** — Push to the branch Vercel uses (e.g. main); or trigger deploy from Vercel dashboard if you deploy from there.
4. **Open production URL** — Use the live site URL (e.g. from Vercel project).
5. **Test both pages** — Homepage and Border Crossing Sessions; EN and KR; key CTAs.
6. **Spot-check analytics** — If you have GA4/Meta dashboards, confirm that key events (e.g. instagram_click, border_crossing_detail_click, bcs_booking_click) still fire when you click the relevant links (optional but recommended).

---

## Post-deploy log

Fill this in after each deploy for a quick history.

| Field | Value |
|-------|--------|
| **Date** | |
| **What changed** | |
| **Files changed** | |
| **Tracking affected?** | yes / no |
| **EN/KR checked?** | yes / no |
| **Production URL checked?** | yes / no |
| **Notes** | |
