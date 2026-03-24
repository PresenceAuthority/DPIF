# TPA Website — Staging Fixes Round 2
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Constraint: surgical edits only. Do not rewrite surrounding HTML. Do not
  introduce CSS class names not already present in the file unless explicitly
  specified in this manifest. Do not alter nav or footer structure unless
  explicitly instructed.
- Calendly URL: `https://calendly.com/bradley-thepresenceauthority/30min`

---

## EXECUTION PROTOCOL

1. Clone repo and `cd DPIF`
2. Process each change ID in order
3. Read only the target file before making its changes
4. Agent behaviour:
   - `autonomous` — execute and continue
   - `stop` — output the proposed change in full and wait for approval
5. After all changes: read current version token in each modified file,
   increment by 1, commit, push

---

## COMPLETE ICON LIBRARY
## Use these exact SVG blocks — do not construct SVGs from descriptions.
## All gradients are namespaced. Swap prefix as instructed per change ID.
## Replace PREFIX with the 2-4 char prefix specified in each change.

### ICON: Identity (person)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <circle cx="14" cy="9" r="4" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M5 24c0-4.418 4.03-8 9-8s9 3.582 9 8" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
</svg>
```

### ICON: Authority (star)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <path d="M14 3l2.5 7h7.5l-6 4.5 2.5 7L14 17l-6.5 4.5 2.5-7L4 10h7.5z" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linejoin="round"/>
</svg>
```

### ICON: Consent (lock with upload arrow)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <rect x="7" y="13" width="14" height="11" rx="2" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M10 13V9a4 4 0 0 1 8 0v4" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
  <path d="M14 17v4M12 19l2-2 2 2" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```

### ICON: Disclosure (new — eye with underline, represents transparency)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <path d="M3 13s4-6 11-6 11 6 11 6-4 6-11 6-11-6-11-6z" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
  <circle cx="14" cy="13" r="2.5" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M9 22h10" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
</svg>
```

### ICON: Containment / Traceability (chain link)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <path d="M11 17l-2 2a4 4 0 0 1-5.657-5.657l4-4A4 4 0 0 1 13 9.686" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
  <path d="M17 11l2-2a4 4 0 0 1 5.657 5.657l-4 4A4 4 0 0 1 15 20.314" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
  <path d="M10.5 17.5l7-7" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
</svg>
```

### ICON: Framework (4-square grid)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <rect x="5" y="5" width="7" height="7" rx="1" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <rect x="16" y="5" width="7" height="7" rx="1" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <rect x="5" y="16" width="7" height="7" rx="1" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <rect x="16" y="16" width="7" height="7" rx="1" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
</svg>
```

### ICON: Verified (circle + checkmark)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <circle cx="14" cy="14" r="9" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M9 14l3.5 3.5 6.5-7" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```

### ICON: Risk Tier (warning triangle + exclamation)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <polygon points="14,4 26,24 2,24" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linejoin="round" fill="none"/>
  <path d="M14 12v5" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
  <circle cx="14" cy="20.5" r="1" fill="url(#PREFIX_ig1)"/>
</svg>
```

### ICON: Lifecycle (clock)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <circle cx="14" cy="14" r="9" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M14 8v6l4 3" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```

### ICON: Conflict (crossed lines with 3 nodes)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <circle cx="6" cy="8" r="2.5" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <circle cx="22" cy="8" r="2.5" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <circle cx="14" cy="22" r="2.5" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M8.2 9.5L12.5 20M19.8 9.5L15.5 20M8.5 8h11" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
</svg>
```

### ICON: Posthumous (dashed person)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <circle cx="14" cy="9" r="4" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-dasharray="3 2"/>
  <path d="M5 24c0-4.418 4.03-8 9-8s9 3.582 9 8" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round" stroke-dasharray="3 2"/>
</svg>
```

### ICON: Audit (document with lines)
```html
<svg width="SIZE" height="SIZE" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs><linearGradient id="PREFIX_ig1" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#9888c0"/><stop offset="33%" stop-color="#7ab89a"/><stop offset="66%" stop-color="#c9a8b8"/><stop offset="100%" stop-color="#c8b890"/></linearGradient></defs>
  <rect x="6" y="4" width="16" height="20" rx="2" stroke="url(#PREFIX_ig1)" stroke-width="1.5"/>
  <path d="M10 10h8M10 14h8M10 18h5" stroke="url(#PREFIX_ig1)" stroke-width="1.5" stroke-linecap="round"/>
</svg>
```

---
## END ICON LIBRARY
---

## CHANGE MANIFEST

