# TPA Website — Change Manifest
## Session: 24 March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Constraint: **Surgical edits only. Do not rewrite surrounding HTML. Do not introduce new CSS classes without checking they don't already exist in the file. Preserve all existing IDs, class names, and event handlers unless the change explicitly replaces them. Each change targets a specific anchor — read only that file, locate the anchor, apply, verify.**

---

## EXECUTION PROTOCOL

1. Clone repo and cd into working directory
2. Process each change in ID order
3. For each change: read only the target file, locate the anchor string exactly as written, apply the action
4. Agent behaviour column governs stops:
   - `autonomous` — execute and continue
   - `stop` — output proposed change, wait for approval before writing
5. After all changes: single commit, push to main, output summary

---

## CHANGE MANIFEST

---

### ID 01 — `site/services.html`
**Anchor:** `EU AI Act obligations for AI systems representing real people are active and enforced. Non-compliance carries material penalties and reputational consequences.`

**Action:** Replace only that sentence (inside the `risk-desc` div under the `risk-title` "Regulatory Exposure") with:

```
EU AI Act obligations for AI systems representing real people are active and enforced. Under Article 99, non-compliance with requirements for high-risk AI systems carries fines of up to €30 million or 6% of global annual turnover — whichever is higher. AI systems that replicate a real person's identity, voice, or communicative presence in public-facing contexts may meet the threshold for high-risk classification, triggering mandatory conformity assessment obligations before deployment.
```

**Agent:** `autonomous`

---

### ID 02 — `site/services.html`
**Anchor:** The `<section class="content-section" id="consult">` block — specifically the closing `</section>` tag of that section (after the consult-card that ends with `<a href="/assessment" class="btn btn-p btn-arrow">Take the Assessment</a>`)

**Action:** Before the closing `</section>` of the `#consult` section, insert the following HTML block (the consultation qualification card) and the accompanying JS function. Place the HTML immediately after the existing `consult-card` div's closing `</div>`, and add the JS function inside the existing `<script>` block (before the closing `</script>` tag).

**HTML to insert after the existing consult-card closing `</div>`:**
```html
<div class="consult-card" style="grid-template-columns:1fr;margin-top:16px">
  <div class="consult-title">Speak with our team</div>
  <p class="consult-desc" style="margin-bottom:20px">Tell us a little about your context first — it helps us make the call as useful as possible.</p>
  <input type="text" id="cq-org" placeholder="Organisation name" style="width:100%;background:var(--mid);border:0.5px solid var(--br);color:var(--tx);border-radius:8px;padding:11px 16px;font-family:var(--fb);font-size:13px;margin-bottom:10px;outline:none;box-sizing:border-box;transition:border-color 0.2s" onfocus="this.style.borderColor='var(--brm)'" onblur="this.style.borderColor='var(--br)'">
  <select id="cq-type" style="width:100%;background:var(--mid);border:0.5px solid var(--br);color:var(--ts);border-radius:8px;padding:11px 16px;font-family:var(--fb);font-size:13px;margin-bottom:10px;outline:none;appearance:none;box-sizing:border-box;cursor:pointer">
    <option value="">Deployment type</option>
    <option value="AI avatar / digital twin">AI avatar / digital twin</option>
    <option value="Synthetic voice clone">Synthetic voice clone</option>
    <option value="Video synthesis / face synthesis">Video synthesis / face synthesis</option>
    <option value="Multi-modal representation">Multi-modal representation</option>
    <option value="Not sure / exploring">Not sure — still scoping</option>
  </select>
  <input type="text" id="cq-concern" placeholder="Primary concern or question" style="width:100%;background:var(--mid);border:0.5px solid var(--br);color:var(--tx);border-radius:8px;padding:11px 16px;font-family:var(--fb);font-size:13px;margin-bottom:12px;outline:none;box-sizing:border-box;transition:border-color 0.2s" onfocus="this.style.borderColor='var(--brm)'" onblur="this.style.borderColor='var(--br)'">
  <button onclick="handleConsultQual()" class="btn btn-p" style="width:100%;justify-content:center">Proceed to Booking →</button>
  <p style="font-size:10px;color:var(--ts);margin-top:10px;font-family:var(--fm);letter-spacing:0.3px">Takes 30 seconds. Not a pitch. If DPIF is not the right fit, we'll say so.</p>
</div>
```

