# SC-AS v1.0 Release

**Released:** 2026-03-26  
**Status:** Current  
**Publisher:** Coherence Research

---

## Included Documents

| Document | Role |
|---|---|
| SC-CORE-000001 | Core structural specification |
| SC-AXIOM-000001 | Axiomatic foundations |
| SC-HDR-000001 | Canonical document header schema |
| SC-SCOPE-000001 | Scope and admissibility boundary |

## Integrity Verification

1. Check file hashes against `RELEASE_MANIFEST.json`
2. Verify Merkle root against `MERKLE_TREE.json` and `MERKLE_ROOT.txt`
3. Verify PGP signature: `gpg --verify SIGNATURE.asc MERKLE_ROOT.txt`
4. Confirm DOIs resolve to archived Zenodo snapshots

## DOI Archive

DOI-registered snapshots are available via Zenodo.  
See `RELEASE_MANIFEST.json` for individual document DOIs.

---

*Manifests, Merkle tree, and verification artifacts will be committed here upon publication.*
