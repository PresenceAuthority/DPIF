# TPA Website — Staging Review Fixes
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Brand reference: `TPA_SKILL.md` in project context — read it before starting
- Constraint: surgical edits only. Do not rewrite surrounding HTML. Do not
  introduce CSS class names not already present in the file. Do not alter
  nav or footer structure unless explicitly instructed.
- Calendly URL (canonical): `https://calendly.com/bradley-thepresenceauthority/30min`
- Icon system: all icons are inline SVG, viewBox="0 0 28 28", stroke-based,
  iridescent gradient fills. Gradient IDs must be namespaced per icon instance.
  Namespace prefix convention: 2–4 chars based on icon name (e.g. `fr_` for
  Framework, `au_` for Audit). See TPA_SKILL.md Section 6 for full catalogue.

---

## EXECUTION PROTOCOL

1. Clone repo and `cd DPIF`
2. Read `TPA_SKILL.md` in full before processing any file
3. Process each change ID in order
4. Read only the target file before making its changes — do not load multiple
   files simultaneously
5. For sidebar changes (IDs 10, 12, 14): before editing the target file, first
   read `site/assessment.html` to extract the current sidebar HTML pattern and
   its associated CSS. Use that exact pattern on all sidebar targets.
6. Agent behaviour:
   - `autonomous` — execute and continue
   - `stop` — output proposed change in full, wait for explicit approval
7. After all changes: increment version token in each modified file, then
   single commit and push

---

## CHANGE MANIFEST

### FILE: site/index.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 01 | Nav element `.topbar-cta` — the "Request a Consultation" button in the topbar | Confirm `href` points to `https://calendly.com/bradley-thepresenceauthority/30min` with `target="_blank" rel="noopener"`. If it points to `/contact` or any other URL, replace with the Calendly URL. | `autonomous` |
| 02 | Hero section — any CTA button or link with text "Request a Consultation" or equivalent within the hero `<section>` | Same as ID 01: confirm or replace href with Calendly URL, `target="_blank" rel="noopener"`. | `autonomous` |
| 03 | The section containing the Pilot Programme content (look for section-label text "Pilot Programme" or heading text containing "Pilot") | Remove the entire `<section>` block from opening to closing tag. Output the first and last line of what you are about to delete before removing it. | `stop` |
| 04 | Every `<span class="section-label">` element in the file | For each one, check whether its CSS renders a 32px violet `::before` bar. The correct CSS is: `.section-label { display:flex; align-items:center; gap:12px; } .section-label::before { content:''; width:32px; height:1px; background:var(--vs); flex-shrink:0; }`. If the class CSS in this file is missing `display:flex` or the `::before` rule, add the missing CSS to the existing `.section-label` rule in the `<style>` block. Do not add inline styles to individual elements. Output the current `.section-label` CSS before and after your change. | `stop` |
| 05 | The section with section-label "The Framework" or equivalent — the section containing the 5 governance principle cards | Read the current icon state for each card. Map each principle to the icon catalogue from TPA_SKILL.md. The five principles correspond to: Identity → `Identity` icon; Authority → `Authority` icon; Consent → `Consent` icon; Disclosure → create new icon (eye with line beneath: circle at top + horizontal line below, stroke-based, 28×28); Containment → `Traceability` icon. Replace broken or missing icons with the correct inline SVG from the catalogue. Use size `width:36px;height:36px` (`.principle-icon` context). Namespace gradient IDs with 2-char prefix per icon (e.g. `id_` for Identity, `au_` for Authority, `co_` for Consent, `di_` for Disclosure, `tr_` for Traceability). Output the current icon state for each card before proposing replacements. | `stop` |
| 06 | The section containing the published instruments list or cards (look for instrument names: Control Model, Control Checklist, Context Risk Classification, Deployment Lifecycle, Conflict Resolution, Posthumous, Scoring Rubric) | Add an icon to each instrument card using the following mapping and the `.inst-icon` size (28×28px). Use the inline SVG paths from TPA_SKILL.md Section 6: Control Model → `Framework` icon (prefix `fm_`); Control Checklist → `Verified` icon (prefix `ve_`); Context Risk Classification Annex → `Risk Tier` icon (prefix `rt_`); Deployment Lifecycle Specification → `Lifecycle` icon (prefix `lc_`); Inter-Deployment Conflict Resolution Framework → `Conflict` icon (prefix `cf_`); Posthumous and Incapacitated Principal Governance → `Posthumous` icon (prefix `po_`); Scoring Rubric → `Audit` icon (prefix `ad_`). Insert each icon as the first child element inside the card, before the card title. Output current card structure before adding icons. | `stop` |
| 07 | The `<body>` or outermost content wrapper — assess whether a sticky sidebar navigation element exists on this page | Read `site/assessment.html` first to extract the exact sidebar HTML and CSS. Then apply the identical pattern to `index.html`, adapting the anchor links to match the actual section IDs present on the homepage. Output the sidebar HTML you are about to add before inserting it. | `stop` |

---

