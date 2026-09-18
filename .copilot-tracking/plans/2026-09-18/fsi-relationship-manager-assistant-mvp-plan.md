---
title: FSI Relationship Manager Assistant MVP Plan
description: Lightweight implementation plan for the first MVP of a human-in-the-loop relationship review assistant for FSI, grounded in workshop evidence and scoped to source-grounded, permission-aware assistance.
ms.date: 2026-09-18
ms.topic: reference
---

## Evidence and scope

This plan is grounded in the workshop evidence under .copilot-tracking/research/2026-09-18/compliance-check-system-research.md, .copilot-tracking/research/2026-09-18/compliance-check-system-session-context.md, .copilot-tracking/research/workshop-input/leancanvas.md, and .copilot-tracking/dt/compliance-check-system-experience-outline.md.

A BRD session directory was not present in the workspace; the plan therefore uses the available research and design evidence and clearly marks unresolved business questions as assumptions to validate.

## MVP objective

Build the first MVP of a relationship review assistant that helps FSI teams prepare and validate client or relationship cases using grounded evidence, explicit confidence, and human approval before any external action. The assistant is not intended to make final compliance decisions autonomously.

The primary MVP job is:

* Review a client or relationship submission against the relevant policy, approval, and evidence requirements.
* Summarize the case, highlight gaps or exceptions, and cite the underlying sources.
* Flag uncertainty and route ambiguous or high-risk cases to human escalation.
* Require approval before sending outbound communications, updating records, or initiating external actions.

## Target MVP user and flow

Primary users:

* Relationship managers and case reviewers
* Compliance analysts and policy reviewers
* Operations or support staff who prepare case records

Primary flow:

1. User opens a case or relationship record.
2. The assistant retrieves only the relevant evidence and policy references the user is allowed to access.
3. The assistant summarizes the case, compares it to policy requirements, and surfaces missing items or exceptions.
4. The assistant shows confidence, cited evidence, and the reason for any uncertainty.
5. The reviewer validates the recommendation and either approves, edits, or escalates the case.
6. Only a human-approved action is sent externally or persisted as a formal decision.

## Phase plan

<!-- rpi:phase id=P01 -->
### Phase 1: Evidence validation and scope lock

Objective:

* Confirm the exact workflow, evidence sources, user roles, and risk profile for the MVP before implementation.

Deliverables:

* Approved MVP scope statement
* Confirmed policy and evidence sources
* User-role and permission matrix
* Initial case taxonomy for low-, medium-, and high-risk scenarios

Requirements:

* Document the target workflow and the evidence systems that will be queried.
* Define what counts as policy source, internal source, and external source.
* Identify which actions are read-only and which require explicit approval.
* Capture assumptions for missing policy library and operational workflows.

Dependencies:

* Business owner confirmation on workflow and user roles
* Access to policy library or approved source references
* A privacy and data-classification review for the chosen data sources

Risks:

* Scope drift into broad relationship-management support instead of a focused case review job
* Incomplete policy source definitions leading to unsupported recommendations
* Ambiguous permissions for retrieval or action approval

Acceptance criteria:

* A named MVP job exists with a defined user story and one primary task
* The evidence sources are listable and categorized
* Permissions, escalation paths, and risk tiers are documented
* Open questions are tracked and not treated as facts

<!-- rpi:phase id=P02 -->
### Phase 2: Interaction design and grounded-response model

Objective:

* Define the user experience so the assistant is a structured review workspace rather than a free-form chat experience.

Deliverables:

* UX flow for case intake, review, approval, and escalation
* Response template with evidence, confidence, gaps, and recommendation
* Decision labels for approved, rejected, needs reviewer input, and escalated

Requirements:

* Show a clear separation between recommendation and final human decision.
* Require visible citations or policy references for each key factual statement.
* Distinguish between source-grounded evidence and uncertain or inferred content.
* Display confidence and rationale in plain language.
* Provide a visible escalation path for ambiguous or high-risk cases.

Dependencies:

* UX and workflow validation with product and compliance stakeholders
* Policy source snippet or policy catalog for citation formatting
* Approval from risk and governance reviewers

Risks:

