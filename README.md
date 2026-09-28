# Earned Autonomy

**A model release changes behavior. An approved grant changes what may execute.**

When nobody can defend write access—or confirm it has been revoked—an agent stays at drafting. Give each action a versioned permission, enforce it through a shared harness, and test how operators take it back.

**Fund a 90-day evaluation of one servicing case type.** The payoff to test is correctly resolved work with less advisor and operations effort. Day 90 produces an evidence-backed decision: expand, narrow or stop.

## What the 90 days should deliver

The operations sponsor owns the outcome; the platform lead owns execution and recovery; domain reviewers and risk partners agree acceptance criteria.

| Window | Deliverable |
|---|---|
| Days 1–30 | Baseline effort/cost, eligible cases, action owners and destination guarantees. |
| Days 31–60 | Bounded implementation; evaluation, approval, restriction and reconciliation drills. |
| Days 61–90 | Supervised cohort when entry conditions pass; economics, control evidence, gaps and expansion recommendation. |

**Resources:** [ILLUSTRATIVE — replace with real data: staff allocation and 90-day budget cap]. Advancement requires evidence, not a date.

## Is the work worth delegating?

Choose sufficient volume, variable investigation paths, measurable resolution and bounded effects with workable recovery. Prefer a fixed workflow where it solves the problem more cheaply.

**Monthly net capacity value** = eligible cases × handling minutes × expected gross reduction ÷ 60 × loaded hourly cost − incremental review, exception, runtime/platform and governance costs.

[ILLUSTRATIVE — replace with real data: all formula inputs; costs in dollars/month; implementation cost reported separately]. Count each cost once. Capacity value becomes cash savings only through a spending decision.

Price the whole investigation/resolution workflow. Measure the extra benefit of removing follow-up approval separately. Don't fund this if review and recovery consume the benefit. [Sizing worksheet](reference-design.md#value-sizing)

## Follow one case through the controls

In fictional case **SC-42**, a document and account record disagree on the mailing address. The agent investigates permitted sources; the discrepancy alone proves no intent to change it. Unauthorized address changes can signal account takeover, so address updates retain verification and approval here. [FINRA](https://www.finra.org/investors/insights/customer-account-takeovers)

<a id="permission-modes"></a>

### 1 · Choose authority per action

**A0** shadows; **A1** drafts; **A2** executes an approved proposal; **A3** executes within delegated limits. Each applies to an action and case population. Address updates stay A2; internal specialist follow-ups are the candidate for A3.

[![Permission modes and evidence needed to change them](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

<a id="shared-harness"></a>

### 2 · Enforce the permission

The **shared harness** checks access, limits and required evidence, dispatches actions and records outcomes. A **grant** sets standing permission; an **approval** authorizes one exact proposal. Each agent has an owner and supported configuration.

[![Agents connect to the shared harness and operating controls](diagrams/p2-agent-harness.png)](diagrams/p2-agent-harness.png)

<a id="execution"></a>

### 3 · Check again at dispatch

Verification establishes the client's intended address; a reviewer approves the exact change. Recheck the payload, current rights, grant and preconditions at dispatch. AI evaluators assess evidence; they cannot grant authority. The address operation **OP-42** times out. Reconcile its outcome before deciding whether to retry.

[![Proposal, fresh checks, execution and verification](diagrams/p2-model-proposes-policy-decides.png)](diagrams/p2-model-proposes-policy-decides.png)

<a id="operator-console"></a>

### 4 · Confirm that a restriction took effect

Operations requests a hold on new address updates for SC-42. The console shows acknowledgment pending and OP-42 unknown. The case-specific hold cannot undo an in-flight update. Follow-up promotion is deferred because necessity and routing evidence are incomplete.

[![Console distinguishes a requested case hold from confirmed enforcement](diagrams/p2-agentic-console.png)](diagrams/p2-agentic-console.png)

<a id="evidence-record"></a>

### 5 · Reconstruct the outcome

Operations looks up OP-42 and compares authoritative state with the approved payload. The update is confirmed without repeating it. Completing that action leaves separate case-resolution checks and closure authorization.

[![Decision record links authorization to the verified outcome](diagrams/p2-decision-record.png)](diagrams/p2-decision-record.png)

<a id="evaluation-loop"></a>

### 6 · Review behavior and authority separately

Engineers improve sources, tools, prompts or models. Action owners review grants using correct outcomes, errors, unresolved operations, review effort and restriction drills. Severe triggers restrict new actions; restoration requires repair evidence and authorization. Mandatory approvals remain binding.

[![Separate behavior-improvement and authority-review loops](diagrams/p2-evaluation-loop.png)](diagrams/p2-evaluation-loop.png)

## Why can't I buy this?

Reuse identity, scoped tools, approval workflows and tracing. Buy their implementation where it meets the contract. Test the connections: **versioned per-action grants separate from model versions, a promotion evidence packet, restriction acknowledgment and owned reconciliation**. The firm owns domain criteria and acceptance even when a supplier implements the controls.

## Fit the decisions into existing governance

Owners confirm this proposed mapping:

| Decision | Existing process and evidence |
|---|---|
| Grant change | Change management; supervisory procedures; versioned authorization. |
| Promotion review | Business owner; model-risk practice where applicable; retained evaluation packet. |
| Suspension/restoration | Incident procedures; enforcement acknowledgment; recovery and audit records. |

> **What this is and isn't:** A reference architecture with synthetic cases and unexecuted design artifacts. The modes are optional design vocabulary; shadow results cannot establish write/recovery safety. Owners set thresholds. No deployed results, vendor endorsement or compliance certification is asserted.

**Earned autonomy means permission supported by evidence—and a working mechanism to take it back.**

[Full paper](earned-autonomy-operating-model.md) · [Reference design](reference-design.md) · [Sources](SOURCES.md)

**Mohit Mittal · Chief Architect · 22+ years.** Experience includes production LLM/RAG at Chegg and governed agent infrastructure and MCP servers in healthcare.

[AI-native delivery architecture](https://github.com/appliedgenai/intent-to-production) · [CC BY 4.0](LICENSE.md)
