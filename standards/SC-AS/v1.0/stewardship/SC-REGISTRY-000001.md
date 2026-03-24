# Structural Coherence Document Registry

## Canonical Document Header (Informative / Non-Normative Metadata)

- Document ID: SC-REGISTRY-000001
- Canonical Name: Structural Coherence Document Registry
- Document Class: LEDGER
- Version: 1.0.0
- Issuance ID: v01
- Release Status: DRAFT
- Effective Date: 2026-03-12
- Last Updated: 2026-03-15
- Issuing Authority: Coherence Research
- DOI / Persistent ID:
- Supersedes:
- Superseded By:
- Header Schema: SC-HDR-000001 (Issuance ID: v10)
- Integrity:
  - SHA-256:
  - Release Tag:

---

## Document Class Extension: LEDGER (Informative / Non-Normative Metadata)

LEDG::Schema-Version: 1.0
LEDG::Ledger-Type: document-registry
LEDG::Applies-To: All SC-AS-governed artifacts
LEDG::Resolution-Classes: namespace-allocation, dependency-tracking, lifecycle-state, conformance-review
LEDG::Generation-Method: manual + tooling-assisted

---

## 1. Purpose

This document is the **authoritative living index** of all artifacts governed by the Structural Coherence — Anchor Specification (SC-AS). It serves as the single source of truth for:

1. **Document discovery** — What exists, where it lives, and what version is current
2. **Namespace allocation** — Which Document IDs and namespace tokens are assigned, reserved, or retired
3. **Dependency tracking** — Which documents reference which, and the cascade impact of upstream changes
4. **Lifecycle state** — Current release status and conformance review obligations for every artifact
5. **Extension schema catalog** — What document class extensions are defined and where
6. **External reference tracking** — Academic and third-party works that cite or extend SC-AS without being governed by it

This registry does **not** replace the RELEASE_MANIFEST.json, which is a signed, integrity-bound release artifact capturing a frozen snapshot at a specific release boundary. The registry is a living operational document; the release manifest is a notarized photograph of a moment in time.

---

## 2. Scope and Authority

### 2.1 Governance Position

SC-REGISTRY-000001 is a **stewardship-tier** document (Tier 3). It carries operational authority within the governance scope defined by SC-GOV-000001 but does not participate in SC-AS derivation. It cannot modify, override, or extend the canonical set.

### 2.2 Relationship to Other Documents

- **SC-HDR-000001** — This document conforms to SC-HDR for its own header structure
- **SC-SCOPE-000001** — This document operates within the jurisdictional boundary defined by SC-SCOPE
- **SC-GOV-000001** — This document follows the governance procedures defined by SC-GOV for updates and issuances
- **RELEASE_MANIFEST.json** — At release time, the manifest captures a frozen slice of this registry's state

### 2.3 Update Cadence

This registry is updated whenever:
- A new document is issued or its status changes
- A namespace token or Document ID is allocated or reserved
- A dependency relationship changes due to a new issuance
- A conformance review obligation is triggered by an upstream change
- An external reference or implementation mapping is added

Updates to this document do not require a new issuance of any canonical document.

---

## 3. Governance Tier Definitions

SC-AS recognizes four governance tiers. Every registered artifact belongs to exactly one tier.

### Tier 0 — Canonical (Constitutional)

The closed, immutable canonical set. These four documents define the rules of the system. Amendment requires extraordinary governance per SC-GOV-000001. No elevation mechanism exists (per SC-SCOPE-000001 §6.1).

Members: SC-CORE-000001, SC-AXIOM-000001, SC-HDR-000001, SC-SCOPE-000001

### Tier 1 — Derived Specifications (Open, Extensible)

Documents that carry normative authority within their declared scope, derived from the canonical set. Each Tier 1 document declares its dependencies on canonical documents explicitly and derives its legitimacy from them. This is the primary growth tier — new specifications, formal theories, implementation specs, conformance suites, and projection frameworks enter here.

Members: SC-FCALC-000001, SC-CALC-000001, SC-TEST-000001, SC-PROJ-000001 (planned)

### Tier 2 — Certificates (Integrity Layer)

Reflexive Closure Certificates (RCCs) that prove a specific document issuance conforms to its declared basis. Certificates are integrity-bound to their targets via SHA-256 and cannot exist independently.

Members: All RCC-* documents

### Tier 3 — Stewardship (Operational Governance)

Documents that define operational governance, policy, licensing, naming, trademark, authorship, and registry infrastructure. Non-normative relative to SC-AS derivation but binding within their stewardship scope.

Members: SC-GOV-000001, SC-LICENSE-000001, SC-NAME-000001, SC-TM-000001, SC-AUTHORSHIP-000001, SC-REGISTRY-000001

---

## 4. Document Registry

### 4.1 Registry Entry Schema

Each registered artifact is described by the following fields:

