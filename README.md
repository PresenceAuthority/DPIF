# Digital Presence Integrity Framework (DPIF)

**Version:** Control Model v1.1 | **Date:** 11 March 2026 | **Licence:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

---

## What is DPIF?

DPIF is a governance standard for AI-mediated digital representations of real persons (DRRPs) — systems that replicate or simulate a person's likeness, voice, or communicative presence using AI.

As technology makes photorealistic avatars, synthetic voices, and scaled multilingual digital presence operationally trivial, new systemic risks emerge: identity distortion, misuse of delegated authority, erosion of consent integrity, and loss of accountability. DPIF defines the non-compensatory controls required to prevent these outcomes.

The framework addresses a specific failure mode: **Presence Drift** — the gradual, often invisible erosion of identity fidelity, authority boundaries, consent integrity, or accountability caused by persistent or scaled digital representation.

---

## Scope

DPIF applies to:

- Photorealistic digital representations of real persons
- Synthetic voice systems linked to identifiable individuals
- AI-mediated video or interactive embodiments of real persons
- Multilingual or scaled digital presence deployments
- Organisational deployments where DRRPs communicate on behalf of individuals

DPIF does **not** evaluate AI model bias, output quality, productivity, or safety except where directly affecting representational integrity.

---

## Control Architecture

DPIF defines **18 controls** across **7 control pillars** plus a scope boundary enforcement requirement.

| Pillar | Controls | Description |
|---|---|---|
| Identity | IC-1.1, IC-1.2 | Fidelity validation and drift monitoring |
| Authority | AC-2.1, AC-2.2, AC-2.3 | Delegated authority definition, escalation blocking, output traceability |
| Consent | CC-3.1, CC-3.2, CC-3.3 | Scope declaration, revocation feasibility, modification logging |
| Disclosure | DC-4.1, DC-4.2 | Contextual disclosure enforcement and placement testing |
| Context Risk | CR-5.1, CR-5.2 | Risk tier classification and regulated context escalation |
| Semantic Integrity | SI-6.1, SI-6.2 | Transformation fidelity validation and version logging |
| Containment | CT-7.1, CT-7.2, CT-7.3 | Interaction logging, access tiering, governance review |
| Scope Boundary | BOUND-0.1 | Enforcement consistency across declared scope |

**14 controls are Critical Presence Controls (CPC)** — failure of any CPC results in immediate certification failure. The model is non-compensatory: no maturity score offsets a CPC failure.

**4 controls are Supporting Presence Controls (SPC)** — assessed on a 1–4 maturity scale via the Scoring Rubric, but only after all CPCs are confirmed Met.

---

## Instruments

All instruments are normative. The Control Model is the authoritative reference; all other instruments conform to it.

| Instrument | Version | File |
|---|---|---|
| Control Checklist | v2.0 | [DPIF_Control_Checklist_v2_0_110326.pdf](./DPIF_Control_Checklist_v2_0_110326.pdf) |
| Control Model | v1.1 | [DPIF_Control_Model_v1_1_110326.pdf](./DPIF_Control_Model_v1_1_110326.pdf) |
| Context Risk Classification Annex | v1.0 | [DPIF_Context_Risk_Classification_Annex_v1_0_110326.pdf](./DPIF_Context_Risk_Classification_Annex_v1_0_110326.pdf) |
| Deployment Lifecycle Specification | v1.0 | [DPIF_Deployment_Lifecycle_Specification_v1_0_110326.pdf](./DPIF_Deployment_Lifecycle_Specification_v1_0_110326.pdf) |
| Inter-Deployment Conflict Resolution Framework | v1.0 | [DPIF_InterDeployment_Conflict_Resolution_Framework_v1_0_110326.pdf](./DPIF_InterDeployment_Conflict_Resolution_Framework_v1_0_110326.pdf) |
| Posthumous and Incapacitated Principal Governance | v1.0 | [DPIF_Posthumous_Incapacitated_Principal_Governance_v1_0_110326.pdf](./DPIF_Posthumous_Incapacitated_Principal_Governance_v1_0_110326.pdf) |
| Scoring Rubric | v1.0 | [DPIF_Scoring_Rubric_v1_0_110326.pdf](./DPIF_Scoring_Rubric_v1_0_110326.pdf) |

---

## Deployment-Centric Verification

The primary unit of DPIF verification is the **Deployment** — a specific DRRP operating within a declared Scope of Use, under a specific Delegated Authority, in a classified context risk tier.

A single DRRP tool may support multiple independent deployments, each separately assessed. Tool-level assessment is subordinate: a tool may satisfy all technical controls and still fail deployment-level assessment if organisational governance, consent structures, or context risk controls are absent.

---

## Lifecycle Model

Every DRRP deployment exists in exactly one of five states: **Provisioning → Active → Suspended → Revoked → Archived**. State transitions are governed events requiring documented authorisation and evidence. Certification attaches to Active deployments only.

---

## Certification Tiers

| Tier | Composite SPC Score | Condition |
|---|---|---|
| Foundational | 1.0 – 1.9 | All CPCs Met; SPCs present but may be immature |
| Standard | 2.0 – 2.9 | All CPCs Met; SPCs consistently implemented |
| Extended | 3.0 – 4.0 | All CPCs Met; SPCs actively managed with metrics |

---

## Regulatory Context

DPIF is designed to operate alongside emerging regulatory frameworks governing synthetic media and AI-generated representations, including the EU AI Act, the proposed US NO FAKES Act, and the ELVIS Act. DPIF provides the operational governance architecture that these instruments identify as necessary but do not themselves specify.

Regulatory alignment documents mapping DPIF controls to specific legislative requirements are in development and will be published at [thepresenceauthority.com](https://thepresenceauthority.com).

---

## Licence and Attribution

All DPIF instruments are published under the [Creative Commons Attribution 4.0 International Licence (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to use, adapt, and redistribute these instruments for any purpose, including commercial assessments, provided you attribute the source.

**Cite as:**
> The Presence Authority. (2026). *Digital Presence Integrity Framework (DPIF) v1.1*. https://thepresenceauthority.com

---

## Contact

**The Presence Authority**
[thepresenceauthority.com](https://thepresenceauthority.com)

For assessment enquiries, standards body engagement, or regulatory alignment requests, contact via the website.
