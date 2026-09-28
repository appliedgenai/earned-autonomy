# Research notes for the autonomy revision

Reviewed 28 September 2026. These notes distinguish primary-source facts from architectural recommendations. Recheck changing product details before publication.

| Source | What it supports | How to use it |
|---|---|---|
| [TypeSafe System One](https://docs.typesafe.ai/concepts/system-one) | Jev's typed decisions/probabilities; no generated explanations; calibration is not a guarantee for individual answers. | Consider focused semantic evaluation. Do not equate schema validity with correct judgment. |
| [Jev 1.13 limitations](https://docs.typesafe.ai/model-jaggedness/jev-1.13) | Numeric/date, indirect-reasoning, context and adversarial-input limitations. | Use code for exact checks and test the actual rubric/domain. |
| [TypeSafe confidence](https://docs.typesafe.ai/confidence) | Choice/Score confidence derives from their distributions; Noul has different output semantics. | Do not substitute confidence for authorization or transfer thresholds between question types without evaluation. |
| [MLflow Jev judge comparison](https://www.mlflow.org/blog/jev-llm-judge/) | A small human-labeled technical-QA comparison and integration example. | Evidence that the approach can be tested, not proof of financial-services suitability. |
| [Anthropic agent evaluation guidance](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) | Combining code, model and human evaluation; outcome and trajectory assessment. | Define rubrics, domain labels and appropriate evidence for each failure class. |
| [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) | Workflow versus agent distinctions and complexity tradeoffs. | Explain why adaptive investigation adds value before introducing an agent. |
| [FINRA 2026 GenAI discussion](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai) | Supervision, testing, monitoring, agent authority, auditability and sensitive-data concerns. | Regulatory context; it does not prescribe our architecture or certify compliance. |

## Synthesis used in the paper

Use four action-scoped permission modes, a shared harness, an operational console, an execution/control diagram and an evaluation feedback diagram. The modes are proposed design vocabulary, not a claimed standard. Keep semantic judge assessment separate from policy enforcement. Separate changes to system/model behavior from changes to authority. Treat training as an optional versioned intervention requiring suitable labeled data and held-out evaluation.

The worked SC-42 promotion request is synthetic. It demonstrates why API correctness alone cannot justify delegation: necessity, routing, recovery, operational capacity and total human effort also matter. No numerical promotion threshold or observed improvement has been invented. The console snapshot precedes the verified outcome in the reference design's decision record.

## Audience-aware editorial decisions

Public financial-services technology material already discusses agent identity, scoped action, confirmation, monitoring and shutoff. For example, [LPL's technology webcast](https://www.lpl.com/join-lpl/managing-your-business/tech-capabilities-and-offerings.html) covers these subjects. Treat governance basics as established audience knowledge. Public material does not establish internal implementation coverage or reveal a capability gap.

[LPL's Focus 2026 release](https://investor.lpl.com/news-releases/news-release-details/lpl-financial-opens-focus-2026-bringing-together-thousands) emphasizes advisor capacity; its [Latitude announcement](https://www.lpl.com/news-media/press-releases/lpl-financial-latitude-unifies-technology-built-for-future-of-advice.html) describes a unified technology direction. The editorial inference is to lead with net workflow effort and reusable operating interfaces. This is an audience assessment, not a statement of any executive's private priorities or reaction.

No Jev benchmark, training exercise or integrated financial-services implementation was run for this paper. Any suggested tool placement is a design recommendation to evaluate.
