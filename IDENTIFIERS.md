# Accountable Record Identifiers (AR)

This document defines the stable requirement identifiers used by the
Accountable Record (AR) specification.

Identifiers are the sole normative reference mechanism.
Section ordering, formatting, and presentation are non-normative.

## Overview

Defines the shared contract identifiers for accountable record systems that
must remain durable, inspectable, and contestable under persistent disagreement.

AR defines record structure, source traceability, attestation, provenance,
prohibited category collapses, export bundle requirements, verification traces,
and domain profile support.

## Identifier Semantics and Ordering

Identifiers are the sole normative reference mechanism.
Section ordering, formatting, and presentation are non-normative.

Identifiers are listed in strict alphabetical order to remove editorial
discretion and ensure deterministic placement.

## Identifier Naming Rules

All identifiers follow this pattern:

All identifiers begin with `AR.` and use uppercase dot-separated semantic terms.

Identifiers are:

- semantic, not positional
- stable across versions
- reusable across prose, code, reports, and verification traces
- language-agnostic
- suitable for direct mapping to verification rule names

Identifiers MUST NOT be renamed or repurposed.
New identifiers MAY be added only in a new major version of this document.

## Identifier Notes

Each identifier MUST be followed by exactly one note.

- The note MUST be expressed as a single bullet.
- The bullet text MAY wrap across lines.
- No additional bullets, sublists, or structural markers are permitted.
- Notes are explanatory only and do not introduce additional requirements.

## Canonical Identifier List (Alphabetical, with Notes)

AR.ATTESTATION

- Defines structural attestation records for scoped assertions about accountable records.

AR.CLAIM.RECORD

- Defines structural claim records for assertions made within a domain.

AR.COLLAPSE.PROHIBITED

- Prohibits collapse of distinct accountable record categories.

AR.CONFORMANCE.CEE.OPTIONAL

- Allows optional CEE conformance as an additional commitment.

AR.CONFORMANCE.GB.REQUIRED

- Requires preservation of Governance Boundary constraints for governance-related records and actions.

AR.CONFORMANCE.IB.REQUIRED

- Requires preservation of Interpretation Boundary constraints for interpretation records.

AR.CONFORMANCE.SE.REQUIRED

- Requires conformance with Structural Explainability.

AR.DEFINITION.CORE

- Defines Accountable Record as a shared contract for durable domain record systems.

AR.DEPENDENCY.RECORD

- Defines dependency records and prohibits treating dependency as validity or correctness.

AR.EXPLANATION.RECORD

- Defines explanation records as derived views over accountable records.

AR.EXPORT.BUNDLE

- Defines the export bundle format required for external verification.

AR.EXTENSION.ADMISSIBILITY

- Defines criteria for admissible future AR extensions.

AR.EXTENSION.VERSIONED_ONLY

- Requires AR extensions to occur only in a new major version.

AR.GOVERNANCE.RECORD

- Defines governance or status records and their non-authoritative constraints.

AR.IDENTITY.RECORD

- Defines identity-bearing records and stable identity requirements.

AR.INTERPRETATION.RECORD

- Defines non-mutating interpretation records attached to accountable records.

AR.MAPPING.AE.SUPPORTED

- Supports explicit mapping of identity-bearing records to AE where required by profiles or verification.

AR.MAPPING.EP.SUPPORTED

- Supports explicit mapping of dependency, continuity, graph, state, delta, or
  history records to EP where required by profiles or verification.

AR.MULTIPLICITY

- Requires support for multiple claims, interpretations, explanations,
  attestations, provenance records, dependencies, and status records.

AR.PROFILE.DOMAIN

- Allows domain profiles to specialize AR without weakening AR constraints.

AR.PROVENANCE

- Defines provenance records for how accountable records or derived records were produced.

AR.REVIEW.STATUS

- Defines review status records or fields without treating review status as correctness or authority.

AR.SCOPE.EXCLUSIONS

- Defines what AR explicitly does not specify.

AR.SOURCE.RECORD

- Defines source records and source references as traceable origins.

AR.VERIFICATION.TRACE

- Defines verification traces linking verification results to records and constraints.

AR.VERSIONING

- Defines AR versioning requirements.

## Cross-Artifact Consistency Rule

Each identifier in this list MUST appear:

- exactly once in SPEC.md
- exactly once in CONFORMANCE.md
- exactly once in generated requirements artifacts
- exactly once in generated conformance-check artifacts where applicable

Alphabetical order SHOULD be preserved across all artifacts.