| Field | Description |
|---|---|
| Document-ID | Globally unique canonical identifier (e.g., SC-CORE-000001) |
| Canonical-Name | Human-readable document title |
| Document-Class | SC-HDR document class (SPEC, MODULE, RCC, LEDGER, PAPER, FRAMEWORK, POLICY, NOTE) |
| Governance-Tier | 0 (canonical), 1 (derived), 2 (certificate), 3 (stewardship) |
| Current-Issuance-ID | Latest issued issuance identifier |
| Current-Version | Current semantic version |
| Release-Status | DRAFT, ISSUED, DEPRECATED, SUPERSEDED, WITHDRAWN |
| DOI | Persistent identifier (Zenodo DOI or equivalent), if assigned |
| Repository-Path | File path relative to repository root |
| SHA-256 | Integrity hash of current issuance (per SC-HDR §3.2 rule 7) |
| Header-Schema-Ref | SC-HDR issuance this document's header conforms to |
| Supersedes | Document + issuance this artifact replaced |
| Superseded-By | Document + issuance that replaced this artifact (if applicable) |
| Direct-Dependencies | Document IDs this artifact explicitly references |
| Spec-Subclass | For SPEC-class documents only: further classification |
| Steward | Responsible party or organization |
| First-Issued | Date of initial issuance |
| Last-Updated | Date of most recent change |
| Abstract | One-line description of purpose |

### 4.2 Tier 0 — Canonical Documents

#### SC-CORE-000001

| Field | Value |
|---|---|
| Document-ID | SC-CORE-000001 |
| Canonical-Name | The Coherence Core Specification |
| Document-Class | SPEC |
| Governance-Tier | 0 — Canonical |
| Current-Issuance-ID | v39c |
| Current-Version | 1.2.5 |
| Release-Status | ISSUED |
| DOI | 10.5281/zenodo.18039635 |
| Repository-Path | specs/canonical/SC-CORE-000001.md |
| SHA-256 | 3e572e7b85e9973e034e3d36ab5cbcdf14a94b0bcc8e17ec2cff8524cddb27f8 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-CORE-000001 (v39b) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 |
| Spec-Subclass | core-spec |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines the foundational structural framework, core terms (T0–T7), binding clauses, and meta-structural governance for all SC-AS-governed artifacts |

#### SC-AXIOM-000001

| Field | Value |
|---|---|
| Document-ID | SC-AXIOM-000001 |
| Canonical-Name | The Coherence Axiom Specification |
| Document-Class | SPEC |
| Governance-Tier | 0 — Canonical |
| Current-Issuance-ID | v11k |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | 10.5281/zenodo.18043770 |
| Repository-Path | specs/canonical/SC-AXIOM-000001.md |
| SHA-256 | 5cdb80fa56af587d12a5c6e10e0fc23fecb5ba07195d6bc23f7d261beb8f487d |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-AXIOM-000001 (v11j) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001, SC-CORE-000001 |
| Spec-Subclass | axiom-spec |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines the axiomatic foundations and derivation rules upon which all structural coherence claims rest |

#### SC-HDR-000001

| Field | Value |
|---|---|
| Document-ID | SC-HDR-000001 |
| Canonical-Name | Structural Coherence Document Header Specification |
| Document-Class | SPEC |
| Governance-Tier | 0 — Canonical |
| Current-Issuance-ID | v10 |
| Current-Version | 0.3.0 |
| Release-Status | ISSUED |
| DOI | PENDING — to be minted on Zenodo |
| Repository-Path | specs/canonical/SC-HDR-000001.md |
| SHA-256 | 045570cfe2fd7b7473f1ddbf8e5611415c262fba56c0430ec5c79759e4791288 |
| Header-Schema-Ref | SC-HDR-000001 (v10) — self-referential |
| Supersedes | SC-HDR-000001 (v09a) |
| Superseded-By | — |
| Direct-Dependencies | SC-CORE-000001, SC-AXIOM-000001 |
| Spec-Subclass | header-spec |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines the normalized base header, document class extensions, integrity computation rules, and validation requirements for all SC-AS artifacts |

#### SC-SCOPE-000001

| Field | Value |
|---|---|
| Document-ID | SC-SCOPE-000001 |
| Canonical-Name | Structural Coherence Scope Specification |
| Document-Class | SPEC |
| Governance-Tier | 0 — Canonical |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | PENDING — to be minted on Zenodo |
| Repository-Path | specs/canonical/SC-SCOPE-000001.md |
| SHA-256 | 1903b0dbcdb69e851cae53b62facdb5f6ae6027077950fc9703b798bcbb8dd2e |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-SCOPE-000001 (v03b) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001, SC-CORE-000001, SC-AXIOM-000001 |
| Spec-Subclass | scope-spec |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines the jurisdictional boundary of SC-AS, canonical set membership, certificate tier architecture, and constitutional bundle composition |

### 4.3 Tier 1 — Derived Specifications

#### SC-FCALC-000001

