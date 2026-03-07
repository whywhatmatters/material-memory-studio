# Border Crossing Sessions page spec — border-crossing-sessions.html

## Page purpose

This page is the **detail page** for Border Crossing Sessions: a distinct coaching format within Material Memory Studio. It explains what the sessions are, who they are for, format, pricing, booking, session flow, and takeaways. The goal is to inform and convert to booking (cal.com) while keeping tone premium, reflective, and non-corporate.

## Positioning summary

- **BORDER Framework™** — Reflective structure developed by Jay Lee; each session is grounded in it.
- **Not a consultation; not a performance.** A held, unhurried conversation at the pace of genuine inquiry.
- For people **in-between** — roles, identities, countries, disciplines, or chapters of life — who need space to hold complexity without being pushed toward a premature answer.
- The session helps identify **the border you are actually standing in** (psychological, professional, relational, geographic, economic) rather than rushing toward clarity.

## Audience summary

- Artists, designers, researchers, founders, professionals moving across disciplines, geographies, or life chapters.
- People who resist easy categorisation.
- Seoul-based or able to come to Seoul in person (sessions are in-person at the studio).

---

## Current format

| Field | Value |
|-------|--------|
| **Format** | 60- or 90-minute one-on-one session |
| **Availability** | Saturdays, by appointment |
| **Location** | Hosted in-person at Material Memory Studio in Seoul |
| **Language (session)** | English or Korean |
| **Pilot** | Limited pilot; small, intentional opening — not a large-scale launch |

---

## Current pricing

- **60 minutes:** USD 180  
- **90 minutes:** USD 260  
- **Label:** "Introductory pilot pricing" / "파일럿 오프닝 가격"

(All in one block: "Session Options" with a pricing table.)

---

## Current booking flow

1. **CTA on page:** "Book Border Crossing Sessions" button → `https://cal.com/material-memory-studio-672ghg`  
   - `data-track="bcs_booking"` `data-location="bcs_detail_page"`.
2. **Supporting text:** "First sessions are available now. Select a Saturday that works for you on the booking page, where both session lengths are offered."  
   - Sub: "The booking page includes both 60-minute and 90-minute session options."
3. No other booking path is documented; booking is external (Cal.com).

---

## Current outputs / takeaways

**Two outputs (both session lengths):**

1. **Output 01 — Border Crossing Portrait**  
   Symbolic portrait centered on a body part or personal object that represents the participant’s current threshold; photographed in the studio and printed on site.

2. **Output 02 — Border Crossing Reflection Print**  
   Personalized reflection print from the session conversation, refined in-studio with AI as a supporting tool. May include: one-line threshold statement, brief reflection sheet, or conceptual print combining image and language.

**Copy note:** "Both session formats include two takeaways, with the 90-minute session allowing more depth and development in the reflection print."  
**AI framing:** "At the close of the session, your words are distilled in-studio with AI as a supporting tool — not as the center of the experience, but as a way to help you leave with a more tangible reflection of your crossing."

---

## Distinction between 60 min and 90 min

- **60 min:** Shorter; "mini coaching"; reflection print "distilled in a more concise form at the close of the session."
- **90 min:** More time for "symbolic exploration and collaborative refinement of the reflection language"; "reflection language is developed more collaboratively, with time to refine the statement together before printing"; includes "Symbolic object / body-part exploration" and "AI-assisted reflection statement creation" as distinct steps.

