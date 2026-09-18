<!-- markdownlint-disable-file -->

# Session Context

Session name: Compliance Check System
Topic: Compliance Check system with LLM
Evidence location: ./copilot-tracking/research/workshop-input
Date: 2026-09-18

## Purpose

This document defines the shared context for a workshop scenario in which a team evaluates a compliance-check workflow supported by a large language model.

## Evidence boundary

This scenario uses workshop evidence stored under ./copilot-tracking/research/workshop-input. The repository should not contain customer-sensitive, regulated, or production-only information unless a trusted environment has approved it.

## Intended use

Use this as the required context source for downstream agent work such as research, BRD/PRD drafting, design, and technical framing.

## Working assumptions

* The system reviews records or submissions against policy, operational, and control requirements.
* The LLM helps summarize evidence, compare submissions against policy language, and identify missing or inconsistent items.
* Human reviewers remain accountable for final decisions and escalation.
* The solution must support traceability, auditability, and escalation for high-risk or low-confidence outputs.

## Production output roots

* Primary research: .copilot-tracking/research/
* Business requirements: .copilot-tracking/brd-sessions/
* Product requirements: .copilot-tracking/prd-sessions/
* Experience and design evidence: .copilot-tracking/dt/

## Human review status

Draft for human review.