* Model output appears authoritative without a visible source trail
* Users treat the assistant as a final decision-maker instead of a reviewer support tool
* Confidence or rationale is too vague for regulated workflows

Acceptance criteria:

* Every recommendation includes a source reference or a documented reason it cannot be grounded
* Confidence is displayed and low-confidence cases are clearly routed to escalation
* The design requires human signoff before final action or approval

<!-- rpi:phase id=P03 -->
### Phase 3: Permission-aware retrieval and evidence assembly

Objective:

* Implement retrieval that is restricted to authorized sources and relevant context only.

Deliverables:

* Retrieval policy and source-scope rules
* Evidence collector for policy, case notes, approvals, and historical records
* Permission-aware filtering layer
* Redaction or minimization controls for sensitive content

Requirements:

* Access only data the user is allowed to view and process.
* Restrict retrieval to the minimum set of approved documents and case evidence required for the job.
* Remove or mask sensitive data before prompt assembly when possible.
* Record the source IDs used for each recommendation.
* Refuse or escalate when required evidence is missing or inaccessible.

Dependencies:

* Directory or document access governance
* Identity and authorization configuration for relevant systems
* Data classification and retention policy review

Risks:

* Overbroad retrieval exposes sensitive or unauthorized data
* Missing-source errors cause unsupported conclusions
* Retrieval is too broad and reduces signal quality or increases latency

Acceptance criteria:

* Retrieval logs show exactly which sources were used
* Unauthorized or out-of-scope documents are excluded
* Sensitive content is redacted or minimized before model use
* The assistant clearly states when required evidence is missing or inaccessible

<!-- rpi:phase id=P04 -->
### Phase 4: Human-in-the-loop decision workflow and external action guardrails

Objective:

* Ensure the MVP supports safe review and escalation without allowing autonomous decision-making or external action.

Deliverables:

* Decision workflow specification
* Approval gates for outbound actions
* Escalation playbook for ambiguity, conflicts, or high-risk cases
* Audit trail design for review actions and overrides

Requirements:

* Require explicit human confirmation before sending email, messages, updates, or external notifications.
* Separate read-only analysis from actionable workflow steps.
* Include a “not enough evidence” or “needs reviewer judgment” state.
* Log the case, sources used, user decision, and escalation path.
* Make it clear when the assistant is uncertain or when a requirement is not grounded.

Dependencies:

* Workflow and approval owner definition
* Audit and logging requirements
* External action integration design if applicable

Risks:

* External actions are triggered without human review
* Model recommends an action that the user assumes is final
* Escalation paths are unclear, creating retry loops or delays

Acceptance criteria:

* No outbound action can be executed without explicit human confirmation
* High-risk, low-confidence, or contradictory cases require escalation
* Every decision record shows the evidence sources and reviewer decision
* The system can explain why a case was routed to escalation

<!-- rpi:phase id=P05 -->
### Phase 5: MVP validation, observability, and readiness review

Objective:

* Verify that the MVP works under realistic case review conditions and that governance is ready for pilot use.

Deliverables:

* Pilot test pack and evaluation dataset
* Observability and monitoring plan
* Security, privacy, and legal review checklist
* Publication-readiness posture memo for Microsoft Marketplace and Microsoft 365 Copilot Agent Store

Requirements:

* Test with realistic, synthetic, or approved review cases that are representative of the target workflow.
* Measure latency, source-grounded answer quality, hallucination resistance, and escalation behavior.
* Validate permitted actions and logging coverage.
* Document all known limitations and unresolved assumptions.
* Keep publication claims provisional until current Microsoft guidance, Partner Center state, and tenant feasibility are verified.

Dependencies:

* Approved test cases and sample scenarios
* Monitoring and log collection configuration
* Governance review from privacy, security, and legal stakeholders

Risks:

* Pilot shows that the assistant is too cautious or too confident
* Operational workflow requires more source integrations than the MVP supports
* Marketplace or Copilot Store publication is attempted before tenant or Partner Center feasibility is clear

Acceptance criteria:

* Pilot cases confirm grounded answers, citations, and escalation behavior
* Monitoring confirms required logging and traceability
* The team can state the MVP readiness status without overstating publication readiness
* All external claims about publisher readiness are marked provisional