### FILE: site/index.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 01 | The section containing the 5 governance principle cards (look for section-label containing "Framework", "Principles", or cards with headings like "Identity", "Authority", "Consent", "Disclosure", "Containment") | Output the current HTML of each principle card including any existing icon element. Then replace icons using the library above. SIZE=36 for all. Map: Identity card → Identity icon (prefix `id_`); Authority card → Authority icon (prefix `au_`); Consent card → Consent icon (prefix `co_`); Disclosure card → Disclosure icon (prefix `di_`); Containment card → Containment/Traceability icon (prefix `ct_`). Insert icon SVG as first child inside each card, before the card title. If an icon element already exists, replace it entirely with the correct SVG. | `stop` |
| 02 | The section containing the published instrument cards (look for card titles: "Control Model", "Control Checklist", "Context Risk", "Deployment Lifecycle", "Conflict Resolution", "Posthumous", "Scoring Rubric") | Output the current HTML of one instrument card to confirm structure. Then add instrument icons using the library above. SIZE=28 for all. Map: Control Model → Framework icon (prefix `fm_`); Control Checklist → Verified icon (prefix `ve_`); Context Risk Classification Annex → Risk Tier icon (prefix `rt_`); Deployment Lifecycle Specification → Lifecycle icon (prefix `lc_`); Inter-Deployment Conflict Resolution Framework → Conflict icon (prefix `cf_`); Posthumous and Incapacitated Principal Governance → Posthumous icon (prefix `po_`); Scoring Rubric → Audit icon (prefix `ad_`). Insert icon SVG as first child inside each card. If icon already exists, replace entirely. | `stop` |

---

### FILE: site/framework.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 03 | The `<h1>` in the hero section | Output the exact current `<h1>` HTML. The fix for gradient-text line-break is: (1) the entire `<h1>` must have `style="line-height:1.15;"`, (2) the white text portion must be in `<span style="color:var(--tx);">`, (3) the gradient text portion must be in `<em style="font-style:inherit; background:linear-gradient(135deg,#9888c0,#7ab89a,#c9a8b8,#c8b890); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;">`. Do NOT add `white-space:nowrap` — allow natural wrapping. The key fix is that `-webkit-text-fill-color:transparent` must be on the `<em>` not the `<h1>`, and the `<h1>` must not have its own `color` or `-webkit-text-fill-color` set. Propose the corrected `<h1>` block in full before writing. | `stop` |

---

### FILE: site/white-paper.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 04 | The sidebar navigation element | Read `site/assessment.html` first. Extract: (a) the sidebar HTML structure, (b) the sidebar CSS, (c) the sidebar JS (scroll spy / active state logic). Then read the white-paper.html sidebar. Output a specific diff: what is present in assessment.html sidebar but absent or different in white-paper.html sidebar. Apply only the missing pieces — HTML, CSS, or JS as needed. Do not replace the entire sidebar block. | `stop` |
| 05 | The topbar `<nav>` in this file — the `<a href="/white-paper"` link | Change `class="topbar-link"` to `class="topbar-link active"` on the `/white-paper` link only. Add `.topbar-link.active{color:var(--tx);}` to the `<style>` block if not already present. | `autonomous` |

---

### FILE: site/assessment.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 06 | The topbar `<nav>` — the `<a href="/assessment"` link | Change `class="topbar-link"` to `class="topbar-link active"` on the `/assessment` link only. Add `.topbar-link.active{color:var(--tx);}` to the `<style>` block if not already present. | `autonomous` |

---

### FILE: site/services.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 07 | The section headed "Book a Consultation" or equivalent — the section blending consultation booking and self-assessment actions | Output the full current HTML of this section. Identify: (a) which elements are consultation-specific (→ Calendly), (b) which elements are assessment-specific (→ /assessment), (c) where the messaging conflation occurs. Do not make changes. Await instruction. | `stop` |
| 08 | The topbar `<nav>` — the `<a href="/services"` link | Change `class="topbar-link"` to `class="topbar-link active"` on the `/services` link only. Add `.topbar-link.active{color:var(--tx);}` to the `<style>` block if not already present. | `autonomous` |

---

### FILE: site/regulatory-alignment.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 09 | The topbar `<nav>` — the `<a href="/regulatory-alignment"` link | Change `class="topbar-link"` to `class="topbar-link active"` on the `/regulatory-alignment` link only. Add `.topbar-link.active{color:var(--tx);}` to the `<style>` block if not already present. | `autonomous` |

---

