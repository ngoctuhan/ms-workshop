---
title: Compliance Check System Business Requirements Draft
description: Concise business requirements outline for a human-in-the-loop compliance check system supported by large language model assistance.
ms.date: 2026-09-18
ms.topic: reference
---

## Evidence basis

This draft is based on the workshop context and research files for the Compliance Check System scenario:

* .copilot-tracking/research/2026-09-18/compliance-check-system-session-context.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-research.md
* .copilot-tracking/research/workshop-input/leancanvas.md

The evidence indicates a synthetic workshop scenario, not a production policy specification, and it explicitly assumes a human-in-the-loop model with strong auditability and governance.

## Business problem

Compliance review teams spend significant effort comparing submissions, case materials, and supporting evidence against policy, operational requirements, and approval conditions. The work is often evidence-heavy, high-volume, and sensitive to inconsistent interpretation, missed exceptions, and fragmented information across systems. Teams need a way to accelerate case preparation and improve consistency without surrendering accountability for final decisions.

## Affected stakeholders

* Compliance analysts who review submissions and confirm requirement coverage
* Policy owners who maintain approved standards and interpretation guidance
* Operations managers who monitor throughput, exception rates, and escalations
* Frontline reviewers or case handlers who need concise case summaries and recommended next steps
* Auditors and governance teams who require traceable decisions and evidence history
* Business owners who care about cycle time, quality, and risk reduction

## Measurable business outcomes

* Reduce average time to triage and prepare a compliance case by at least 30 percent
* Increase completeness of evidence capture before final review by 25 percent
* Reduce missed or late-discovered policy gaps and missing approvals in reviewed cases
* Improve consistency of rule application across reviewers and case types
* Increase the percentage of low-confidence or high-risk cases that are escalated appropriately
* Maintain a clear audit trail for all recommendations, human decisions, and overrides

## Scope

### In scope

* Review of evidence, policy references, and case records against approved requirements
* Structured summarization of a case and its supporting materials
* Identification of missing evidence, policy gaps, outdated approvals, and inconsistencies
* Risk-aware routing for uncertain, contradictory, or high-risk cases
* Traceable recommendations with cited policy and evidence references
* Human review and final decision authority retained by authorized staff

### Out of scope

* Full autonomous compliance adjudication or automatic approval of regulated decisions
* Final legal or regulatory interpretation beyond approved policy sources
* Broad workflow automation outside the designated compliance-check process
* Direct customer-facing decision making or unreviewed external action execution

## Non-goals

* Replacing the compliance reviewer role with a model-only decision engine
* Eliminating audit, policy governance, or human escalation workflows
* Supporting unmanaged access to confidential, regulated, or sensitive evidence
* Providing a general-purpose legal or financial advisory experience outside approved review workflows

## Business rules

* Final decisions remain with a human reviewer or designated authority
* Recommendations must be grounded in approved policy documents or trusted evidence sources
* Cases with low confidence, contradictory evidence, or legal ambiguity must escalate
* Sensitive personal, regulated, or confidential data must be minimized or protected before model processing
* Missing evidence, invalid signatures, outdated approvals, and policy exceptions must be flagged
* A recommendation must be distinguishable from the final decision and not presented as authority

## Constraints

* The workflow must operate within approved policy libraries, case-management systems, and evidence repositories
* Human accountability is mandatory for final decisions and escalations
* Privacy, data classification, and retention requirements must be observed
* Model behavior must avoid unsupported policy interpretations and hallucinated citations
* The solution must support traceability, explainability, and reviewers’ override options

## Risks

* The model may misread policy wording or generalize from similar cases incorrectly
* A case may appear compliant while missing a required control, attestation, or approval
* Sensitive data may be exposed through logs, prompts, or model outputs if guardrails are weak
* Reviewers may over-trust recommendations without checking source grounding or confidence
* Incomplete or inaccessible evidence may lead to unsupported conclusions or delays

## Assumptions

* The target workflow is a compliance or policy review process with documents and evidence stored across systems
* Approved policy sources and control frameworks exist but require validation in the target environment
* The organization already has case-management or evidence repositories to support traceability
* The system will be used as a decision-support assistant rather than a final adjudicator
* Human reviewers already own the final signoff and escalation path

## Dependencies

* Access to relevant policy libraries, control frameworks, and approved source documents
* Integration with existing case-management or evidence systems
* Data classification, privacy, and retention rules for evidence and model logs
* Role-based access and permission controls for legal review and escalation workflows
* Operational ownership for exceptions, overrides, and audit review

## Unresolved questions

* Which policy sources and control frameworks are in scope for the target workflow?
* What risk tiers or sensitivity thresholds require escalation instead of standard review?
* Which roles should own final approval, exception handling, and review overrides?
* What is the baseline process today and which operational metrics should define success?
* What evidence sources, formats, and retention rules apply to this workflow?
* What workflow should be used for appeals, conflicting evidence, and low-confidence decisions?

## Business summary

The proposed solution is a human-in-the-loop compliance review assistant that helps teams prepare and validate submissions more quickly, improves consistency, flags exceptions early, and preserves accountability and policy traceability. The strongest business value is not autonomous compliance decision-making, but safer and faster case preparation with clear escalation and auditability.
