# Sources and claim boundaries

Reviewed 28 September 2026. Links below support external context; the architectural proposals and synthetic examples are the author's analysis.

| Source | Used for | Boundary |
|---|---|---|
| [DORA: Balancing AI tensions](https://dora.dev/insights/balancing-ai-tensions/) | Association between adoption, throughput and instability. | Observational research; not a prediction of any firm's return. |
| [METR early-2025 study](https://arxiv.org/abs/2507.09089) | A bounded randomized developer-productivity result. | Specific developers, repositories and tools; not a general claim about current tools. |
| [METR February 2026 update](https://metr.org/blog/2026-02-24-uplift-update/) | Limitations affecting newer productivity measurements. | Avoid extrapolating the earlier slowdown into 2026. |
| [FINRA 2026 GenAI report section](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report/gen-ai) | Agent risks concerning authority, auditability and data. | Report discussion is not a prescription for this architecture or a new universal logging requirement. |
| [MCP authorization, 2025-11-25](https://modelcontextprotocol.io/specification/2025-11-25/basic/authorization) | Protocol-level authorization for protected HTTP MCP services. | Business entitlements and transaction approvals require additional implementation. |
| [MCP security guidance](https://modelcontextprotocol.io/docs/2025-11-25/tutorials/security/security_best_practices) | Audience validation and prohibition of token passthrough. | Does not establish end-to-end compliance or remove destination authorization duties. |

The portfolio does not claim legal compliance, measured production savings, an implemented policy engine, or validated performance of the sample design. Author experience is based on the author's supplied professional background. No client records, employer source code or internal architecture documents are included.

## AI-DLC companion

The [article](03-intent-driven-ai-dlc.md) and [playbook](ai-dlc-implementation-playbook.md) use these primary sources, checked 28 September 2026:

- [AWS AI-DLC methodology](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle/): inception, construction and operations with human validation. The six-layer architecture in this portfolio is the author's synthesis.
- [DORA delivery metrics](https://dora.dev/guides/dora-metrics/): definitions of delivery performance measures. Additional intent, review and evidence metrics are labeled as proposed measures.
- [Kiro specs](https://kiro.dev/docs/specs/), [Backstage catalog](https://backstage.io/docs/features/software-catalog/) and [Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html): examples of specification, catalog and retrieval capabilities.
- [GitHub Copilot cloud agent](https://docs.github.com/en/copilot/concepts/agents/cloud-agent/about-cloud-agent), [Temporal](https://docs.temporal.io/) and [GitHub deployment environments](https://docs.github.com/en/actions/reference/workflows-and-actions/deployments-and-environments): examples of agent execution, durable workflows and deployment controls.
- [OPA](https://www.openpolicyagent.org/docs), [Promptfoo](https://www.promptfoo.dev/docs/intro/) and [Langfuse](https://langfuse.com/docs): examples of policy evaluation, AI testing and observability/evaluation tooling.
- [OpenTelemetry GenAI conventions](https://github.com/open-telemetry/semantic-conventions-genai): telemetry concepts and versioned conventions. Relevant specifications remain under development.

Product capability references do not establish contractual suitability, licensing, security approval, integration completeness or performance. Buy/adopt/build choices are architecture recommendations. All worked numerical examples are illustrative, not measured employer outcomes.
