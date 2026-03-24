# The Presence Authority — Copy Change Manifest
## Session: March 2026 | Executes against: github.com/PresenceAuthority/DPIF

---

## PREAMBLE

- Repo: `https://github.com/PresenceAuthority/DPIF`
- Branch: `main`
- Working directory: repo root
- Authenticated GitHub access: confirmed
- Constraint: **surgical text edits only** — do not rewrite surrounding
  HTML structure, do not introduce new CSS classes, do not alter attributes,
  do not modify anything outside the quoted anchor strings. If an anchor
  is not found exactly, log as SKIPPED and continue.

### Pre-flight (run before any changes)

```bash
find . -name "*.html" | sort
```

Confirm the following files exist at these paths. If any path differs,
update the FILE column in the manifest before proceeding — do not rename files.

| Expected path | Page |
|---|---|
| `index.html` | Homepage |
| `framework.html` | Framework |
| `white-paper.html` | White Paper |
| `services.html` | Services |
| `about.html` | About |
| `regulatory-alignment.html` | Regulatory Alignment |

---

## EXECUTION PROTOCOL

1. Clone repo and cd into root
2. Run the pre-flight file check above
3. Process each change in ID order
4. For each change: open only the target file, locate the ANCHOR string exactly,
   apply the ACTION, close the file
5. Agent behaviour governs stops:
   - `autonomous` — execute and continue
   - `stop` — output the proposed change and the 3 lines of surrounding
     HTML context, wait for explicit approval before writing
6. After all changes: single commit, push to main, output summary

---

## CHANGE MANIFEST

| ID | File | Anchor (find this exactly) | Action | Agent |
|----|------|---------------------------|--------|-------|
| 01 | `index.html` | `The EU AI Act is now in force. Regulatory scrutiny is intensifying. The window to retrofit governance is narrowing.` | Replace with: `The EU AI Act is now in force, and the window to retrofit governance into active deployments is narrowing as enforcement activity increases.` | `autonomous` |
| 02 | `services.html` | `The EU AI Act is now in force. Regulatory scrutiny is intensifying. The window to retrofit governance is narrowing.` | Replace with: `The EU AI Act is now in force, and the window to retrofit governance into active deployments is narrowing as enforcement activity increases.` | `autonomous` |
| 03 | `index.html` | `If the result identifies gaps you recognise, a formal assessment is the logical next step. Use it to orient internally before a conversation with us.` | Replace with: `If the result identifies gaps you recognise, use it to orient internally — a formal assessment is the logical next step.` | `autonomous` |
| 04 | `index.html` | `Use it, cite it, build on it.` | Replace with: `No restrictions. Attribution only.` | `autonomous` |
| 05 | `index.html` | Section with heading text `What we ask in return` — locate the `<ul>` or `<ol>` element containing three list items beginning with `Permission to document` | Replace the entire `<ul>`/`<ol>` block with a `<p>` tag: `<p>We ask to document the process as a case study, subject to your editorial review and sign-off before publication. Any public acknowledgement — timing and format — is agreed in advance.</p>` | `stop` |
| 06 | `framework.html` | `DPIF is a deployment-level operational governance standard for DRRPs.` | Replace with: `DPIF is a deployment-level governance standard for DRRPs.` | `autonomous` |
| 07 | `framework.html` | `This is intentional — CPC failure represents a foundational governance gap that maturity scores cannot offset.` | Replace with: `CPC failure represents a foundational governance gap that no maturity score can offset.` | `autonomous` |
| 08 | `white-paper.html` | `It is written for governance, legal, and compliance functions within organisations` | Replace `functions` with `teams` and reorder: `It is written for legal, governance, and compliance teams within organisations` | `autonomous` |
| 09 | `white-paper.html` | `Where this document and a normative instrument address the same requirement, the normative instrument takes precedence.` | This sentence appears twice. Locate both instances. Delete only the **second** instance (the one in the Document Record body, not the banner). Output both instances with surrounding context before deleting. | `stop` |
| 10 | `services.html` | `We wrote the standard. Now we help you meet it.` | Replace with: `We wrote the standard — and we're the people who can help you meet it.` | `autonomous` |
| 11 | `services.html` | `The technology arrived. The governance did not.` | Replace with: `The technology arrived before the governance did.` | `autonomous` |
| 12 | `services.html` | `The output is not a report. It is governance infrastructure that operates.` | Replace with: `The output is governance infrastructure that operates — not a document for filing.` | `autonomous` |
| 13 | `services.html` | `Not a report that sits in a drawer — operational governance infrastructure with a clear evidence chain.` | Replace with: `Every engagement produces documented, auditable governance artefacts — structured to support internal accountability, legal review, and regulatory disclosure.` | `autonomous` |
| 14 | `services.html` | Section containing heading `Scoping conversation` — locate any sentence or phrase containing `no sales process, no obligation` | Delete the sentence or phrase containing `no sales process, no obligation`. Output surrounding paragraph before deleting. | `stop` |
| 15 | `about.html` | `identity, consent, and dignity do not get left behind.` | Replace with: `identity, consent, and dignity remain enforceable.` | `autonomous` |
| 16 | `about.html` | `Built by people who saw what was missing and decided to fix it themselves.` | Replace with: `Built by the people who identified the gap and wrote the standard to close it.` | `autonomous` |
| 17 | `about.html` | `Between them, every dimension of what DPIF needed to be.` | Replace with: `The combination covered every dimension the framework required — domain authority, structural rigour, and deployment-level practicality.` | `autonomous` |
| 18 | `about.html` | `The moment that made everything clear.` | Replace with: `The founding observation.` | `autonomous` |
| 19 | `about.html` | `Real people's identities are being replicated and operated with minimal oversight, unclear accountability, and no accountability structures.` | Replace with: `Real people's identities are being replicated at scale with minimal oversight, no documented consent, and no audit trail when something goes wrong.` | `autonomous` |
| 20 | `about.html` | `2% of AI deployments` — locate the full sentence or paragraph containing this statistic | Output the full sentence in context. Do not edit. Flag as NEEDS_CITATION for human review. | `stop` |
| 21 | `about.html` | Second instance of `13 years` in Brad Gaylard's biography section — the sentence beginning `Bradley spent 13 years leading` | Delete the sentence containing `Bradley spent 13 years leading`. Output it before deleting for confirmation. | `stop` |
| 22 | `regulatory-alignment.html` | ISO/IEC entry — locate the sentence: `The Presence Authority is preparing a formal contribution to` followed by ISO/IEC body reference | Output both the ISO/IEC and IEEE instances of this sentence in full. Do not edit. Flag as NEEDS_DIFFERENTIATION for human review. | `stop` |

