# Project goals and current state

Updated 28 September 2026.

## Goal and scope

Explain when an enterprise should use an agent, which specific business actions it may perform, and how verified outcomes inform retaining, expanding or restricting its authority. Connect business benefit, evaluation, observability and accountable operating decisions.

The entry point is a six-minute visual brief; detailed controls, rubrics, failure behavior and metrics belong in the full paper and reference design. Reading time is a design target, not a guarantee. Work on Earned Autonomy separately from the [AI-DLC architecture](https://github.com/appliedgenai/intent-to-production), unless the user expands scope.

## Current publication — completed

The revised brief, full paper and reference design are published and verified on GitHub. This revision replaces the earlier paper at `fb580b3` and completes the work identified when project instructions were added at `4bb6cc0`.

| Artifact | Published commit | Verification |
|---|---|---|
| Four diagrams, editable SVGs and diagram index | [971328b](https://github.com/appliedgenai/earned-autonomy/commit/971328b1a305dfd5e7deaafed99ec1b237b19b19) | All four rendered PNGs visually reviewed locally; all four loaded in the published brief, paper or reference design. |
| Action contract and fifteen evaluation scenarios | [f48918f](https://github.com/appliedgenai/earned-autonomy/commit/f48918fdb5977cd75f47bdf18726d0af1edffa0b) | JSON parses; fifteen unique scenario IDs; final architecture rereview resolved current-grant and unknown-evidence semantics. |
| Brief, paper, reference design, sources and navigation cleanup | [c1936e6](https://github.com/appliedgenai/earned-autonomy/commit/c1936e6bce3d76dc2000f746966eaa9c16240315) | Published thesis, Jev section, feedback loops, corrected metric and case-closure boundary inspected. Reference Mermaid diagram renders. |

## Completed revision checklist

- [x] Justify adaptive investigation against a deterministic workflow or extraction baseline.
- [x] Use synthetic service case SC-42 throughout, without claiming a production deployment.
- [x] Replace the old ladder with an action-authority matrix; show the same linked follow-up action gaining or losing permission.
- [x] Route exact approval through fresh dispatch checks, controlled execution, destination enforcement and outcome verification/reconciliation.
- [x] Explain code checks, semantic judges and domain adjudication, including accepted-case sampling and evaluator failure.
- [x] Place LLM-as-a-judge and TypeSafe's Jev accurately, with typed-output, calibration, uncertainty and version limitations.
- [x] Draw separate system-improvement and authority-review feedback loops, plus immediate restriction for defined severe control events.
- [x] Explain optional model changes/training with approved data, reviewed labels, held-out evaluation and controlled rollout.
- [x] Define expansion, restriction, suspension and restoration by action, cohort and version; preserve mandatory approvals.
- [x] Define autonomy observability measures with denominators, windows, severity, sampling and business-effort qualifications.
- [x] Distinguish verified action completion from authorized whole-case closure and whole-case autonomous coverage.
- [x] Resolve source, architecture and skeptical-reader reviews; inspect all four rendered diagrams.
- [x] Validate relative file/image links, heading anchors, JSON and SVG syntax; audit external destinations.
- [x] Clean navigation: superseded delivery essays point to the current AI-DLC paper and their original Git-history versions. Historical diagram assets remain labeled as background.
- [x] Publish and verify the actual GitHub paper, images, reference diagram and history pointers.

## Decisions to preserve

- Business benefit must justify agent complexity. Compliance constraints alone do not establish the business case.
- Reasoning flexibility, semantic assessment, business-action permission and verified outcome are separate concerns.
- The linked specialist-follow-up action starts approval-required; its grant can later be narrowed or expanded. SC-42's account update retains human approval.
- A judge cannot grant authority. Better system behavior does not automatically increase permission.
- Training is optional; diagnose source, retrieval, prompt, tool and workflow defects first. Raw traces and unadjudicated judge verdicts are not training truth.
- Unknown outcomes are valid recorded states. Receipts and verified results are conditional; unresolved work requires an owner.
- A human-approved case is not counted as fully autonomous. Reduced human effort can still establish value.
- Low overrides, high judge agreement and a small zero-failure pilot do not prove readiness for broad expansion.

## Remaining work and limits

No editorial or publication blocker remains for this revision. The contracts and evaluation cases are design specifications, not an implemented policy engine or executed tests. No Jev benchmark, model training, financial-services integration or measured savings result was produced. A real pilot still requires domain-labeled evaluation, implemented controls, destination guarantees, staffed recovery and agreed acceptance criteria.

For the next requested change, read [AGENTS.md](AGENTS.md), [RESEARCH-NOTES.md](RESEARCH-NOTES.md) and [SOURCES.md](SOURCES.md), then inspect the affected published text and actual images. Recheck changing product facts. Do not silently reopen or update the separate AI-DLC paper.