| Field | Value |
|---|---|
| Document-ID | SC-FCALC-000001 |
| Canonical-Name | Structural Coherence Formal Operational Calculus — Formal Theory |
| Document-Class | FRAMEWORK |
| Governance-Tier | 1 — Derived |
| Current-Issuance-ID | v03 |
| Current-Version | 0.7.0-DRAFT |
| Release-Status | DRAFT |
| DOI | — |
| Repository-Path | specs/derived/SC-FCALC-000001.md |
| SHA-256 | — |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-FCALC-000001 (v02) |
| Superseded-By | — |
| Direct-Dependencies | SC-CORE-000001, SC-AXIOM-000001, SC-HDR-000001, SC-SCOPE-000001 |
| Spec-Subclass | — (FRAMEWORK class; uses FWK:: extension) |
| Steward | Coherence Research |
| First-Issued | 2026-03-15 |
| Last-Updated | 2026-03-15 |
| Abstract | Formal operational theory over SC-AS primitives; proves convergence, closure correspondence, emergence transitions, composition, and ordering-representability conditions |

#### SC-CALC-000001

| Field | Value |
|---|---|
| Document-ID | SC-CALC-000001 |
| Canonical-Name | Structural Coherence Implementation Calculus |
| Document-Class | SPEC |
| Governance-Tier | 1 — Derived |
| Current-Issuance-ID | v02 |
| Current-Version | — |
| Release-Status | DRAFT |
| DOI | — |
| Repository-Path | PENDING — not yet in repository |
| SHA-256 | — |
| Header-Schema-Ref | PENDING — must conform to SC-HDR-000001 (v10) upon issuance |
| Supersedes | SC-CALC-000001 (v01) |
| Superseded-By | — |
| Direct-Dependencies | SC-FCALC-000001, SC-HDR-000001 |
| Spec-Subclass | implementation-spec |
| Steward | Coherence Research |
| First-Issued | — |
| Last-Updated | — |
| Abstract | Translates the formal calculus into implementable computation rules, algorithms, and data structure specifications |

#### SC-TEST-000001

| Field | Value |
|---|---|
| Document-ID | SC-TEST-000001 |
| Canonical-Name | Structural Coherence Conformance Suite |
| Document-Class | SPEC |
| Governance-Tier | 1 — Derived |
| Current-Issuance-ID | — |
| Current-Version | — |
| Release-Status | PLANNED |
| DOI | — |
| Repository-Path | PENDING — not yet created |
| SHA-256 | — |
| Header-Schema-Ref | PENDING — must conform to SC-HDR-000001 (v10) upon issuance |
| Supersedes | — |
| Superseded-By | — |
| Direct-Dependencies | SC-CALC-000001, SC-HDR-000001 |
| Spec-Subclass | conformance-suite |
| Steward | Coherence Research |
| First-Issued | — |
| Last-Updated | — |
| Abstract | Defines conformance test methodology, pass/fail criteria, and test vectors for validating implementations against SC-CALC |

#### SC-PROJ-000001

| Field | Value |
|---|---|
| Document-ID | SC-PROJ-000001 |
| Canonical-Name | Structural Coherence Projection Discipline |
| Document-Class | FRAMEWORK |
| Governance-Tier | 1 — Derived |
| Current-Issuance-ID | — |
| Current-Version | — |
| Release-Status | PLANNED |
| DOI | — |
| Repository-Path | PENDING — not yet created |
| SHA-256 | — |
| Header-Schema-Ref | PENDING — must conform to SC-HDR-000001 (v10) upon issuance |
| Supersedes | — |
| Superseded-By | — |
| Direct-Dependencies | SC-TEST-000001, SC-CALC-000001, SC-HDR-000001 |
| Spec-Subclass | — (FRAMEWORK class; uses FWK:: extension) |
| Steward | Coherence Research |
| First-Issued | — |
| Last-Updated | — |
| Abstract | Defines the projection discipline for applying structural coherence to specific domains, including projection constraints, binding requirements, and validation criteria |

### 4.4 Tier 2 — Certificates

#### RCC-SC-CORE-000001 (v02 — Current)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-CORE-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-CORE v39c |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v02 |
| Current-Version | 1.0.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-CORE-000001__v39c__v02.md |
| SHA-256 | 20cc6007b5841bccc208b4b656245b3896d92165684c2fca01cba4f5e7eaceb0 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | RCC-SC-CORE-000001 (v01) |
| Superseded-By | — |
| Direct-Dependencies | SC-CORE-000001 (v39c) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-11 |
| Last-Updated | 2026-03-11 |
| Abstract | Certifies SC-CORE-000001 v39c conformance to SC-AS via reflexive closure analysis |

#### RCC-SC-AXIOM-000001 (v02 — Current)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-AXIOM-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-AXIOM v11k |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v02 |
| Current-Version | 1.0.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-AXIOM-000001__v11k__v02.md |
| SHA-256 | 70699c4220ed1f7edfd64557d72e8619421f25ffb49489f101e7412b02fbf156 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | RCC-SC-AXIOM-000001 (v01) |
| Superseded-By | — |
| Direct-Dependencies | SC-AXIOM-000001 (v11k) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-11 |
| Last-Updated | 2026-03-11 |
| Abstract | Certifies SC-AXIOM-000001 v11k conformance to SC-AS via reflexive closure analysis |