(See [Session flow](#session-flow-summary) below for step-by-step.)

---

## Session flow summary

**60 minutes:**

| Step | EN (flow text) | Time |
|------|-----------------|------|
| 1 | Studio intro + intention setting | 8 min |
| 2 | BORDER Framework introduction | 10 min |
| 3 | Mini coaching | 18 min |
| 4 | Symbol selection for portrait | 7 min |
| 5 | Photoshoot | 7 min |
| 6 | Wrap-up + reflection print + feedback | 10 min |

**90 minutes:**

| Step | EN (flow text) | Time |
|------|-----------------|------|
| 1 | Studio intro + intention setting | 10 min |
| 2 | BORDER Framework introduction | 15 min |
| 3 | Coaching | 25 min |
| 4 | Symbolic object / body-part exploration | 15 min |
| 5 | Photoshoot | 10 min |
| 6 | AI-assisted reflection statement creation | 10 min |
| 7 | Reflection print + wrap-up | 5 min |

**Implementation note:** The flow is implemented as **two columns** (60 min | 90 min). For bilingual, there are **duplicate DOM blocks**: `.flow-col-en` (EN) and `.flow-col-ko` (KR); Korean has its own labels ("60분", "90분") and step text. Visibility is toggled by `applyLang()`, not by `data-en`/`data-ko` (because the structure is list items). When editing flow text or times, update both EN and KO blocks.

---

## Possible reflection elements (current list)

Shown as tags; used to describe what may appear on the reflection print / in the session:

- **EN:** Today's Border, What I'm Leaving, What I'm Entering, What Wants to Emerge, A Symbol from Today, Next Courageous Step  
- **KR:** 오늘의 경계, 내가 떠나는 것, 내가 들어서는 것, 지금 피어나려는 것, 오늘의 상징, 다음의 용기 있는 한 걸음  

Plus optional note (EN/KR): "In some sessions, this may also take the form of a one-line threshold statement…"

---

## Current CTA and outbound links

| Link | Purpose | data-track | data-location |
|------|---------|------------|----------------|
| Back to homepage | Nav "← Back" / "← 돌아가기" → `index.html` (lang param added by JS) | bcs_back_to_home | bcs_detail_page |
| Book Border Crossing Sessions | Button → cal.com URL above | bcs_booking | bcs_detail_page |
| Instagram | Secondary CTA "Instagram" / @materialmemorystudio | instagram | bcs_detail_page |
| whywhatmatters.com | "For coaching essays, reflections, and newsletter" (cross-link note at bottom) | bcs_coaching_site | bcs_detail_page |

**URLs to preserve:**

- Booking: `https://cal.com/material-memory-studio-672ghg`
- Instagram: `https://www.instagram.com/materialmemorystudio/`
- Coaching site: `https://www.whywhatmatters.com/`

---

## Tracking events (BCS page)

**GA4 (gtag) and Meta Pixel (fbq)** use the same `data-track` / `data-location` pattern as the homepage.

| data-track | GA4 event | Meta event |
|------------|-----------|------------|
| instagram | instagram_click | InstagramClick |
| bcs_booking | bcs_booking_click | BCSBookingClick |
| bcs_coaching_site | bcs_coaching_site_click | BCSCoachingSiteClick |
| bcs_back_to_home | bcs_back_to_home_click | BCSBackToHomeClick |

Params: `link_url`, `link_location`. Do not remove or change these without updating the tracking script and [site-rules.md](site-rules.md).

---

## Language and tone (what to keep)

- **Premium, non-corporate** — No "sign up", "book now" pressure; keep "First sessions are available now" and "small, intentional opening."
- **Reflective** — "Think slowly", "speak without forced resolution", "hold that complexity", "unhurried conversation."
- **AI as support only** — "AI as a supporting tool", "not as the center of the experience"; do not make the session sound like an AI product.
- **BORDER Framework™** — Always use the ™ and the exact name.
- **Korean:** Natural, not over-translated; keep proper nouns (Border Crossing Sessions, BORDER Framework™) in English.

---

## Do not accidentally change

- [ ] **Location:** "Hosted in-person at Material Memory Studio in Seoul" — do not change to remote or another city unless explicitly requested.
- [ ] **Day:** "Saturdays, by appointment" — do not change to other days without explicit instruction.
- [ ] **Durations:** 60 and 90 minutes; do not add or remove options without instruction.
- [ ] **Pricing:** USD 180 / USD 260 and "Introductory pilot pricing" — do not change without instruction.
- [ ] **Booking URL:** `https://cal.com/material-memory-studio-672ghg` — do not replace or remove.
- [ ] **BORDER Framework™** — Keep exact spelling and ™.
- [ ] **Two takeaways:** Portrait + Reflection Print; do not remove or rename without instruction.
- [ ] **Tracking:** Keep all `data-track` and `data-location` on the links listed above; do not remove or rename GA4/Meta events.
- [ ] **Analytics scripts:** Same GA4 ID (G-9ZTW6LK4WY) and Meta Pixel ID (2119949305436798) as homepage — do not remove or change unless explicitly instructed.
- [ ] **Back link:** Must point to `index.html` (with lang param); do not unlink or change destination.
- [ ] **whywhatmatters.com** — Described as coaching essays, reflections, newsletter; do not repurpose this link.
