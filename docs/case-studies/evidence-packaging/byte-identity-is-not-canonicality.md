# Byte Identity Is Not Canonicality

> **This is a sanitized, non-normative qualified-evidence case study. It is not raw source evidence and does not modify the Governance Event Core normative surface.**

## Scope

This case examines one narrow governance question:

**When two verification receipts are byte-identical but exist at different paths, does byte equality establish creation authority or canonicality?**

The qualified answer is no. Content identity, path identity, creation authority, and canonicality remain separate dimensions.

## Core separation

~~~text
byte identity != path identity
path identity != creation authority
creation authority != canonicality
byte identity != canonicality
creation order != canonicality
~~~

Byte equality proves only that the compared payload bytes are equal under the selected digest algorithm. It does not prove that the files occupy the same path, were produced under the same authority, or hold the same canonical status.

## Sanitized candidates

| Dimension | Candidate 01 | Candidate 02 |
| --- | --- | --- |
| Public fixture path | `fixtures/candidate-01/receipt.json` | `fixtures/candidate-02/receipt.json` |
| Fixture SHA-256 | `196808d4851c5fb8bb534b11a7011e9ee795f27af840e83f6e621ab6ab103875` | `196808d4851c5fb8bb534b11a7011e9ee795f27af840e83f6e621ab6ab103875` |
| Creation context | `FIRST_SUCCESSFUL_CREATION` | `LATER_UNINTENDED_RERUN` |
| Creation authority | `INITIAL_CREATION_AUTHORITY_BOUND` | `NO_SEPARATE_CREATION_AUTHORITY_OBSERVED` |
| Canonical status | `CANONICAL` | `NONCANONICAL_DUPLICATE` |

The fixture files intentionally have identical bytes at distinct repository paths. Candidate-specific authority and canonicality facts are recorded separately in `byte-path-authority-canonicality-case-v0.1.json` so those facts do not alter the receipt payload identity.

## Canonical selection

Candidate 01 is canonical because an explicit sealed adjudication selected it. It is not canonical merely because its creation occurred first or because its bytes match the later candidate.

Candidate 02 is classified as:

~~~text
BYTE_IDENTICAL_UNINTENDED_RERUN
~~~

It adds no new receipt semantics and no separate creation authority was observed. It remains preserved as a noncanonical historical candidate rather than being rewritten or deleted.

## Claim-to-evidence matrix

| Claim | Qualification |
| --- | --- |
| The two public fixture payloads are byte-identical | **PROVEN_PUBLIC_FIXTURE** |
| The two public fixture paths are distinct | **PROVEN_PUBLIC_FIXTURE** |
| Byte equality establishes creation authority | **CONTRADICTED** |
| Byte equality establishes canonicality | **CONTRADICTED** |
| Earlier creation time automatically establishes canonicality | **CONTRADICTED** |
| Candidate 01 was selected by explicit adjudication | **QUALIFIED_PRIVATE_SOURCE_DERIVATION** |
| Candidate 02 was classified as a byte-identical unintended rerun | **QUALIFIED_PRIVATE_SOURCE_DERIVATION** |

## Sanitization boundary

The public case does not disclose source hostnames, usernames, shell transcripts, absolute evidence paths, timestamped source directories, raw evidence packages, or original manifest and seal hashes.

The SHA-256 value in this case belongs only to the sanitized public fixture. It is not the digest of the private source receipt.

## Non-claims

This case study does **not** claim:

- that byte equality grants creation, publication, execution, or canonical-selection authority;
- that path order or timestamps alone prove causality;
- that the public fixture is raw audit evidence;
- that the case defines runtime behavior, durable closeout, or a product-specific profile;
- that qualification modifies the Governance Event Core schema or normative contracts.

## Repository status

This document, its companion JSON case record, and its two receipt fixtures are non-normative case-study artifacts under:

~~~text
docs/case-studies/evidence-packaging/
~~~

They do not modify `schemas/`, `contracts/`, or `conformance/`.
