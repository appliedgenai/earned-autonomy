# Earned Autonomy

### Use agents to investigate. Grant them bounded permission to act. Keep that permission revocable.

**A six-minute visual brief · Mohit Mittal · September 2026**

**An enterprise agent earns useful autonomy when it resolves more work under explicit controls, with less total human effort.** The operating model has two feedback loops: improve the system using evaluated outcomes, and separately decide whether a specific action should gain, retain or lose permission. A better model does not grant itself more authority.

[Read the full paper](02-agents-you-can-audit.md) · [Reference design](reference-design.md) · [Sources](SOURCES.md)

## 1 · Start with work that actually needs investigation

“Why is this advisor service case still open, and what can we safely do next?”

The answer may depend on a request, case history, account status, submitted documents and applicable servicing rules. One case needs missing evidence; another contains conflicting records; another needs a specialist. An agent can select the next permitted source as it learns, assemble an evidence-backed resolution package and escalate unresolved ambiguity.

That adaptive investigation is the reason to consider an agent. A fixed address update can use an ordinary workflow. Compare the agent against that simpler baseline; compliance requirements alone do not justify agent complexity.

Use one illustrative case, **SC-42**, throughout this design. The investigation identifies a possible mailing-address mismatch. It can propose a correction, but the advisor's request to investigate does not authorize changing the account.

## 2 · Assign permission to each action

[![One service case with action-specific authority and a reversible delegation path](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

The same assistant can read permitted sources, prepare a resolution package, create a linked internal specialist follow-up case and propose an account update. Each action has its own scope, approval conditions and policy ceiling. Creating that follow-up starts approval-required. Selected follow-up types may later qualify for bounded execution; SC-42's account update retains human approval.

Bind approval to the exact proposal and relevant record version. Recheck rights, policy, expiry and current state immediately before dispatch. A controlled executor and destination service enforce the change. Human approval returns through those checks; it never bypasses them.

A timeout means **outcome unknown** until reconciliation establishes what happened. Display action completion only after authoritative state confirms it; otherwise expose an owned exception. A verified update completes that action; closing SC-42 requires its separate resolution conditions and authorization.

## 3 · Evaluate judgment and consequences

Use three kinds of evidence: code checks for exact conditions and actual state; semantic judges for source support and completeness; domain reviewers for difficult cases, calibration and sampled accepted work.

**LLM-as-a-judge and TypeSafe's Jev belong in the semantic evaluation role.** Jev offers typed judgments and probabilities; it does not generate explanations. Evaluate it against domain-labeled cases before choosing where it fits. A typed verdict is still fallible. [TypeSafe documentation](https://docs.typesafe.ai/concepts/system-one)

For SC-42, a judge can assess whether the proposed resolution is supported by the supplied evidence. Code checks the exact account, rights, approved fields, dates and destination outcome. A high judge score cannot authorize an account write or override missing mandatory evidence.

Run failure and regression cases before deployment. In production, enforce required controls on every applicable action, combine outcome monitoring with risk-based semantic review, and independently sample accepted cases. Monitoring only escalations misses confidently wrong answers.

## 4 · Close the loop without giving the system permission to promote itself

[![Operational evidence feeds evaluation and separate system-improvement and authority-review loops](diagrams/p2-evaluation-loop.png)](diagrams/p2-evaluation-loop.png)

**Improve behavior:** investigate failures; correct sources, retrieval, instructions or tools; consider model changes or offline training for persistent behavior gaps. Evaluate the versioned candidate on held-out cases before rollout. Raw traces and unreviewed judge verdicts are not training truth.

**Adjust authority:** review evidence for the same action and cohort. Expand deliberately within policy ceilings. Restrict sustained quality failures through predefined thresholds. Defined severe control events can suspend affected new actions immediately, with a separate procedure for work already in flight. Restoration requires evidence, an owner and a recorded decision.

Track the signals that support those decisions:

| Signal | What it tells the owner |
|---|---|
| Unauthorized effects and incorrect completion | Whether the system acted outside its grant or claimed a result it did not achieve. |
| Missed escalation and judge unsafe passes | Whether apparently acceptable cases conceal consequential errors. |
| Unknown outcomes, age and evidence gaps | Whether operations can reconstruct and resolve the work. |
| Autonomous coverage alongside human effort | Whether useful work is completed with less review, exception handling and rework. |

The full paper defines denominators and sampling. A low override rate can reflect weak review; a small zero-failure pilot cannot establish rare-event safety. Agree thresholds before assessing results.

**The executive decision:** fund one bounded investigation-and-resolution workflow, its execution controls and evaluation capability. Expand only when verified outcomes and total effort justify it. Maximum autonomy is not the objective; dependable resolution is.

---

**Author:** Mohit Mittal, Chief Architect, with 22+ years in enterprise architecture and distributed systems, including production LLM/RAG work at Chegg and governed agent infrastructure and MCP servers in healthcare. SC-42 is a synthetic design, not an employer deployment or measured result.

[Full paper](02-agents-you-can-audit.md) · [Sources and scope](SOURCES.md) · [Separate AI-DLC architecture](https://github.com/appliedgenai/intent-to-production) · [CC BY 4.0](LICENSE.md)
