# Project goals and current state

Updated 28 September 2026.

## Goal and scope

Explain which agent action can receive more authority, what evidence supports the decision, and whether delegation reduces total human work. The entry point is a six-minute visual brief; the full paper supplies execution contracts, failure behavior, operating roles, evaluation and metrics.

The current revision uses four action-scoped modes, a shared harness, an agentic console and continuous evaluation. It is a reference architecture, not a deployed product or an assertion that any particular firm lacks these capabilities. Work on this paper separately from the [AI-DLC architecture](https://github.com/appliedgenai/intent-to-production).

## Current first-time-reader revision

Published and verified in [1feb658](https://github.com/appliedgenai/earned-autonomy/commit/1feb65856c1779948ddebbfa8f9f310ae7d6a8a1). The opening now defines earned autonomy and states three key decisions before introducing the architecture: delegate actions separately, require evidence before expanding permission, and enforce/monitor permission outside the model. The business goal is correctly resolved work with less total human effort.

- Defined harness, standing grant and exact-proposal approval in plain language.
- Made SC-42 a fictional account-maintenance request with conflicting document/account addresses. The discrepancy does not establish client intent.
- Explained why the example has two actions: address maintenance demonstrates controlled execution and recovery; an internal specialist task demonstrates a separate decision about broader permission.
- Added the missing events before OP-42: required verification, exact approval, fresh checks and a response timeout. Explained the case-specific temporary hold, pending enforcement, later lookup/state verification and separate case-closure decision.
- Architecture and source reviewers found no material blocker. The first-time-reader reviewer requested a reason and scope for the hold; the revised caption supplies both and received an architecture rereview.
- Preserved all six diagrams and the statement **The future of AI depends on disciplined engineering.** Rechecked 73 relative links/anchors. The README has 1,077 whitespace-separated words including Markdown and image alternative text; the six-minute path remains a guided scan.
- Published README and AGENTS contents match the local reviewed files. Inspected the live first screen and complete rendered prose; the definition and all three decisions are visible before the worked example.
- Added the first-time-reader criteria to persistent project instructions. No deployment, measured savings or executed qualification tests are claimed.

## Previous homepage layout revision

Published in [d6954c2](https://github.com/appliedgenai/earned-autonomy/commit/d6954c2bd90cf7f0d1c13cb544a4a5bc44526914) at the repository-root URL. The homepage is now a complete guided scan with all six runtime-authority diagrams embedded directly: modes, harness, execution, console, decision record and evaluation loop. Takeaways and captions connect the same SC-42 case across figures. OP-42 is explicitly unknown in the console and verified later in the evidence record.

- Added the author statement: **The future of AI depends on disciplined engineering.**
- Shortened surrounding prose and supplied six jump links, full-resolution image links and backward-compatible anchors for the previous five sections.
- Clarified that A0–A3 are proposed vocabulary and that Jev is distinct from an LLM judge; any candidate evaluator still requires domain qualification.
- Separate architecture, skeptical-reader and source reviewers rereviewed this revision; their material findings are resolved. The lead inspected all six rendered PNGs and their GitHub homepage presentation.
- Verified all six live images loaded at a rendered width of 823 pixels. Their Git blob hashes match the local images reviewed. Published README, AGENTS and diagram-index contents match the local files exactly.
- Document validation checked 73 relative links/anchors with no errors. That layout revision's README contained 820 whitespace-separated words including Markdown and image alternative text. Six minutes denotes a guided scan, not a timed claim about reading every diagram label.
- Added persistent instructions requiring the six core diagrams to remain on the homepage. No product implementation, empirical evaluation or new production outcome is claimed.

The records below describe the preceding substantive architecture revision. Its former two-image homepage has been superseded by the six-image homepage above.

## Previous substantive architecture revision

Published and verified in [15d4f13](https://github.com/appliedgenai/earned-autonomy/commit/15d4f13f239d11c868749b35f5080f942f7f675c). All seventeen changed/new file blobs match the reviewed local files exactly. The GitHub-rendered brief and full-paper sections were inspected; both brief images and all five full-paper images loaded successfully. The prior published baseline is [7b78189](https://github.com/appliedgenai/earned-autonomy/commit/7b781896e9f5cafe236953b2e43028b717f4736b).

- Rebuilt the executive story around net advisor/operations effort and one concrete permission decision.
- Added four modes for a specific action/cohort: shadow, propose, approved execution and bounded execution. Suspension is a separate control state.
- Worked through the linked specialist-follow-up action from drafting to supervised use, a rejected premature promotion, possible narrow delegation, and restriction/restoration. The address action retains approval.
- Added a shared-harness diagram and per-agent registration example. Unsupported providers cannot be assumed to inherit enforcement guarantees.
- Added an illustrative console showing current grants, requested promotion, missing evidence, pending enforcement acknowledgment and an unknown operation.
- Kept inline checks, ongoing monitoring/sample review and offline candidate evaluation distinct. System improvement and authority changes remain separate decisions.
- Expanded evaluation specifications from fifteen to twenty-two cases, including A0/A1 execution boundaries, unsupported provider controls, restriction acknowledgment and missing promotion evidence.
- Preserved the execution, evaluation-loop and decision-record diagrams. Six current diagrams have editable SVG sources; that revision's brief used only the four-mode and console figures. The current homepage includes all six.
- Completed independent source/audience research, skeptical-reader review and targeted architecture review. The three changed/new diagrams were visually inspected by the lead and both targeted reviewers. No material finding remains in that scope.

## Decisions to preserve

- Lead with business value and a reusable operating decision. Basic logging, scoped access and approval are established enterprise concerns, not a claim of novelty.
- Use synthetic SC-42 consistently. Do not invent first-person deployments, pilot results, incidents or savings. Author background must come from supplied facts.
- Permission is versioned separately from model/system releases, per action, cohort, environment and validated configuration. An agent has mixed permissions, not one global maturity score.
- A0/A1 results cannot establish actual-write safety. A2 requires qualified execution, exact approval, fresh authorization and owned recovery. A3 additionally requires same-action outcomes, policy eligibility, capacity and net benefit.
- A judge, including Jev, cannot authorize execution. Judge confidence, API validity and low overrides cannot by themselves justify broader authority.
- The shared harness enforces supported contracts; each agent supplies a versioned binding. A second workflow reuses interfaces but supplies its own tests, action evidence and recovery adapter.
- The console distinguishes a restriction request from runtime acknowledgment and in-flight reconciliation. An accepted stop click is not proof of enforcement.
- Training is optional. Investigate source, retrieval, prompt, tool and workflow defects first. Judge verdicts and raw traces are not training truth.
- Unknown outcomes remain visible and owned. The console snapshot shows OP-42 before reconciliation; the reference decision record shows its later verified outcome.
- Verified action completion is not whole-case closure. A case needing human approval is not fully autonomous; lower total human effort can still establish value.
- Preserve the existing navigation cleanup and historical links. The other AI-DLC repository remains separate.

## Review and verification record

The architecture rereview checked mode semantics, grant scope, promotion proof, console states, harness bindings and E16–E22. The reader rereview checked the six-minute narrative and all three changed/new figures. Both passed with the boundary that these are proposed designs, not demonstrated operating performance. Audience research uses public primary sources and makes no claim to know an executive's private priorities or likely response.

Validation passed: sixty relative links/anchors, four JSON files, twenty-two unique evaluation scenario IDs, and nine retained SVG sources. That revision's executive brief had 941 whitespace-separated words, with two figures; the current homepage figures and count are recorded above. These checks validate document integrity; the scenarios remain unexecuted specifications. No editorial or publication blocker remains for this revision.

## Limits and next work

The example contracts, registration profile and evaluation cases are specifications, not implemented policies or executed tests. No financial-services integration, Jev benchmark, model training or measured savings was produced. A pilot requires domain-labeled evaluation, implemented controls, destination guarantees, staffed recovery and agreed acceptance criteria. Do not turn these limits into invented evidence.

For the next requested change, read [AGENTS.md](AGENTS.md), [RESEARCH-NOTES.md](RESEARCH-NOTES.md) and [SOURCES.md](SOURCES.md), then inspect the affected text and actual images. Recheck changing product facts. An earlier review does not certify later edits.
