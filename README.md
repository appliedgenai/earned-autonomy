# Earned Autonomy

### How to give enterprise agents permission to act in regulated workflows

**A six-minute visual brief · Mohit Mittal · September 2026**

**An enterprise should grant an agent bounded authority over specific business actions, with enforceable limits, verified outcomes and an accountable owner.** Evidence can justify expanding that authority within the firm's permitted boundaries; it cannot remove a legal or business requirement for human approval.

That is the message of this paper. Its subject is **agent autonomy in regulated operations**: moving from useful answers to dependable action. The financial-services examples are illustrative designs.

[Read the full paper](02-agents-you-can-audit.md) · [Inspect the reference design](reference-design.md) · [Research sources](SOURCES.md)

## 1 · Separate freedom to reason from permission to act

An assistant may investigate a problem through several steps, compare sources and prepare a proposal. That reasoning flexibility does not give it permission to change an account or send a client communication.

| Decision | Who or what controls it? |
|---|---|
| How should the agent investigate and propose? | The model and harness, inside a bounded task and tool scope. |
| May this exact business action execute now? | Current entitlements, business policy, approval conditions and destination controls. |

[![Different actions within one assistant have different autonomy ceilings](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

*The ladder is illustrative. Each action has a policy ceiling. Better model performance does not raise that ceiling automatically.*

A meeting summary, a draft follow-up and an account update belong to different permission classes—even when one assistant performs all three. Assess authority **per action, population and environment**. Start with drafts or supervised execution where appropriate, and name the owner who can expand, restrict or stop the action.

This matters to an advisor platform because less effort preparing work has limited value if completion creates more work for operations. [FINRA's 2026 GenAI discussion](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai) addresses authority, supervision and auditability concerns. The design below is an engineering response, not a regulator-prescribed architecture.

## 2 · Put permission at the point of execution

Consider a mailing-address correction. The advisor approves the proposed change. Before execution, someone updates the same record. The submitted write later times out.

Two questions now matter: **is the approval still valid, and did the action happen?** A fluent model response answers neither.

[![The agent proposes; policy and execution services control the action; assurance records the outcome](diagrams/p2-model-proposes-policy-decides.png)](diagrams/p2-model-proposes-policy-decides.png)

The action contract names the actor, target, permitted fields, evidence, approval requirements, expected record version, completion condition and recovery owner. Approval binds to that exact proposal. Execution rechecks rights, policy and relevant record state. Material changes require fresh review.

Use durable operation identity, conditional writes and destination-supported duplicate prevention. A timeout produces an **unknown outcome** until reconciliation resolves it. A kill switch stops new actions and has a separate runbook for work already in flight. Human approval and MCP connectivity do not replace these controls.

The user sees “completed” only after authoritative state confirms completion. Otherwise, the system shows a pending or failed result with a named resolution path.

## 3 · Make agent observability explain business consequences

A model trace can show tool calls, latency and tokens. The business needs to know **who authorized what, what changed and whether the request was resolved**.

Link the request and action IDs to the proposal, source versions, policy decision, approval, execution receipt and verified outcome. Record concise decision factors; hidden model reasoning is unnecessary. Apply access and retention rules to sensitive evidence.

Monitor stale approvals, denied actions, repeated attempts, uncertain writes, overdue exceptions, reviewer corrections and total workflow cost. A successful tool response is not always a completed business process.

Observability has an operational purpose: detect a problem, restrict the affected action, give an owner enough evidence to recover, and add a regression case before restoring authority.

## 4 · Earn expansion with evidence and recovered capacity

Evaluate wrong-account selection, revoked rights, stale data, injected document instructions, duplicate requests, policy outages and partial completion. Test disruptive cases outside live customer workflows. Review results by action and risk cohort; zero failures in a small pilot does not establish rare-event safety.

Expansion requires an accountable business owner, applicable risk review, defined observation criteria and a permitted policy ceiling. Restrictions need explicit triggers and a recovery process. Model confidence alone is never the promotion rule.

Measure the result from request arrival through resolution:

**Recovered human capacity = baseline effort − handling, review, exception and rework effort after automation.**

Report that beside verified completion, unresolved outcomes, exception age, quality and total cost per completed workflow. Include unsuccessful attempts and operational support. Faster drafting that produces more reconciliation has not delivered the intended benefit.

The practical starting point is one bounded action with clear completion semantics and manageable recovery. Prove that it closes work under control; then reuse its identity, policy, execution and evidence interfaces for another action.

---

**About the author:** Mohit Mittal is a Chief Architect with 22+ years in enterprise architecture and distributed systems. His experience includes governed agent infrastructure and MCP servers in healthcare, and production LLM/RAG systems at Chegg. These financial-services examples are independent proposals, not claimed deployments.

[Full paper](02-agents-you-can-audit.md) · [Failure cases and reference design](reference-design.md) · [Separate six-layer AI-DLC architecture](https://github.com/appliedgenai/intent-to-production) · [Sources](SOURCES.md) · [CC BY 4.0](LICENSE.md)