#### RCC-SC-HDR-000001 (v01 — Current)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-HDR-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-HDR v10 |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v01 |
| Current-Version | 1.0.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-HDR-000001__v10__v01.md |
| SHA-256 | 5cda8cbacb0ae7178f504a73cae94f0798cdec8e50602ccee548e39585c426f2 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | — |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 (v10) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-11 |
| Last-Updated | 2026-03-11 |
| Abstract | Certifies SC-HDR-000001 v10 self-referential conformance, extension schema completeness, and namespace token uniqueness |

#### RCC-SC-SCOPE-000001 (v01 — Current)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-SCOPE-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-SCOPE v04 |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v01 |
| Current-Version | 1.0.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-SCOPE-000001__v04__v01.md |
| SHA-256 | 99b2d0ccb082fda8a022c9fc5bcb4860f972114c35790278387b92675f3521ab |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | — |
| Superseded-By | — |
| Direct-Dependencies | SC-SCOPE-000001 (v04) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-11 |
| Last-Updated | 2026-03-11 |
| Abstract | Certifies SC-SCOPE-000001 v04 jurisdictional boundary definitions, canonical set membership, and constitutional bundle composition |

#### RCC-SC-CORE-000001 (v01 — Superseded)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-CORE-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-CORE v39c (Original) |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v01 |
| Current-Version | 1.0.0 |
| Release-Status | SUPERSEDED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-CORE-000001__v39c__v01.md |
| SHA-256 | e2ea31cbfa17d2ff41775d665a60391161e2b9b088f4be616b62cad026860cba |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | — |
| Superseded-By | RCC-SC-CORE-000001 (v02) |
| Direct-Dependencies | SC-CORE-000001 (v39c) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Original RCC for SC-CORE v39c; superseded by v02 with updated integrity coupling |

#### RCC-SC-AXIOM-000001 (v01 — Superseded)

| Field | Value |
|---|---|
| Document-ID | RCC-SC-AXIOM-000001 |
| Canonical-Name | Reflexive Closure Certificate — SC-AXIOM v11k (Original) |
| Document-Class | RCC |
| Governance-Tier | 2 — Certificate |
| Current-Issuance-ID | v01 |
| Current-Version | 1.0.0 |
| Release-Status | SUPERSEDED |
| DOI | — |
| Repository-Path | specs/certificates/rcc__SC-AXIOM-000001__v11k__v01.md |
| SHA-256 | 0aa2da2c83272be621babc8ea8b087e9bc4842bec34e46c6b972554fd7f43146 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | — |
| Superseded-By | RCC-SC-AXIOM-000001 (v02) |
| Direct-Dependencies | SC-AXIOM-000001 (v11k) — target |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Original RCC for SC-AXIOM v11k; superseded by v02 with updated integrity coupling |

### 4.5 Tier 3 — Stewardship Documents

#### SC-GOV-000001

| Field | Value |
|---|---|
| Document-ID | SC-GOV-000001 |
| Canonical-Name | Structural Coherence Governance Policy |
| Document-Class | POLICY |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/stewardship/SC-GOV-000001.md |
| SHA-256 | 4d46636c305a32308e32d0aa14cde22f8fd615deccaa8d1166e896d0a547d2a1 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-GOV-000001 (v03) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001, SC-CORE-000001, SC-SCOPE-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines governance procedures, validation phases, versioning policy, and issuance authority for all SC-AS-governed artifacts |

#### SC-LICENSE-000001

| Field | Value |
|---|---|
| Document-ID | SC-LICENSE-000001 |
| Canonical-Name | Structural Coherence Licensing Policy |
| Document-Class | POLICY |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/stewardship/SC-LICENSE-000001.md |
| SHA-256 | 4e9236957d15daa8e94487062d8857f65f4a5457d1a6fcbc780970f4794f3877 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-LICENSE-000001 (v03) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines licensing terms and distribution rights for SC-AS artifacts |

#### SC-NAME-000001

| Field | Value |
|---|---|
| Document-ID | SC-NAME-000001 |
| Canonical-Name | Structural Coherence Naming Policy |
| Document-Class | POLICY |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/stewardship/SC-NAME-000001.md |
| SHA-256 | e54a62e61736962c3f44e949c52c3715cbe7ca11c612a94863d901de893fa456 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-NAME-000001 (v03) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines naming conventions, Document ID format rules, and namespace token allocation for SC-AS artifacts |

#### SC-TM-000001

| Field | Value |
|---|---|
| Document-ID | SC-TM-000001 |
| Canonical-Name | Structural Coherence Trademark Policy |
| Document-Class | POLICY |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/stewardship/SC-TM-000001.md |
| SHA-256 | 9abf3ac546d6ea3e09f53b14b5622b99a0493b2aef6df0795501fed1272e8bc7 |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-TM-000001 (v03) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Defines trademark protections, usage constraints, and brand integrity requirements for the Structural Coherence mark |

