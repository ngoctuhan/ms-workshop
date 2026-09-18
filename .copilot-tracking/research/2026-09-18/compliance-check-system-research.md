<!-- markdownlint-disable-file -->

# Compliance Check System Research

## Scope

This research note supports a workshop scenario for a compliance-check system that uses a large language model to help review submissions and identify policy gaps or control exceptions.

## Evidence base

This workshop uses the synthetic evidence folder at ./copilot-tracking/research/workshop-input. No production system files were available in the workspace, so the findings below are framed as evidence-informed workshop assumptions rather than a legal or operational final specification.

## Business facts and likely workflow

* Compliance review is a high-volume, policy-sensitive activity where human judgment is still necessary.
* Review teams likely need to compare submitted evidence against policy requirements, operating procedures, and approval conditions.
* Manual review can be slow, inconsistent, and vulnerable to missed exceptions when evidence is fragmented across systems.
* A compliance-check assistant can provide structured triage by locating relevant requirements, summarizing supporting evidence, and highlighting missing items.
* The strongest value is likely not autonomous decision-making, but faster case preparation and consistency across reviewers.

## Affected users and stakeholders

* Compliance analysts who validate submissions against rules and controls
* Policy owners responsible for the regulatory or internal standards
* Operations managers who need consistent throughput and escalations
* Frontline reviewers or case handlers who need concise recommendations
* Auditors or governance teams who need traceable decisions and evidence histories

## Business rules and constraints

* Final decisions must remain with a human reviewer or designated authority.
* Policy interpretations should be grounded in approved source documents, not model guesses.
* Sensitive personal, regulated, or confidential data should be minimized and protected.
* Cases with low confidence, contradictory evidence, or legal ambiguity should escalate instead of being auto-approved.
* The system should flag missing evidence, missing signatures, outdated approvals, and policy exceptions.

## Likely failure cases

* The model misreads policy wording or overgeneralizes from a similar case.
* A submission appears compliant but misses a required control or attestation.
* The model hallucinates a regulation or policy interpretation that has no approved basis.
* Risk scoring is too lenient or too rigid for edge cases.
* Sensitive data is exposed in logs, explanations, or model prompts.

## Likely AI guardrails

* Require source-grounded outputs and links to policy references or approved evidence.
* Separate recommendation from final decision and show confidence and rationale clearly.
* Route uncertain or high-risk outputs to human review.
* Log user prompts, policy references, and decision outcomes in an audit-friendly way.
* Apply redaction or minimization for sensitive data before it enters the model context.
* Provide override and appeal paths for human reviewers.

## Facts vs assumptions

### Evidence-backed facts

* The scenario concerns compliance review and policy alignment.
* The likely goal is consistent, faster case review with safer human oversight.
* A compliance assistant should support traceability and escalation rather than full automation.

### Assumptions to validate

* The system will review structured documents or case materials rather than fully autonomous financial or legal review.
* The organization has a defined compliance policy library and approval workflow.
* The solution will integrate with existing case management or evidence repositories.
* The model will be used as a decision-support assistant, not a final adjudicator.

### Open questions

* Which policy sources and control frameworks apply in the target domain?
* What qualifies as a high-risk or sensitive case requiring escalation?
* How should low-confidence outputs, conflicting evidence, and appeals be handled?
* What approval path will govern final human signoff?
* Which data classification and retention rules apply to submitted evidence and model logs?

## Workshop recommendation

The most credible workshop direction is to frame the solution as a human-in-the-loop compliance review assistant that improves consistency and speed while preserving accountability, auditability, and policy correctness. This is a safer and more defensible product concept than an autonomous compliance oracle.

## Next steps

* Confirm the relevant policy library and review workflow.
* Draft the business and product requirements around human decision authority.
* Define risk tiers, escalation paths, and confidence thresholds.
* Capture the user journey for analysts and policy reviewers.
* Validate the design for traceability, privacy, and explainability before implementation.
