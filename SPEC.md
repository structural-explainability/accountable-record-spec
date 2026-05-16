# Accountable Record Specification (AR)

Status: Working Draft Specification

This document defines the normative requirements for conformance with the
Accountable Record (AR).

AR is a downstream specification that conforms to Structural Explainability (SE).
All SE neutrality constraints apply.

AR defines a shared contract for domain record systems that must remain
durable, inspectable, and contestable under persistent disagreement.

AR specifies record structure, source traceability, attestation, provenance,
prohibited category collapses, export bundle requirements, and verification
trace requirements.

AR is guided by Contextual Evidence & Explanations (CEE) patterns for
interpretation, explanation, attestation, and provenance, but AR does not
require CEE conformance. Domain record systems that conform to AR MAY
implement interpretation and explanation through CEE or through other
mechanisms consistent with the Interpretation Boundary (IB).

AR does not define domain vocabularies, domain-specific ontologies, or domain
correctness.

## How to Read This Spec

Keywords MUST, MUST NOT, SHOULD, and MAY
are to be interpreted as described in RFC 2119.

Use of terms such as "canonical" denotes structural role only and
does not imply epistemic, causal, or normative preference.

This specification does not prescribe editorial structure,
terminology preference, or documentation layout beyond identifier semantics.

## Representation vs Constraint Classes

Some requirements describe what accountable record structures MAY represent,
while others constrain how such representations MUST NOT be interpreted.

Overlap between these classes is intentional:
representation permissions do not imply explanatory, epistemic,
causal, normative, authoritative, or enforcement commitment.

## Identifier Semantics and Stability

Each requirement in this document is identified by a stable identifier
of the form `AR.*`.

Identifiers are the sole normative reference for conformance.
Textual wording MAY be clarified over time without changing meaning;
any change that alters the requirement MUST result in a new identifier.

Renaming, reordering, or relocating identifiers constitutes a semantic
change and is therefore intentionally diff-visible.

Repository paths, filenames, and section ordering are non-normative and
do not affect identifier meaning.

---

## AR.ATTESTATION

AR MUST provide a structural form for attestation records that identify the
actor or actors asserting responsibility for a record or set of records.

Attestation records:

- MUST reference the records being attested
- MUST identify the asserting actor
- MUST identify the scope of the assertion
- MUST be distinguishable from the records being attested
- MUST NOT certify correctness, authority, legitimacy, or enforcement
- MUST NOT modify the records being attested

Multiple attestations MAY reference the same record.

Attestation records MAY be implemented using CEE attestation patterns, but AR
does not require CEE conformance.

## AR.CLAIM.RECORD

AR MUST provide a structural form for claim records that represent assertions
made within a domain.

Claim records:

- MUST reference source records or source spans
- MUST be distinguishable from interpretation records
- MUST be distinguishable from explanation records
- MUST NOT assert truth, validity, correctness, or authority

Multiple claim records MAY reference the same source.

## AR.COLLAPSE.PROHIBITED

AR MUST prohibit structural collapse of the following distinct record categories
into a single record:

- identity
- source
- dependency
- governance status
- interpretation
- evidence
- explanation
- attestation
- provenance
- judgment

A record MUST identify which category or categories it represents.

A single record MUST NOT simultaneously assert membership in categories whose
separation is required by this specification or by domain profiles.

## AR.CONFORMANCE.CEE.OPTIONAL

AR record systems MAY claim conformance with Contextual Evidence &
Explanations (CEE) as an additional commitment.

Systems claiming CEE conformance MUST implement interpretation, explanation,
attestation, and provenance records as CEE artifacts.

CEE conformance is not required for AR conformance.

## AR.CONFORMANCE.GB.REQUIRED

Any system claiming conformance with this specification MUST preserve
Governance Boundary (GB) constraints for governance-related records and actions.

AR governance or status records MUST NOT assert authority, legitimacy,
obligation, correctness, or enforcement.

## AR.CONFORMANCE.IB.REQUIRED

Any system claiming conformance with this specification MUST preserve
Interpretation Boundary (IB) constraints.