#### SC-AUTHORSHIP-000001

| Field | Value |
|---|---|
| Document-ID | SC-AUTHORSHIP-000001 |
| Canonical-Name | Structural Coherence Authorship Declaration |
| Document-Class | POLICY |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v04 |
| Current-Version | 1.1.0 |
| Release-Status | ISSUED |
| DOI | — |
| Repository-Path | specs/stewardship/SC-AUTHORSHIP-000001.md |
| SHA-256 | 8bf07e6d1f18dd968d398115a87c58bfacfd52764fdbc29bf90ad630e375e80a |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | SC-AUTHORSHIP-000001 (v03) |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-04 |
| Last-Updated | 2026-03-11 |
| Abstract | Declares authorship, PGP key fingerprints, and provenance chain for the SC-AS specification suite |

#### SC-REGISTRY-000001

| Field | Value |
|---|---|
| Document-ID | SC-REGISTRY-000001 |
| Canonical-Name | Structural Coherence Document Registry |
| Document-Class | LEDGER |
| Governance-Tier | 3 — Stewardship |
| Current-Issuance-ID | v01 |
| Current-Version | 1.0.0 |
| Release-Status | DRAFT |
| DOI | — |
| Repository-Path | specs/stewardship/SC-REGISTRY-000001.md |
| SHA-256 | — (computed upon issuance) |
| Header-Schema-Ref | SC-HDR-000001 (v10) |
| Supersedes | — |
| Superseded-By | — |
| Direct-Dependencies | SC-HDR-000001, SC-SCOPE-000001, SC-GOV-000001 |
| Steward | Coherence Research |
| First-Issued | 2026-03-12 |
| Last-Updated | 2026-03-15 |
| Abstract | Authoritative living index of all SC-AS-governed artifacts, namespace allocations, dependency graph, and lifecycle state |

---

## 5. Namespace Allocation Table

Namespace allocation rules and naming conventions are governed by SC-NAME-000001. This section records current allocations; SC-NAME governs the allocation process and format requirements.

### 5.1 Allocated Document ID Prefixes

| Prefix | Document-ID | Status | Tier | Allocated Date |
|---|---|---|---|---|
| SC-CORE | SC-CORE-000001 | ACTIVE | 0 | 2026-03-04 |
| SC-AXIOM | SC-AXIOM-000001 | ACTIVE | 0 | 2026-03-04 |
| SC-HDR | SC-HDR-000001 | ACTIVE | 0 | 2026-03-04 |
| SC-SCOPE | SC-SCOPE-000001 | ACTIVE | 0 | 2026-03-04 |
| SC-GOV | SC-GOV-000001 | ACTIVE | 3 | 2026-03-04 |
| SC-LICENSE | SC-LICENSE-000001 | ACTIVE | 3 | 2026-03-04 |
| SC-NAME | SC-NAME-000001 | ACTIVE | 3 | 2026-03-04 |
| SC-TM | SC-TM-000001 | ACTIVE | 3 | 2026-03-04 |
| SC-AUTHORSHIP | SC-AUTHORSHIP-000001 | ACTIVE | 3 | 2026-03-04 |
| SC-REGISTRY | SC-REGISTRY-000001 | ACTIVE | 3 | 2026-03-12 |
| SC-FCALC | SC-FCALC-000001 | ACTIVE | 1 | 2026-03-12 |
| SC-CALC | SC-CALC-000001 | ALLOCATED | 1 | 2026-03-12 |
| SC-TEST | SC-TEST-000001 | RESERVED | 1 | 2026-03-12 |
| SC-PROJ | SC-PROJ-000001 | RESERVED | 1 | 2026-03-12 |

### 5.2 Allocated RCC Document ID Prefixes

| Prefix | Status | Bound-To |
|---|---|---|
| RCC-SC-CORE | ACTIVE | SC-CORE-000001 |
| RCC-SC-AXIOM | ACTIVE | SC-AXIOM-000001 |
| RCC-SC-HDR | ACTIVE | SC-HDR-000001 |
| RCC-SC-SCOPE | ACTIVE | SC-SCOPE-000001 |

### 5.3 Namespace Token Status Legend

| Status | Meaning |
|---|---|
| ACTIVE | Document exists and is ISSUED or DRAFT in repository |
| ALLOCATED | Document ID assigned; document exists but not yet in repository |
| RESERVED | Document ID reserved for a planned document that does not yet exist |
| RETIRED | Prefix permanently withdrawn from use |

### 5.4 Sequence Number Allocation

All current documents use sequence number `000001` within their prefix. Sequence numbers `000002+` are available for future use if multiple documents share a prefix (not currently anticipated for SC-AS).

---

## 6. Dependency Graph

### 6.1 Upstream Dependency Matrix

This matrix shows what each document directly depends on (reads left-to-right: row document depends on column document).

