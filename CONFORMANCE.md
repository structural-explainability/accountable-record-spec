# Accountable Record Conformance Checklist

This document defines the criteria for determining whether an artifact conforms
to the Accountable Record specification.

Identifiers referenced in this document are the sole normative reference.
Section ordering, formatting, and presentation are non-normative.

An artifact may be a specification, record system, export bundle, verifier,
repository, or other deliverable claiming conformance.

## Conformance Overview

An artifact CONFORMS if and only if:

- all mandatory requirements are satisfied
- no prohibited assertions are present
- conformance with Structural Explainability (SE) is preserved
- Governance Boundary constraints are preserved for governance-related records
- Interpretation Boundary constraints are preserved for interpretation records
- accountability properties remain durable, inspectable, and contestable

Failure of any single check constitutes non-conformance.

## AR.ATTESTATION

- [ ] Attestation records reference the records being attested.
- [ ] Attestation records identify the asserting actor.
- [ ] Attestation records identify the scope of the assertion.
- [ ] Attestation records remain distinguishable from the records being attested.
- [ ] Attestation records do not certify correctness, authority, legitimacy, or enforcement.
- [ ] Attestation records do not modify the records being attested.
- Fail if: attestation is treated as correctness, authority, legitimacy,
  enforcement, or mutation of the attested record.

## AR.CLAIM.RECORD

- [ ] Claim records reference source records or source spans.
- [ ] Claim records remain distinguishable from interpretation records.
- [ ] Claim records remain distinguishable from explanation records.
- [ ] Claim records do not assert truth, validity, correctness, or authority.
- Fail if: a claim is treated as truth, validity, correctness, authority, interpretation, or explanation.

## AR.COLLAPSE.PROHIBITED

- [ ] Records identify their primary category.
- [ ] Records do not collapse categories whose separation is required by AR or by domain profiles.
- [ ] Records that reference other categories preserve category-specific meanings.
- [ ] Domain profiles explicitly declare any permitted composition and prohibited inferences.
- Fail if: identity, source, dependency, governance status, interpretation,
  evidence, explanation, attestation, provenance, or judgment
  are collapsed into a record that violates required separation.

## AR.CONFORMANCE.CEE.OPTIONAL

- [ ] Systems claiming CEE conformance implement interpretation,
  explanation, attestation, and provenance records as CEE artifacts.
- [ ] Systems not claiming CEE conformance do not represent CEE conformance as required for AR conformance.
- Fail if: CEE conformance is falsely required for AR conformance or
  falsely claimed without implementing CEE commitments.

## AR.CONFORMANCE.GB.REQUIRED

- [ ] Governance-related records preserve Governance Boundary constraints.
- [ ] Governance or status records do not assert authority.
- [ ] Governance or status records do not assert legitimacy.
- [ ] Governance or status records do not assert obligation.
- [ ] Governance or status records do not assert correctness.
- [ ] Governance or status records do not assert enforcement.
- Fail if: governance or status is treated as authority, legitimacy,
  obligation, correctness, or enforcement.

## AR.CONFORMANCE.IB.REQUIRED

- [ ] Interpretation records preserve Interpretation Boundary constraints.
- [ ] Interpretation records do not modify substrate records.
- [ ] Interpretation attaches only through non-mutating mechanisms.
- Fail if: interpretation mutates substrate records or enters the
  substrate as semantic content.

## AR.CONFORMANCE.SE.REQUIRED

- [ ] The artifact declares conformance with Structural Explainability.
- [ ] The artifact does not weaken SE neutrality constraints.
- [ ] The artifact does not override SE neutrality constraints.
- [ ] The artifact does not reinterpret SE neutrality constraints.
- Fail if: AR conformance is asserted while weakening, overriding, or reinterpreting SE neutrality.

## AR.DEFINITION.CORE

- [ ] The artifact treats AR as a shared contract for domain record systems.
- [ ] The artifact limits AR to structural record, traceability, export, and verification requirements.
- [ ] The artifact does not define domain correctness, truth criteria,
  causal models, authority, legitimacy, obligation, or enforcement.
- Fail if: AR is treated as a domain ontology, truth model, decision engine,
  authority system, or enforcement framework.

## AR.DEPENDENCY.RECORD

- [ ] Dependency records identify dependent records.
- [ ] Dependency records identify depended-upon records.
- [ ] Dependency records do not imply validity of the dependent record.
- [ ] Dependency records do not imply correctness of either record.
- [ ] Dependency records remain distinguishable from reference, citation,
  or relationship records that do not assert dependency.