**JS to insert before closing `</script>` tag:**
```javascript
function handleConsultQual(){
  const org = document.getElementById('cq-org').value.trim();
  const type = document.getElementById('cq-type').value;
  const concern = document.getElementById('cq-concern').value.trim();
  if(org || type || concern){
    const subject = encodeURIComponent('Consultation request' + (org ? ' — ' + org : ''));
    const body = encodeURIComponent('Organisation: ' + (org||'Not provided') + '\nDeployment type: ' + (type||'Not specified') + '\nPrimary concern: ' + (concern||'Not provided'));
    window.open('mailto:bradley@thepresenceauthority.com?subject=' + subject + '&body=' + body);
  }
  window.open('https://calendly.com/bradley-thepresenceauthority/30min', '_blank');
}
```

**Agent:** `stop`

---

### ID 03 — `site/services.html`
**Anchor:** `<span class="footer-ver">TPA-WEB-v` (the footer version token in services.html)

**Action:** Increment the version number by 1. Read the current value (e.g. `v12.0`), replace with next integer (e.g. `v13.0`).

**Agent:** `autonomous`

---

### ID 04 — `site/index.html`
**Anchor:** Find the section containing the text `"DPIF is the governance standard for enterprise legal, compliance, and risk teams deploying AI-mediated digital representations of real persons."` — this is the `.hero-sub` paragraph in the hero section.

**Action:** Immediately after the closing `</p>` tag of that `.hero-sub` paragraph, and before whatever element follows it (likely the hero CTA buttons div), insert:

```html
<div style="display:flex;align-items:center;flex-wrap:wrap;gap:8px;margin-bottom:32px;margin-top:4px">
  <span style="font-family:var(--fm);font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--ts);flex-shrink:0">Applies to:</span>
  <span style="font-size:12px;color:var(--tm);border:0.5px solid var(--brm);border-radius:100px;padding:4px 12px;background:rgba(152,136,192,0.06)">AI customer service avatar</span>
  <span style="font-size:12px;color:var(--tm);border:0.5px solid var(--brm);border-radius:100px;padding:4px 12px;background:rgba(152,136,192,0.06)">Executive video or voice clone</span>
  <span style="font-size:12px;color:var(--tm);border:0.5px solid var(--brm);border-radius:100px;padding:4px 12px;background:rgba(152,136,192,0.06)">Synthetic representation in regulated communications</span>
</div>
```

**Agent:** `autonomous`

---

### ID 05 — `site/index.html`
**Anchor:** Find the section containing `section-label` text `"Governance Credentials"` — this is the credentials section near the bottom of the page (before the footer). Locate the element immediately before this section's opening tag (likely an `<hr class="grad-sep">` or the closing tag of the Team section).

**Action:** Immediately before the opening of the Credentials section (i.e. after whatever separator or closing tag precedes it), insert the following breakout band:

```html
<div style="background:var(--mid1);border-top:0.5px solid var(--br);border-bottom:0.5px solid var(--br);padding:56px 0">
  <div style="max-width:920px;margin:0 auto;padding:0 var(--gl-left)">
    <div style="font-size:10px;font-weight:600;letter-spacing:2.5px;text-transform:uppercase;color:var(--vs);display:flex;align-items:center;gap:12px;margin-bottom:20px"><span style="display:inline-block;width:32px;height:1px;background:var(--vs);flex-shrink:0"></span>Why It Matters Who Built This</div>
    <p style="font-family:var(--fd);font-size:clamp(18px,2vw,24px);line-height:1.65;color:var(--td)">We did not adopt the standard. We did not adapt another framework. <strong style="background:linear-gradient(135deg,#9888c0,#7ab89a,#c9a8b8,#c8b890);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text">We wrote DPIF</strong> — from first principles, against the specific governance gap we identified directly, before any certification income existed. That is a material difference when you are working with the body that assesses your deployment.</p>
  </div>
</div>
```

**Agent:** `stop`

---

### ID 06 — `site/index.html`
**Anchor:** `<span class="footer-ver">TPA-WEB-v` in index.html

