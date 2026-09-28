# Earned Autonomy

**How enterprises decide what AI agents may do—and keep that authority under control.**

An AI agent can investigate a service request, recommend a change or use tools to update a business system. Each activity carries different consequences. Access to read a customer record should not also permit changing it.

**Earned autonomy means granting permission for specific business actions, based on evidence, with a working way to restrict or withdraw it.** One agent can have different permissions: draft a response, update an address after approval, or create an internal follow-up within delegated limits.

The operating model connects three responsibilities: **owners decide permissions; a shared harness (control software) enforces them; people and evaluation tools review outcomes.** That review informs the owner's next permission decision. The aim is useful work with less total human effort while preserving quality and control.

The recorded permission is a **grant**. **A model release changes behavior. An approved grant changes what may execute.**

## Follow one case through the controls

In fictional **SC-42**, an advisor asks why a request remains open. The agent finds conflicting mailing addresses, which do not establish client intent. Unauthorized address changes can signal account takeover, so an update requires verification and approval. [FINRA](https://www.finra.org/investors/insights/customer-account-takeovers)

<a id="permission-modes"></a>

### 1 · Connect decisions, execution and evidence

Set permissions per action and case population. Address updates require approval. The delegation candidate creates specialist follow-up tickets in approved internal queues.

[![Permission decisions, enforcement and outcome review](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

<a id="shared-harness"></a>

### 2 · Enforce the permission

The **shared harness** is the control software between an agent and its business tools. It checks permission, required approval and current conditions before execution, then records outcomes. An **approval** authorizes one exact proposal within the standing grant.

[![Agents connect to the shared harness and operating controls](diagrams/p2-agent-harness.png)](diagrams/p2-agent-harness.png)

<a id="execution"></a>

### 3 · Check again at dispatch

Verification establishes the client's intended address; a reviewer approves the exact change. Before sending it, the shared harness rechecks the payload, rights, grant and preconditions. AI evaluators assess evidence; they cannot grant authority. The address operation **OP-42** times out. Reconcile its outcome before deciding whether to retry.

[![Proposal, fresh checks, execution and verification](diagrams/p2-model-proposes-policy-decides.png)](diagrams/p2-model-proposes-policy-decides.png)

<a id="operator-console"></a>

### 4 · Confirm that a restriction took effect

Operations requests a hold on new SC-42 address updates. Acknowledgment is pending; OP-42 remains unknown. The hold cannot undo an in-flight update. The owner retains A2 for follow-ups: necessity and routing evidence remain incomplete.

[![Console distinguishes a requested case hold from confirmed enforcement](diagrams/p2-agentic-console.png)](diagrams/p2-agentic-console.png)

<a id="evidence-record"></a>

### 5 · Reconstruct the outcome

Operations looks up OP-42 and verifies authoritative state against the approved payload, confirming the update without repeating it. Case closure requires separate checks and authorization.

[![Decision record links authorization to the verified outcome](diagrams/p2-decision-record.png)](diagrams/p2-decision-record.png)

<a id="evaluation-loop"></a>

### 6 · Review behavior and authority separately

Engineers improve sources, tools, prompts or models. Action owners review grants using correct outcomes, errors, unresolved operations, review effort and restriction drills. Severe triggers restrict new actions; restoration requires repair evidence and authorization. Mandatory approvals remain binding.

[![Separate behavior-improvement and authority-review loops](diagrams/p2-evaluation-loop.png)](diagrams/p2-evaluation-loop.png)

## Is the work worth delegating?

Choose frequent cases where investigations take different paths, outcomes are measurable and recovery is workable. Prefer a cheaper fixed workflow when it suffices.

**Monthly net capacity value** = eligible cases × handling minutes × expected gross reduction ÷ 60 × loaded hourly cost − incremental review, exception, runtime/platform and governance costs.

Use monthly volumes and dollar costs; report implementation costs separately. Count costs once. Released capacity becomes cash savings through a spending reduction.

Price the whole workflow and the extra benefit of removing follow-up approval separately. Stop if review and recovery consume the benefit. [Sizing worksheet](reference-design.md#value-sizing)

## Why can't I buy this?

Reuse identity, scoped tools, approval and tracing. Evaluate purchased controls against four contracts: **versioned per-action grants separate from model versions, promotion evidence, restriction acknowledgment and owned reconciliation**. The firm defines acceptable actions and outcomes.

## Fit the decisions into existing governance

Owners confirm this proposed mapping:

| Decision | Existing process and evidence |
|---|---|
| Grant change | Change management; supervisory procedures; versioned authorization. |
| Promotion review | Business owner; model-risk practice where applicable; retained evaluation packet. |
| Suspension/restoration | Incident procedures; enforcement acknowledgment; recovery and audit records. |

## Test one workflow over 90 days

The operations sponsor owns results; the platform lead owns execution and recovery. Domain and risk reviewers set acceptance criteria.

| Window | Deliverable |
|---|---|
| Days 1–30 | Select cases; baseline effort/cost; agree permissions and recovery responsibilities. |
| Days 31–60 | Implement controls; test approvals, restrictions and recovery from uncertain outcomes. |
| Days 61–90 | Supervised use when entry criteria pass. Review costs, outcomes and controls; decide: expand, narrow or stop. |

> **What this is and isn't:** A reference architecture with synthetic cases and unexecuted design artifacts. The modes are optional design vocabulary; shadow results cannot establish write/recovery safety. Owners set thresholds. No deployed results, vendor endorsement or compliance certification is asserted.

**Earned autonomy means permission supported by evidence—and a working mechanism to take it back.**

[Full paper](earned-autonomy-operating-model.md) · [Reference design](reference-design.md) · [Sources](SOURCES.md)

**Mohit Mittal · Chief Architect · 22+ years.** Experience includes production LLM/RAG at Chegg and governed agent infrastructure and MCP servers in healthcare.

[AI-native delivery architecture](https://github.com/appliedgenai/intent-to-production) · [CC BY 4.0](LICENSE.md)