| Document | SC-CORE | SC-AXIOM | SC-HDR | SC-SCOPE | SC-FCALC | SC-CALC | SC-TEST |
|---|---|---|---|---|---|---|---|
| **SC-CORE** | — | | ✓ | | | | |
| **SC-AXIOM** | ✓ | — | ✓ | | | | |
| **SC-HDR** | ✓ | ✓ | — (self) | | | | |
| **SC-SCOPE** | ✓ | ✓ | ✓ | — | | | |
| **SC-FCALC** | ✓ | ✓ | ✓ | ✓ | — | | |
| **SC-CALC** | | | ✓ | | ✓ | — | |
| **SC-TEST** | | | ✓ | | | ✓ | — |
| **SC-PROJ** | | | ✓ | | | ✓ | ✓ |
| **SC-GOV** | ✓ | | ✓ | ✓ | | | |
| **SC-LICENSE** | | | ✓ | | | | |
| **SC-NAME** | | | ✓ | | | | |
| **SC-TM** | | | ✓ | | | | |
| **SC-AUTHORSHIP** | | | ✓ | | | | |
| **SC-REGISTRY** | | | ✓ | ✓ | | | |

### 6.2 Cascade Impact Sets

When a document receives a new issuance, all documents in its cascade set require **conformance review** — their existing RCCs become stale and must be re-validated against the new upstream issuance.

**SC-CORE-000001 cascade:**
- Direct: SC-AXIOM, SC-HDR, SC-SCOPE, SC-FCALC, SC-GOV
- Transitive: SC-CALC → SC-TEST → SC-PROJ
- Impact: **Full ecosystem review** — SC-CORE changes ripple everywhere

**SC-AXIOM-000001 cascade:**
- Direct: SC-HDR, SC-SCOPE, SC-FCALC
- Transitive: SC-CALC → SC-TEST → SC-PROJ
- Impact: **Derived chain review** — SC-AXIOM changes cascade through all documents that depend on it, but NOT back to SC-CORE (SC-CORE does not depend on SC-AXIOM)

**SC-HDR-000001 cascade:**
- Direct: Every document in the ecosystem (all declare Header-Schema conformance)
- Impact varies by amendment classification (see §6.4):
  - **Structural amendment** (base header key set or integrity/validation rules): Universal conformance review
  - **Extension amendment** (new document class or extension keys): Review limited to documents of the affected class
  - **Editorial amendment** (typos, examples, clarifications): SC-HDR re-issuance for traceability; no downstream review required

**SC-SCOPE-000001 cascade:**
- Direct: SC-GOV, SC-REGISTRY, SC-FCALC
- Impact: **Governance review** — scope boundary changes affect governance tier classification and membership

**SC-FCALC-000001 cascade:**
- Direct: SC-CALC
- Transitive: SC-TEST → SC-PROJ
- Impact: **Derived specification chain** — formal theory changes cascade through implementation

**SC-CALC-000001 cascade:**
- Direct: SC-TEST, SC-PROJ
- Impact: **Implementation chain** — calculation changes cascade through testing and projection

**SC-TEST-000001 cascade:**
- Direct: SC-PROJ
- Impact: **Conformance chain** — test methodology changes affect projection validation

### 6.3 Conformance Review Obligation Policy

When an upstream document receives a new issuance:

1. **The downstream document's existing conformance certificate (RCC or SCC) is NOT automatically invalidated.** It remains ISSUED but is marked as **REVIEW-REQUIRED** in this registry.
2. The steward of each downstream document has a **conformance review obligation** — they must assess whether the upstream change materially affects their document.
3. If the review determines no material impact, the existing certificate remains valid and the REVIEW-REQUIRED flag is cleared.
4. If the review determines material impact, a new issuance of the downstream document is required, followed by a new conformance certificate.
5. The cascade propagates transitively — if a Tier 1 document is re-issued due to upstream changes, its own downstream documents inherit conformance review obligations.

### 6.4 SC-HDR Amendment Classification

Because SC-HDR is a universal dependency (every document declares Header-Schema conformance), changes to SC-HDR require classification to determine the appropriate cascade scope. Amendment classification is the responsibility of the issuing authority per SC-GOV-000001.

**Structural amendment** — Changes to the base header key set (SC-HDR §3.1) or integrity/validation rules (SC-HDR §3.2, §7). These alter what constitutes a conformant header or how integrity is computed. Impact: universal conformance review obligation for all documents.

**Extension amendment** — Addition of a new document class to the class enumeration (SC-HDR §4.1) or a new extension schema (SC-HDR §5). These expand capability without altering existing schemas. Impact: conformance review limited to documents of the affected class, plus the SC-HDR conformance certificate itself.

**Editorial amendment** — Typographic corrections, example updates (SC-HDR §8), or clarifications to non-normative text that do not change any requirement. Impact: SC-HDR re-issuance for traceability; no downstream conformance review required.

---

## 7. Extension Schema Catalog

This section catalogs all document class extension schemas defined by SC-HDR-000001. New schemas require an SC-HDR issuance.

