---
title: Compliance Check System
description: Draft product requirements outline for a human-in-the-loop compliance check system supported by an LLM.
ms.date: 2026-09-18
ms.topic: reference
---

## Compliance Check System — Product Requirements Draft

Status: Draft for human review
Version: 0.1.0

### Evidence references

* [Session context](../research/2026-09-18/compliance-check-system-session-context.md)
* [Research artifact](../research/2026-09-18/compliance-check-system-research.md)
* [Workshop evidence README](../research/workshop-input/README.md)
* [Lean canvas](../research/workshop-input/leancanvas.md)

### Document purpose

This draft defines a product requirements outline for a compliance-check workflow that uses a large language model to help reviewers assess submissions against policy, operational, and control requirements while preserving human accountability and auditability.

## 1. Facts, assumptions, decisions, and open questions

### Facts from the evidence base

* The scenario concerns compliance review and policy alignment.
* The workflow likely compares submitted evidence against policy requirements, operating procedures, and approval conditions.
* Human reviewers remain accountable for final decisions and escalation.
* The solution must support traceability, auditability, and escalation for low-confidence or high-risk outputs.
* A compliance-check assistant is most credible as a decision-support workflow rather than an autonomous adjudicator.
* The research explicitly calls out model hallucination, missed required controls, and sensitive-data exposure as failure modes.

### Assumptions to validate

* The primary workflow is internal case or submission review in a regulated or policy-sensitive environment.
* The system supports evidence intake from documents, notes, or structured case materials rather than fully autonomous legal or financial decision-making.
* The organization has an approved policy library, operating procedures, and final signoff path.
* The assistant integrates with internal case-management or evidence repositories, and the model output is used for review support rather than approval.

### Decision log

* Decision: The product should be framed as a human-in-the-loop compliance review assistant.
* Decision: Final decisions remain with a human reviewer or designated authority.
* Decision: Outputs must be source-grounded and subject to escalation when confidence is low or contradictions are material.

### Open questions

* Which policy sources and control frameworks apply in the target domain?
* Which case types are in scope: onboarding, annual review, exception handling, or other relationship review workflows?
* What qualifies as a high-risk or sensitive case that requires escalation?
* Which evidence sources and repositories are in scope?
* What data-classification and retention rules apply to model prompts, logs, and cached outputs?
* How will low-confidence outputs, conflicting evidence, and appeals be handled?

## 2. Target users and stakeholders

### Primary target users

* Compliance analysts who validate submissions against rules and controls
* Frontline reviewers or case handlers who need concise review support
* Policy owners who maintain approved standards and control wording
* Operations managers who need consistent throughput and escalations
* Governance or audit teams that need traceable decisions and evidence history

### Jobs to be done

* Review submitted evidence against applicable policy and approval conditions.
* Identify missing evidence, exceptions, and approval gaps quickly.
* Prepare a consistent summary for human review and escalation.
* Reduce the effort needed to locate applicable policy language and compare it to a submission.
* Preserve auditability and accountability for final decisions.

## 3. User journeys

### Journey 1: Case intake and initial review

1. A reviewer opens a case or submission.
2. The system identifies relevant policy sources, procedures, and approval requirements.
3. The assistant summarizes the evidence and flags missing or inconsistent items.
4. The reviewer confirms or corrects the assessment and records the final decision.
5. The case is stored with policy references and reviewer rationale for audit purposes.

### Journey 2: Exception handling

1. A submission raises a policy exception, missing signature, outdated approval, or conflicting evidence.
2. The assistant highlights the exception and identifies supporting or missing evidence.
3. The workflow routes the case to a human reviewer or escalation path.
4. The reviewer decides whether to accept, reject, request more evidence, or escalate further.

### Journey 3: Audit and traceability review

1. A governance or audit user accesses a completed case.
2. The system provides the review summary, policy references, evidence used, and decision record.
3. The user checks whether the decision was grounded and whether the escalation path was followed.

## 4. Scope

### In scope

* Summarization of case evidence and supporting material
* Comparison of evidence against approved policy or control requirements
* Detection of missing evidence, missing signatures, outdated approvals, and policy exceptions
* Evidence-grounded recommendations with confidence and rationale
* Human escalation for low-confidence, contradictory, or high-risk outputs
* Traceable logging of policy references, review rationale, and final decisions

### Out of scope

* Fully autonomous approval or rejection decisions
* Interpretation of policy without approved source documents
* Final legal or regulatory determination outside designated authority
* Unbounded open-ended analysis of unrelated case data
* Use of sensitive data beyond the approved case context and retention policy

## 5. Functional requirements

| ID | Requirement | Description | Priority |
|---|---|---|---|
| FR-001 | Evidence intake support | The system shall accept a case or submission with relevant evidence, notes, or attachments for review. | Must |
| FR-002 | Policy matching | The system shall identify relevant policy language, standards, or approval conditions from approved source material. | Must |
| FR-003 | Exception highlighting | The system shall highlight missing evidence, inconsistent items, outdated approvals, missing signatures, and policy exceptions. | Must |
| FR-004 | Summary generation | The system shall produce a concise summary of the case and support it with source-grounded references. | Must |
| FR-005 | Recommendation separation | The system shall distinguish recommendations from final human decisions. | Must |
| FR-006 | Confidence and rationale | The system shall show confidence, rationale, and evidence basis for outputs when available. | Must |
| FR-007 | Human escalation | The workflow shall route low-confidence, conflicting, or high-risk cases to a human reviewer or escalation path. | Must |
| FR-008 | Traceability log | The system shall preserve references to policy sources, evidence used, and final decisions in an audit-friendly record. | Must |
| FR-009 | Redaction support | The system shall support minimization or redaction of sensitive information before model processing when required by policy. | Must |
| FR-010 | Override path | Human reviewers shall be able to override, annotate, or reject the assistant output. | Must |
| FR-011 | Operational feedback | The system shall allow users to flag incorrect interpretations or false positives for review and improvement. | Should |