**Action:** Increment version token by 1 from current value.

**Agent:** `autonomous`

---

### ID 07 — `site/about.html`
**Anchor:** `<span class="section-label">Our Mission</span>` — this is the mission section label near the bottom of the about page main content.

**Action:** Immediately before that `<span class="section-label">Our Mission</span>` element (and before any `<section>` or `<hr>` tag that wraps it), insert the following new section:

```html
<section class="content-section" id="advisory-board">
  <span class="section-label">Advisory Board</span>
  <h2 class="section-title">External governance and <em>independent expertise.</em></h2>
  <p class="t-body" style="margin-bottom:20px">The Presence Authority is assembling an independent advisory board to provide external scrutiny, domain expertise, and institutional oversight of DPIF and its governance processes.</p>
  <div class="callout-block">
    <div class="callout-eyebrow">Board Formation in Progress</div>
    <p class="callout-text">Advisors are being recruited with expertise in <strong>data protection law, AI governance, digital identity standards, and regulated sector deployment</strong>. Board members provide independent oversight of framework development — not commercial endorsement. Appointments will be announced publicly on this page as confirmed.</p>
  </div>
  <p class="t-body" style="margin-top:20px">If you have relevant expertise and an interest in contributing to an open governance standard for AI-mediated digital representations, <a href="/contact" style="color:var(--vs)">express your interest via the contact form</a>.</p>
</section>
<hr class="grad-sep">
```

Also, add a sidebar nav link for this section. In the `<nav class="page-nav">` block, find `<a href="#why" class="page-nav-link">Why this matters</a>` and insert before it:
```html
<a href="#advisory-board" class="page-nav-link">Advisory Board</a>
```

**Agent:** `stop`

---

### ID 08 — `site/about.html`
**Anchor:** `<section class="content-section" id="mission">` — the opening of the mission section.

**Action:** After the opening `<section class="content-section" id="mission">` tag and before the `<span class="section-label">Our Mission</span>` element, insert the following independence statement block:

```html
<div class="callout-block" style="margin-bottom:36px">
  <div class="callout-eyebrow">Independence &amp; Governance</div>
  <p class="callout-text">The Presence Authority is privately held and vendor-neutral. DPIF is authored by its co-founders, published under CC BY 4.0, and maintained under no commercial influence from AI platform operators, technology vendors, or certification candidates. The organisation generates no revenue from organisations whose deployments it assesses — certification and advisory income is structurally separate from the standard itself. The full framework record is version-controlled and publicly auditable on <strong>GitHub</strong>.</p>
</div>
```

**Agent:** `stop`

---

### ID 09 — `site/about.html`
**Anchor:** `<span class="footer-ver">TPA-WEB-v` in about.html

**Action:** Increment version token by 1 from current value.

**Agent:** `autonomous`

---

### ID 10 — `site/assessment.html`
**Anchor:** Find the text `"No data is collected or transmitted. Results are calculated in your browser."` — this appears near the result display area of the assessment tool.

**Action:** This is a two-part change:

**Part A — HTML:** Immediately after the element containing that text, insert the following email capture block (initially hidden):

```html
<div id="email-results-wrap" style="display:none;margin-top:20px;padding:20px 24px;background:var(--mid1);border:0.5px solid var(--brm);border-radius:10px">
  <p style="font-family:var(--fm);font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--vs);margin-bottom:10px;display:flex;align-items:center;gap:8px"><span style="display:inline-block;width:20px;height:1px;background:var(--vs)"></span>Keep a copy</p>
  <p style="font-size:13px;color:var(--tm);line-height:1.6;margin-bottom:14px">Optional — enter your email to send yourself a copy of these results for your governance records.</p>
  <div style="display:flex;gap:10px;flex-wrap:wrap">
    <input type="email" id="result-email" placeholder="your@email.com" style="flex:1;min-width:200px;background:var(--mid);border:0.5px solid var(--br);color:var(--tx);border-radius:8px;padding:10px 14px;font-family:var(--fb);font-size:13px;outline:none;box-sizing:border-box">
    <button onclick="emailResults()" style="background:var(--vm);color:#f0ecf8;border:none;border-radius:100px;padding:10px 20px;font-family:var(--fb);font-size:12px;font-weight:500;cursor:pointer;white-space:nowrap;transition:background 0.2s" onmouseover="this.style.background='#7d6ca0'" onmouseout="this.style.background='var(--vm)'">Email me my results →</button>
  </div>
  <p style="font-size:10px;color:var(--ts);margin-top:8px;font-family:var(--fm)">No data is sent to TPA. This opens your email client with a pre-filled message to your own address.</p>
</div>
```

