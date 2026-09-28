# Operating model wins, not tooling

### Six layers for AI-native delivery you can prove

*Mohit Mittal · September 2026*

If a coding agent halves implementation time but doubles the review queue, the organization may ship no sooner. If an advisor agent saves four minutes of entry and creates six minutes of exception handling, the business has lost capacity.

Both failures come from optimizing a step while ignoring the system around it.

**The operating model must connect intent, bounded execution and evidence of the final outcome.** That is what makes AI investment measurable and lets teams reuse capabilities without recreating governance for every application.

Google's [2025 DORA research](https://dora.dev/insights/balancing-ai-tensions/) associates higher AI adoption with both greater delivery throughput and greater instability. That is an association, not a guarantee for an individual firm. METR's [early-2025 randomized study](https://arxiv.org/abs/2507.09089) found slower completion in a specific experienced-developer setting; its [February 2026 update](https://metr.org/blog/2026-02-24-uplift-update/) explains why newer measurements were affected by selection and measurement problems. Neither is a substitute for measuring your own current workflow.

## Six layers, with a contract between each

The layers are responsibilities, not a mandate for six new platforms.

| Layer | Responsibility | Concrete output |
|---|---|---|
| **L6 Intent** | Define the business change, exclusions and success criteria. | Versioned requirement with acceptance and failure cases. |
| **L5 Knowledge** | Expose authoritative domain knowledge with ownership and permissions. | Service contracts, policy sources and decision records with provenance. |
| **L4 Context** | Assemble the smallest sufficient, permission-filtered evidence for this task. | Context manifest with source versions and freshness. |
| **L3 Execution** | Run bounded agents and deterministic workflows. | Proposed changes, tool receipts and explicit execution state. |
| **L2 Control** | Enforce policy, evaluation, review and release rules. | Versioned authorization and release decisions. |
| **L1 Memory** | Preserve outcomes and link them back to requirements. | Restricted evidence record and candidates for future evaluations. |

The harness is the runtime that connects these responsibilities. Evaluation is defined with intent and checked throughout, not added as a final quality screen. Production evidence informs future tests, but raw traces do not automatically become trusted knowledge. Curate, redact and approve them before reuse.

## One change through the stack

Consider adding an AI-assisted account-maintenance workflow to an advisor platform. An advisor can prepare a mailing-address change; a reviewed, authorized proposal is executed through the existing account service. Money movement, investment recommendations and beneficiary changes are excluded from this first slice.

**Intent:** Product and operations define when the workflow is useful and when it must stop. Acceptance tests include a wrong account, a changed record, a revoked entitlement and a timeout after a write. Success means a correctly resolved request with less total human effort.

**Knowledge:** Reuse the account API contract, identity requirements, business rules and support runbook. Assign a domain owner to each. Where two sources conflict, flag the conflict instead of asking a model to choose the most convenient answer.

**Context:** Retrieve only what the current actor may access for the relevant relationship. Apply access controls before retrieval results reach the model. Include freshness and version information; partition caches by the permissions and data boundaries they must preserve.

**Execution:** A coding agent can implement the proposal and review experience within a scoped branch. At runtime, the advisor agent prepares the proposed action. A durable workflow owns the authorized write and its reconciliation. The coding agent's permissions and the advisor agent's permissions are separate concerns.

**Control:** The release gate tests the changed workflow's risk, regardless of who wrote its code. Runtime controls bind approval to the exact proposed change and revalidate authority before execution. These are separate gates; passing a release evaluation does not authorize an individual transaction.

**Memory:** Link the requirement, code change, evaluated model/prompt/tool versions and review evidence. Link runtime operations to their approvals and verified outcomes. Use separate retention and access policies for software-delivery records and client-related evidence.

## Centralize enforcement; keep domain ownership

A shared AI platform should make the safe path easier than a bespoke integration. It should not become the team that must understand and approve every business decision.

| Shared platform owns | Domain team owns |
|---|---|
| Identity integration, model access and common gateway enforcement | Business action definitions and entitlement semantics |
| Agent/tool registries and versioned deployment mechanisms | Typed domain APIs, validation and recovery behavior |
| Evaluation infrastructure and evidence interfaces | Representative test cases, labels and acceptance thresholds |
| Observability, quotas and reusable security controls | Workflow outcomes, exception queues and business value |

Risk and security partners define applicable constraints with both teams. Domain release ownership remains explicit.

The test of reuse is practical: can a second domain onboard through the same interfaces without a parallel identity stack, a second audit format or weeks of platform-specific customization?

## Buy capabilities; own the boundary

Buy or adopt commodity coding tools, orchestration, search, evaluation runners and telemetry where they fit. Own the business-specific contracts: authorized actions, evidence fields, context boundaries and recovery obligations. Integration may be substantial; calling it small glue does not make legacy behavior, data quality or entitlements simple.

Use a deterministic workflow when the steps are known. Add an agent where interpretation or variable planning adds value. Use multiple agents only when independent responsibilities justify the coordination cost.

Choose models using representative evaluations, latency and total workflow cost. Smaller models can be useful for bounded extraction or classification; a more capable model may be justified for ambiguous synthesis. Permissions, arithmetic and transaction preconditions belong in deterministic services. Model confidence can inform routing, but cannot grant authority.

## Measure the bottleneck you actually have

For software delivery, track requirement-to-production lead time, review wait time, rework and production failures. For advisor workflows, track human handling time, elapsed resolution time, correct completion and exception load.

Compare eligible, similarly complex work across a staged rollout or a matched baseline, accounting for seasonality and staffing. Include failed and abandoned cases. Report adoption separately from realized capacity: unused automation creates no business savings.

An illustrative calculation makes the distinction concrete. For 1,000 eligible requests, a measured baseline of 12 human minutes is 12,000 minutes. If the pilot averages four minutes of routine human work per request, plus 20 additional minutes on each of 100 exceptions, total effort is 6,000 minutes. That is a potential 100 staff-hours recovered. It is **not a forecast or an observed result**, and it is not automatically cash savings. Platform operating cost, oversight and the ability to redeploy the time still matter.

If exceptions rise to 400 under the same assumptions, the saving disappears. An executive dashboard that only counts generated drafts would miss that.

## Modernization is the proving ground

AI can help read old code, map dependencies and propose characterization tests. Extracted behavior remains a hypothesis until confirmed against business rules and observed system behavior.

Introduce a governed interface around one existing capability. Compare results, reconcile differences and move a bounded cohort. Preserve a reversible rollout where possible, with an explicit path for changes that cannot be undone. This makes modernization progress visible without requiring a wholesale platform replacement before the first useful workflow.

The same evidence structure now serves delivery and operation: what was intended, what changed, what was verified and what happened afterward. That is the durable contribution of the architecture.

---

[Read Agents you can audit](02-agents-you-can-audit.md) · [Inspect the reference design](reference-design.md) · [Sources and scope](SOURCES.md)
