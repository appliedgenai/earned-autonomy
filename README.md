# Earned Autonomy

### Give agents bounded authority. Expand it when verified outcomes justify it. Keep it revocable.

**A six-minute visual brief · Mohit Mittal · September 2026**

A better model can produce a stronger recommendation while leaving the business with the same approval, exception and recovery work. The next decision is **which action, for which cases, can now be delegated—and whether doing so actually reduces total work.**

**Manage permission as a versioned operating decision, separate from the model release.** Use a shared harness to enforce it and an agentic console to review outcomes and change grants. An agent can improve without receiving more authority, or lose permission for one action while continuing useful work elsewhere.

[Full paper](02-agents-you-can-audit.md) · [Reference design](reference-design.md) · [Sources](SOURCES.md)

## 1 · Start with the work you want to remove

Consider synthetic service case **SC-42**. An advisor asks why it remains open. Operations may need to reconstruct the request, compare submitted evidence with the account record, identify missing verification and find the right specialist.

An agent could assemble that evidence and choose the next permitted source as the facts emerge. The intended benefit is less searching, rekeying and back-and-forth. Compare it with a fixed checklist plus extraction; use an agent only where the variable investigation earns its complexity.

The investigation finds a possible address mismatch. That does not establish the client's intent to change it. The assistant may prepare an account-update proposal and a linked internal specialist follow-up. Those actions have different permission limits.

## 2 · Use four modes, scoped to each action

[![Four autonomy modes apply to a specific action and cohort; suspension is a separate control state](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

The modes are **shadow, propose, execute with approval, and execute within delegated limits**. They describe a particular action and case population, not one maturity score for the whole agent.

SC-42's follow-up creation starts with approval for each execution. Its address update also requires approval and retains that ceiling in this design. Shadow testing has no business effects and cannot prove that live writes or recovery work correctly.

## 3 · Make one promotion decision concrete

Imagine requesting permission for the assistant to create selected specialist follow-ups without reviewing each one. Three questions determine the decision:

| Test | What must be established |
|---|---|
| **Permitted?** | Applicable policy allows delegation for this action, actor, case type and environment. Mandatory approvals remain. |
| **Dependable?** | The follow-up is necessary, linked to the right case, routed correctly and created without duplicate effects. Exceptions and restriction controls work. |
| **Worthwhile?** | Avoided handling and review exceed added audit, exception and rework effort at acceptable quality and total cost. |

A syntactically valid follow-up and a high judge score do not answer all three.

**A hypothetical decision:** retain approval while domain review finds unnecessary or misrouted follow-ups. Improve the system and reevaluate. If the agreed evidence supports delegation, the owner grants bounded execution for named case types and queues, with volume limits, expiry and a validated configuration. The account-update permission does not change.

A defined severe control breach can suspend affected new dispatches. Operations reconciles work already in flight. Restoring permission requires repair evidence and a recorded decision. [Worked promotion and restriction record](02-agents-you-can-audit.md#one-action-through-the-four-modes)

## 4 · Put every agent under a supported harness and an operational console

Use a **shared harness with a versioned configuration for each agent**: identity, permitted context and tools, action grants, execution limits, required evaluations, evidence and exception ownership. Adopt existing platform services where they meet these contracts. Each agent/provider must demonstrate that the controls can actually be enforced.

The **agentic console** makes those responsibilities operable:

[![Illustrative agentic console shows action-level grants, a promotion decision and unconfirmed restriction separately from in-flight outcomes](diagrams/p2-agentic-console.png)](diagrams/p2-agentic-console.png)

Owners review permission changes. Operations sees unknown outcomes, queue pressure and the status of restriction requests. A clicked stop button is not evidence that dispatch has stopped; the console shows runtime confirmation and unresolved in-flight work.

## 5 · Turn continuous evaluation into two decisions

Required policy and pre-action checks run on every applicable action. Continuous evaluation combines outcome monitoring, risk-based semantic checks and independently reviewed samples of accepted cases. Offline regression and held-out evaluation qualify proposed changes.

LLM judges, including **TypeSafe's Jev**, can assess semantic questions such as whether evidence supports a proposed resolution. Their verdicts remain fallible and cannot authorize execution. [Evaluator design and Jev's limits](02-agents-you-can-audit.md#where-jev-fits)

Evaluation feeds two loops:

- **Change behavior:** repair sources, retrieval, prompts or tools; consider a model change or training when justified. Evaluate the candidate before rollout.
- **Change authority:** retain, expand, restrict or suspend a specific grant, within policy, through accountable decisions.

Judge scores describe one part of the evidence. Track verified outcomes, missed escalation, unsafe passes, unknown-operation age, total human effort and time to enforce restrictions by action, cohort and version. A human-approved case is not fully autonomous; it can still deliver substantial value.

**The investment decision:** establish one reusable path for registered agents to propose actions, obtain permission, execute, and produce verifiable outcomes. Prove the benefit on one case class. Then onboard a second action through the same grant, execution and evidence interfaces.

**Success is more correctly resolved work with less total human effort.** A verified address update completes that action; SC-42 closes only after its separate resolution conditions and closure authorization are satisfied.

---

**Author:** Mohit Mittal, Chief Architect, with 22+ years in enterprise architecture and distributed systems, including production LLM/RAG work at Chegg and governed agent infrastructure and MCP servers in healthcare. SC-42, the console and promotion decisions are illustrative designs, not employer deployments or measured results.

[Full paper](02-agents-you-can-audit.md) · [Reference design](reference-design.md) · [Separate AI-DLC architecture](https://github.com/appliedgenai/intent-to-production) · [CC BY 4.0](LICENSE.md)
