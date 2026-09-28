# Earned Autonomy

### Give agents bounded authority. Expand it when verified outcomes justify it. Keep it revocable.

**Agent autonomy in regulated operations · Mohit Mittal · September 2026**

The business question is **which actions can agents take over while reducing total advisor and operations effort at acceptable quality and cost?**

Build one shared path to **propose, authorize, execute and verify** business actions. Treat permission as a versioned operating decision, separate from a model release. Expand it only when delegation is permitted, dependable and worthwhile.

**Six-minute scan:** follow the six takeaways and captions. All six diagrams are on this page; select any image for full resolution.

[Permissions](#permission-modes) · [Harness](#shared-harness) · [Execution](#execution) · [Console](#operator-console) · [Evidence](#evidence-record) · [Evaluation](#evaluation-loop)

<a id="1--start-with-the-work-you-want-to-remove"></a>

## One service case, two different permissions

In synthetic case **SC-42**, an advisor asks why a request remains open. An agent investigates permitted documents and account records, choosing the next source as facts emerge. Use a fixed workflow where a checklist plus extraction suffices.

An address mismatch does not establish client intent. The assistant can prepare an address-update proposal and, if necessary, a specialist follow-up. Those actions need separate permissions.

<a id="permission-modes"></a>
<a id="2--use-four-modes-scoped-to-each-action"></a>

## 1 · What may this action do?

**Give authority to a defined action and case population.** A0–A3 are this paper's proposed vocabulary, not an industry standard or mandatory progression.

[![Four modes: shadow, propose, approved execution and bounded execution, with evidence requirements and a separate suspension control](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

*Follow-up creation may qualify for A3; the address update retains A2 approval. Shadow evidence cannot prove live-write safety.*

<a id="shared-harness"></a>
<a id="4--put-every-agent-under-a-supported-harness-and-an-operational-console"></a>

## 2 · What makes that permission enforceable?

**Bind every registered agent to a shared harness with versioned controls.** Reuse platform services for identity, tools, grants, execution, evidence and recovery.

[![Registered agents connect to shared controls; operational evidence feeds evaluation and the console, which requests grants and receives enforcement acknowledgments](diagrams/p2-agent-harness.png)](diagrams/p2-agent-harness.png)

*Each agent supplies its scope and evidence. A provider that cannot enforce a required control stays outside the affected execution mode.*

<a id="execution"></a>

## 3 · What happens before a business change?

**A judge assesses evidence; current policy and permissions control dispatch.** An LLM judge or TypeSafe's Jev is a candidate semantic evaluator that must be qualified against domain-labeled cases. Neither grants authority. [Evaluator limits](02-agents-you-can-audit.md#where-jev-fits)

[![Investigation produces an exact proposal; judge evidence and required human approval return through fresh checks before controlled execution and outcome verification](diagrams/p2-model-proposes-policy-decides.png)](diagrams/p2-model-proposes-policy-decides.png)

*Approval binds the exact proposal. Fresh checks precede dispatch. A timeout leaves an unknown outcome with a recovery owner, not permission for a blind retry.*

<a id="operator-console"></a>

## 4 · Can operations see and restrict what is happening?

**Show requested changes, confirmed enforcement and unresolved work separately.** Owners review grants; operations handles exceptions.

[![Agentic console shows deferred follow-up promotion, a restriction awaiting runtime acknowledgment and unknown operation OP-42 assigned to account operations](diagrams/p2-agentic-console.png)](diagrams/p2-agentic-console.png)

*In this synthetic snapshot, follow-up promotion is deferred and address operation OP-42 needs reconciliation. A stop request is not confirmed enforcement or an undo of in-flight work.*

<a id="evidence-record"></a>

## 5 · Can we reconstruct the result?

**Link the exact proposal, authority, execution and verified outcome.** This record continues OP-42 after the console snapshot.

[![SC-42 decision record follows proposal and approval through an uncertain write to later verification and evaluation](diagrams/p2-decision-record.png)](diagrams/p2-decision-record.png)

*Authoritative lookup now confirms the address update without repeating the write. Closing SC-42 still requires its separate resolution conditions and authorization. An approved action is not fully autonomous case resolution.*

<a id="evaluation-loop"></a>
<a id="5--turn-continuous-evaluation-into-two-decisions"></a>
<a id="3--make-one-promotion-decision-concrete"></a>

## 6 · What earns—or removes—the next permission?

**Improve behavior and review authority through separate decisions.** Required checks run on applicable actions; outcome monitoring and reviewed samples assess operation; held-out evaluation qualifies changes.

[![Operational evidence feeds separate system-improvement and authority-review loops, with immediate restriction for defined severe triggers](diagrams/p2-evaluation-loop.png)](diagrams/p2-evaluation-loop.png)

*Engineers repair the system; training is optional. Accountable owners change grants within policy ceilings. Defined severe events trigger restrictions; restoration requires repair evidence and an authorized decision.*

**For the same follow-up action:** retain A2 until necessity, routing, recovery and net-benefit evidence support A3. Any grant names eligible cases, queues, limits, expiry and configuration. Address-update authority stays unchanged.

Observe unauthorized effects, incorrect completion, missed escalation, judge unsafe passes, unknown-outcome age, restriction-enforcement delay and total human effort. Segment by action, case population and version, with explicit denominators, review coverage and observation windows. [Metric definitions](02-agents-you-can-audit.md#observe-what-makes-autonomy-defensible)

## The investment decision

Prove **more correctly resolved work with less total human effort**, including review and recovery, on one case class. Then reuse the interfaces for a second action, qualifying its controls and outcomes independently.

**The future of AI depends on disciplined engineering.**

[Full paper](02-agents-you-can-audit.md) · [Worked reference design](reference-design.md) · [Sources](SOURCES.md)

---

**Author:** Mohit Mittal, Chief Architect, with 22+ years in enterprise architecture and distributed systems, including production LLM/RAG work at Chegg and governed agent infrastructure and MCP servers in healthcare. SC-42, the console and promotion decisions are illustrative designs, not employer deployments or measured results.

[Separate AI-DLC architecture](https://github.com/appliedgenai/intent-to-production) · [CC BY 4.0](LICENSE.md)