AR interpretation records MUST NOT modify substrate records.

Interpretation MAY attach only through non-mutating mechanisms consistent with IB.

## AR.CONFORMANCE.SE.REQUIRED

Any system claiming conformance with this specification MUST also conform to
the Structural Explainability (SE) specification.

AR MUST NOT weaken, override, or reinterpret any SE neutrality constraints.

## AR.DEFINITION.CORE

Accountable Record defines a shared contract for domain record systems that
must remain durable, inspectable, and contestable under persistent disagreement.

AR specifies structural forms for:

- identity-bearing records
- source records and source references
- claim records
- dependency records
- governance or status records
- interpretation records
- explanation records
- attestation records
- provenance records
- export bundles
- verification traces

AR does not define:

- domain vocabularies
- domain correctness
- truth criteria
- causal models
- authority, legitimacy, obligation, or enforcement

## AR.DEPENDENCY.RECORD

AR MUST provide a structural form for dependency records that represent
declared relationships between records.

Dependency records:

- MUST identify dependent and depended-upon records
- MUST NOT imply validity of the dependent record
- MUST NOT imply correctness of either record
- MUST be distinguishable from reference, citation, or relationship records
  that do not assert dependency

## AR.EXPLANATION.RECORD

AR MUST provide a structural form for explanation records that derive
human-readable or machine-readable explanations from accountable records.

Explanation records:

- MUST reference the records they explain
- MUST be derived views, not authoritative substrate
- MUST NOT replace the records they explain
- MUST NOT be treated as proof, validation, or endorsement of the records

AR explanation records MAY be implemented using CEE explanation patterns,
but AR does not require CEE conformance.

## AR.EXPORT.BUNDLE

AR MUST define a structural export bundle format that an accountable record
system produces for external verification.

Export bundles:

- MUST include identifier-stable references to all included records
- MUST include manifests describing record types and counts
- MUST include source traces sufficient to reconstruct provenance
- MUST include attestation and provenance records associated with included records
- MUST be self-describing with respect to AR and domain profile versions
- MUST NOT embed interpretation as substrate

## AR.EXTENSION.ADMISSIBILITY

Any extension to AR in a future version MUST satisfy all of the following
criteria:

- conformance with Structural Explainability
- preservation of all AR constraints in effect at the prior version
- preservation of the separation of identity, source, dependency, governance,
  interpretation, evidence, explanation, attestation, provenance, and judgment
- neutrality with respect to epistemic, causal, normative, authoritative,
  legitimacy-bearing, obligation-bearing, and enforcement interpretation
- explicit versioning under a new major version of this specification

Failure to meet any criterion renders the extension inadmissible.

## AR.EXTENSION.VERSIONED_ONLY

Extension of AR is permitted only in a new major version of this specification.

No extension is permitted within AR v1.

## AR.GOVERNANCE.RECORD

AR MUST provide a structural form for governance or status records that
represent governance actions or status labels applied to accountable records.

Governance or status records:

- MUST conform to the Governance Boundary specification (GB)
- MUST identify the record or record state to which they apply
- MUST NOT assert correctness of the record
- MUST NOT assert authority, legitimacy, obligation, or enforcement

## AR.IDENTITY.RECORD

AR MUST provide a structural form for identity-bearing records that represent
durable entities within a domain.

Identity-bearing records:

- MUST use stable identifiers
- MUST be declared explicitly as identity-bearing
- MUST distinguish identity from graph continuity
- MUST NOT derive identity persistence from record continuity alone

## AR.INTERPRETATION.RECORD

AR MUST provide a structural form for interpretation records that attach
interpretive content to accountable records.

Interpretation records:

- MUST conform to the Interpretation Boundary specification (IB)
- MUST reference the records they interpret
- MUST identify the asserting actor or framework
- MUST NOT modify substrate records
- MUST NOT assert correctness, authority, or enforcement

AR interpretation records MAY be implemented using CEE patterns, but AR
does not require CEE conformance.

## AR.MAPPING.AE.SUPPORTED

AR MUST support explicit mapping of identity-bearing records to Accountable
Entities (AE) where required by a domain profile or SE verification profile.