**Part B — JS:** In the existing `<script>` block, find the function that displays the assessment result (it likely calls something like `showResult()`, `displayResult()`, or updates a result container's visibility/content). Inside that function, after the result is rendered, add:
```javascript
document.getElementById('email-results-wrap').style.display = 'block';
```

Also add the following `emailResults` function before the closing `</script>` tag:
```javascript
function emailResults(){
  const email = document.getElementById('result-email').value.trim();
  if(!email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){
    alert('Please enter a valid email address.');
    return;
  }
  // Build a plain-text summary of results from the DOM
  const resultTitle = document.querySelector('#result-panel .result-title, #result-panel h3, [class*="result-heading"], [class*="result-status"]');
  const resultText = resultTitle ? resultTitle.innerText : 'DPIF Self-Assessment result';
  const failedControls = Array.from(document.querySelectorAll('[class*="fail"], [class*="unmet"]')).map(el => el.innerText).join(', ');
  const subject = encodeURIComponent('My DPIF Self-Assessment Results');
  const body = encodeURIComponent(
    'DPIF Self-Assessment Results\n' +
    '============================\n\n' +
    'Result: ' + resultText + '\n\n' +
    (failedControls ? 'Controls to review: ' + failedControls + '\n\n' : '') +
    'Full assessment: https://thepresenceauthority.pages.dev/assessment\n' +
    'Framework reference: https://github.com/PresenceAuthority/DPIF\n\n' +
    '— The Presence Authority · DPIF v1.3'
  );
  window.location.href = 'mailto:' + email + '?subject=' + subject + '&body=' + body;
}
```

**Note for Claude Code:** The exact function name and result container class/ID must be identified by reading the assessment.html script block before applying this change. The result display trigger and result container selectors in the `emailResults` function above are best-guesses — update them to match the actual element IDs/classes found in the file.

**Agent:** `stop`

---

### ID 11 — `site/assessment.html`
**Anchor:** `<span class="footer-ver">TPA-WEB-v` in assessment.html

**Action:** Increment version token by 1 from current value.

**Agent:** `autonomous`

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `site/index.html` | Confirm `.breakout-band` CSS class exists in the file's `<style>` block OR that the ID 05 insertion uses inline styles (no class dependency) | Output: "breakout CSS present" or "inline styles used — no dependency" |
| `site/assessment.html` | Output the name of the function that triggers result display, and the ID/class of the result container element | Output: function name + element ID/class |
| `site/services.html` | Confirm `handleConsultQual` function does not already exist | Output: "function absent — safe to add" or "function already present" |

---

## COMMIT

```
git add site/index.html site/services.html site/about.html site/assessment.html
git commit -m "feat: site — independence statement, advisory board, EU AI Act specifics, qualification form, email results, entry-path tags, standard authorship callout"
git push origin main
```

Output `git log --oneline -3` to confirm push.

Output final summary:
- Every file changed
- Every ID applied
- Which `stop` items were approved before writing
- Any verify flags raised
- Actual version tokens written to each file

---

## REFERENCE — COPY NOTES

**Items mapped to IDs:**
- Item 4 (independence statement): IDs 08 + 09 → `about.html`
- Item 5 ("We wrote the standard"): IDs 05 + 06 → `index.html`
- Item 6 (entry-path tags): ID 04 → `index.html`
- Item 7 (email results): IDs 10 + 11 → `assessment.html`
- Item 9 (EU AI Act penalties): ID 01 → `services.html`
- Item 10 (qualification form): IDs 02 + 03 → `services.html`
- Item 11 (advisory board): IDs 07 + 09 → `about.html`

**Item 11 note:** Advisory board section is a structural placeholder only. Member names and credentials are NOT populated — they will be added manually once appointments are confirmed. Claude Code should not invent names or credentials.