### FILE: site/framework.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 08 | The `<h1>` element in the hero section — which contains both plain white text and gradient-styled text | The gradient portion must be wrapped in a `<span>` with these inline styles: `style="background:linear-gradient(135deg,#9888c0,#7ab89a,#c9a8b8,#c8b890);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;display:inline;"`. The white portion must also be a `<span>` with `style="color:var(--tx);display:inline;"`. Confirm both spans use `display:inline` so line breaks fall naturally within the inline flow rather than between gradient resets. Output the current `<h1>` HTML before and after. | `stop` |
| 09 | Hero section body copy — the paragraph(s) of text beneath the H1 | On first use of the term "Digital Representation of a Real Person" or "DRRP", introduce the acronym. If the term appears in full, add `(DRRP)` immediately after it. If only "DRRP" appears without prior expansion, insert a sentence before first use: `"A Digital Representation of a Real Person (DRRP) is an AI-mediated or digitally generated system replicating or simulating the likeness, voice, or communicative presence of an identifiable natural person."` Do not alter surrounding copy. | `autonomous` |

---

### FILE: site/white-paper.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 10 | The sidebar navigation element on this page | Read `site/assessment.html` to extract the working sidebar pattern (HTML + CSS). Compare against the white-paper.html sidebar implementation. Identify the specific difference causing inconsistent behaviour (missing CSS, incorrect JS, wrong class names, missing section IDs on target sections). Apply the fix only — do not replace the entire sidebar block unless the structure is fundamentally wrong. Output: current white-paper sidebar HTML, assessment sidebar HTML, and the specific diff you are applying. | `stop` |

---

### FILE: site/assessment.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 11 | The `<body>` or outermost content wrapper — assess whether a sticky sidebar navigation element exists | If sidebar is absent: read the sidebar pattern from this file's own structure (it is the reference page) — then confirm it is present and correctly wired. If it is already present and working, output "Sidebar confirmed present — no change made." If something is broken, apply the fix. | `stop` |

---

### FILE: site/services.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 12 | The hero section — any `<span>` or `<p>` element containing the text "No registration" or "No data collected" adjacent to CTA buttons | Remove the element entirely. This text does not belong in the services hero. Output the element you are removing before deletion. | `autonomous` |
| 13 | Bottom of page content (above footer) — any `<span>` or `<p>` element containing the text "No registration" or "No data collected" | Remove the element entirely. Output what you are removing before deletion. | `autonomous` |
| 14 | The section headed "Book a Consultation" or equivalent — the section that conflates consultation booking and assessment actions | Output the current section HTML in full. Do not make changes until approved. Flag the specific copy or structural elements that mix consultation and assessment messaging. | `stop` |
| 15 | The topbar nav within this file — the `<a>` element linking to `/services` | Add `class="topbar-link active"` (replacing `class="topbar-link"`) to the Services nav link only. Then add the following CSS to the `<style>` block if not already present: `.topbar-link.active { color: var(--tx); }` | `autonomous` |

---

### FILE: site/about.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 16 | The `<h1>` element in the hero section containing both white and gradient text | Apply the same fix as ID 08: wrap white text in `<span style="color:var(--tx);display:inline;">` and gradient text in `<span style="background:linear-gradient(135deg,#9888c0,#7ab89a,#c9a8b8,#c8b890);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;display:inline;">`. Output before and after. | `stop` |
| 17 | Any enquiry form or contact section on this page | Output the current form/enquiry HTML in full. Identify whether: (a) no form exists, (b) a `<form>` tag exists (brand violation — must use event handlers instead), or (c) event handlers exist but are unwired. Do not make changes. Report the current state and await instruction. | `stop` |

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `index.html` | After removing Pilot Programme section (ID 03), confirm the surrounding sections flow correctly — no orphaned closing tags, no broken grid. | `clean` / `structural issue found` |
| `services.html` | After IDs 12 and 13, confirm no remaining instances of "No registration" or "No data collected" exist anywhere in the file. | `clean` / `instances remaining: [list]` |

---

## OUT OF SCOPE — SEPARATE SESSION

**`site/updates.html` — brand styling**
This requires a full page redesign against the TPA brand system, not a surgical
edit. Treat as a separate build session. Do not modify this file in this run.

---

## VERSION TOKENS + COMMIT

After all changes are complete, increment the footer version token in each
modified file by 1 (e.g. `TPA-WEB-v9.0` → `TPA-WEB-v10.0`). Read the current
token before incrementing — do not assume the value.

Then:

```bash
git add site/index.html site/framework.html site/white-paper.html \
  site/assessment.html site/services.html site/about.html

git commit -m "fix: staging review fixes — Calendly CTAs, pilot removed, icons, \
section labels, sidebar nav, H1 gradient, DRRP intro, services cleanup, \
active nav state, about form audit"

git push origin main
```

Output `git log --oneline -3` to confirm push.

Output final summary table:

| ID | File | Change | Status |
|----|------|--------|--------|
| 01 | index.html | Nav CTA → Calendly | |
| ... | | | |

Flag any ID where the anchor was not found or the change was skipped.