## MVP requirements

Functional requirements:

* Review a case and identify the most relevant policy, approval, and evidence items
* Summarize the case in a structured, review-friendly format
* Highlight missing evidence, contradictory items, or policy exceptions
* Show citations or approved evidence references for key statements
* Present confidence and uncertainty explicitly
* Escalate ambiguous, contradictory, or high-risk cases to a human reviewer
* Require human confirmation for any external action or formal decision

Non-functional requirements:

* High confidence in source grounding and minimal unsupported assertions
* Permission-aware retrieval and source minimization
* Traceable decision history and logs
* Clear readability for review users and accessible interaction patterns
* Support for operational review timeframes without creating workflow friction

## Dependencies

* Access to approved policy and evidence sources
* Identity and authorization controls for case data and approval actions
* Governance and privacy review for sensitive or regulated data
* Business confirmation of the exact workflow and user roles
* Definition of escalation ownership and approval authority

## Key risks and mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Unsupported policy interpretation | High | Require source citations and refuse unsupported answers |
| Overbroad retrieval | High | Restrict retrieval to authorized, relevant sources only |
| Data exposure | High | Minimize sensitive data, log only what is needed, and validate permissions |
| User over-trust in AI output | High | Separate recommendation from decision and show confidence clearly |
| Ambiguous escalation path | Medium | Define escalation criteria and owners before pilot |
| Scope creep | Medium | Keep the first job limited to one case-review workflow |
| Publication assumptions too early | Medium | Keep marketplace and Copilot Agent Store claims provisional until official guidance and tenant validation |

## Acceptance criteria for the MVP

The MVP is accepted when all of the following are true:

* The system supports one clearly defined FSI review job with a documented user flow.
* The assistant responds with grounded, source-backed findings and cites the evidence used.
* Missing or inaccessible evidence causes a clear “not enough evidence” state rather than speculation.
* Low-confidence or high-risk cases are routed to human escalation.
* No external action is executed without explicit human confirmation.
* Logging captures the evidence used, the recommendation, the reviewer decision, and the final outcome.
* The workflow is explainable enough for a compliance or operations review team to understand and challenge it.
* The product is ready for pilot review, but not yet a publication claim.

## Microsoft Marketplace and Copilot Agent Store posture

This plan aligns with the concept of an internal productivity and decision-support solution that could become a Microsoft ecosystem offering later, but publication claims are intentionally provisional.

The MVP is structured to support a future readiness review against:

* Microsoft guidance for Copilot agents and AI-enabled business scenarios
* Partner Center or marketplace requirements and tenant feasibility
* Data protection, privacy, security, and operational governance constraints
* Customer-specific deployment and approval requirements

The plan does not assume that publication, listing, or marketplace readiness are complete. Any future publication claim must be validated against current Microsoft guidance, the tenant’s legal and technical feasibility, and the applicable Partner Center process at the time of the decision.

## Facts vs assumptions

Facts from evidence:

* Compliance and relationship review are policy-sensitive and require human accountability.
* Manual review can be slow, inconsistent, and vulnerable to missed exceptions.
* The strongest value is faster case preparation and clearer review consistency, not autonomous decision-making.
* Traceability, auditability, and policy grounding are required.

Assumptions to validate:

* The target workflow is internal FSI case review or relationship evaluation.
* A policy library and case records are available for the pilot.
* The solution will be embedded in an existing enterprise workflow rather than stand-alone consumer usage.
* The user can only act on cases and evidence they are authorized to access.

Open questions:

* Which FSI workflow is the first pilot: onboarding, annual review, exception handling, or relationship servicing?
* Which policy sources and approval workflows are in scope?
* What specific external actions are intended to require approval?
* What are the baseline operational metrics that define success for the pilot?

## Summary

The first MVP should be narrow, grounded, and approval-gated. Its focus is a single evidence-backed review job that helps FSI staff prepare and validate relationship or compliance cases with citations, explicit uncertainty, permitted retrieval, and human escalation before any action is taken. This approach is consistent with the workshop evidence and is a defensible first step toward broader governance and platform readiness without making unverified publication claims.