- Fail if: dependency is treated as validity, correctness, proof,
  authority, or undifferentiated reference.

## AR.EXPLANATION.RECORD

- [ ] Explanation records reference the records they explain.
- [ ] Explanation records are derived views.
- [ ] Explanation records are not authoritative substrate.
- [ ] Explanation records do not replace the records they explain.
- [ ] Explanation records are not treated as proof, validation, or endorsement.
- Fail if: explanation is treated as proof, authority, validation, endorsement,
  or replacement of underlying records.

## AR.EXPORT.BUNDLE

- [ ] Export bundles include identifier-stable references to all included records.
- [ ] Export bundles include manifests describing record types and counts.
- [ ] Export bundles include source traces sufficient to inspect
  provenance claims represented within the bundle.
- [ ] Export bundles include attestation and provenance records
  associated with included records when required.
- [ ] Export bundles identify AR and domain profile versions.
- [ ] Export bundles do not embed interpretation as substrate.
- Fail if: the export bundle is not self-describing, cannot support
  verification, or embeds interpretation as substrate.

## AR.EXTENSION.ADMISSIBILITY

- [ ] Extensions preserve conformance with Structural Explainability.
- [ ] Extensions preserve all AR constraints in effect at the prior version.
- [ ] Extensions preserve separation of identity, source, dependency,
  governance, interpretation, evidence, explanation, attestation, provenance, and judgment.
- [ ] Extensions remain neutral with respect to epistemic, causal, normative, authoritative,
  legitimacy-bearing, obligation-bearing, and enforcement interpretation.
- [ ] Extensions are explicitly versioned under a new major version.
- Fail if: an extension weakens AR, collapses required categories, or
  introduces unstated interpretation or enforcement commitments.

## AR.EXTENSION.VERSIONED_ONLY

- [ ] AR extension occurs only in a new major version.
- [ ] AR v1 does not permit unversioned extension.
- Fail if: AR is extended silently, informally, or within the same major version.

## AR.GOVERNANCE.RECORD

- [ ] Governance or status records conform to AR.
- [ ] Governance or status records identify the record or record state to which they apply.
- [ ] Governance or status records do not assert correctness.
- [ ] Governance or status records do not assert authority, legitimacy, obligation, or enforcement.
- Fail if: governance or status labels become correctness, authority, legitimacy,
  obligation, or enforcement claims.

## AR.IDENTITY.RECORD

- [ ] Identity-bearing records use stable identifiers.
- [ ] Identity-bearing records are declared explicitly as identity-bearing.
- [ ] Identity-bearing records distinguish identity from graph continuity.
- [ ] Identity-bearing records do not derive identity persistence from record continuity alone.
- Fail if: identity is implicit, unstable, derived from graph continuity, or
  derived from record continuity alone.

## AR.INTERPRETATION.RECORD

- [ ] Interpretation records conform to IB.
- [ ] Interpretation records reference the records they interpret.
- [ ] Interpretation records identify the asserting actor or framework.
- [ ] Interpretation records do not modify substrate records.
- [ ] Interpretation records do not assert correctness, authority, or enforcement.
- Fail if: interpretation mutates substrate records or asserts correctness, authority, or enforcement.

## AR.MAPPING.AE.SUPPORTED

- [ ] AR supports explicit mapping of identity-bearing records to AE where required
  by a domain profile or SE verification profile.
- [ ] Identity-bearing records can declare AE kind and SE profile-kind mappings where applicable.
- [ ] AR does not redefine AE kinds, SE profile kinds, identity regimes, or persistence behavior.
- [ ] AR conformance does not require full AE conformance unless required by an applicable profile.
- Fail if: AR prevents required AE mapping, redefines AE/profile-kind semantics, or
  silently treats AR conformance as full AE conformance.

## AR.MAPPING.EP.SUPPORTED

- [ ] AR supports explicit mapping of dependency, continuity, graph, state, delta, or
  history records to EP where required by a domain profile or SE verification profile.
- [ ] Dependency, continuity, and evolution records can declare EP mappings where applicable.
- [ ] AR does not redefine EP graph evolution rules, persistence references, or transformation references.
- [ ] AR conformance does not require full EP conformance unless required by an applicable profile.
- Fail if: AR prevents required EP mapping, redefines EP semantics, or
  treats graph continuity as identity persistence.

## AR.MULTIPLICITY

