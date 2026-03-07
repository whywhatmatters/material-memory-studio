# Homepage spec — index.html

## Page purpose

The homepage introduces Material Memory Studio as a private studio and salon in Seoul. It establishes the four pillars (Artist Studio, Salon, Coaching, Material Research), explains current appointment-based offerings, and directs visitors to Border Crossing Sessions, Instagram, whywhatmatters.com, and jayartmaking.com/works as appropriate.

## Primary audiences

- People seeking reflective coaching (especially Border Crossing Sessions).
- Artists, designers, researchers, founders, practitioners interested in studio offerings, works, or dialogue.
- Visitors who want to follow the studio (Instagram) or read coaching/reflections (whywhatmatters.com).

---

## Section-by-section structure (current order)

### 1. Nav (fixed)

- **Section/label:** Global nav; not a content section.
- **Purpose:** Site identity and main jump links; language toggle EN/KR.
- **Current content:**
  - Logo/link: "Material Memory Studio" → `#hero`.
  - Links: About → `#about`, Offerings → `#offerings`, Connect → `#connect`.
  - Language: EN · KR (buttons `#btn-en`, `#btn-ko`; `setLang('en')` / `setLang('ko')`).
- **Bilingual:** Link text via `data-en` / `data-ko`: "About" / "소개", "Offerings" / "프로그램", "Connect" / "연결".
- **Tracking:** None on nav links (internal anchors).

---

### 2. Hero — `#hero`

- **Section id:** `#hero`.
- **Purpose:** Main headline, positioning, and primary CTAs.
- **Current messaging summary:**
  - Eyebrow: "Private Studio & Salon" / "프라이빗 스튜디오 & 살롱".
  - Title: "Material **Memory** Studio" (three lines, *Memory* in italics).
  - Subtitle (serif, italic): "A space for art, tech/AI-informed coaching, and material research — for making, conversation, and border-crossing."
  - Body: Private studio and salon in Seoul for coaching, reflection, creative practice, research, prints, and experimental dialogue.
  - Image label: "Seoul Studio — Spring 2026" / "서울 스튜디오 — 2026년 봄".
- **CTAs (order matters):**
  1. **Instagram** — Primary button (underline style).  
     URL: `https://www.instagram.com/materialmemorystudio/`  
     `data-track="instagram"` `data-location="hero_button"`.
  2. **Border Crossing Sessions** — Secondary text link.  
     `href="border-crossing-sessions.html"` (lang param appended by JS).  
     EN: "Explore Border Crossing Sessions →"  
     KR: "Border Crossing Sessions 자세히 보기 →"  
     Implemented as two wrappers: `.hero-bcs-link-en` and `.hero-bcs-link-ko` (visibility toggled by language).  
     `data-track="border_crossing_detail"` `data-location="hero_secondary_cta"`.
