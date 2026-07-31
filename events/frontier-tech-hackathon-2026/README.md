# Frontier Technologies Hackathon 2026 — Coherence Research Multiplier

**Event:** [Frontier Technologies: AI & Blockchain](https://nvlope.app/events/frontier-tech-hackathon-2026)
**Co-sponsors:** MOMENT (Missouri Mission for Exponential Technology) · Stand With Crypto Missouri
**Build window:** May 20 – June 3, 2026 · **Awards:** June 18, 2026
**Coherence Research role:** Strategic Multiplier — optional weighted scoring advantage

> This directory contains the rubric and guidance for the Coherence Research
> Strategic Multiplier. It is provided to make the multiplier objectively
> scorable and to help participants design submissions that claim it credibly.

The hackathon awards weighted scoring advantages for submissions that implement
"design principles from coherenceresearch.com to achieve low semantic drift,
reduced system variance, and verifiably low-hallucination AI behavior."

This document defines what that means in practice, gives you a scoring rubric,
and shows what a credible application looks like.

---

## TL;DR for builders

You don't need to read the four canonical SC-AS specifications to claim the
multiplier. You need to design your primitive so that:

1. **Its identity stays stable across transformations.** What the system *is*
   doesn't drift as it learns, retrains, or accepts new inputs.
2. **Its interactions are bounded.** Composition with other systems doesn't
   create unbounded paths between the outside world and the system's internals.
3. **Its changes are redistributive, not destructive.** Updates preserve prior
   structural commitments rather than silently replacing them.
4. **Its claims are verifiable.** State, provenance, and transformations are
   cryptographically attestable — not asserted on faith.
5. **Its design imports only what's necessary.** No semantic smuggling, no
   ungrounded dependencies.

Hit three of five with structural justification and you have a credible claim.
Hit all five and you have a strong one.

---

## The Rubric (5 axes, 0–2 each, max 10)

Judges score each axis independently. The rubric is designed so a non-specialist
judge can apply it without having read the SC-AS specification.

### 1. Identity Persistence

> *Does the primitive maintain stable structural identity across its operations?*

- **0** — The system can silently change what it represents or optimizes for
  without an explicit gate (e.g., self-modifying objective functions; classifiers
  whose categories mutate without versioning).
- **1** — Identity is stable in normal operation but ambiguous under updates,
  retraining, or composition.
- **2** — Identity is explicitly preserved across all admissible transformations,
  and changes that would alter identity are gated as regime transitions.

### 2. Bounded Interaction

> *Are the system's interactions structurally bounded under composition?*

- **0** — External input can reach internal state through unbounded paths
  (e.g., user feedback directly modifies model weights or contract logic).
- **1** — Interactions are bounded in the common case but bounds are not explicit
  in the design.
- **2** — Interaction boundaries are declared, enforced, and auditable.

### 3. Admissible Change

> *When the system changes, is the change redistributive (preserves prior
> structural commitments) rather than destructive (silently overwrites)?*

- **0** — Updates can delete or replace prior commitments without trace.
- **1** — Updates are tracked but prior commitments are not formally preserved.
- **2** — Change explicitly redistributes structural content; nothing is lost
  in derivation.

### 4. Verifiable Provenance

> *Are state and transformations cryptographically attestable?*

- **0** — Claims about state or history rely on the system's own assertion.
- **1** — Some provenance is attestable, some is asserted.
- **2** — End-to-end cryptographic provenance: state, transformations, and
  derivation chain are independently verifiable.

*This axis is where the blockchain half of your submission earns its weight
inside the Coherence multiplier. SHA-256 hashes, Merkle commitments, on-chain
attestation, signed transitions — all count.*

### 5. Structural Austerity

> *Does the design import only what's structurally necessary?*

- **0** — Significant unjustified complexity, ungrounded dependencies, or
  semantic smuggling.
- **1** — Design is mostly austere but includes some unjustified scope.
- **2** — Every component carries explicit justification; no implicit imports.

**Total: /10.** Treat as a multiplier weight against the team's base score per
the host's scoring matrix.

---

## How to claim the multiplier in your submission

Add a **Coherence Multiplier Statement** to your 6-slide deck (fold into the
"Technical Architecture" slide) or to your code repository's README. Maximum
200 words. Address each of the five axes in one to two sentences:

```
Coherence Multiplier Statement
==============================
1. Identity Persistence: [what is invariant in your primitive, what gates change]
2. Bounded Interaction: [what bounds the inputs that can reach internal state]
3. Admissible Change: [how updates preserve prior commitments]
4. Verifiable Provenance: [what is cryptographically attestable]
5. Structural Austerity: [what scope you chose not to include and why]
```

Judges read this statement against the rubric. You are not required to use
SC-AS terminology — clear plain-language statements grounded in your design
score the same as formal citations.

---

## Worked example: IP provenance primitive

**Scenario.** A creator uploads creative work. An AI classifier produces a
structural fingerprint (style, derivative-of relations, fingerprint hash). The
system registers an IP token on-chain carrying the fingerprint metadata. A
royalty smart contract distributes payments by use.

**Naive design (scores ~3/10):**

- Classifier is a hosted model that can be retrained at will.
- On-chain token references off-chain metadata that can change.
- Royalty contract is hard-coded; updates require redeploying.

**Coherence-strengthened design (scores ~9/10):**

1. *Identity.* Token represents a specific (work, fingerprint, classifier-version)
   triple. Retraining the classifier creates a new classifier-version; existing
   tokens are not silently re-classified.
2. *Bounded interaction.* Creator inputs can mint tokens but cannot modify
   existing ones. Classifier outputs are inputs to minting, not to mutation.
3. *Admissible change.* Re-classification creates a successor token that
   *cites* the predecessor. Nothing is overwritten; the chain is redistributive.
4. *Verifiable provenance.* Original work hash + classifier-version hash +
   classification signature + on-chain attestation. Every step is independently
   verifiable.
5. *Austerity.* No additional scope (auth, marketplace, social features) bundled
   into the core primitive.

The Coherence-strengthened version is not more complex — it is more *structured*.

---

## Resources

- **The Standard:** <https://coherenceresearch.com/standard> — full SC-AS specification
- **Overview** (start here if you want structural intuition first):
  <https://coherenceresearch.com/overview>
- **Worked admissibility example:** <https://coherenceresearch.com/standard#worked-example>
- **Discussions** (questions, help, project chatter):
  <https://github.com/Coherence-Research/public/discussions>
- **Hackathon brief:** <https://nvlope.app/events/frontier-tech-hackathon-2026>

## Suggested blockchain substrate

The hackathon requires meaningful AI + blockchain integration. Coherence
Research's structural provenance model maps naturally onto chains that support
verifiable on-chain attestation and agent-level identity. **Apex Fusion / Vector**
provides this natively, including an on-chain agent registry, governance
primitives, and metadata-bearing transactions — but any substrate that supports
cryptographic attestation of state and transformations satisfies axis 4 of the
rubric. Substrate choice does not affect scoring.

## Where to get help

- **Quick questions:** open a thread in the Hackathon Help discussion category
  on GitHub Discussions.
- **Specification ambiguity or interpretation:** open an issue with the
  `spec-clarification` template.
- **Implementation help:** Discussions → Hackathon Help. Tag your post with
  the MOMENT track you're building under (Industrial Provenance, IP,
  Healthcare Assets, Transportation).

## What does not count for the multiplier

- Citing SC-AS without applying any of the five axes to your design.
- Adding the word "coherence" to your README without structural follow-through.
- Implementations that fail the host's AI-and-blockchain baseline — the
  multiplier cannot rescue a submission that doesn't satisfy the host's
  primary criterion.

---

*Coherence Research is a nonprofit public-benefit organization. The standards
are free, open, and permanently archived. We are not selling anything to
hackathon participants. We benefit when builders adopt structural rigor — that
is the entire reason this multiplier exists.*
