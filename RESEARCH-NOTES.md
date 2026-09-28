# Research notes for the next autonomy revision

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

## Proposed synthesis

Use an action-authority matrix, an execution/control diagram and a real evaluation feedback diagram. Keep semantic judge assessment separate from policy enforcement. Separate changes to system/model behavior from changes to authority. Treat training as an optional versioned intervention requiring suitable labeled data and held-out evaluation.

No Jev benchmark, training exercise or integrated financial-services implementation was run for this paper. Any suggested tool placement is a design recommendation to evaluate.