Identity-bearing records:

- MUST be declared explicitly
- MUST use stable identifiers
- MAY declare AE kind and SE profile-kind mappings
- MUST NOT redefine AE kinds, SE profile kinds, identity regimes, or
  persistence behavior

AR conformance does not require full AE conformance unless required by an
applicable domain profile or SE verification profile.

## AR.MAPPING.EP.SUPPORTED

AR MUST support explicit mapping of dependency, continuity, graph, state,
delta, or history records to Evolution Protocol (EP) where required by a
domain profile or SE verification profile.

Dependency, continuity, and evolution records:

- MUST be declared explicitly
- MAY declare EP graph, state, delta, or history mappings
- MUST NOT imply identity persistence, validity, correctness, causation,
  or explanation by default
- MUST NOT redefine EP graph evolution rules, persistence references, or
  transformation references

AR conformance does not require full EP conformance unless required by an
applicable domain profile or SE verification profile.

## AR.MULTIPLICITY

AR MUST support multiple interpretations, explanations, claims, attestations,
and provenance records over the same accountable records.

AR MUST NOT require reconciliation, prioritization, or resolution of
conflicting interpretations or explanations.

Disagreement is representable, not eliminatible.

## AR.PROFILE.DOMAIN

AR MUST allow domain profiles to specialize AR for specific record domains.

Domain profiles:

- MUST conform to AR
- MUST declare profile-specific record types, constraints, and prohibited collapses
- MUST identify the AR version they extend
- MUST NOT weaken AR constraints

A system conforming to a domain profile MUST also conform to AR.

## AR.PROVENANCE

AR MUST provide a structural form for provenance records that describe how
accountable records, attestations, interpretations, or explanations were
produced.

Provenance records:

- MUST reference the records whose provenance is being described
- MUST identify sources, methods, or tools involved in production where known
- MUST be distinguishable from the records they describe
- MUST NOT modify the records they describe
- MUST NOT assert epistemic validity, correctness, legitimacy, authority,
  obligation, causality, or enforcement

Provenance records MAY be implemented using CEE provenance patterns, but AR
does not require CEE conformance.

## AR.REVIEW.STATUS

AR MUST provide a structural form for review status on accountable records,
derived records, interpretations, explanations, attestations, provenance
records, and verification results.

Review status records or fields:

- MUST identify whether a record is draft, machine-suggested, curated,
  reviewed, disputed, deprecated, or superseded where applicable
- MUST be distinguishable from governance or status records that apply to
  domain meaning or lifecycle
- MUST NOT assert truth, correctness, authority, legitimacy, obligation,
  causality, or enforcement
- MUST be traceable to the actor, process, or mechanism that assigned the status
  where available

## AR.SCOPE.EXCLUSIONS

This specification does not define:

- domain vocabularies
- domain-specific ontologies
- legal, civic, benefits, planning, or scientific determinations
- analytics, inference, optimization, recommendation, or decision logic
- causal explanations
- epistemic evaluation
- authority, legitimacy, obligation, or enforcement
- replacements for existing domain standards or systems

These concerns are explicitly out of scope.

## AR.SOURCE.RECORD

AR MUST provide a structural form for source records and source references
that represent traceable origins of claims, relationships, or other records.

Source records and source references:

- MUST use stable identifiers
- MUST be distinguishable from records that interpret or derive from them
- MUST NOT be modified to reflect interpretation of their contents
- MUST be referenceable across record types

## AR.VERIFICATION.TRACE

AR MUST define a structural form for verification traces that link verification
results to the records and constraints they reference.

Verification traces:

- MUST identify the records, constraints, and check categories involved
- MUST distinguish passing checks from failing checks
- MUST be reproducible from the export bundle
- MUST NOT assert correctness of the records beyond the checks performed

## AR.VERSIONING

AR MUST define versioning rules for the specification and for accountable
record systems claiming conformance.

Versioning:

- MUST be explicit
- MUST be stable
- MUST NOT allow silent or implicit change
- MUST identify the AR version a conforming system targets
