# Instructions for working on Earned Autonomy

## Read first

1. `PROJECT-GOALS.md` for scope, current decisions and unfinished work.
2. `RESEARCH-NOTES.md` and `SOURCES.md` for claim boundaries and research leads.
3. `README.md`, `02-agents-you-can-audit.md` and `reference-design.md` for the actual published argument.
4. The rendered diagrams. Reading Markdown captions is not a substitute for inspecting images.

Current user instructions take precedence over this file. Work on this paper separately from the companion AI-DLC repository unless the user expands the scope.

## Intended outcome

A busy enterprise leader should understand the message, business value and proposed decision in a six-minute brief. A practitioner should find concrete controls, interfaces, failure behavior, operating roles, metrics and tradeoffs in the full paper. The subject is runtime agent authority in regulated workflows, not an AI-DLC tooling catalog.

State the thesis immediately. Establish why a task warrants an agent before explaining how to govern it. Compare with an ordinary workflow or narrowly scoped model call. Compliance requirements constrain the design; they do not establish a business case for agent autonomy.

## Research and integrity

- Keep public repository files focused on the architecture. Do not include private outreach recipients, sharing status, job-search correspondence or assumptions about who has received a link.
- Check current primary sources for material product, evaluation and regulatory claims. Attribute articles to their authors, including guest authors on Martin Fowler's site.
- Distinguish verified product capabilities, author experience, design recommendations and synthetic examples. Never invent deployments, incidents, savings or benchmark results.
- Keep regulatory statements within their source's scope. Do not label a design compliant or present an engineering proposal as a prescribed regulatory architecture.
- Jev means TypeSafe's structured decision model. Use official `typesafe.ai` / `docs.typesafe.ai` sources. Typed output and calibrated probabilities do not establish semantic correctness, authorization or compliance.
- Keep model-based evaluation separate from deterministic policy enforcement. Explain evaluator failure, uncertainty, calibration and human adjudication.

## Architecture requirements

- Separate adaptive investigation, exact business-action permission, controlled execution and verified outcome.
- Bind approval to the exact proposal and relevant state. Draw approval returning through fresh authorization/precondition checks before execution.
- Give unknown, partial, denied and expired results an explicit owner and next step. Do not assume a timeout means failure or promise exactly-once behavior without destination guarantees.
- Separate system improvement from authority changes. Better models or judge scores do not automatically confer broader permissions. Policy ceilings and mandatory approvals remain binding.
- Explain expansion, restriction, suspension and restoration per action, cohort, environment and version. Avoid a single universal trust score or invented promotion threshold.
- Treat model training as an optional controlled response to demonstrated behavior gaps. Investigate source, retrieval, prompt, tool and workflow defects first. Do not assume every vendor exposes fine-tuning.
- Use four permission modes for a specific action/cohort: A0 shadow, A1 propose, A2 approved execution and A3 bounded execution. This is a proposed vocabulary, not an industry standard. Shadow results cannot establish live-write safety; mode progression is optional and suspension is a separate control state.
- Bind each registered agent to versioned shared-harness controls. Do not suggest that wrapping an unsupported provider establishes enforcement. A second workflow reuses interfaces but requires its own action evidence and recovery integration.
- Distinguish a requested restriction, confirmed runtime enforcement and reconciled in-flight work in the console. Required inline checks, ongoing outcome/sample evaluation and offline requalification have different jobs.

## Narrative and diagram requirements

- Use one coherent running example across text, authority matrix, runtime flow and evidence record. A small subordinate failure example is acceptable when explicitly linked.
- Every diagram must answer a specific architectural question and show meaningful flow, decision rights or exchanged evidence.
- Captions cannot repair misleading arrows. Inspect branch direction, bypass paths, examples, counts and outcome semantics.
- Show an actual evaluation feedback loop, including distinct system-improvement and authority-review branches. Do not end with a box labelled continuous evaluation.
- Show how the same action can gain or lose permission; changing tasks on successive ladder rungs does not demonstrate that.
- Render and visually inspect diagrams before publishing. Preserve editable sources. Check labels at normal reading size and provide full-resolution links.
- Keep the README compact; place detailed metrics, rubrics and operational cases in the full paper or reference material.
- Keep all six core runtime-authority diagrams directly visible on the homepage: permission modes, shared harness, execution boundary, operating console, decision record and evaluation feedback loop. Do not reduce the homepage to a teaser that requires another document to understand the architecture.
- Maintain a guided six-minute scan with short takeaways and captions, clickable full-resolution images and an explicit transition from the console's unknown OP-42 outcome to the later verified decision record. Inspect the assembled GitHub page after publication.
- Review the homepage as a first-time reader: define earned autonomy and state the main decisions before introducing the architecture. Define harness, grant and approval in plain language. The prose must explain why there are two example actions and narrate verification, approval, uncertain execution and recovery without relying on diagram labels or a companion document to supply missing events.

## Measurements

Define numerator, denominator, observation window, severity, sampling and version/cohort segmentation where relevant. Include failed, abandoned and pending work in the appropriate population. Distinguish blocked attempts from unauthorized effects, tool success from verified completion, and model confidence from observed correctness.

Pair autonomous coverage with quality and total human effort. Low override rates may reflect weak review. Judge agreement alone can conceal unsafe passes. Do not treat raw drift as proof of harm without a defined response rule.

## Review loop

This project requests separate review agents, when available, for primary-source claims, architecture/failure semantics, and skeptical-reader clarity. The lead owns the edits and resolves disagreements with reasons. Reviewers should return concrete defects, evidence and corrections, rather than generic praise or numerical quality scores.

1. Arrange the key messages and identify the executive decision.
2. Establish evidence and a justified example.
3. Draft text and diagrams as one argument.
4. Resolve material findings, then rereview changed sections and visuals.
5. Check links and relevant artifact syntax. Do not describe example specifications as executed tests.
6. When publication is in scope, verify the actual GitHub text and diagrams and record commit evidence. Preserve existing history and unrelated work.

Do not invent approval requirements. Continue authorized work without repeatedly asking permission. If the current request is a design discussion, clearly distinguish recommendations from implemented or published changes.

## End-of-session handoff

Update `PROJECT-GOALS.md` with completed work, exact remaining issues, decisions still open and publication status. Update research notes when sources or assumptions change. An old completed review does not certify later revisions or previously uninspected diagrams.
