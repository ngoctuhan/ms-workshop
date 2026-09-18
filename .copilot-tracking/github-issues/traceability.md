<!-- markdownlint-disable-file -->

# GitHub issue traceability record

## Target repository

* GitHub repository: https://github.com/ngoctuhan/ms-workshop
* Repository owner/name: ngoc tuhan / ms-workshop
* Confirmed from the workspace git remote: `git remote -v`.

## Status

Issue creation is complete. The parent issue and all planned child issues have been created in the target repository, with priority labels applied. The parent issue body lists the child issues by title; cross-linking them by issue number (`#2`-`#7`) is still an open follow-up.

## Created MVP issue set

### Parent issue

* Title: MVP: Grounded compliance review assistant
* Purpose: establish the first review workflow for source-grounded compliance case review with human escalation and approval gates.
* Priority: P0
* Status: created in GitHub
* Link: https://github.com/ngoctuhan/ms-workshop/issues/1

### Child issues

| Priority | Title | Summary | Link |
|---|---|---|---|
| P0 | Intake and permission-aware evidence retrieval | Restrict retrieval to the minimum authorized evidence and protect sensitive data before model processing. | https://github.com/ngoctuhan/ms-workshop/issues/2 |
| P0 | Policy matching and exception detection | Compare case evidence to approved policy requirements and surface gaps, exceptions, and inconsistencies. | https://github.com/ngoctuhan/ms-workshop/issues/3 |
| P0 | Human escalation and approval gate | Require human signoff and escalate low-confidence, contradictory, or high-risk cases to review. | https://github.com/ngoctuhan/ms-workshop/issues/4 |
| P1 | Traceability and reviewer override history | Preserve policy references, evidence history, and override decisions for auditability. | https://github.com/ngoctuhan/ms-workshop/issues/5 |
| P1 | Pilot governance, privacy, and security review | Validate retention, access control, redaction, and governance for pilot operations. | https://github.com/ngoctuhan/ms-workshop/issues/6 |
| P2 | Publication readiness assessment (provisional) | Evaluate Microsoft guidance and tenant implications without claiming publication status yet. | https://github.com/ngoctuhan/ms-workshop/issues/7 |

## Traceability note

This file records the approved MVP requirements from:

* .copilot-tracking/prd-sessions/compliance-check-system-prd.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-session-context.md
* .copilot-tracking/research/2026-09-18/compliance-check-system-research.md
* .copilot-tracking/research/workshop-input/leancanvas.md
* .copilot-tracking/github-issues/prds/compliance-check-system/issues-plan.md

The GitHub issue set has been created in the verified repository and is ready for backlog execution.
