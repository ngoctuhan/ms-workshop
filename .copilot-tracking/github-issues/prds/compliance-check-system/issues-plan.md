<!-- markdownlint-disable-file -->

# MVP backlog plan

## Summary

This MVP focuses on one grounded review job: a compliance or relationship case is summarized, compared to approved policies, and escalated when confidence is low or the evidence is incomplete. The system does not make final decisions and requires human approval before external actions.

## Target repository and creation status

* Repository: https://github.com/asiapartners/hve-innovation
* Current status: GitHub issue creation is blocked in this session because the browser session is signed out and the GitHub CLI is not installed (`gh` not available).
* Proposed issue hierarchy remains ready to create once auth is available.

## Planned issue hierarchy

* Parent issue: `MVP: Grounded compliance review assistant`
* Child issues:
  * `P0: Intake and permission-aware evidence retrieval`
  * `P0: Policy matching and exception detection`
  * `P0: Human escalation and approval gate`
  * `P1: Traceability and reviewer override history`
  * `P1: Pilot governance, privacy, and security review`
  * `P2: Publication readiness assessment (provisional)`

## Priority labels

* P0 = required for the first shipped MVP
* P1 = important for pilot safety, quality, or operational viability
* P2 = de-scope or post-MVP readiness work

## Epic 1: Grounded case review MVP

### Feature 1: Intake and evidence retrieval

#### Story 1 — Reviewers can open a case and load only the necessary evidence

* Priority: P0
* Acceptance criteria:
  * User opens a case and sees a review-ready workspace.
  * System retrieves only relevant policy and case evidence within authorized scope.
  * Missing or inaccessible evidence is clearly flagged.
* Tasks:
  * Define case input contract and required fields.
  * Design source-scoping and authorization checks.
  * Implement minimal retrieval pipeline for policy and evidence.

#### Story 2 — Retrieval respects permission boundaries and sensitive data handling

* Priority: P0
* Acceptance criteria:
  * Unauthorized or out-of-scope documents are excluded.
  * Sensitive records are minimized or redacted before model input.
* Tasks:
  * Define data classification and redaction rules.
  * Implement permission-aware retrieval filter.
  * Add audit logging for source access decisions.

### Feature 2: Policy comparison and issue detection

#### Story 3 — The assistant summarizes the case and matches it to policy requirements

* Priority: P0
* Acceptance criteria:
  * The system identifies the most relevant policy or approval conditions.
  * The summary cites approved policy language or evidence references.
  * Missing evidence and gaps are surfaced in plain language.
* Tasks:
  * Map case fields to policy criteria.
  * Add grounded summary template with citations.
  * Add comparison logic for missing items and exceptions.

#### Story 4 — Confidence, uncertainty, and risk are explicit

* Priority: P0
* Acceptance criteria:
  * Low-confidence or contradictory findings are marked clearly.
  * Risk and uncertainty are visible to the reviewer before signoff.
* Tasks:
  * Define confidence model and escalation thresholds.
  * Add explanation layer for rationale and evidence basis.
  * Add risk flags for ambiguous or high-risk cases.

### Feature 3: Human decision and escalation

#### Story 5 — Ambiguous or higher-risk cases escalate to a human reviewer

* Priority: P0
* Acceptance criteria:
  * Low-confidence, conflicting, or high-risk cases route to an escalation path.
  * Reviewer sees the reason for escalation and the evidence behind it.
* Tasks:
  * Define escalation rules and owners.
  * Implement case-state transitions for review, escalation, and closure.
  * Add review notes and required handoff flow.

#### Story 6 — External actions require human confirmation

* Priority: P0
* Acceptance criteria:
  * No outbound communication or workflow action executes without explicit confirmation.
  * Final decision remains with a human reviewer.
* Tasks:
  * List allowed and blocked actions.
  * Implement approval gate and confirmation workflow.
  * Add audit record for approved, rejected, or changed actions.

## Epic 2: Trust, traceability, and operational readiness

### Feature 4: Auditability and explainability

#### Story 7 — Reviewers can trace recommendations to source material and decision history

* Priority: P1
* Acceptance criteria:
  * Each summary or recommendation references approved sources.
  * Reviewers can inspect evidence used, rationale, and final decision history.
* Tasks:
  * Add evidence trace log for each case.
  * Capture reviewer overrides and decision outcomes.
  * Add export or review history view for audit use.

#### Story 8 — Human override and feedback are captured

* Priority: P1
* Acceptance criteria:
  * Reviewer can override or correct the assistant output.
  * Overrides are visible in the case record and are usable for later tuning.
* Tasks:
  * Define override workflow and annotation model.
  * Persist reviewer feedback and correction reasons.

### Feature 5: Pilot compliance and governance

#### Story 9 — Security, privacy, and operational review are complete for pilot

* Priority: P1
* Acceptance criteria:
  * Privacy, security, and compliance review is complete for the pilot.
  * Logging and data retention rules are defined.
* Tasks:
  * Review data classification and logging requirements.
  * Confirm retention, redaction, and access controls.
  * Document human ownership for exceptions and review quality.

#### Story 10 — Publication readiness is assessed but not claimed

* Priority: P2
* Acceptance criteria:
  * The team documents what is needed for Microsoft Marketplace and Microsoft 365 Copilot Agent Store readiness.
  * No publication claim is made without current guidance and tenant review.
* Tasks:
  * Review current Microsoft guidance and dependencies.
  * Confirm Partner Center and tenant feasibility.
  * Document readiness gaps and required follow-up steps.

## Recommended execution order

1. P0: Case intake, permission-aware retrieval, grounded review, escalation, and approval gates.
2. P1: Traceability, auditability, and governance for pilot readiness.
3. P2: Publication readiness evaluation and broader platform packaging work.

## Publication readiness assessment

### Microsoft Marketplace

* Status: Not ready to claim publication readiness.
* Gaps: current Microsoft guidance, Partner Center state, commercial requirements, and tenant feasibility have not been verified.
* Recommendation: Keep this as a governance and feasibility assessment only until validated.

### Microsoft 365 Copilot Agent Store

* Status: Not ready to claim store readiness.
* Gaps: agent packaging, tenant compatibility, enterprise governance, and any required Microsoft approval path remain unresolved.
* Recommendation: Treat as a later-stage assessment, not a current MVP milestone.

## Outcome

The MVP should produce a safe, grounded review workflow that improves case preparation and consistency without replacing human accountability.
