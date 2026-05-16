# accountable-record-spec

[![Repo](https://img.shields.io/badge/repo-GitHub-black?logo=github)](https://github.com/structural-explainability/accountable-record-spec)
[![Tooling](https://img.shields.io/badge/python-3.15%2B-blue?logo=python)](./pyproject.toml)
[![License](https://img.shields.io/badge/license-MIT-yellow.svg)](./LICENSE)

[![CI](https://github.com/structural-explainability/accountable-record-spec/actions/workflows/ci-python.yml/badge.svg?branch=main)](https://github.com/structural-explainability/accountable-record-spec/actions/workflows/ci-python.yml)
[![Links](https://github.com/structural-explainability/accountable-record-spec/actions/workflows/links.yml/badge.svg?branch=main)](https://github.com/structural-explainability/accountable-record-spec/actions/workflows/links.yml)
[![Dependabot](https://img.shields.io/badge/Dependabot-enabled-brightgreen.svg)](https://github.com/structural-explainability/accountable-record-spec/security)

> Shared contract for Accountable Record systems.

## Overview

The Accountable Record (AR) contract defines shared requirements for
information systems that must remain durable, inspectable, and contestable
under persistent disagreement.

An Accountable Record system may represent decisions, relationships, claims,
dependencies, sources, interpretations, or processes.
The specific domain vocabulary may vary.
The accountability properties are shared.

AR answers questions like:

- What must an accountable record system preserve?
- What must remain separately identifiable?
- What must be traceable to source records?
- What kinds of interpretation must remain external?
- What category collapses must be prevented?
- What must a domain system export for verification?

AR defines a contract for record structure and verification readiness,
not a domain ontology, causal model, epistemic evaluation, normative
judgment, authority claim, or enforcement mechanism.

## Purpose

The purpose of AR is to specify what a domain record system must provide
to support inspection, contestation, audit, and continued use under
persistent disagreement.

AR defines constraints on:

- identity-bearing records
- source records and source references
- claims and dependencies
- governance or status records
- interpretations and explanations
- prohibited category collapses
- export bundles
- verification traces

AR does not define the domain meaning of records.
Domain systems keep their own vocabularies, standards, ontologies,
schemas, and data sources.

AR helps protect information systems from a specific failure mode:

- Collapsing identity, source, dependency, governance, interpretation,
  evidence, explanation, and judgment into a single record.

## Versioning and Stability

Current versions are pre-v1.
The contract is being co-developed with its
implementations and verifiers;
dependencies track main during this phase.
Versioned releases will follow once the contract stabilizes.

v1 will commit to:

- the shared contract shape across domains
- export bundle structure
- verification trace requirements
- prohibited category collapse definitions

v1 does not claim closure over domain meaning, vocabulary,
or downstream interpretation.

## Extension Policy

Extension is explicitly permitted only under a new version of the contract
or through a declared domain profile.

Any extension MUST:

- preserve conformance with Structural Explainability
- preserve the separation of identity, structure, governance,
  interpretation, evidence, and explanation
- introduce explicit record definitions and constraints
- declare prohibited inferences
- remain neutral with respect to epistemic, causal, normative,
  authoritative, legitimacy-bearing, obligation-bearing, and enforcement claims
- be explicit, traceable, and verifiable

## Scope

This contract defines:

- accountable record systems
- export bundle requirements
- shared record constraints
- source traceability requirements
- verification trace requirements
- prohibited category collapses
- domain profile expectations
- common accountability properties across domains

This contract does NOT define:

- domain vocabularies
- domain-specific ontologies
- legal, civic, benefits, planning, or scientific determinations
- analytics, inference, optimization, recommendation, or decision logic
- causal explanations
- epistemic evaluation
- authority, legitimacy, obligation, or enforcement
- replacements for existing domain standards or systems

## Relationship to Other Work

- AR is grounded in Structural Explainability.
- AR operationalizes SE constraints for domain record systems.
- AR does not replace domain standards, ontologies, schemas, or data systems.
- AR defines what a domain system must export to support SE verification.
- Domain products such as `judicial-record` and `civic-influence-record`
  specialize AR. Other domain products may specialize AR similarly.
- SE verification repos check whether domain systems satisfy AR and
  domain-profile constraints.

## Clarifying Statement

Accountable Record defines record accountability, not domain correctness.

An accountable record system records and exposes the structures needed for
inspection, contestation, audit, and continued use under disagreement.
It does not decide whether a domain claim is true, valid, legitimate,
binding, authoritative, or enforceable.

AR exists so that domain systems can remain inspectable across
disagreement, reinterpretation, and time.

## Repository Contents

- [SPEC.md](./SPEC.md) - Accountable Record contract
- [IDENTIFIERS.md](./IDENTIFIERS.md) - Stable requirement identifiers
- [CONFORMANCE.md](./CONFORMANCE.md) - Conformance checklist
- [EXPORT_CONTRACT.md](./EXPORT_CONTRACT.md) - Export bundle requirements
- [VERIFICATION_MODEL.md](./VERIFICATION_MODEL.md) - Verification model
- [FAILURE_MODES.md](./FAILURE_MODES.md) - Common prohibited collapses
- [ANNOTATIONS.md](./ANNOTATIONS.md) - Annotation standards
- [LICENSE](./LICENSE) - Licensing terms
- [CITATION.cff](./CITATION.cff) - Citation metadata
- [CHANGELOG.md](./CHANGELOG.md) - Version history

## Command Reference

<details>
<summary>Show command reference</summary>

### In a machine terminal

Open a machine terminal where you want the project:

```shell
git clone https://github.com/structural-explainability/accountable-record-spec

cd accountable-record-spec
code .
```

### In a VS Code terminal

```shell
uv self update
uv python pin 3.15
uv sync --extra dev --extra docs --upgrade

# install git hooks once per clone
uvx pre-commit install

# autofix and manual fix issues
git add -A
uvx pre-commit run --all-files
# repeat if changes were made
git add -A
uvx pre-commit run --all-files

# validate Markdown sources and generated specification artifacts
uv run se-validate

# generate machine-readable specification artifacts under data/spec/
uv run se-ref-export

# check that generated data/spec/ artifacts are current
uv run se-ref-export --check

# validate reference artifacts and registry consistency
uv run se-ref-validate

# run strict validation, including all standard source and export checks
uv run se-validate --strict

# do chores
uv run python -m pyright
uv run python -m pytest

# save progress
git add -A
git commit -m "update"
git push -u origin main
```

</details>

## Citation

[CITATION.cff](./CITATION.cff)

## License

[MIT](./LICENSE)

## Manifest

[SE_MANIFEST.toml](./SE_MANIFEST.toml)
