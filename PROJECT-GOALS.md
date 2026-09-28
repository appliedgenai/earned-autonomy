# Project goals and current state

Updated 28 September 2026.

## Goal

Explain when an enterprise should use an agent, which specific business actions it may perform, and how verified outcomes justify retaining, expanding or restricting that authority. Show the business benefit, evaluation design, observability and accountable operating decisions needed for regulated workflows.

The brief must make this argument understandable in approximately six minutes; detailed architecture and examples belong in the full paper. Reading time is a design target, not a guarantee.

## Current scope

- Work on **Earned Autonomy first**, separately from the [AI-DLC architecture](https://github.com/appliedgenai/intent-to-production).
- Keep people, process and technology connected to specific decisions and failure behavior.
- Include LLM-as-a-judge and evaluate the role of **Jev from TypeSafe**, without treating either as a final compliance or authorization authority.
- Explain evaluation feedback, possible model improvement/training, changes in autonomy, and meaningful observability measures.

## Current publication

The last paper revision was published at `fb580b3`. It clarified action authority and approval/recovery semantics. A later conceptual review found additional shortcomings in the existing diagrams. The checklist below concerns that next revision; it is not completed by the earlier commit.

## Findings to resolve

- [ ] **Justify agent use.** A plain address update or calendar operation can use a deterministic workflow. Establish a variable investigation problem and compare with a simpler baseline.
- [ ] **Choose one running example.** Proposed: investigation of an advisor service-case exception, followed by controlled execution of an exact approved action where needed. This is a recommendation awaiting incorporation, not a claimed deployment.
- [ ] **Replace the autonomy ladder.** Show the same action's modes and limits in an action-authority matrix. Remove distracting portfolio-advice examples and blanket demotion language.
- [ ] **Repair the runtime diagram.** Human approval must return through fresh checks, then an explicit executor, destination enforcement and authoritative outcome verification/reconciliation.
- [ ] **Make evaluation operational.** Include code checks, semantic judging, domain adjudication, calibrated uncertainty and review of accepted cases.
- [ ] **Add Jev accurately.** Candidate for narrow typed judgments; compare domain performance and operating cost. Preserve an insufficient-evidence/escalation path and version the rubric/model.
- [ ] **Draw two feedback branches.** One changes the system/model after evaluation; the other changes the action's permission grant through an accountable authority decision.
- [ ] **Define autonomy transitions.** Expansion, restriction, suspension and restoration need action/cohort/version scope, evidence criteria, policy ceilings and recovery rules.
- [ ] **Define the scorecard.** Include unauthorized effects, incorrect completion, missed escalation, unknown outcomes, evidence completeness, judge unsafe passes, autonomous coverage and human burden.
- [ ] **Align the evidence example.** Use the same case/action throughout. Show exact approval/authority, actual effect, verified or unknown outcome and owner. Broad meeting-preparation intent does not authorize a calendar invitation.
- [ ] **Review, render, verify and publish the resulting revision.** Update both brief and full paper coherently. Record actual commit and verification evidence after publication.

## Decisions and constraints to preserve

- Business benefit must justify agent complexity. Compliance alone does not require an agent.
- Reasoning flexibility and execution authority are separate.
- An LLM judge or Jev supplies probabilistic assessment; deterministic checks and accountable policies decide permitted execution.
- Training is optional. Fix source/context/tool/workflow defects before assuming model weights are the problem. Do not train blindly on raw traces or unadjudicated judge outputs.
- Improved behavior does not automatically increase permissions. Required human approvals remain required.
- Metrics need explicit denominators and cohort/version context. Low override rates and small zero-failure pilots are insufficient evidence for broad promotion.
- No invented production experience, quantified outcomes or validated vendor integrations.

## Completion criteria

A reader can explain why an agent is useful, name its bounded actions, follow execution and evaluation, identify the owner of an exception, and understand exactly how authority can change. The diagrams must express the same rules as the prose. Review findings, source checks, artifact checks and publication verification must support the completion claim.

## Most recent work

- Inspected all three current diagrams in detail.
- Researched TypeSafe's official Jev documentation, limitations and confidence semantics, MLflow's narrow judge comparison, agent evaluation guidance and FINRA's agent discussion.
- Obtained separate source and architecture critiques and documented proposed corrections.
- Added persistent project instructions and this goals file.
- The diagram/evaluation revision remains pending; saving these instructions does not complete it.