## 6. Non-functional requirements

| ID | Category | Requirement | Metric or target |
|---|---|---|---|
| NFR-001 | Reliability | The system shall avoid presenting unsupported policy interpretations as fact. | 0 unsupported policy claims without approved source reference |
| NFR-002 | Security/privacy | Sensitive and regulated data shall be protected, minimized, and logged in accordance with policy. | No sensitive data exposed outside approved workflow |
| NFR-003 | Auditability | Each case review shall retain the evidence, policy references, and final decision in a reviewable record. | Full traceability for each case |
| NFR-004 | Explainability | The assistant shall show the basis for recommendations, including key evidence and uncertainty. | Human reviewer can trace output to source material |
| NFR-005 | Accessibility | Core review workflows, outputs, and status indicators shall be accessible to users with diverse needs. | Conforms to applicable accessibility standards for the target environment |
| NFR-006 | Availability | Review workflow shall remain usable for intended operating hours. | Availability target to be established by operational owner |
| NFR-007 | Performance | Users shall receive initial triage and summary output within the operating need of the workflow. | Time target to be established by business owner |
| NFR-008 | Maintainability | Policy source mappings and escalation rules shall be configurable without a redesign. | Policy updates can be implemented without code-only changes |

## 7. Data and AI guardrails

### Data handling

* Sensitive personal, regulated, or confidential data should be minimized before model use.
* Approved policy sources and evidence should be explicitly referenced rather than inferred.
* Logs should capture prompt context, policy references, and decision outcomes in an audit-friendly way.
* Only approved data should enter the model context.

### AI guardrails

* Require source-grounded outputs and traceability to approved policy references.
* Separate recommendation from final decision and show confidence and rationale clearly.
* Route uncertain, contradictory, or high-risk outputs to human review.
* Apply redaction or minimization as required before model input.
* Allow human override and appeal paths.
* Prevent unsupported policy statements or model-generated legal interpretations without source basis.

### Known failure cases

* The model misreads policy wording or overgeneralizes from a similar case.
* A submission appears compliant but misses a required control or attestation.
* The model hallucinates a regulation or policy interpretation without approved basis.
* Risk scoring is too lenient or too rigid for edge cases.
* Sensitive data is exposed in logs, explanations, or prompts.

## 8. Accessibility needs

### Required considerations

* Support keyboard access for reviewers using assistive technology.
* Ensure summaries, flags, and status indicators are understandable without relying on color alone.
* Make evidence references and rationale available in a readable, structured format.
* Ensure work products can be consumed by screen readers and other assistive technologies.

### Open accessibility question

* Which accessibility standards apply in the target operational environment, and what assistive technology support is required for internal reviewers?

## 9. Success metrics

The project should track operational quality and policy correctness rather than only software output volume.

* Average time to triage or review a case
* Percentage of cases with missing evidence identified before final signoff
* Percentage of low-confidence or high-risk cases escalated appropriately
* Reviewer override or correction rate
* Number of unsupported policy interpretations caught before final decision
* Reduction in manual evidence-search effort
* Improved consistency of review outcomes across reviewers

## 10. Dependencies

* Approved policy library and control references
* Existing case-management or evidence repository integration
* Defined human review and escalation workflow
* Data classification and retention rules
* Operational ownership for review quality and exceptions
* Governance process for model output monitoring and issue triage

## 11. Testable acceptance criteria

### AC-001: Case summary and gap detection

Given a case with relevant evidence and a policy set,
When a reviewer submits the case for review,
Then the system shall produce a summary and identify missing or inconsistent items tied to the relevant policy or approval conditions.

### AC-002: Human accountability

Given a case with low confidence or contradictory evidence,
When the system evaluates the submission,
Then it shall route the case to human review instead of auto-approving the decision.

### AC-003: Evidence traceability

Given a completed review,
When a reviewer or auditor reviews the case record,
Then the output shall include the policy references and supporting evidence used for the recommendation.

### AC-004: Safe handling of sensitive data

Given sensitive or regulated data in a case,
When the system prepares model input,
Then it shall minimize or redact data according to approved data-handling policy and avoid exposing it outside the workflow.

### AC-005: Override behavior

Given a reviewer disagrees with the assistant recommendation,
When the reviewer records an override or explanation,
Then the final decision shall remain under human control and the override shall be retained in the audit history.

### AC-006: Accessibility baseline

Given a reviewer using assistive technology,
When they access the case summary and status indicators,
Then the relevant content shall be available in an accessible, non-color-only presentation.

## 12. Risks and unresolved items

* Policy interpretation risk if approved source documents are not clearly mapped.
* False confidence if the assistant does not distinguish summary from decision.
* Sensitive-data exposure if minimization and redaction are not enforced.
* Inconsistent review quality if no calibration or escalation thresholds are defined.
* Unclear success criteria without baseline operational metrics.

## 13. Summary

The most defensible product direction is a human-in-the-loop compliance review assistant that helps analysts compare evidence to approved requirements, spot missing or inconsistent items, and route ambiguous or high-risk cases to human review. This approach matches the evidence base: faster case preparation and more consistent review support while preserving accountability, traceability, and policy correctness.

## 14. Draft status

This document is a draft for human review and should be revised as the target policy framework, users, data classes, and operational workflow are confirmed.