- [ ] AR supports multiple interpretations over the same accountable records.
- [ ] AR supports multiple explanations over the same accountable records.
- [ ] AR supports multiple claims over the same accountable records.
- [ ] AR supports multiple dependencies over the same accountable records.
- [ ] AR supports multiple attestations over the same accountable records.
- [ ] AR supports multiple provenance records over the same accountable records.
- [ ] AR supports multiple governance or status records over the same accountable records.
- [ ] AR does not require reconciliation, prioritization, or resolution of
  conflicting interpretations or explanations.
- Fail if: disagreement is forced to resolve, conflicting records are collapsed, or
  multiplicity is prohibited.

## AR.PROFILE.DOMAIN

- [ ] Domain profiles conform to AR.
- [ ] Domain profiles declare profile-specific record types.
- [ ] Domain profiles declare profile-specific constraints.
- [ ] Domain profiles declare profile-specific prohibited collapses.
- [ ] Domain profiles identify the AR version they extend.
- [ ] Domain profiles do not weaken AR constraints.
- Fail if: a domain profile weakens AR, hides profile-specific constraints, or
  fails to identify its AR version.

## AR.PROVENANCE

- [ ] Provenance records reference the records whose provenance is described.
- [ ] Provenance records identify sources, methods, or tools involved in production where known.
- [ ] Provenance records remain distinguishable from the records they describe.
- [ ] Provenance records do not modify the records they describe.
- [ ] Provenance records do not assert epistemic validity, correctness, legitimacy,
  authority, obligation, causality, or enforcement.
- Fail if: provenance is treated as correctness, authority, legitimacy, causality,
  enforcement, or mutation of the described record.

## AR.REVIEW.STATUS

- [ ] Review status records or fields identify review status where applicable.
- [ ] Review status remains distinguishable from governance or status records
  that apply to domain meaning or lifecycle.
- [ ] Review status does not assert truth, correctness, authority, legitimacy,
  obligation, causality, or enforcement.
- [ ] Review status is traceable to the actor, process, or mechanism that
  assigned the status where available.
- Fail if: review status is treated as truth, correctness, authority,
  legitimacy, causality, enforcement, or domain lifecycle status without distinction.

## AR.SCOPE.EXCLUSIONS

Verify that the artifact does not define:

- [ ] domain vocabularies
- [ ] domain-specific ontologies
- [ ] legal, civic, benefits, planning, or scientific determinations
- [ ] analytics, inference, optimization, recommendation, or decision logic
- [ ] causal explanations
- [ ] epistemic evaluation
- [ ] authority, legitimacy, obligation, or enforcement
- [ ] replacements for existing domain standards or systems
- [ ] automatic inference that dependency implies validity
- [ ] automatic inference that relationship implies causation, endorsement, control, or agreement

Presence of any excluded concern as an AR-defined construct constitutes non-conformance.

## AR.SOURCE.RECORD

- [ ] Source records and source references use stable identifiers.
- [ ] Source records remain distinguishable from records that interpret or derive from them.
- [ ] Source records are not modified to reflect interpretation of their contents.
- [ ] Source records are referenceable across record types.
- [ ] Source records do not assert that source content is true, complete, current, or
  authoritative unless represented separately.
- Fail if: source records are modified by interpretation or treated as truth,
  completeness, currency, or authority by default.

## AR.VERIFICATION.TRACE

- [ ] Verification traces identify records involved.
- [ ] Verification traces identify constraints involved.
- [ ] Verification traces identify check categories involved.
- [ ] Verification traces distinguish passing checks from failing checks.
- [ ] Verification traces are reproducible from the export bundle.
- [ ] Verification traces do not assert correctness beyond the checks performed.
- Fail if: verification traces are not reproducible, omit records or
  constraints, or assert correctness beyond performed checks.

## AR.VERSIONING

- [ ] AR versioning is explicit.
- [ ] AR versioning is stable.
- [ ] AR versioning does not allow silent or implicit change.
- [ ] Conforming systems identify the AR version they target.
- Fail if: AR versioning is missing, implicit, unstable, or silently changed.

## Final Determination

An artifact CONFORMS if:

- all checks above pass
- no prohibited assertions are present
- conformance with Structural Explainability is preserved
- governance and interpretation boundaries are preserved where applicable
- accountable records remain durable, inspectable, contestable, and traceable

Otherwise, the artifact is NON-CONFORMANT.

## Conformance Declaration

Artifacts claiming conformance SHOULD include a declaration of the form:

```text
Conforms to: AR Specification vX.Y
Conforms to: SE Specification vX.Y
```