### 7.1 Currently Defined Schemas

| Document Class | Namespace Token | Defining Document | Required Keys | Optional Keys |
|---|---|---|---|---|
| SPEC | SPEC | SC-HDR-000001 (v10) §5.1 | Header-Schema-Version, Standard, Spec-Subclass, Revisability, Canonical-Dependencies | Subtitle, Representational-Perspective, Discipline-Scope, Document-Posture, Patch-Label |
| MODULE | MOD | SC-HDR-000001 (v10) §5.2 | Header-Schema-Version, Standard, Module-ID, Canonical-Dependencies | Binding-Surface-Index, Admitted-Vocabulary-Notes |
| RCC | RCC | SC-HDR-000001 (v10) §5.3 | Schema-Version, Target-Document-ID, Target-SHA-256, Basis, Result | Findings-Index, Assumptions, Tooling-Notes |
| LEDGER | LEDG | SC-HDR-000001 (v10) §5.4 | Schema-Version, Ledger-Type, Applies-To | Resolution-Classes, Unresolved-Surface-Policy, Generation-Method |
| PAPER | PAPR | SC-HDR-000001 (v10) §5.5 | Schema-Version, Series, Dependency-Basis, Stability | Abstract-Intent, Claims |
| FRAMEWORK | FWK | SC-HDR-000001 (v10) §5.6 | Schema-Version, Basis, Scope | Interfaces, Invariants, Compliance-Tests |
| NOTE | NOTE | SC-HDR-000001 (v10) §5.7 | Schema-Version, NonNormative-Only (must be TRUE) | Topic-Tags, Context |
| POLICY | POL | SC-HDR-000001 (v10) §5.8 | Schema-Version, NonDerivational-Only, Policy-Subtype, Applies-To | Enforcement-Scope, Related-Artifacts |

### 7.2 Schema Usage by Registered Documents

| Schema | Documents Using It |
|---|---|
| SPEC | SC-CORE, SC-AXIOM, SC-HDR, SC-SCOPE, SC-CALC, SC-TEST |
| FRAMEWORK | SC-FCALC, SC-PROJ |
| RCC | All RCC-* documents |
| LEDGER | SC-REGISTRY |
| POLICY | SC-GOV, SC-LICENSE, SC-NAME, SC-TM, SC-AUTHORSHIP |
| MODULE | (none currently — reserved for domain-specific projection modules) |
| PAPER | (none currently — reserved for research papers) |
| NOTE | (none currently — reserved for informal notes) |

---

## 8. External References

This section tracks academic publications, third-party works, and external artifacts that cite, extend, or implement SC-AS but are **not governed** by it. These entries carry no SC-AS Document ID and no header conformance obligation.

### 8.1 External Reference Schema

| Field | Description |
|---|---|
| External-ID | DOI, URL, or other persistent identifier |
| Title | Publication or artifact title |
| Authors | Creator(s) |
| Date | Publication date |
| Relationship | One of: CITES, EXTENDS, IMPLEMENTS, VALIDATES, DISCUSSES |
| Target-Document-IDs | Which SC-AS documents it relates to |
| Notes | Brief description of the relationship |

### 8.2 Registered External References

(No external references registered at this time. Entries will be added as academic papers and third-party implementations are published.)

---

## 9. Lifecycle State Machine

Lifecycle transition rules, approval gates, and governance authority are governed by SC-GOV-000001. This section defines the state model and records current document states; SC-GOV governs the transition process and authorization requirements.

### 9.1 Allowed State Transitions

```
                    ┌──────────────────────┐
                    │                      │
                    ▼                      │
              ┌──────────┐          ┌──────────────┐
              │  DRAFT   │─────────▶│   ISSUED     │
              └──────────┘          └──────────────┘
                                      │         │
                                      │         │
                                      ▼         ▼
                              ┌────────────┐ ┌─────────────┐
                              │ DEPRECATED │ │ SUPERSEDED  │
                              └────────────┘ └─────────────┘
                                      │          (terminal)
                                      │
                                      ▼
                              ┌────────────┐
                              │ WITHDRAWN  │
                              └────────────┘
                                 (terminal)
```

### 9.2 Transition Rules

| From | To | Trigger | Authority Required |
|---|---|---|---|
| DRAFT | ISSUED | Conformance certificate (RCC or SCC) issued + validation pass | Steward + governance approval |
| ISSUED | DEPRECATED | Governance decision (planned retirement) | Governance authority per SC-GOV |
| ISSUED | SUPERSEDED | New issuance of same Document ID issued | Automatic upon new issuance |
| DEPRECATED | WITHDRAWN | Final retirement after deprecation period | Governance authority per SC-GOV |
| SUPERSEDED | (none) | Terminal state — no transitions out | — |
| WITHDRAWN | (none) | Terminal state — no transitions out | — |

### 9.3 Prohibited Transitions

