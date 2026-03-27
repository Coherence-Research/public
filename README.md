# Structural Coherence — Anchor Specification (SC-AS)

**An open, formally structured specification defining structural coherence as a universal invariant.**

Published by [Coherence Research](https://coherenceresearch.com) — a nonprofit public benefit organization.

---

## What This Is

The Structural Coherence — Anchor Specification (SC-AS) defines the conditions under which structure is admissible, representable, and enforceable — independent of domain, substrate, or scale.

It is not a theory about what exists. It is a specification of what must hold for any structure to cohere. Every term traces to explicit primitives. Every claim carries its own dependency chain, necessity proof, and minimality proof. The specification defines its own conformance criteria internally — anyone can audit it for structural consistency without relying on an external authority.

SC-AS is designed to be readable by both humans and AI systems.

## Canonical Documents

The specification consists of four canonical documents:

| Document | Description |
|----------|-------------|
| **SC-CORE-000001** | The Core Specification — primitive definitions, foundational conditions, valid emergence conditions, and admissibility rules. The complete structural kernel. |
| **SC-AXIOM-000001** | The Coherence Axioms — canonical derivations from the Core establishing the axiomatic structure of coherence. |
| **SC-HDR-000001** | Document Header Specification — the normalized metadata header required for all canonical artifacts. |
| **SC-SCOPE-000001** | Semantic Scope and Non-Prescriptive Clause — binding constraints on interpretation, projection, and the canonical boundary. |

Each document is available as both markdown source (`.md`) and rendered PDF in `standards/SC-AS/v1.0/pdf/`.

## Reading the Specification

Start with **SC-SCOPE** to understand what the specification does and does not claim. Then read **SC-CORE** for the formal kernel. **SC-AXIOM** derives the axiomatic consequences. **SC-HDR** governs document structure and integrity.

The Core specification uses a rigorous term schema (T0–T7) where every definition, condition, and rule carries explicit scope, dependencies, necessity witness, minimality proof, and admissibility interface. This is intentional — it is the minimum structure necessary to guarantee that every piece of the foundation has been checked.

## Structural Integrity

Every canonical document carries a SHA-256 hash in its header, computed per SC-HDR §3.2 Rule 7. You can verify any document's integrity:

1. Open the `.md` source file
2. Blank the `SHA-256:` value (line ends at the colon)
3. Compute SHA-256 over the UTF-8 bytes with LF line endings
4. Compare against the hash in the header

Or use the included verification script:

```bash
cd standards/SC-AS/v1.0
python3 verify_bundle.py
```

This independently verifies every SHA-256 hash, recomputes the Merkle root, validates RCC target coupling, and checks bundle composition. Zero dependencies — just Python 3.

## Repository Structure

```
standards/SC-AS/v1.0/
  ├── SC-CORE-000001.md         # Core Specification
  ├── SC-AXIOM-000001.md        # Coherence Axioms
  ├── SC-HDR-000001.md          # Document Header Specification
  ├── SC-SCOPE-000001.md        # Semantic Scope
  ├── pdf/                      # Rendered PDFs
  ├── certificates/             # Reflexive Closure Certificates
  ├── stewardship/              # Governance, license, naming, trademark, authorship
  ├── RELEASE_MANIFEST.json     # All artifacts with SHA-256 hashes
  ├── MERKLE_TREE.json          # Integrity tree
  ├── MERKLE_ROOT.txt           # Root hash
  ├── RELEASE_NOTES.md          # Release notes and conformance findings
  ├── DOCUMENT-INDEX.md         # Full document index
  ├── verify_bundle.py          # Independent integrity verification
  ├── A-NOTE-TO-THE-READER.md   # Reader orientation
  └── LICENSE                   # CC BY-ND 4.0
```

## License

The SC-AS specification documents are released under the **Creative Commons Attribution-NoDerivatives 4.0 International License** (CC BY-ND 4.0).

You are free to share the specification in its original form with attribution. You may not distribute modified versions of the canonical documents. Independent implementation — including commercial implementation — is unrestricted.

See [LICENSE](LICENSE) for the full license text.

## About Coherence Research

Coherence Research is a nonprofit public benefit organization that publishes open structural coherence standards. The institutional structure separates the authority to define from the incentive to monetize — the steward of the standard does not sell the implementation.

Website: [coherenceresearch.com](https://coherenceresearch.com)

## Citation

If you reference SC-AS in academic or technical work:

> Carroll, J. (2026). *Structural Coherence — Anchor Specification (SC-AS)*, v1.0. Coherence Research. https://coherenceresearch.com/standard

## Contact

Questions, feedback, or interest in collaboration:

- Website: [coherenceresearch.com](https://coherenceresearch.com)
- GitHub: [Coherence-Research](https://github.com/Coherence-Research)

---

*This work does not ask you to trust the framework. It asks you to test it.*
