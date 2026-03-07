# Tracking rules — Material Memory Studio

Rules for analytics and link tracking. The site uses GA4 (gtag) and Meta Pixel with custom events driven by `data-track` and `data-location` on links.

---

## Do not remove or change without explicit instruction

- **Never remove** the existing GA4 (gtag) or Meta Pixel script blocks from index.html or border-crossing-sessions.html.
- **Do not change** the measurement IDs unless the user explicitly asks.
  - GA4: `G-9ZTW6LK4WY`
  - Meta Pixel: `2119949305436798`

---

## data-track and data-location

- **Preserve** existing `data-track` and `data-location` attributes on all links that are currently tracked. The inline script on each page reads these and sends events to GA4 and Meta; removing or renaming them will break or change reporting.
- **When editing a link** that already has `data-track` and `data-location`, keep those attributes on the same element (e.g. when changing href or link text).
- **Naming style:** Lowercase with underscores (e.g. `border_crossing_detail`, `coaching_site`). GA4 event names are derived (e.g. `border_crossing_detail_click`); Meta uses PascalCase (e.g. `BorderCrossingDetailClick`). Do not introduce new naming styles.

---

## Adding a new tracked link

- Add tracking **only if** the link is a meaningful CTA (e.g. outbound to Instagram, booking, whywhatmatters.com, jayartmaking.com/works) or an important internal CTA (e.g. to Border Crossing Sessions detail). Do not track every link.
- **Steps:**
  1. Add `data-track="unique_key"` and `data-location="descriptive_location"` to the `<a>`.
  2. In the **same page’s** script block, add the key to both `GA4_EVENTS` and `META_EVENTS` with the desired event names. Follow existing pattern: GA4 = `key_click` or similar, Meta = PascalCase (e.g. `UniqueKeyClick`).
  3. Ensure the key is **unique** on that page and does not conflict with existing keys (each page has its own script and its own event map).
- **Do not** create arbitrary or duplicate tracking keys. Keep keys aligned with current style (e.g. `instagram`, `coaching_site`, `artist_site`, `border_crossing_detail` on homepage; `bcs_booking`, `bcs_coaching_site`, `bcs_back_to_home`, `instagram` on BCS page).

---

## Reference

- Homepage tracked links and event names: see `docs/website/homepage-spec.md` (CTA hierarchy and tracking table).
- BCS page tracked links and event names: see `docs/website/border-crossing-sessions-spec.md` (Tracking events section).
- High-level rules: `docs/website/site-rules.md` (Analytics section).

When in doubt, **preserve** existing attributes and **extend** the maps only for new CTAs that match site conventions.