- DEPRECATED → ISSUED (no un-deprecation; issue a new document instead)
- WITHDRAWN → any state (withdrawal is permanent)
- SUPERSEDED → any state (supersession is permanent; the superseding document carries forward)
- DRAFT → DEPRECATED/SUPERSEDED/WITHDRAWN (drafts are either issued or abandoned)

---

## 10. Cryptographic Signing Infrastructure

Key provenance, authorship, and hardware custody are governed by SC-AUTHORSHIP-000001. This section provides the verification-facing subset needed for end-user artifact validation; SC-AUTHORSHIP governs in case of conflict (see §10.4).

### 10.1 Authoritative PGP Keys

The following PGP keys are authorized to sign SC-AS release artifacts (manifests, release tags, detached signatures).

#### Key 1 — Primary Signing Key

| Field | Value |
|---|---|
| Role | Primary release signing |
| Key Type | RSA 4096 |
| Fingerprint | `7D8A 695A E9B8 3A4E 005D D856 8556 37E7 AA76 819C` |
| Key ID | `AA76819C` |
| Status | ACTIVE |
| Authorized Operations | Manifest signing, release tag signing, detached artifact signatures |

#### Key 2 — Backup Signing Key

| Field | Value |
|---|---|
| Role | Backup / continuity signing |
| Key Type | RSA 4096 |
| Fingerprint | `4CAF C45D D616 7A35 FB30 1ED9 3051 558B 1E1C 1237` |
| Key ID | `1E1C1237` |
| Status | ACTIVE (backup) |
| Authorized Operations | Same as Key 1; used only when Key 1 is unavailable |

### 10.2 Verification

To verify a signed SC-AS release artifact:

1. Obtain the signer's public key from a trusted keyserver or directly from the issuing authority
2. Confirm the key fingerprint matches one of the ACTIVE keys listed in §10.1
3. Validate the detached signature or signed tag against the artifact

### 10.3 Key Trust Policy

1. **Dual independent keys.** Key 1 and Key 2 are independently generated key pairs — neither is a subkey of the other. Both are full-authority signing keys.
2. **Hardware-bound.** Private keys are non-exportable. Loss of a hardware module means permanent loss of that key pair.
3. **Single-signer authority.** Either key may sign a release artifact independently. Dual-signature is not required but may be used for high-assurance releases.
4. **Key rotation.** If either key is compromised or retired, the old key's fingerprint must be marked REVOKED in this section, and the new fingerprint registered. SC-AUTHORSHIP-000001 must be updated in parallel.

### 10.4 Cross-Reference

The authoritative source for authorship, key provenance, and hardware custody details is **SC-AUTHORSHIP-000001 §5**. This section provides only the verification-facing subset needed for end-user artifact validation. In case of conflict, SC-AUTHORSHIP-000001 governs.

---

## 11. Registry Maintenance Procedures

### 11.1 Adding a New Document

1. Allocate a Document ID prefix in §5.1 (status: RESERVED or ALLOCATED)
2. Create a registry entry in the appropriate tier section (§4.2–4.5)
3. If the document has dependencies, update §6.1 (dependency matrix) and §6.2 (cascade impact sets)
4. If the document uses an extension schema, verify it exists in §7.1 and update §7.2

### 11.2 Issuing a New Version of an Existing Document

1. Update the registry entry: Current-Issuance-ID, Current-Version, SHA-256, Last-Updated
2. Set the previous issuance's registry entry to SUPERSEDED (if tracked separately, as with RCCs)
3. Review §6.2 cascade impact sets — flag downstream documents as REVIEW-REQUIRED
4. Update the release manifest at next release boundary

### 11.3 Retiring a Document

1. Change Release-Status to DEPRECATED in the registry entry
2. Set a deprecation notice with planned withdrawal date
3. After deprecation period: change to WITHDRAWN
4. Update namespace table: change status to RETIRED
5. Do NOT delete the registry entry — maintain full history

### 11.4 Adding an External Reference

1. Add entry to §8.2 with External-ID, relationship type, and target Document IDs
2. No header conformance or RCC required — external references are informational

---

## Appendix A: Registry Statistics

| Metric | Count |
|---|---|
| Total registered documents | 20 (including this document) |
| Tier 0 (Canonical) | 4 |
| Tier 1 (Derived — ISSUED) | 0 |
| Tier 1 (Derived — DRAFT/PLANNED) | 4 |
| Tier 2 (Certificates — ISSUED) | 4 |
| Tier 2 (Certificates — SUPERSEDED) | 2 |
| Tier 3 (Stewardship — ISSUED) | 5 |
| Tier 3 (Stewardship — DRAFT) | 1 (this document) |
| Document ID prefixes allocated (§5.1) | 14 |
| RCC prefixes allocated (§5.2) | 4 |
| Namespace prefixes reserved | 2 (SC-TEST, SC-PROJ) |
| External references | 0 |
| DOIs assigned | 2 (SC-CORE, SC-AXIOM) |
| DOIs pending | 2 (SC-HDR, SC-SCOPE) |

---

End of Document
