# TPA — Domain Migration Change Manifest
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: `site/`
- Authenticated GitHub access: confirmed
- Constraint: surgical edits only — locate exact strings, replace, do not rewrite
  surrounding HTML, do not alter layout, styles, or content outside the listed anchors

---

## CONTEXT

This manifest is the file-based component of migrating
`www.thepresenceauthority.com` from Webflow to Cloudflare Pages.

**Manual prerequisites — confirm before executing this manifest:**

Domain: `www.thepresenceauthority.com`
DNS authority: Cloudflare (registrar + DNS)
Current serving: Webflow

Execute in this order:

**Step 1 — Remove domain from Webflow**
Webflow dashboard → Project Settings → Hosting → Custom Domains →
remove `www.thepresenceauthority.com`. This releases the domain and
prevents SSL conflicts during cutover.

**Step 2 — Add custom domain in Cloudflare Pages**
Cloudflare dashboard → Pages → DPIF project → Custom Domains →
Add a custom domain → enter `www.thepresenceauthority.com` → Save.
Cloudflare will automatically create the required DNS record (CNAME
`www` → `thepresenceauthority.pages.dev` proxied). No manual DNS
entry required.

**Step 3 — Confirm DNS and SSL**
Wait for Cloudflare Pages to show status "Active" for the custom domain.
This typically takes 1–5 minutes. SSL certificate is provisioned
automatically by Cloudflare — no manual certificate step required.

Verify propagation: https://dnschecker.org/#CNAME/www.thepresenceauthority.com
Expected result: resolves to Cloudflare IPs (not Webflow IPs).

**Step 4 — Smoke test before running manifest**
Visit `https://www.thepresenceauthority.com` in an incognito window.
Site should load from Cloudflare Pages. Confirm no Webflow 404 or
SSL error before proceeding.

Do not execute this manifest until Step 4 passes.

---

## EXECUTION PROTOCOL

1. Clone repo and cd into it
2. Process each change in ID order
3. For each change: read only the target file, locate the exact anchor string,
   apply the replacement, verify the anchor no longer exists in its original form
4. Agent behaviour column governs stops:
   - `autonomous` — execute and continue
   - `stop` — output proposed change, wait for approval before writing
5. After all changes: single commit, push to main, output summary

---

## CHANGE MANIFEST

| ID | File | Anchor (find this) | Action | Agent |
|----|------|--------------------|--------|-------|
| 01 | `site/index.html` | `thepresenceauthority.pages.dev` (first occurrence — canonical `<link>` or og:url meta tag) | Replace all occurrences of `thepresenceauthority.pages.dev` with `www.thepresenceauthority.com` throughout the file. Output a count of replacements made before writing. | `stop` |
| 02 | `site/index.html` | `"@id": "https://thepresenceauthority.pages.dev"` OR any JSON-LD `url` or `@id` value containing `thepresenceauthority.pages.dev` | Confirm all JSON-LD schema URLs have been updated by change 01. If any remain, replace them. Output: all JSON-LD `url`/`@id` fields and their current values. | `autonomous` |
| 03 | `site/index.html` | `TPA-WEB-v5.0` (footer version token) | Replace with `TPA-WEB-v5.1` to mark the domain migration build. | `autonomous` |

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `site/index.html` | Search for any remaining occurrence of `pages.dev` or `webflow.io` after changes are applied | Output: count of matches. Expected: 0. If any found, list line numbers and surrounding context. |
| `site/index.html` | Confirm `<link rel="canonical" href="https://www.thepresenceauthority.com">` is present | Output: the exact canonical tag as it appears in the file |
| `site/index.html` | Confirm `og:url` meta content value is `https://www.thepresenceauthority.com` | Output: the exact og:url meta tag as it appears in the file |

---

## COMMIT

```
git add site/index.html
git commit -m "fix: homepage v5.1 — domain migration, staging URLs replaced with www.thepresenceauthority.com"
git push origin main
```

Output `git log --oneline -3` to confirm.

Output final summary:
- Files changed
- Count of `pages.dev` → `www.thepresenceauthority.com` replacements
- Version token updated from → to
- Any verify flags raised
- Confirm: zero remaining `pages.dev` or `webflow.io` references

---

## POST-EXECUTION CHECKS (manual, after Cloudflare Pages redeploys)

Cloudflare Pages redeploys automatically on push to main (~30 seconds).

1. Visit `https://www.thepresenceauthority.com` — confirm site loads
2. Check browser address bar — confirm no redirect to staging URL
3. View page source → confirm canonical tag shows `www.thepresenceauthority.com`
4. Test `https://thepresenceauthority.pages.dev` — confirm it still resolves
   (staging URL remains valid; both can coexist)
5. Confirm Webflow project no longer serves the domain — Webflow dashboard
   should show custom domain field empty or removed
