<!-- markdownlint-disable-file -->

# Artifact analysis

## Evidence used

* .copilot-tracking/research/2026-09-18/compliance-check-system-session-context.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-research.md
* .copilot-tracking/research/workshop-input/leancanvas.md
* .copilot-tracking/prd-sessions/compliance-check-system-prd.md
* .copilot-tracking/dt/compliance-check-system-experience-outline.md

## Requirements summary

* Human-in-the-loop compliance review support is the primary product concept.
* The assistant should prepare cases, compare evidence to policy, and flag gaps or exceptions.
* Final decisions remain with human reviewers.
* Source-grounded outputs, confidence, and escalation are required.
* Permission-aware retrieval and sensitive-data minimization are required.
* The MVP should be limited to one job with a concrete workflow, not a broad autonomous review capability.

## Candidate hierarchy

### Epic 1: Grounded case review MVP

* Feature: Case intake and evidence retrieval
* Feature: Policy comparison and issue detection
* Feature: Human review and escalation
* Feature: Action gating and audit trail

### Epic 2: Governance and pilot readiness

* Feature: Security, privacy, and review controls
* Feature: Publication readiness assessment

## Key gaps to resolve before execution

* The exact FSI workflow and case types are still not fully confirmed.
* The real policy library, evidence systems, and approval rules are still assumed.
* Publication claims remain provisional until Microsoft guidance, Partner Center status, and tenant feasibility are verified.

## Recommended backlog stance

Keep the first backlog narrow and execution-ready. The MVP should focus on one review job, one evidence flow, and one human approval gate.
