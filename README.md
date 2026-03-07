# Material Memory Studio — Website

Static website for **Material Memory Studio**, a private studio and salon in Seoul. Bilingual (EN/KR), minimal, text-led. Deployed on Vercel.

## Structure

- **index.html** — Homepage (hero, about, four pillars, offerings, connect).
- **border-crossing-sessions.html** — Detail page for Border Crossing Sessions (coaching format).
- **assets/images/** — Image assets (e.g. studio-hero.jpg).
- **docs/** — Brand and website reference docs.
- **ops/** — Workflow and deployment: AGENT_WORKFLOW.md, COPY_SOURCE_OF_TRUTH.md, DEPLOY_CHECKLIST.md, UPDATE_REQUEST_TEMPLATE.md.
- **.cursor/rules/** — Cursor AI rules for editing and content.

## Deploy

Push to the connected Vercel project; no build step. Root HTML files and assets must stay at paths Vercel serves from project root.

## Edits

Read `ops/AGENT_WORKFLOW.md` and `.cursor/rules/` before changing the site. Use `ops/UPDATE_REQUEST_TEMPLATE.md` when requesting updates.
