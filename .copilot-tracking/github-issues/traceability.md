<!-- markdownlint-disable-file -->

# GitHub issue traceability record

## Target repository

* GitHub repository: https://github.com/asiapartners/hve-innovation
* Repository owner/name: asiapartners/hve-innovation
* Confirmed from git remote and GitHub repository page.

## Status

Issue creation is currently blocked by authentication and tooling availability.

* GitHub CLI (`gh`) is not installed in this environment.
* The GitHub web session is not authenticated; the repository issue page shows a "Sign in" requirement.
* Per the backlog guardrails and GitHub execution conventions, no mutation was attempted without a verified platform preflight and authenticated target.

## Planned MVP issue set

### Parent issue (planned)

* Title: MVP: Grounded compliance review assistant
* Purpose: establish the first review workflow for source-grounded compliance case review with human escalation and approval gates.
* Status: not created; pending authenticated GitHub session

### Child issues (planned)

1. P0: Intake and permission-aware evidence retrieval
2. P0: Policy matching and exception detection
3. P0: Human escalation and approval gate
4. P1: Traceability and reviewer override history
5. P1: Pilot governance, privacy, and security review
6. P2: Publication readiness assessment (provisional)

## Links

No live GitHub issue URLs are available yet because the session cannot create the issues while signed out and without the required GitHub tooling.

## Traceability note

This file records the approved MVP requirements from:

* .copilot-tracking/prd-sessions/compliance-check-system-prd.md
* .copilot-tracking/dt/compliance-check-system-experience-outline.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-session-context.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-research.md
* .copilot-tracking/github-issues/prds/compliance-check-system/issues-plan.md

Once the GitHub session is authenticated, the next step is to create the parent issue first, then add the child issues under it using the planned hierarchy above.
