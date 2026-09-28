# Sources and claim boundaries

Reviewed 28 September 2026. Links below support external context; the architectural proposals and synthetic examples are the author's analysis.

| Source | Used for | Boundary |
|---|---|---|
| [FINRA 2026 GenAI report section](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai) | Agent risks concerning authority, auditability and data. | Report discussion is not a prescription for this architecture or a new universal logging requirement. |
| [MCP authorization, 2025-11-25](https://modelcontextprotocol.io/specification/2025-11-25/basic/authorization) | Protocol-level authorization for protected HTTP MCP services. | Business entitlements and transaction approvals require additional implementation. |
| [MCP security guidance](https://modelcontextprotocol.io/docs/2025-11-25/tutorials/security/security_best_practices) | Audience validation and prohibition of token passthrough. | Does not establish end-to-end compliance or remove destination authorization duties. |

The portfolio does not claim legal compliance, measured production savings, an implemented policy engine, or validated performance of the sample design. Author experience is based on the author's supplied professional background. No client records, employer source code or internal architecture documents are included.

## Address-change risk and governance

- [FINRA: Customer Account Takeovers](https://www.finra.org/investors/insights/customer-account-takeovers): unauthorized address changes are a warning sign. This supports treating the address-update example cautiously; it does not establish frequency or prescribe its approval control.
- [FINRA 2026 GenAI discussion](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai): governance, supervision, model-risk practice, testing and monitoring inform the proposed mapping to existing processes. The firm confirms the mapping.
- [TypeSafe Jev introduction](https://typesafe.ai/blog/introducing-system-one-models-and-jev): September 2026 introduction. The paper avoids an access-status claim because availability changes.

## Runtime architecture research

- [TypeSafe System One](https://docs.typesafe.ai/concepts/system-one): Jev's typed decisions and probabilities, without generated explanations. Calibration does not guarantee individual semantic correctness.
- [Jev 1.13 limitations](https://docs.typesafe.ai/model-jaggedness/jev-1.13) and [confidence semantics](https://docs.typesafe.ai/confidence): task limitations and question-type-specific output interpretation. Validate the actual rubric and domain; exact invariants remain code checks.
- [MLflow's Jev judge comparison](https://www.mlflow.org/blog/jev-llm-judge/): a 30-case technical-QA comparison and implementation example, not validation for regulated servicing.
- [Anthropic: Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents): code, model and human evaluation, with trajectory and outcome evidence.
- [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents): workflow/agent distinctions inform the separation of reasoning flexibility from execution authority.
- [AWS Builders' Library: safe retries](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/): operation identity and API semantics inform retry and reconciliation design. Adapters cannot create destination guarantees.
- [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework): voluntary governance context, not certification of this design.

## Separate AI-DLC paper

The current delivery architecture and its sources are maintained in [Intent to Production](https://github.com/appliedgenai/intent-to-production) and its [source inventory](https://github.com/appliedgenai/intent-to-production/blob/main/SOURCES.md).

Product references establish documented capabilities, not contractual suitability, security approval, validated integration or measured domain performance. Tool placement and control design are proposals to evaluate.