### FILE: site/about.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 10 | The `<h1>` in the hero section | Apply the same fix as ID 03. Output current `<h1>` HTML. Propose corrected block with: `<h1 style="line-height:1.15;">`, white text in `<span style="color:var(--tx);">`, gradient text in `<em style="font-style:inherit; background:linear-gradient(135deg,#9888c0,#7ab89a,#c9a8b8,#c8b890); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;">`. | `stop` |
| 11 | Any enquiry, contact, or form section on this page | Output the current HTML of any form or enquiry section. Identify the current state: (a) no enquiry section exists, (b) a `<form>` tag exists (must be replaced — brand guideline prohibits `<form>` tags), or (c) input fields with event handlers already exist. Report state. If state is (a) or (b), propose the following replacement structure and await approval: A section with a two-column layout. Left: heading "Get in touch" + two lines of copy directing different enquiry types to the appropriate action. Right: three `<input>` fields (name, organisation, email) + one `<textarea>` (message) + a dropdown (enquiry type: Readiness Assessment / Pilot Programme / Advisory Board / General) + a submit `<button>`. All wired with a JS `handleEnquiry()` function that validates fields and opens `mailto:bradley@thepresenceauthority.com` with subject and body pre-populated from the form values. Use `var(--mid2)` background on inputs, `var(--br)` border, `var(--tx)` text, `border-radius:8px`, `padding:12px 16px`. No `<form>` tag — use a `<div>` wrapper. | `stop` |

---

### FILE: site/updates.html

| ID | Anchor | Action | Agent |
|----|--------|--------|-------|
| 12 | The entire `<body>` content (excluding `<nav>`, mobile menu, and `<footer>`) | Output the current body content in full. Then replace it entirely with a brand-styled updates page using the following structure. Read TPA_SKILL.md for all CSS tokens, component patterns, and typography classes. Do not invent new class names — use only classes confirmed present in the file's existing `<style>` block or standard TPA classes from TPA_SKILL.md. Structure to implement: (1) Page hero — section with section-label "Version History", H1 using `.t-display` reading "Framework Updates", lead paragraph using `.t-lead` reading "A versioned record of all changes to the DPIF normative instrument suite."; (2) Updates section — section with section-label "Changelog", three cards using `.card` class, newest first: Card 1 — date badge `12 March 2026`, title "DPIF White Paper v1.3", body "Updated to align with Control Model v1.1. Reflects IC-1.2 reclassification, deployment formalisation as primary unit of verification, and the full normative instrument suite of seven documents."; Card 2 — date badge `11 March 2026`, title "Control Model v1.1 · Control Checklist v2.0", body "IC-1.2 (Identity Drift Monitoring) reclassified from SPC to CPC. Deployment formalised as primary unit of DPIF verification. Normative references updated across all six companion instruments. Control count corrected to 18 (14 CPC, 4 SPC). Scoring Rubric and Certification Pathway added to normative suite."; Card 3 — date badge `20 February 2026`, title "Control Model v1.0 · Control Checklist v1.0", body "Initial normative release."; (3) The date badge style: `<span>` with `font-family:var(--fm); font-size:11px; color:var(--vs); letter-spacing:1.5px; display:block; margin-bottom:8px;`. Output the complete proposed replacement HTML before writing. | `stop` |

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `index.html` | After icon changes (IDs 01, 02): confirm no duplicate gradient IDs exist across all SVGs on the page. Each prefix must be unique. | `clean` / `duplicate IDs found: [list]` |
| `about.html` | After H1 fix (ID 10): confirm the `<h1>` contains no top-level `color` or `-webkit-text-fill-color` property that would override child span styles. | `clean` / `override found: [value]` |

---

## VERSION TOKENS + COMMIT

For each modified file: read the current footer version token, increment by 1.
Do not assume the current value — read it from the file.

```bash
git add site/index.html site/framework.html site/white-paper.html \
  site/assessment.html site/services.html site/regulatory-alignment.html \
  site/about.html site/updates.html

git commit -m "fix: round 2 staging fixes — icons, H1 gradients, active nav, \
sidebar parity, services copy, about form, updates brand styling"

git push origin main
```

Output `git log --oneline -3` to confirm.

Output final summary:

| ID | File | Change | Status | Notes |
|----|------|--------|--------|-------|
| 01 | index.html | Principle icons | | |
| 02 | index.html | Instrument icons | | |
| 03 | framework.html | H1 gradient fix | | |
| 04 | white-paper.html | Sidebar parity | | |
| 05 | white-paper.html | Active nav | | |
| 06 | assessment.html | Active nav | | |
| 07 | services.html | Book a Consultation — STOP | | |
| 08 | services.html | Active nav | | |
| 09 | regulatory-alignment.html | Active nav | | |
| 10 | about.html | H1 gradient fix | | |
| 11 | about.html | Enquiry form — STOP | | |
| 12 | updates.html | Brand styling — STOP | | |

Flag any ID where the anchor was not found or the change was skipped.
