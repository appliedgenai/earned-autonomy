# Earned Autonomy: an operating model for agents that act

**A model release changes behavior. An approved grant changes what may execute.**

*Mohit Mittal · September 2026*

When a team cannot defend write access or demonstrate revocation, its agent remains a drafting tool. Give each business action a versioned grant, enforce it through a shared harness, and make operations responsible for unresolved effects. Judge success by correctly resolved work, total human effort and operating cost.

Start with a bounded 90-day evaluation of one case type. The decision packet should show whether to expand, narrow or stop, which controls worked, what remains unresolved and who will operate the service. [Scope, resources and value sizing](reference-design.md#value-sizing)

> **What this is and isn't:** An independent reference architecture. Cases, identifiers, console states and grant-review outcomes are synthetic; design artifacts are unexecuted. A0–A3 are optional design vocabulary. Owners choose numerical acceptance limits before evaluation; shadow results cannot establish write or recovery safety. Sources provide context, not certification of the design. Product examples are candidates to evaluate; no employer deployment, measured benefit or customer fine-tuning capability is asserted.

[Six-minute visual brief](README.md) · [Reference design](reference-design.md)

## First establish why an agent belongs

An advisor asks: **“Why is service case SC-42 still open, and what can we safely do next?”** The relevant evidence is spread across a request, servicing history, account status, documents and current rules. The next useful step depends on what the investigation discovers. A missing document, contradictory record and ambiguous policy call for different paths.

Use an agent for bounded investigation that selects among permitted sources and tools, identifies gaps, and proposes a resolution. The output is a package containing facts, source references, unresolved questions, proposed actions and the owner of any exception. A fixed checklist plus targeted extraction may still be sufficient; compare quality, elapsed time, human effort and cost before choosing an agent. [Workflow/agent distinction](https://www.anthropic.com/engineering/building-effective-agents)

In SC-42, investigation discovers a mailing-address mismatch. The domain owner must verify the client’s intent before any update. Unauthorized address changes can signal account takeover; address updates therefore retain verification and approval in this design. Existing identity, fraud and servicing controls apply. [FINRA account-takeover guidance](https://www.finra.org/investors/insights/customer-account-takeovers)

Price the whole investigation and resolution workflow. Internal follow-up creation is the first limited delegation to evaluate; it cannot justify the platform on ticket volume alone. Compare the additional A2-to-A3 benefit with the review removed and the audit, exception and queue work it adds. Keep the action approval-gated when that incremental benefit is absent.

[AUTHOR: Add one anonymized example of a real delegation decision you owned: the workflow, the permission withheld or granted, your design choice and the observed result. Include only facts you can publish.]

## Authority is a contract for an action

[![Four action-scoped autonomy modes, with distinct promotion evidence and a separate suspension control](diagrams/p2-autonomy-per-action.png)](diagrams/p2-autonomy-per-action.png)

Treat an authority grant as a versioned record: **action, actor/delegation, scope, eligible cohort, environment, allowed mode, mandatory approvals, limits, expiry, validated system/configuration versions and accountable owner**. The registered capability describes what the agent can attempt; the grant describes what it may perform. Current policy and destination authorization can further restrict it.

For SC-42, permitted source access and draft preparation have bounded scopes. `create_internal_case` creates a linked internal specialist follow-up for SC-42; it starts approval-required. A later grant might allow selected follow-up types under explicit limits, or restrict the action to draft-only. The mailing-address update retains human approval in this design. Different actions do not inherit one another's permissions.

Expansion is multidimensional. A grant may cover more case types, a larger volume, a different environment or fewer discretionary reviews. Evaluate each change explicitly. Removing a discretionary review does not remove an approval mandated by applicable policy. “Read-only” still requires access controls and data-handling limits.

The user interface should state which action will happen, under whose authority, and which parts remain proposals. A broad instruction to investigate a case is not an instruction to send a client message, close an unresolved case or modify an account.

## One action through the four modes

These modes describe **an action for a defined cohort under a particular grant**. A console may summarize an agent's activity, but one global agent level would conceal mixed permissions.

| Mode | What the system may do | Evidence needed before entering |
|---|---|---|
| **A0 · Shadow** | Investigate authorized data and record simulated proposals; no business writes or operational instructions for others to execute. | Approved access/data handling, scoped tools, evaluation capture and an owner. |
| **A1 · Propose** | Present an actionable draft for human use; the agent's execution path remains disabled. | Representative evidence that the draft is useful, grounded and routes ambiguity appropriately. |
| **A2 · Approved execution** | Dispatch the exact approved proposal after fresh checks. | Tested action contract, approval binding, destination authorization, duplicate/concurrency controls, reconciliation and staffed exceptions. |
| **A3 · Bounded execution** | Execute eligible actions without per-instance discretionary review, within the owner's grant. | Same-action/cohort outcome evidence, applicable judge calibration, tested restriction/recovery, operational capacity and net benefit; policy must permit delegation. |

A1 may still allow a human to perform work through a separate authorized system; it does not create permission for the agent's executor. Mandatory per-action approval prevents A3 for that action. Suspension is a separate dispatch-control state and can apply regardless of the previous mode.

### A grant review for SC-42

Consider `create_internal_case`, which creates a linked specialist follow-up. Keep the cohort fixed: eligible servicing cases with verified account/parent linkage and an approved follow-up type and destination queue. The decision sequence below follows that same action and cohort.

| Review point | Evidence and decision | What the runtime permits |
|---|---|---|
| Qualify the draft | A0 results support useful, grounded proposals and appropriate escalation. Approve A1; no business execution evidence is implied. | Show the proposal; agent dispatch stays disabled. |
| Enable supervised execution | Isolated integration tests and drills establish exact approval, fresh policy checks, correct effects, duplicate prevention and owned recovery. Approve A2 for a limited supervised cohort. | Create the exact follow-up after approval and current checks. |
| Reject a premature promotion | API checks pass, but reviewers find unnecessary follow-ups or incorrect routing. Retain A2; correct context/routing and add regressions. | Improved model or judge scores do not change the grant. |
| Delegate a narrow action | Independently reviewed outcomes meet criteria agreed in advance; queue capacity and total effort justify delegation. The action owner approves grant revision CF-42@v2. | A3 only for the eligible cohort, approved queues/fields and volume limits, until expiry; the address action stays A2. |
| Contain and restore | A confirmed effect on an out-of-scope parent case triggers the predefined severe-event rule. Block affected new dispatches and reconcile in-flight work. After repair, relevant tests, observation and owner review, restoration may begin at A2. | Suspension is enforced outside the model. Restoring A2 does not silently restore A3 or erase the incident. |

The review packet binds the grant request to an evaluation window and matured cohort, actual system/tool/model/rubric versions, sample selection, severity-specific error counts, unresolved operations, reviewer effort and downstream rework. Fix minimum evidence, acceptance limits, queue capacity and restriction/restoration rules before examining results.

The A3 grant limits the parent/account relationship, follow-up type, permitted fields, destination queue and volume. An existing follow-up for the same parent and type is reconciled or escalated rather than recreated; duplicate prevention must be enforced by the destination's supported operation/uniqueness contract. Creating a correctly routed case is action success. Resolving the original servicing problem remains a separate outcome.

[Illustrative authority review record](examples/authority-review.json)

## Bind every agent to the shared harness

The **shared harness** is the common control boundary that checks permissions, dispatches actions and records outcomes. Each registered agent receives a **versioned configuration**, backed by common platform services. The configuration binds identity/delegation, allowed context and tools, budgets, grant references, required evaluations, evidence and exception routing.

[![Each registered agent binds to the shared harness, with evidence, evaluation and accountable console decisions outside the model](diagrams/p2-agent-harness.png)](diagrams/p2-agent-harness.png)

For the servicing investigator, registration links an accountable owner and validated runtime configuration to source-access rules, read tools and the two action contracts. Tool availability does not imply permission to execute. The shared harness resolves current grants at dispatch; a cached startup decision cannot establish that permission is still valid.

An approved implementation must demonstrate request identity propagation, scoped tool/credential access, required-check failure behavior, durable operation identity, cancellation/reconciliation, and export of usable evidence. An external agent or provider that cannot support a required boundary stays outside that execution mode. A wrapper or a prompt cannot manufacture missing enforcement guarantees.

Shared-harness services provide identity integration, grant evaluation, durable execution, evidence correlation and evaluation plumbing. Domain teams own eligible cohorts, meaning of correct completion, escalation labels and recovery. The second workflow supplies its own action contract, tests and recovery adapter while reusing those services.

[Illustrative per-agent registration profile](examples/agent-profile.json)

## What to buy, and what the firm must decide

Identity integration, scoped tools, approval workflows and tracing are candidates for reuse or purchase. Evaluate the assembled implementation against four operating contracts:

| Contract | Acceptance exercise | Accountable owner |
|---|---|---|
| Versioned action grants independent of model releases | Change the model configuration; verify the grant stays bounded and dispatch checks the validated configuration. | Action owner and platform lead. |
| Promotion evidence packet | Reconstruct population, sample selection, outcomes, errors, effort and the decision for the requested action/cohort. | Business owner and evaluation lead. |
| Restriction acknowledgment | Request a restriction, verify the enforcement point blocks affected new dispatches, and measure the delay. | Operations and platform on-call. |
| Owned reconciliation | Inject a timeout after a possible write; resolve the operation without an accidental duplicate. | Service owner and recovery team. |

Buy an implementation when it meets these contracts. Build adapters only for demonstrated integration gaps. The firm supplies domain meaning, evidence requirements, incident authority and recovery acceptance in either choice. Compare licensing, integration, evaluation, human review, on-call support and exit costs. A supplier demonstration becomes useful when the team can repeat these exercises against its own destination systems.

## Use an agentic console to operate those decisions

The console lets operators see registered agents, inspect each action’s current grant, examine outcomes and request changes. It is an operational interface to the underlying controls; runtime and destination services enforce the decision.

[![Reference console separates requested promotion, current grants, restriction acknowledgments and unresolved operations](diagrams/p2-agentic-console.png)](diagrams/p2-agentic-console.png)

This snapshot shows OP-42 after a timeout, before reconciliation. The later decision record shows its verified outcome. In the console, operations requests a hold on **new address-update dispatches for SC-42 only**. The A2 grant for other eligible cases remains unchanged. Acknowledgment is pending; OP-42 stays unknown until reconciliation establishes its outcome.

For each action/cohort, show the effective grant and configuration, owner, policy ceiling, evaluation window, sample coverage, material errors, human effort and exception backlog. Expose missing evidence instead of displaying an unexplained green trust score. Operators should be able to move from a metric to the reviewed cases and operation records that produced it.

A promotion request records the proposed change, evidence and approvers. Restriction records have separate **requested**, **enforcement confirmed**, and **in-flight reconciled** states. Measure the delay between them. The console must not display “suspended” merely because it accepted a button click; an unacknowledged request needs a defined operational escalation.

[AUTHOR: Add an anonymized operational lesson about revocation, a stop control or an uncertain write. State what you personally observed, who owned recovery and what changed. Omit this note if no publishable example exists.]

Business owners authorize grant expansion with risk partners. Operations may restrict within preauthorized incident procedures. Restoration has its own approval path. These changes use authenticated, authorized and audited control APIs; the evaluating model cannot write the grant store or approve its own recommendations.

## Separate model judgment from the execution boundary

[![Scoped investigation and semantic assessment feed an action proposal; approval returns through fresh checks before controlled execution and outcome verification](diagrams/p2-model-proposes-policy-decides.png)](diagrams/p2-model-proposes-policy-decides.png)

The agent investigates through scoped read connectors, then produces a structured proposal. Required evidence and semantic checks can block or escalate that proposal. Permission to perform the exact action is evaluated outside model instructions.

Bind approval to the target, exact field changes, supporting evidence, relevant record version, proposal expiry and applicable policy. At dispatch, recheck current entitlements, the authority grant, active policy, required approval and business preconditions. Invalidate materially changed proposals. An approved payload must not be rewritten by the model afterward.

The executor supplies durable operation identity and recovery state. The destination enforces authorization and conditional-write semantics where supported. Use a payload-bound idempotency key and supported operation lookup; a duplicate key with different intent is an error. These guarantees depend on the destination contract. [Retry semantics](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/)

| Event | Required behavior in this design |
|---|---|
| Record, approval or relevant conditions become stale | Stop dispatch; obtain a corrected proposal and fresh review. |
| Authorization denies the action | Record denial; do not reinterpret it as a request to try another path. |
| Policy or required evidence is unavailable | Stop the affected consequential step; retain a draft and an owned exception. |
| Submitted write times out | Mark unknown; reconcile by operation identity and authoritative state before deciding whether retry is safe. |
| Only part of the workflow completes | Expose partial completion; use supported compensation or owned reconciliation. |
| Stop control activates | Prevent affected new dispatches; classify and resolve work already in flight. |

A lock around our own writers cannot constrain all external writers. If the destination cannot support adequate concurrency/reconciliation controls, keep the action draft-only until an alternative design is accepted. Do not promise exactly-once effects across unrelated systems.

MCP is a connectivity and protocol authorization mechanism, not the firm's action-approval model. Use audience-bound credentials and preserve destination authorization; token passthrough is prohibited in the referenced guidance. [MCP security](https://modelcontextprotocol.io/docs/2025-11-25/tutorials/security/security_best_practices)

## Evaluate three different things

**Correct judgment, permitted behavior and a completed business outcome are different claims.** Test each with evidence suited to it.

| Evaluator | Suitable questions | Evidence and limits |
|---|---|---|
| Deterministic checks | Are rights current? Is the payload exact? Did the expected state change occur without a duplicate effect? | Policy decisions, contracts, state queries and assertions. These checks cover what has actually been encoded and observed. |
| Semantic judge: LLM or structured decision model | Does the resolution follow the supplied evidence? Are important contradictions or gaps omitted? | A versioned rubric, relevant evidence and a verdict with uncertainty. Measure unsafe passes and false rejections; authorization stays with policy controls. |
| Domain reviewer | Is the proposed next step appropriate in this case? Is the rubric missing an important exception? | Adjudicated reference cases, disagreement review and sampling of accepted work. Human review also needs quality controls. |

Combining code, model and human evaluation is consistent with [Anthropic's agent-evaluation guidance](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents). Evaluate the model, shared harness, sources, tools and controls together.

### Structured decision models alongside LLM judges

An LLM judge can assess evidence against a rubric and supply a rationale for review. A structured decision model is another option for narrow classifications. TypeSafe’s **Jev**, introduced in September 2026, returns typed choices, scores and probabilities rather than generated explanations. [Launch](https://typesafe.ai/blog/introducing-system-one-models-and-jev) · [Documentation](https://docs.typesafe.ai/concepts/system-one)

For either approach, ask a focused question: “Do these records support, contradict or leave unresolved the proposed correction?” Supply criteria and source excerpts. Preserve an explicit insufficient-evidence route. Validate error rates, calibration, latency and review burden on independently labeled domain cases. Correlated judges can share the same blind spots; adding judges requires evidence that it improves the decision.

Pin the evaluator version, question type, rubric, input manifest and routing threshold. Keep exact numeric/date comparisons and invariants in code. Test adversarial content against both the agent and evaluator. Jev’s documented task limitations and question-specific confidence semantics belong in that qualification. [Limitations](https://docs.typesafe.ai/model-jaggedness/jev-1.13) · [Confidence](https://docs.typesafe.ai/confidence)

### Evaluation before deployment and during operation

Before deployment, build domain-labeled cases covering normal work, ambiguous intent, missing/conflicting sources, wrong-account selection, revoked rights, malicious document instructions, stale approvals, retries and partial outcomes. Include repeated trials for variable behavior and separate held-out cases from development/tuning cases. Check the final state and the path, not just the wording of the answer.

During operation, run required policy and execution checks on every applicable action. Use configured pre-action semantic checks where the action contract requires them; an unavailable required evaluator routes to the defined hold/review path. Sample other semantic assessments asynchronously, alongside outcome monitoring and human audits. Retrospective evaluation cannot undo an unsafe effect.

Review accepted cases as well as escalations. Record sampling probabilities and risk strata so aggregate estimates are not mistaken for an unbiased population measure. Domain reviewers adjudicate disagreements and periodically review one another's labels. Watch missed escalations, unsafe passes and false rejections separately; overall agreement can conceal the errors that matter most.

## Two feedback loops, two decisions

[![Evaluation feeds a system-improvement release process and a separate authority-change process, with an immediate restriction path for defined severe events](diagrams/p2-evaluation-loop.png)](diagrams/p2-evaluation-loop.png)

**The improvement loop changes behavior.** Investigate the cause before selecting the remedy. Incorrect source material needs correction; poor retrieval needs better selection; ambiguous instructions need clarification; a retry defect needs an execution fix. Consider another model or offline training for persistent behavior gaps supported by suitable, reviewed data. Keep current policy in authoritative sources and enforceable rules; weights are not a reliable store of changing permissions.

Training requires approved data use, curation/redaction, labels with provenance, separate training and held-out sets, a versioned candidate, regression evaluation and a rollout/rollback decision. Raw traces, user corrections and judge verdicts are inputs for adjudication, not automatically training truth. Evaluate the whole system after a model change and review any authority grant whose evidence it invalidates.

**The authority loop changes permission.** The business action owner reviews outcome quality, control coverage, residual risk, operational capacity and benefit with applicable risk/security partners. The result is a versioned grant to retain, expand, restrict or suspend an action for a defined cohort. A run can select a more cautious path inside that grant; it cannot widen the grant itself.

| Decision | Evidence or trigger | Operating response |
|---|---|---|
| Expand deliberately | Representative evaluation and supervised/shadow results; severity-specific errors within agreed limits; judge calibration; complete required evidence; tested recovery; lower total effort | Approve a narrowly defined grant change and controlled rollout. Keep mandatory approvals. |
| Restrict proportionately | Sustained adjudicated defects, missed escalation or unresolved operations against defined windows and minimum samples | Reduce eligible scope, require approval or return to draft-only mode. Assign a repair owner. |
| Suspend promptly | A predefined severe event such as an unauthorized write or confirmed authorization bypass | Block affected new actions, preserve evidence and reconcile in-flight work. |
| Restore after repair | Root cause addressed, relevant regressions passed, observation criteria satisfied and owner decision recorded | Reinstate a specified grant; monitor the restored cohort. Do not reset history. |

Agree criteria before looking at pilot outcomes. Separate restriction and restoration thresholds/windows to avoid repeated switching on noise. Distribution shift is a signal to investigate; low override rates may reflect rubber-stamping. Zero failures in a small sample do not establish that rare events are acceptably unlikely. Material source, tool, model, judge or policy changes require impact review and relevant requalification.

## Observe what makes autonomy defensible

Correlate **case → action/proposal → authority grant → policy/approval → operation → verified outcome → evaluation/review**. Record model/tool/rubric versions and concise evidence-backed decision factors; hidden reasoning is unnecessary. Keep sensitive payloads in an access-controlled evidence store with appropriate retention, legal-hold and deletion processes. An append-only table alone is not tamper-proof evidence.

Report metrics by action, risk cohort, environment and system/judge/policy version. Use a defined observation window and outcome-maturity rule; show samples, pending work and severity. Use the following measures to decide whether to change the grant or repair the system.

| Measure | Definition | What it changes |
|---|---|---|
| Unauthorized effects | Count/severity of effects outside valid scope or approval; also report executed-action count | Containment and control repair. Track blocked attempts separately. |
| Incorrect completion | Adjudicated wrong/incomplete outcomes / reviewed completion claims | Verification, scope or approval requirements; disclose sampling. |
| Missed escalation | Adjudicated cases requiring escalation that were not escalated / all adjudicated cases requiring escalation | Routing and autonomy limits. |
| Unnecessary escalation | Avoidable escalations / reviewed escalations | Context/routing quality and reviewer capacity. |
| Unknown outcomes | Dispatched operation IDs unresolved beyond the agreed interval / dispatched operation IDs; plus oldest age | Reconciliation capacity and new-write restrictions. Count operations, not retries. |
| Evidence completeness | Actions with all required valid linked records / actions requiring those records | Evidence pipeline repair; completeness is not correctness. |
| Judge unsafe-pass rate | Unacceptable cases passed / adjudicated unacceptable cases | Evaluator selection, thresholds and review routing. Also report false rejection and domain calibration. |
| Autonomous coverage | Eligible cases correctly resolved without intervention / eligible cases in a matured cohort | Useful scope of automation, paired with quality. Hold eligibility rules stable; show pending and abandoned cases. |
| Human effort and correction | Total handling/review/exception/rework minutes per eligible case; material corrections / reviewed proposals | Whether work was removed or shifted; low correction counts alone are inconclusive. |
| Time to restrict | Detection-to-enforced-restriction time, with unresolved in-flight operations | Whether revocation works in drills and incidents. |

A verified account update completes an action. SC-42 closes only when the servicing workflow's separate resolution conditions are satisfied and closure is authorized and confirmed. A case requiring human approval does not count as resolved without intervention. Report automated investigation or action coverage separately; reduced human effort can establish value even when whole-case autonomous coverage is zero.

Sampled judgments estimate quality with uncertainty; do not represent them as complete observation of all autonomous outcomes. Validate reported probabilities against human-adjudicated outcomes by rubric and cohort. Use a calibration curve and a proper scoring measure where appropriate rather than interpreting confidence as a universal reliability score.

Total cost per correctly resolved case includes the model, judges, platform and human work across the whole cohort, including unsuccessful attempts. Compare comparable case mixes and mature outcome windows against the prior workflow. Faster investigation is valuable only if review and reconciliation do not consume the gain.

## Fit authority decisions into existing governance

Map these decisions into the firm’s existing governance; owners confirm the routing and required evidence. [FINRA’s 2026 GenAI discussion](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai) addresses supervision, governance, model-risk practice, testing and monitoring.

| Decision | Proposed process connection | Record to retain |
|---|---|---|
| Change an action grant | Change management and supervisory procedures; action owner authorizes scope. | Before/after grant, reason, approver, validated configuration and effective time. |
| Promote to a broader grant | Business review and model-risk practice where the firm classifies it as applicable. | Cohort, evidence window, sampling, outcomes, errors, effort and residual risks. |
| Suspend or restrict | Incident/supervisory procedures with preauthorized containment rights. | Requested scope, confirmed enforcement, in-flight operations and recovery owner. |
| Restore permission | Repair review, change authorization and owned rollout. | Root cause, regressions, operating observations and exact restored grant. |
| Reconstruct an action | Audit and recordkeeping processes, with source-system access and retention rules. | Proposal, approval, grant, dispatch, receipt, verification and exception history. |

## Make the operating model executable by people

The business owner defines eligible work and grants; operations/domain experts define outcomes and adjudicate exceptions; engineering owns execution and recovery; the evaluation owner maintains cases and judge quality; security/risk partners establish applicable constraints; platform owners maintain identity, connectors and evidence services. Assign these responsibilities within existing teams wherever practical.

Begin with one case class in shadow or supervised mode and a staffed exception path. Rehearse denial, unknown outcomes and stop/recovery before increasing exposure. The second use case should reuse action contracts and evidence interfaces without copying a bespoke harness.

**Earned autonomy means permission supported by evidence—and a working mechanism to take it back.**

---

**Author:** Mohit Mittal, Chief Architect, with 22+ years in enterprise architecture and distributed systems, including production LLM/RAG at Chegg and governed agent infrastructure and MCP servers in healthcare.

[Reference design and evidence record](reference-design.md) · [Sources](SOURCES.md) · [Separate AI-DLC architecture](https://github.com/appliedgenai/intent-to-production)