- **Tracking:** See [CTA hierarchy and tracking](#cta-hierarchy-and-tracking) below.

---

### 3. About — `#about`

- **Section id:** `#about`.
- **Purpose:** Explain what the studio is, who it’s for, and how it operates.
- **Current messaging summary:**
  - Label: "About the Studio" / "스튜디오 소개".
  - Heading: "Where materials, memory, and *practice meet.*" (line breaks after each phrase).
  - Body (three paragraphs): Private research studio and salon; material culture, artistic practice, border-crossing conversations; hosted by Jay Lee, Seoul; operates across artistic practice, coaching, material research; welcomes artists, designers, founders, practitioners, researchers, professionals; some formats by appointment (coaching, studio conversations), others in development (material-led workshops, salon gatherings); gradual opening.
  - Detail row: Location "Seoul, Korea", Format "Private Studio", Access "By Appointment".
- **Links / CTAs:** None in this section.
- **Tracking:** None.

---

### 4. Four Pillars — `#pillars`

- **Section id:** `#pillars`.
- **Purpose:** Define the studio’s four pillars that shape research, practice, and programs.
- **Current messaging summary:**
  - Label: "Four Pillars" / "네 개의 기둥".
  - Intro heading: "The studio is shaped by four intersecting pillars."
  - Intro sub: "Together, these pillars shape the studio's research, practice, and evolving programs."
  - Cards (Roman numerals I–IV):
    - **I — Artist Studio:** Jay Lee's practice across materials, prints, research, works.
    - **II — Salon:** Conversation platform for visiting speakers, gatherings, talks.
    - **III — Coaching:** Distinctive layer centered on Border Crossing Sessions and transitional inquiry.
    - **IV — Material Research:** Material archive, biomaterial exploration, regional materials.
- **Links / CTAs:** None.
- **Tracking:** None.

---

### 5. Offerings — `#offerings`

- **Section id:** `#offerings`.
- **Purpose:** List current and upcoming studio offerings; drive to BCS detail, whywhatmatters.com, jayartmaking.com/works.
- **Offerings logic (current):**
  - **Current offerings** = appointment-based formats the studio runs now.
  - **Currently available by appointment:** Border Crossing Sessions, Studio Conversations, selected original works and prints.
- **Header:**
  - Title: "Studio Offerings" / "스튜디오 프로그램".
  - Note: "All sessions by appointment" / "모든 세션은 예약제로 운영됩니다".
  - Two intro lines (small, muted): (1) Current offerings reflect present appointment-based formats, beginning with coaching and conversation. (2) *Currently available by appointment: Border Crossing Sessions, Studio Conversations, and selected original works and prints.*

**Offerings list (keep order and numbering):**

| Num | Name (EN/KR) | Summary | Tag | CTAs / links |
|-----|----------------|--------|-----|---------------|
| 01 | Coaching / 코칭 | Private coaching for transition, reinvention, leadership; Border Crossing Sessions (BORDER Framework™); may include symbolic portrait + AI-assisted reflection print in studio. | Limited pilot booking | whywhatmatters.com (data-track: coaching_site, data-location: coaching_section); border-crossing-sessions.html (data-track: border_crossing_detail, data-location: coaching_offering_detail). |
| 02 | Original Artworks & Art Prints / 오리지널 아트워크 & 아트 프린트 | Original works and photographic prints; studio practice and nomadic archive; materials hold memory. | Original works & limited editions | jayartmaking.com/works (data-track: artist_site, data-location: original_works_section). |
| 03 | Studio Conversations / 스튜디오 대화 | Intimate, appointment-based dialogue; not consultation. | Appointment only | None. |
| 04 | Material Research Archive / 소재 리서치 아카이브 | Evolving archive; material references, biomaterial, pigments, etc. | In development | None. |
| 05 | Material-led Art Workshops / 소재 기반 아트 워크숍 | Jay Lee–led; natural, historical, local materials; making, cooking, transformation. | Upcoming, starting in April / 4월부터 시작 예정 | None. |
| 06 | Future Salons & Guest Hosts / 살롱 & 게스트 호스트 | Workshops, talks, events with international network. | Upcoming, starting in May / 5월부터 시작 예정 | None. |

- **Coaching (01) copy details:** Two paragraphs; second in italics for BORDER Framework™ and Border Crossing Sessions; third paragraph on studio-based format (symbolic portrait, AI-assisted reflection print). Then two link lines: (1) "For coaching essays, reflections, and newsletter: whywhatmatters.com" (EN) / "코칭 에세이, 성찰, 뉴스레터: whywhatmatters.com" (KR). (2) "Explore Border Crossing Sessions →" / "Border Crossing Sessions 자세히 보기 →". Implemented with `.coaching-link-en` / `.coaching-link-ko`, `.bcs-link-en` / `.bcs-link-ko` (visibility by language).
- **Tracking:** See [CTA hierarchy and tracking](#cta-hierarchy-and-tracking).

---

### 6. Note (quote block) — `#note`

- **Section id:** `#note`.
- **Purpose:** Short, memorable one-line positioning; dark background.
- **Current messaging:** Quote: "Material Memory Studio is a space for making, conversation, and border-crossing — where art, coaching, and technology meet. Open by appointment." Attribution: "Seoul — Spring 2026".
- **Links / CTAs:** None.
- **Tracking:** None.

---

### 7. Connect — `#connect`

- **Section id:** `#connect`.
- **Purpose:** Encourage following the studio on Instagram; explain that updates and appointments are often shared there first.
- **Current messaging summary:**
  - Label: "Connect" / "연결".
  - Heading: "Follow the studio *as it unfolds.*"
  - Body: Follow ongoing process, selected works and prints, program announcements; updates, appointments, collaboration shared there first.
  - Instagram link: "Instagram" + handle @materialmemorystudio (both clickable).
- **CTAs:**  
  - Same Instagram URL.  
  - `data-track="instagram"` `data-location="connect_label"` on the main link.  
  - `data-track="instagram"` `data-location="connect_handle"` on the handle link.
- **Tracking:** See below.

---

### 8. Footer

- **Purpose:** Studio name, host, year.
- **Current content:** "Material Memory Studio"; "Hosted by Jay Lee" / "Jay Lee 운영"; "© 2026".
- **Tracking:** None.

---

## CTA hierarchy and tracking

**Intended priority:**

1. **Instagram** — Hero button + Connect section (primary follow channel).
2. **Border Crossing Sessions** — Hero secondary + Offering 01 detail link (main bookable offering).
3. **whywhatmatters.com** — Coaching essays, reflections, newsletter (Offering 01 only).
4. **jayartmaking.com/works** — Selected works and extended archive (Offering 02 only).

**Tracking attributes (preserve when editing):**

- All outbound and key internal links use `data-track` and `data-location`.
- **GA4 (gtag):** Events are derived from `data-track`: `instagram_click`, `coaching_site_click`, `artist_site_click`, `border_crossing_detail_click`. Params: `link_url`, `link_location`.
- **Meta Pixel (fbq):** Custom events: `InstagramClick`, `CoachingSiteClick`, `ArtistSiteClick`, `BorderCrossingDetailClick`. Same params.
- Do not remove these attributes or change IDs when updating copy or links. See [site-rules.md](site-rules.md).

**Current mapping:**

| data-track              | data-location (examples)     | GA4 event                   | Meta event              |
|-------------------------|-------------------------------|-----------------------------|--------------------------|
| instagram               | hero_button, connect_label, connect_handle | instagram_click             | InstagramClick          |
| border_crossing_detail   | hero_secondary_cta, coaching_offering_detail | border_crossing_detail_click | BorderCrossingDetailClick |
| coaching_site           | coaching_section              | coaching_site_click         | CoachingSiteClick        |
| artist_site             | original_works_section        | artist_site_click           | ArtistSiteClick         |

---

## Bilingual implementation (homepage)

- **Mechanism:** `data-en` and `data-ko` on elements; `applyLang(lang)` sets `innerHTML` from `data-{lang}`. Some blocks use duplicate elements (e.g. `.coaching-link-en` / `.coaching-link-ko`, `.hero-bcs-link-en` / `.hero-bcs-link-ko`) and are shown/hidden by language.
- **Persistence:** `localStorage['mms-lang']` and `?lang=` query; cross-links to `border-crossing-sessions.html` get `?lang=ko` or `?lang=en` via `updateCrossLinks(lang)`.
- **Parity:** When updating copy, update both EN and KR for the same section so the site stays in parity.

---

## Future update notes

- **Offerings:** If new formats go live (e.g. workshops, salons), add or renumber rows and update the intro line "Currently available by appointment" and the italic line listing them. Keep "All sessions by appointment" and "Current offerings reflect…" logic unless the model changes.
- **Pillars:** Text can be refined; structure (four cards, Roman numerals) should stay unless the brand explicitly changes pillars.
- **Hero:** If the main tagline or subtitle changes, keep "tech/AI-informed" and "material research" and "border-crossing" in some form to stay aligned with [voice.md](../brand/voice.md). Keep primary CTA (Instagram) and secondary (Border Crossing Sessions).
- **Analytics:** Do not remove or rename `data-track` / `data-location`; add new ones for new CTAs if needed, and extend the tracking script mapping.
- **New sections:** If a new section is added, give it a stable `id` and consider adding a nav link; document section id, purpose, and any new CTAs/tracking here.
