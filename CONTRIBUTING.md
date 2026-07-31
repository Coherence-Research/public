# Contributing to Coherence-Research / public

This repository contains both **canonical specification documents** and **community-facing supporting materials**. The contribution rules differ by layer. Read this document before opening an issue or pull request.

## The two layers

### Canonical layer — modifications not accepted via community PR

```
standards/SC-AS/v1.0/SC-CORE-000001.md
standards/SC-AS/v1.0/SC-AXIOM-000001.md
standards/SC-AS/v1.0/SC-HDR-000001.md
standards/SC-AS/v1.0/SC-SCOPE-000001.md
standards/SC-AS/v1.0/certificates/
standards/SC-AS/v1.0/stewardship/
standards/SC-AS/v1.0/RELEASE_MANIFEST.json
standards/SC-AS/v1.0/MERKLE_TREE.json
standards/SC-AS/v1.0/MERKLE_ROOT.txt
standards/SC-AS/v1.0/pdf/
releases/
```

These artifacts carry SHA-256 hashes, RCC attestations, and a Merkle root. Modifying any of them invalidates the integrity chain for the entire release. They are released under CC BY-ND 4.0 — you cannot publish modified versions under the same name.

If you believe a canonical document contains an error — even a typo — **open an issue, do not open a PR.** Errata that affect canonical content go through a controlled revision process that produces a new versioned artifact, not an edit-in-place.

### Community layer — PRs welcome

```
guides/
educational/
research-notes/
events/                    (active event directories)
README.md
CONTRIBUTING.md, SUPPORT.md, CODE_OF_CONDUCT.md
.github/
```

These materials evolve through ordinary community contribution. Open issues, open PRs, suggest changes — the usual GitHub workflow.

## What we accept

- **Errata reports** (issue, not PR) for canonical documents — typos, broken links, formatting issues, header inconsistencies, integrity check failures.
- **Specification clarification requests** (issue) — passages where multiple readings are defensible, apparent inconsistencies between sections, or proposed structural counterexamples.
- **Improvements to guides** — `guides/using-the-spec.md`, applied patterns, FAQ, reading aids (PR).
- **Educational additions** — derivations, briefings, explainers in `educational/` (PR).
- **Research notes** — non-canonical research adjacent to the specification in `research-notes/` (PR).
- **Event materials** — new event directories under `events/` for events Coherence Research participates in (PR, coordinated with maintainers).
- **References to implementations** — link your repository or product from a Discussions thread. Don't open a PR to add your own implementation to this repo.

## What we don't accept

- **Direct modifications to canonical specification documents.** Issues yes, PRs no.
- **Modifications to release artifacts** (manifests, Merkle files, certificates, PDFs). These are mechanical outputs; corrections happen upstream in the revision process.
- **Promotional material masquerading as guidance.** Guides serve readers; they don't promote products, including ours. PRs that read as marketing will be declined.
- **Translations of canonical documents** as derivative works. Translations as *separate companion documents* with clear non-canonical status are welcome under `educational/`; modifications to canonical files are not.

## How canonical changes land

Accepted changes to the specification are never edited in place. They are batched into the next versioned release — re-derived where the change ripples, re-hashed per SC-HDR, with a new manifest, Merkle root, and release notes. The prior version remains published, verifiable, and citable indefinitely. Every proposal is evaluated against the same bar the existing text passed: explicit scope, dependency chain, necessity, minimality, and joint admissibility with what is already admitted. The evaluation happens in the open, on the issue, so the admission call is itself inspectable and challengeable.

Accepted errata and structural reports that shape a release are credited in that release's notes.

## How to contribute

### Report a typo or broken link in a canonical document

Open an issue with the `errata` template. Include the exact document, section or line, and a description of the issue.

### Propose a spec clarification

Open an issue with the `spec-clarification` template. State the passage, the multiple readings or apparent inconsistency, and your structural argument.

### Improve a guide, educational document, or research note

Open a PR. Small changes can go directly via PR; substantial changes (new guides, new patterns, new educational artifacts) should be discussed in an issue or Discussions thread first.

### Ask a question

Don't open an issue. Open a Discussions thread. See `SUPPORT.md` for routing.

## Conventions

- **Voice.** Declarative, austere, sourced. Match the existing repository tone.
- **Format.** Markdown, LF line endings, UTF-8, no trailing whitespace.
- **Citations.** When referencing canonical sections, use the form `SC-CORE §X.Y` or `SC-SCOPE §X`, not a hyperlink.
- **Authorship.** Community contributions to non-canonical paths are credited via git history. We do not maintain a separate contributors file at present.

## Maintainer review

Contributions to community-layer paths are reviewed by maintainers. Reviews focus on:

- Does the contribution match the repository's voice and structural standards?
- Does it cross the canonical boundary, intentionally or accidentally?
- Does it serve readers, not promote a product?

PRs that require extended discussion may be moved to a Discussions thread before merge. Resolution does not need to happen in a single review pass.

## Code of Conduct

Participation in this repository is governed by the Code of Conduct in `CODE_OF_CONDUCT.md`. Behavior that violates it is grounds for moderation independent of the technical quality of the contribution.

## Questions about contributing

Open a Discussions thread under *General*, or read `SUPPORT.md` for the full routing.
