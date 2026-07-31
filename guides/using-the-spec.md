# Using the Specification

This guide is the entry point for anyone working with the Structural Coherence — Anchor Specification (SC-AS). It does not teach SC-AS — the specification documents themselves do that. It tells you what's in this repository, where to start depending on what you came for, and how to verify everything you're reading.

## What lives where

```
standards/SC-AS/v1.0/    canonical specification documents (CC BY-ND 4.0)
guides/                  community guidance — using, applying, FAQ, patterns
educational/             explanatory materials, briefings, derivations
research-notes/          non-canonical research adjacent to the specification
releases/                release artifacts and bundle archives
events/                  materials for events Coherence Research participates in
```

The canonical specification lives in `standards/SC-AS/v1.0/`. Everything else is supporting, derived, or community material.

## Reading order

**If you're new and want structural intuition first.**
Start with the overview at <https://coherenceresearch.com/overview>. Come back to the canonical documents when concrete claims need verification.

**If you're going to apply SC-AS to a system.**
Read in this order:

1. **SC-SCOPE-000001** — what the specification does and does not claim. This bounds everything that follows.
2. **SC-CORE-000001** — the formal kernel: primitives, admissibility conditions, valid emergence rules.
3. **SC-AXIOM-000001** — canonical derivations from the kernel.
4. **SC-HDR-000001** — only if you need to understand how canonical documents declare their own integrity. Most readers can skip this on a first pass.

The four documents live at `standards/SC-AS/v1.0/` as both `.md` source and rendered PDFs under `pdf/`.

**If you're checking integrity rather than reading.**
Skip to *Verifying what you're reading* below.

## Reading the formal kernel

SC-CORE uses a strict term schema (T0–T7). Every definition, condition, and rule carries explicit scope, dependencies, necessity witness, minimality proof, and admissibility interface. This is deliberate — the schema is the minimum structure required for a specification to audit itself without an external authority. Expect a slower first pass than typical technical documentation. The density rewards re-reading.

If a term feels opaque, the dependency chain in its header points to every term it relies on. Walk the chain.

## What the specification asks of you

The specification is not a theory about what exists. It is a specification of what must hold for any structure to cohere. You are not asked to accept it. You are asked to test it — to find a structural counterexample, an inconsistency, or a missing minimality proof. The specification is designed to be falsifiable in that direction.

If you find one, see *Where to ask questions* below.

## Verifying what you're reading

Every canonical document carries a SHA-256 hash in its header, computed per SC-HDR §3.2 Rule 7. The release also includes a Merkle tree over all artifacts and Reflexive Closure Certificates (RCCs) coupling the integrity claims back to the kernel.

To verify one document by hand:

1. Open the `.md` source.
2. Blank the `SHA-256:` value (line ends at the colon, nothing after).
3. Compute SHA-256 over the UTF-8 bytes with LF line endings.
4. Compare against the hash in the header.

To verify the entire release at once:

```bash
cd standards/SC-AS/v1.0
python3 verify_bundle.py
```

The script recomputes every hash, the Merkle root, and the RCC target couplings. Zero dependencies — Python 3 standard library only.

## Implementing systems on top of SC-AS

The canonical documents are released under CC BY-ND 4.0. The license restricts derivative works of those documents — you cannot publish a modified specification under the same name. **Independent implementation is unrestricted**, including commercial implementation. You can build any system you want on top of SC-AS; you cannot publish a competing-but-modified SC-AS document.

If you publish an implementation, the citation format is in the repository `README.md`.

## Where to ask questions

- **General questions, interpretation, applying the spec to a specific design.**
  [GitHub Discussions](https://github.com/Coherence-Research/public/discussions). When in doubt, this is the right place.
- **Possible errata** (typo, broken link, header inconsistency, integrity check failure).
  Open a GitHub Issue with the `errata` template.
- **Possible ambiguity, inconsistency, or structural counterexample in the specification itself.**
  Open a GitHub Issue with the `spec-clarification` template. These are the most valuable reports.

See `CONTRIBUTING.md` for what contributions this repository accepts, and `SUPPORT.md` for the full routing.

---

*The specification does not ask for your agreement. It asks for your verification.*
