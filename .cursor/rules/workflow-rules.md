# Workflow rules — Material Memory Studio

How AI agents should work in this repo. Follow this so edits are safe, consistent, and traceable.

---

## Before editing

1. **Read relevant docs** in `/docs` before changing the site:
   - **Any copy or structure change:** `docs/brand/voice.md`, `docs/website/site-rules.md`.
   - **Homepage:** `docs/website/homepage-spec.md`.
   - **Border Crossing Sessions page:** `docs/website/border-crossing-sessions-spec.md`.
2. **Inspect the current HTML** for the file you will edit. Confirm section IDs, bilingual pattern (data-en/data-ko vs .xxx-en/.xxx-ko), and any links/tracking you will touch. Prefer **precise, patch-style edits** (targeted search/replace or small blocks) over rewriting entire files.

---

## When making edits

- **Copy updates:** Propose or apply the **exact section and exact replacement** (and the matching KR if applicable). Do not rewrite surrounding paragraphs unless asked.
- **Strategy or ideas:** If the user asks for strategy, recommendations, or options, **do not silently edit code.** Propose in text or in docs; only change HTML when the user asks for implementation.
- **Code edits:** Preserve the **style and formatting** already used in the file (indentation, attribute order, class names). Match existing patterns for data-en/data-ko and for script blocks.

---

## After edits

**Summarize:**

1. **What changed** — Sections or strings updated; any new links or attributes.
2. **Which files changed** — List paths (e.g. index.html, docs/website/homepage-spec.md).
3. **Tracking** — Whether any link lost or gained `data-track`/`data-location`, or whether the tracking script was extended. If so, say so explicitly.
4. **Bilingual parity** — Whether EN and KR were both updated for the same content. If only one language was changed, state why (e.g. "user asked for EN only") or flag that KR may need a follow-up.

If the change **affects both pages** (e.g. a shared convention or a cross-link), say that explicitly in the summary.

---

## When to ask, not guess

- **Ambiguous requests** — If the user’s request could apply to multiple sections or both languages, ask for clarification instead of guessing (e.g. "Do you want this in both EN and KR?" or "Should this replace the hero subtitle or the about intro?").
- **Conflicts with rules** — If the user asks for something that conflicts with these rules (e.g. remove analytics, expose address, add a framework), confirm before doing it or explain the conflict and ask how to proceed.
- **Structural changes** — If the user asks for a redesign, new sections, or new pages, clarify scope before rewriting large portions of the site.

---

## Cross-references

- **Editing constraints:** `.cursor/rules/editing-rules.md`
- **Content and tone:** `.cursor/rules/content-rules.md`
- **Tracking:** `.cursor/rules/tracking-rules.md`
- **End-to-end workflow:** root-level `AGENT_WORKFLOW.md`
