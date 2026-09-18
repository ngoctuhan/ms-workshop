---
title: Compliance Check System Experience Outline
description: Draft user journey, experience outline, and key pain points for a human-in-the-loop compliance review workflow supported by an LLM.
ms.date: 2026-09-18
ms.topic: reference
---

## Compliance Check System Experience Outline

Status: Draft for human review

### Evidence basis

* [Session context](../research/2026-09-18/compliance-check-system-session-context.md)
* [Research artifact](../research/2026-09-18/compliance-check-system-research.md)
* [Workshop evidence README](../research/workshop-input/README.md)

## 1. Simple user journey

### Reviewer opens a case

* A compliance analyst or frontline reviewer opens a submission or record to assess.
* The case may include documents, approvals, notes, or supporting evidence.
* The reviewer needs to know whether the submission matches policy and approval conditions.

### System prepares a structured review

* The assistant summarizes the evidence and identifies relevant policy language.
* The workflow highlights missing evidence, missing signatures, outdated approvals, or policy exceptions.
* The reviewer sees a concise summary with sources and a clear distinction between recommendation and final decision.

### Reviewer validates the assessment

* The reviewer checks the summary, confidence, and supporting references.
* If the output is high-confidence and consistent, the reviewer can proceed with signoff.
* If the output is low-confidence or contradictory, the case is escalated to a human reviewer or designated authority.

### Final decision and audit trail

* The human reviewer records the decision and rationale.
* The system stores evidence references and decision history for traceability and audit review.

## 2. Experience outline

### Core interaction model

The experience should be a structured review workspace, not a free-form chat assistant.

* Intake: the reviewer loads a case and relevant evidence.
* Triage: the system identifies policy requirements, gaps, and risks.
* Review: the user checks outputs, validates evidence, and corrects any incorrect interpretation.
* Decision: the reviewer records final signoff or escalation.
* Audit: the system maintains the case record and references for governance.

### User needs

* Find the relevant policy language quickly.
* See whether required evidence or approvals are missing.
* Understand why the system flagged a gap or exception.
* Know when a case requires escalation instead of auto-approval.
* Maintain confidence that the final decision remains human-led and traceable.

### Experience principles

* Ground every recommendation in approved policy or evidence.
* Separate recommendation from final decision.
* Surface uncertainty clearly.
* Support escalation for ambiguous cases.
* Preserve accountability and auditability.

## 3. Key pain points

### Pain point 1: fragmented evidence

* Evidence may be spread across systems, submissions, and approvals.
* Reviewers must manually aggregate materials before comparing them to policy.

### Pain point 2: inconsistent review quality

* Manual review can be slow and inconsistent across users or case types.
* Similar cases may be interpreted differently depending on reviewer experience or workload.

### Pain point 3: missed policy exceptions

* Missing signatures, outdated approvals, or incomplete evidence can be easily missed.
* Weak triage increases the risk of late-discovered noncompliance.

### Pain point 4: low-confidence or unsupported AI output

* The model may misread policy language or invent a requirement without source basis.
* Unclear confidence or rationale can reduce trust in the review workflow.

### Pain point 5: risk of sensitive-data exposure

* Regulated or confidential information may be exposed if prompts, logs, or explanations are not carefully controlled.

### Pain point 6: unclear escalation path

* Reviewers need a clear way to escalate low-confidence, contradictory, or high-risk cases.
* Without a clear escalation path, ambiguous cases may be incorrectly approved or delayed.

## 4. Facts vs assumptions

### Facts from evidence

* Manual review is slow, inconsistent, and vulnerable to missed exceptions.
* The product should support policy comparison, evidence summarization, and missing-item detection.
* Human accountability and escalation remain required.
* The workflow must preserve traceability and auditability.

### Assumptions to validate

* The case workflow involves structured records or submissions rather than fully autonomous financial or legal decisions.
* Review teams have an approved policy library and internal review process.
* The assistant is embedded in an existing case-management or evidence workflow.
* The use case is primarily internal operational review, not direct user-facing consumer interaction.

### Open questions

* Which policy sources and control frameworks are in scope?
* Which workflows are targeted: onboarding, exception review, annual review, or other submissions?
* What counts as a high-risk or sensitive case?
* What makes a low-confidence output escalate, and who owns that decision?

## 5. Draft design recommendations

* Use a structured review panel with clear summary, evidence, flags, and decision status.
* Show a visible confidence indicator and evidence trail for each recommendation.
* Separate “recommended action” from “final decision.”
* Keep escalation paths explicit and visible.
* Minimize sensitive data before model processing and log only what is required for auditability.
* Provide a clear override and review history for each case.

## 6. Draft status

This document is a draft for human review and should be refined with the target policy library, workflow details, and user role definitions before implementation planning.
