# TPA Contact Forms — Change Manifest
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PRECONDITIONS — Complete before running this manifest

1. **Create a Formspree account** at https://formspree.io (free tier: 50 submissions/month)
2. **Create a new form** in the Formspree dashboard
3. **Set the notification email** to: `bradley@thepresenceauthority.com`
4. **Add a second recipient** in Settings → Submissions: `bobbie-jane@thepresenceauthority.com`
5. **Copy the Form ID** from the endpoint URL shown in your Formspree dashboard
   - It looks like: `https://formspree.io/f/abcdefgh` — the ID is `abcdefgh`
6. ~~Substitute your Form ID~~ — **Form ID `xeerynjp` is already substituted in this manifest. No substitution step required.**

---

## PREAMBLE

- Repo: `github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Constraint: **Surgical edits only.** Do not rewrite surrounding HTML, CSS, or JS. Do not rename IDs, restructure sections, or change copy. Match anchors exactly — character for character.

---

## EXECUTION PROTOCOL

1. Clone repo and `cd` into it
2. Process each change ID in order
3. For each change: read only the target file, locate the exact anchor string, apply the action, verify
4. Agent behaviour column governs stops:
   - `autonomous` — apply and continue
   - `stop` — output the proposed change in full, wait for explicit approval before writing
5. After all changes: single commit, push to `main`, output summary

---

## CHANGE MANIFEST

| ID | File | Anchor (find this exact string) | Action | Agent |
|----|------|---------------------------------|--------|-------|
| 01 | `site/contact.html` | `const FORMSPREE_ENDPOINT = 'https://formspree.io/f/REPLACE_WITH_YOUR_FORM_ID';` | Replace the entire line with: `const FORMSPREE_ENDPOINT = 'https://formspree.io/f/xeerynjp';` | `autonomous` |
| 02 | `site/contact.html` | `enquiry_type: typeLabel,` | On the line immediately after this, insert: `_source: 'contact',` | `autonomous` |
| 03 | `site/about.html` | `function handleEnquiry(){` | Stop. See full replacement block ID-03 below. Replace the entire `handleEnquiry` function (from `function handleEnquiry(){` through to its closing `}`) with the replacement block. | `stop` |
| 04 | `site/about.html` | `<button onclick="handleEnquiry()" class="btn btn-p" style="width:100%">Send Enquiry</button>` | Replace with: `<button id="eqBtn" onclick="handleEnquiry()" class="btn btn-p" style="width:100%">Send Enquiry</button><div id="eq-status" style="display:none"></div>` | `autonomous` |
| 05 | `site/about.html` | The opening `<script>` tag of the script block that contains `function handleEnquiry` | Immediately after the opening `<script>` tag, insert on a new line: `const FORMSPREE_ENDPOINT = 'https://formspree.io/f/xeerynjp';` | `autonomous` |
| 06 | `site/contact.html` | `TPA-WEB-v12.0` (in the footer `<span class="footer-ver">`) | Replace with: `TPA-WEB-v13.0` | `autonomous` |
| 07 | `site/about.html` | `TPA-WEB-v12.0` (in the footer `<span class="footer-ver">`) | Replace with: `TPA-WEB-v14.0` | `autonomous` |

---

## ID-03 REPLACEMENT BLOCK — Full `handleEnquiry` function

Replace the existing `handleEnquiry` function in `site/about.html` with the following. Do not modify anything outside the function boundaries.

```javascript
async function handleEnquiry() {
  const name = document.getElementById('eq-name').value.trim();
  const org  = document.getElementById('eq-org').value.trim();
  const email = document.getElementById('eq-email').value.trim();
  const type = document.getElementById('eq-type').value;
  const msg  = document.getElementById('eq-msg').value.trim();
  const statusEl = document.getElementById('eq-status');
  const btn = document.getElementById('eqBtn');

  /* Reset status */
  statusEl.style.display = 'none';

  /* Validation */
  if (!name || !email || !msg) {
    showEqStatus('Please complete name, email, and message.', 'error');
    return;
  }
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
    showEqStatus('Please enter a valid email address.', 'error');
    return;
  }

  /* Loading state */
  btn.textContent = 'Sending\u2026';
  btn.disabled = true;
  btn.style.opacity = '0.65';
  btn.style.cursor = 'default';

  try {
    const res = await fetch(FORMSPREE_ENDPOINT, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json', 'Accept': 'application/json' },
      body: JSON.stringify({
        name,
        email,
        organisation: org || '\u2014',
        enquiry_type: type || 'General',
        message: msg,
        _source: 'about',
        _subject: 'TPA Enquiry \u2014 ' + (type || 'General') + ' (' + name + ')'
      })
    });

    if (res.ok) {
      showEqStatus('Your message has been sent. We will respond within 2 business days.', 'success');
      ['eq-name', 'eq-org', 'eq-email', 'eq-msg'].forEach(id => {
        document.getElementById(id).value = '';
      });
      document.getElementById('eq-type').value = '';
      btn.textContent = 'Sent';
    } else {
      showEqStatus('Submission failed. Please email bradley@thepresenceauthority.com directly.', 'error');
      resetBtn();
    }
  } catch (e) {
    showEqStatus('Could not connect. Please email bradley@thepresenceauthority.com directly.', 'error');
    resetBtn();
  }

  function resetBtn() {
    btn.textContent = 'Send Enquiry';
    btn.disabled = false;
    btn.style.opacity = '1';
    btn.style.cursor = 'pointer';
  }

  function showEqStatus(message, type) {
    statusEl.textContent = message;
    statusEl.style.display = 'block';
    statusEl.style.marginTop = '12px';
    statusEl.style.padding = '12px 16px';
    statusEl.style.borderRadius = '8px';
    statusEl.style.fontSize = '13px';
    statusEl.style.lineHeight = '1.6';
    if (type === 'success') {
      statusEl.style.background = 'rgba(61,122,92,0.12)';
      statusEl.style.border = '0.5px solid rgba(90,158,122,0.35)';
      statusEl.style.color = 'var(--gl)';
    } else {
      statusEl.style.background = 'rgba(201,168,184,0.08)';
      statusEl.style.border = '0.5px solid rgba(201,168,184,0.28)';
      statusEl.style.color = 'var(--rm)';
    }
    statusEl.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
  }
}
```

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `site/contact.html` | Confirm `FORMSPREE_ENDPOINT` does NOT contain the string `REPLACE_WITH_YOUR_FORM_ID` | Output the exact value of the constant |
| `site/about.html` | Confirm `FORMSPREE_ENDPOINT` constant exists in the script block | Output the constant line |
| `site/about.html` | Confirm `id="eqBtn"` exists on the submit button | Output the button element |
| `site/about.html` | Confirm `id="eq-status"` element exists after the button | Output the element |

---

## COMMIT

```
git add site/contact.html site/about.html
git commit -m "feat: contact + about v13-14 — Formspree wired on both forms, about mailto replaced with fetch handler, source field added, version tokens incremented"
git push origin main
```

Output `git log --oneline -3` to confirm push.

Output final summary:
- Every file changed
- Every change ID applied
- Verify checks with pass/fail and actual values observed
