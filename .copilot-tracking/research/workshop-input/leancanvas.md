<!-- markdownlint-disable-file -->

# FSI Relationship Manager Assistant — Lean Canvas

## Evidence basis

- Session: Compliance Check System
- Evidence root: ./copilot-tracking/research/workshop-input
- Research source: .copilot-tracking/research/2026-09-18/compliance-check-system-research.md
- Status: synthetic workshop evidence only; not a production policy specification.

## 1) Problem

Relationship managers and review teams in financial services institutions need to assess client, account, or relationship submissions against policy, operating procedures, and approval conditions. The review process is likely high-volume, evidence-heavy, and sensitive to missed exceptions or inconsistent interpretation.

Facts:
- Review is policy-sensitive and requires human accountability.
- Manual review can be slow, inconsistent, and vulnerable to missed exceptions when evidence is fragmented.
- The strongest value is faster case preparation and more consistent review, not full automation.

Assumptions:
- The assistant would support case triage and comparison against internal policy language and approvals.
- Many review tasks involve documents, case notes, and evidence stored across multiple systems.

Unknowns to follow up:
- [Unknown — follow-up] Which relationship-management workflows are in scope: onboarding, annual review, exception handling, or client servicing?
- [Unknown — follow-up] What evidence sources are typically fragmented across systems in the target FSI workflow?

## 2) Target customer segments

Primary users likely include internal teams that handle client relationships and compliance review.

Facts:
- Affected users include compliance analysts, policy owners, operations managers, frontline reviewers, and governance teams.
- The workflow is likely used by staff who review submissions and decide whether they meet policy requirements.

Assumptions:
- Relationship managers are a key user group for pre-review summarization and exception surfacing.
- Compliance and operations teams are the primary decision owners for final approval or escalation.

Unknowns to follow up:
- [Unknown — follow-up] Which roles in the FSI are the primary buyers and day-to-day users?
- [Unknown — follow-up] How many cases per month do these teams process, and how much review effort is consumed by repetitive triage?

## 3) Value proposition

Provide an assistant that helps reviewers prepare and assess cases more quickly by summarizing evidence, comparing it to approved policy and control requirements, and highlighting missing or inconsistent items.

Facts:
- A compliance assistant can provide structured triage and summarize supporting evidence.
- The assistant should flag missing evidence, missing signatures, outdated approvals, and policy exceptions.
- Human reviewers remain accountable for final decisions.

Assumptions:
- This reduces manual search effort and supports more consistent review quality.
- A grounded summary is more useful than a free-form answer when policy risk is involved.

Unknowns to follow up:
- [Unknown — follow-up] What review steps consume the most time today for relationship managers and compliance staff?
- [Unknown — follow-up] Which outputs would be considered materially useful by reviewers (summary, risk indicators, gap list, evidence map, next-step recommendation)?

## 4) Core offering

A human-in-the-loop assistant for relationship review and compliance validation.

Core functions:
- Collect and summarize relevant case evidence.
- Match evidence against policy language and approval requirements.
- Highlight missing items, inconsistencies, potential exceptions, and overdue actions.
- Route low-confidence, contradictory, or higher-risk cases to human review.
- Maintain traceability to source documents and decision history.

Facts:
- The scenario supports source-grounded outputs tied to approved policy references.
- Cases with low confidence, contradictory evidence, or legal ambiguity should escalate.
- Auditability and traceability are required.

Assumptions:
- The assistant sits inside an existing case-management or CRM workflow.
- Reviewers need not rely on the assistant for final adjudication, only for preparation and triage.

Unknowns to follow up:
- [Unknown — follow-up] Which policies and controls are in-scope for the assistant: compliance, KYC, AML, account opening, client suitability, or document approval?
- [Unknown — follow-up] What data is available in the target workflow, and how is it classified or protected?

## 5) Channels

The product would likely be delivered through internal operational and compliance workflows rather than standalone consumer channels.

Facts:
- The scenario assumes integration with existing case management or evidence repositories.
- The workflow likely runs within an internal system where human review remains central.

Assumptions:
- Policy library and document repositories are the primary evidence channels.
- Approval and escalation paths are managed through operational workflows, not direct user chat.

