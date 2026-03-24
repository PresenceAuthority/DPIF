# TPA Website — Pre-Launch Change Manifest
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Deploy: push to main = live via Cloudflare Pages (~30s)
- Constraint: surgical edits only — do not rewrite surrounding HTML, do not introduce new CSS classes, do not alter nav or footer structure on any file

---

## EXECUTION PROTOCOL

1. Clone repo and `cd DPIF`
2. Process each change in ID order
3. For each change: read only the target file, locate the anchor, apply the change, verify
4. Agent behaviour column governs stops:
   - `autonomous` — execute and continue
   - `stop` — output proposed change, wait for approval before writing
5. After all changes: single commit, push to main, output summary

---

## CHANGE MANIFEST

| ID | File | Anchor (find this) | Action | Agent |
|----|------|--------------------|--------|-------|
| 01 | `index.html` | Section with section-label containing "Presence Drift" or equivalent problem-statement content | Move entire `<section>` block (opening to closing tag) to immediately after the hero section. Do not alter content inside the section. Verify by outputting last 2 lines of hero section and first 2 lines of relocated section. | `stop` |
| 02 | `index.html` | Hero section — the `<p>` or `<div>` containing the subtitle/lead text beneath the `.t-display` headline | Insert as first sentence of lead paragraph or as new `<p class="t-lead">` immediately before existing lead: `"DPIF is the governance standard for enterprise legal, compliance, and risk teams deploying AI-mediated digital representations of real persons."` | `autonomous` |
| 03 | `index.html` | Every CTA button or inline mention of the self-assessment within page sections (exclude nav link). Look for: text containing "self-assessment", "Start the Assessment", or `href="/assessment"` in section bodies | For each match: add `<span class="t-meta" style="display:block;margin-top:8px;opacity:0.7;">No registration &middot; No data collected</span>` immediately after the CTA element. Output list of every location modified. | `autonomous` |
| 04 | `index.html` | Pilot programme section — descriptive copy beneath the section heading | Replace tentative copy ("small first cohort", "get in touch", "we're looking for") with: `"We are onboarding a limited first cohort of pilot organisations. Applications are reviewed individually. Each participant receives a full 18-control DPIF assessment, written gap analysis, and certification readiness report — at no cost. In return, participants contribute to a documented case study. Cohort places are limited."` Preserve section heading and CTA buttons unchanged. | `stop` |
| 05 | `index.html` | Footer version token (e.g. `TPA-WEB-v5.0` or `TPA-WEB-v5.1`) | Replace with `TPA-WEB-v6.0` | `autonomous` |
| 06 | `index.html` | Footer copyright string | Confirm reads `© 2026 The Presence Authority`. If it reads 2025, replace year with 2026. | `autonomous` |
| 07 | `framework.html` | Section introducing the 7 control categories (Identity, Authority, Consent, Disclosure, Context Risk, Semantic Integrity, Containment) | Insert immediately before this section's introductory paragraph as `<p class="t-body" style="margin-bottom:24px;">`: `"DPIF is organised at three levels. The five governance principles define what presence integrity requires. The seven control categories translate those principles into operational domains. The eight assessment sections map to those categories, with Scope Boundary (BOUND-0.1) assessed as a standalone gate that applies across all deployments. These levels are related but distinct — a single assessment covers all eight sections and all 18 controls."` | `autonomous` |
| 08 | `about.html` | The statistic claiming ~2% of AI deployments have documented consent or governance frameworks | Add immediately after the statistic figure, as `<span class="t-meta">` or `<p class="t-meta">`: `"Based on The Presence Authority's review of publicly documented AI avatar and digital twin deployments conducted during framework development, 2025–2026."` Do not alter the statistic or surrounding copy. | `autonomous` |
| 09 | `regulatory-alignment.html` | Page title or first content block below the page heading | Insert as `<p class="t-meta" style="margin-bottom:32px;">`: `"Framework mapping current as of March 2026 · Reflects EU AI Act obligations in force and NIST AI RMF v1.0"` | `autonomous` |
| 10 | `regulatory-alignment.html` | Any text referencing ISO/IEC JTC 1/SC 42 or IEEE SA engagement as "planned", "under development", or "being explored" | Replace hedged language with: `"The Presence Authority is preparing a formal contribution to ISO/IEC JTC 1/SC 42 addressing governance standards for AI-mediated representations of real persons."` If the surrounding section contains no other substantive content beyond the hedge, remove the entire section block and output a note explaining what was removed. | `stop` |
| 11 | `updates.html` | Main content section of the page | Read current content first and output it. Then replace or populate with the following entries using existing card/list component patterns found in the file. If no card pattern exists, use `<div class="card">` per entry. Display newest first: **Entry 1:** Date badge: `12 March 2026` · Title: `DPIF White Paper v1.3` · Body: `Updated to align with Control Model v1.1. Reflects IC-1.2 reclassification, deployment formalisation as primary unit of verification, and the full normative instrument suite of seven documents.` **Entry 2:** Date badge: `11 March 2026` · Title: `Control Model v1.1 · Control Checklist v2.0` · Body: `IC-1.2 (Identity Drift Monitoring) reclassified from SPC to CPC. Deployment formalised as primary unit of DPIF verification. Normative references updated across all six companion instruments. Control count corrected to 18 (14 CPC, 4 SPC). Scoring Rubric and Certification Pathway added to normative suite.` **Entry 3:** Date badge: `20 February 2026` · Title: `Control Model v1.0 · Control Checklist v1.0` · Body: `Initial normative release.` | `stop` |
| 12 | `services.html` | Any mention of or link to the self-assessment within page section bodies (exclude nav) | Apply same change as ID 03: add `<span class="t-meta" style="display:block;margin-top:8px;opacity:0.7;">No registration &middot; No data collected</span>` after each match. If no assessment references found, output "No assessment references on services.html — skip." | `autonomous` |

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `assessment.html` | Is friction-removal language ("No registration", "No data collected") already present? | `present` / `absent` / `partial` — flag if absent for follow-up |
| `white-paper.html` | Does the page render substantive white paper content as HTML body text, or is it primarily a PDF download gateway? | `substantive` / `gateway` / `partial` — flag if gateway for follow-up |

---

## COMMIT

After all changes and verifications complete:

```
git add site/index.html site/framework.html site/about.html site/regulatory-alignment.html site/updates.html site/services.html

git commit -m "fix: pre-launch multi-page edits v6 — section reorder, audience targeting, friction signals, pilot reframe, terminology bridge, stat attribution, regulatory datestamp, version history"

git push origin main
```

Output `git log --oneline -3` to confirm.
Output final summary: every file changed, every change ID applied, any verify flags raised.