---

## VERIFY-ONLY (no changes)

| File | Check | Output |
|------|-------|--------|
| `index.html` | Confirm hero heading `When a digital system represents a real person, identity must remain intact.` is present and unaltered | Output: CONFIRMED or NOT FOUND |
| `about.html` | Confirm founding story `She went looking for the standard that should have existed. It didn't exist. So she and Brad built it.` is present and unaltered | Output: CONFIRMED or NOT FOUND |
| `framework.html` | Confirm `Seven normative instruments. One coherent standard.` is present and unaltered | Output: CONFIRMED or NOT FOUND |

---

## SKIPPED (do not touch — requires human review before next session)

The following items from the assessment are intentionally excluded from this manifest.
They require either Bobbie-Jane's input, a layout/design decision, or a taxonomy
review before copy can be finalised.

| Item | Location | Reason for exclusion |
|------|----------|----------------------|
| Bobbie-Jane bio restructure | `about.html` | Changes bio emphasis significantly — review with Bobbie first |
| Cascade triadic: "A failure in Identity may cascade through Authority, Consent, and Containment." | `framework.html` | Requires check against framework's own domain taxonomy before altering |
| Parallel illustration sentences (Issue 4, Assessment B) | `index.html` | B's closing line addition ("None of these failures require intent…") is good but adds new copy — out of scope for surgical manifest |
| Four failure classes in parenthetical | `white-paper.html` | Requires layout/card format decision, not a text-only edit |
| Regulatory Alignment colon list reorder | `regulatory-alignment.html` | Requires judgment on which framework elements deserve most positioning weight |
| Curriculum metaphor in Brad bio | `index.html` | Rewrites information architecture of the bio — review in context first |

---

## COMMIT

```bash
git add index.html framework.html white-paper.html services.html about.html regulatory-alignment.html
git commit -m "fix: copy — AI signal removal, register corrections, redundancy fixes (triangulated assessment March 2026)"
git push origin main
```

Output `git log --oneline -3` to confirm.

Output final summary:
- Every file changed
- Every ID applied or SKIPPED
- Any NEEDS_CITATION or NEEDS_DIFFERENTIATION flags
- Any VERIFY-ONLY failures