Unknowns to follow up:
- [Unknown — follow-up] What internal tools are used today for case intake, approval, and audit trail?
- [Unknown — follow-up] Is the assistant embedded in CRM, case management, workflow orchestration, or a separate review portal?

## 6) Revenue model

This is likely an internal productivity and risk-reduction investment rather than a direct customer-facing subscription model.

Facts:
- The evidence supports operational efficiency and review consistency as the primary value.
- No pricing or revenue structure was provided in the synthetic workshop evidence.

Assumptions:
- The business case may be framed as reduced manual review effort, fewer exceptions, and more consistent throughput.
- Costs may be absorbed as part of digital transformation or compliance modernization work.

Unknowns to follow up:
- [Unknown — follow-up] Is the solution funded as a platform feature, a compliance modernization investment, or a business-unit capability?
- [Unknown — follow-up] How will value be measured in financial terms: hours saved, lower exception cost, faster processing, or reduced compliance risk?

## 7) Costs

Likely costs are dominated by governance, integration, and operational controls rather than product marketing.

Facts:
- Sensitive data and regulated content require minimization, redaction, and operational controls.
- Audit-friendly logging and policy grounding add implementation cost.
- Final decisions require human review, so operational staffing is still required.

Assumptions:
- Integration with policy repositories and case systems will require engineering effort.
- Monitoring, review calibration, and exception handling will require ongoing operational ownership.

Unknowns to follow up:
- [Unknown — follow-up] What is the expected environment footprint: cloud-hosted model, enterprise deployment, or existing internal AI platform?
- [Unknown — follow-up] What privacy and retention controls are required for each data class in scope?

## 8) Success metrics

Metrics should focus on operational quality and decision support, not only output volume.

Facts:
- The research calls for traceability, auditability, escalation, and policy correctness.
- The strongest value is consistency and case preparation, not autonomous decision-making.

Assumptions:
- Success can be measured by reduced cycle time, improved completeness of evidence, and fewer late-discovered misses.
- Human reviewers should see more confident, better-structured review support.

Measures to validate:
- Average time to review or triage a case.
- Percentage of cases with complete evidence flagged before final decision.
- Number of exceptions or policy gaps caught earlier.
- Percentage of low-confidence or high-risk cases escalated appropriately.
- Reviewer override rate and appeal rate.

Unknowns to follow up:
- [Unknown — follow-up] What is the baseline performance today for the target workflow?
- [Unknown — follow-up] Which metric is the organization most likely to use as the primary success indicator?

## 9) Unique advantage

The differentiator is not speed alone; it is a source-grounded, human-governed review assistant with explicit escalation and accountability.

Facts:
- The scenario explicitly rejects autonomous compliance authority.
- The assistant should separate recommendation from final decision and show confidence, rationale, and policy references.
- Risky, ambiguous, or contradictory cases should escalate.

Assumptions:
- This approach is easier to govern and more defensible than a fully autonomous decision engine.
- It supports both reviewer productivity and policy traceability.

Unknowns to follow up:
- [Unknown — follow-up] Which existing process would be the first pilot site, and what makes it a good fit for the human-in-the-loop model?
- [Unknown — follow-up] How will the capability be differentiated from generic document summarization or a standard policy search tool?

## Facts vs assumptions

Facts from evidence:
- Compliance review is a policy-sensitive, high-volume workflow.
- Human review remains accountable for final decisions.
- The likely objective is faster, more consistent review support and escalation, not autonomous decision-making.
- Traceability, auditability, and policy grounding are required.

Assumptions to validate:
- The target workflow is relationship or case review in an FSI context.
- The assistant would integrate into an internal case-management or policy workflow.
- The value is measured in lower manual effort, fewer missed exceptions, and improved consistency.

Unknowns flagged for follow-up:
- [Unknown — follow-up] What specific FSI workflow is in scope?
- [Unknown — follow-up] What policy sources and control frameworks apply?
- [Unknown — follow-up] What system integration points and data classifications are involved?
- [Unknown — follow-up] What business or compliance metric is used to justify investment?

## Bottom line

The most evidence-based concept is a human-in-the-loop relationship management assistant that prepares and checks case evidence against policy and approval criteria, flags gaps and exceptions, and escalates uncertain or high-risk items to a human reviewer. It is positioned as a control-oriented support tool, not an autonomous policy authority.
