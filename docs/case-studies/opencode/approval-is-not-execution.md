# Approval Is Not Execution: Evidence-Driven Authority Continuity in OpenCode

> **This is a qualified evidence-side case study, not a public normative OpenCode profile.**

## Scope

This case study examines one narrow governance question:

**How should a source-native permission request and permission decision event be represented without collapsing a recorded decision into execution authority or into a granted outcome?**

The work is bounded to the OpenCode evidence collected and qualified through the OSS-R3 external-harness and scoped-profile lineage.

It does not claim to define an official OpenCode contract.

## Core separation

The governing semantic rule is:

~~~text
request != decision
decision != decision outcome
decision != authorization grant
authorization grant != execution
execution != result
~~~

For this case, `permission.replied` is therefore **not** treated as proof that execution authorization was granted.

The canonical event type records that an authorization decision exists; the actual decision outcome remains an independent fact.

## Qualified mapping

| Dimension | Source or candidate input | Qualified canonical value |
| --- | --- | --- |
| Authority stage | `SEALED_SEMANTIC_CANDIDATE_EVIDENCE` | `RUNTIME_AUTHORIZATION` |
| Permission request event | `permission.asked` | `TOOL_EXECUTION_AUTHORIZATION_REQUESTED` |
| Permission decision event | `permission.replied` | `TOOL_EXECUTION_AUTHORIZATION_DECISION_RECORDED` |
| Source system | `OPENCODE_PRODUCT_IDENTITY` | `opencode` |

Source-system policy:

~~~text
CASE_POLICY=LOWERCASE_ASCII
NAMESPACE_POLICY=GEC_SOURCE_SYSTEM_NAMESPACE_V1
~~~

## Why `DECISION_RECORDED`, not `GRANTED`

The observed decision-event vocabulary establishes a decision boundary.

It does not, by itself, establish a particular decision outcome.

Therefore:

~~~text
permission.replied
    -> TOOL_EXECUTION_AUTHORIZATION_DECISION_RECORDED
~~~

and not:

~~~text
permission.replied
    -> TOOL_EXECUTION_AUTHORIZATION_GRANTED
~~~

This preserves the distinction between:

1. a request being made,
2. a decision being recorded,
3. the decision outcome,
4. execution authorization,
5. actual execution.

## Authority lineage

The qualified mapping was produced through separated governance gates:

~~~text
profile candidate
    ↓
explicit canonical-value decision
    ↓
materialization request
    ↓
explicit materialization authorization
    ↓
one-shot evidence-side materialization
    ↓
post-execution qualification
    ↓
scoped-profile closeout
    ↓
bounded repository-adoption authorization
~~~

Relevant sealed lineage identifiers:

~~~text
OSS-R3-SPR-H3-R10  canonical-value decision
OSS-R3-SPR-H3-R12  materialization authorization
OSS-R3-SPR-H3-R13  materialization execution
OSS-R3-SPR-H3-R14  post-execution qualification
OSS-R3-SPR-H3-R15  scoped-profile closeout
OSS-R3-RPA-H3-R2   bounded repository-write authorization
~~~

Qualified evidence artifact:

~~~text
SHA256=e84c05eda719bd97134237a04dcf1e9adab287ce5aa3e2633f2e49bec29cb458
~~~

## Claim-to-evidence matrix

| Claim | State |
| --- | --- |
| OpenCode `permission.asked` was observed as source-native event vocabulary | **PROVEN** |
| OpenCode `permission.replied` was observed as source-native event vocabulary | **PROVEN** |
| `permission.replied` semantically means authorization was granted | **CONTRADICTED** |
| The evidence-side OpenCode mapping was qualified | **PROVEN** |
| An official/public normative OpenCode profile already exists in this work | **CONTRADICTED** |
| Repository adoption had already been authorized before the RPA lineage | **CONTRADICTED** |
| Broad external community validation of this case study has already occurred | **NOT_OBSERVED** |

## Non-claims

This case study does **not** claim:

- official OpenCode endorsement;
- OpenSSF endorsement;
- CNCF endorsement;
- that this mapping is an external standard;
- that a permission decision implies execution;
- that qualification itself grants runtime authority;
- that this repository artifact is a public normative OpenCode profile.

## Repository status

This document and its companion JSON profile are intentionally classified as **non-normative case-study artifacts**.

They do not modify the Governance Event Core schema or normative contract surfaces.

Repository placement:

~~~text
docs/case-studies/opencode/
~~~

The separation is intentional:

~~~text
qualified evidence
    != normative core contract
    != product endorsement
    != publication authority
~~~
