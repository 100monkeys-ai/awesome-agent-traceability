# Awesome Agent Traceability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Open tools, standards and papers for building AI agent systems whose actions can be traced, audited and replayed.

An agent that acts on real systems should leave a record a person can follow: what it was asked, what it called, what it changed, under which policy, and how to run it again. This list collects open work on that record: tracing and observability, durable and replayable execution, policy enforcement, tamper-evident logs and provenance, and the research that frames them.

Entries are chosen for what they make traceable, not for popularity. Each description says what the project does, in neutral words.

## Contents

- [Standards and specifications](#standards-and-specifications)
- [Tracing and observability](#tracing-and-observability)
- [Durable and replayable execution](#durable-and-replayable-execution)
- [Policy, guardrails and governance](#policy-guardrails-and-governance)
- [Evaluation with recorded runs](#evaluation-with-recorded-runs)
- [Provenance and tamper-evident logs](#provenance-and-tamper-evident-logs)
- [Papers](#papers)
- [From the maintainers](#from-the-maintainers)

## Standards and specifications

- [OpenTelemetry semantic conventions for generative AI](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - Shared attribute and span names for model calls, agent steps and tool invocations, so traces from different frameworks can be read the same way.
- [OpenLineage](https://github.com/OpenLineage/OpenLineage) - Open standard for collecting lineage metadata about jobs, runs and the datasets they read and write.
- [W3C PROV-O](https://www.w3.org/TR/prov-o/) - W3C ontology for expressing provenance: which agent carried out which activity that used or generated which entity.
- [SLSA](https://slsa.dev/) - Framework of levels and requirements for build provenance, describing how an artifact was produced and by what.
- [C2PA specification](https://c2pa.org/specifications/specifications/2.1/index.html) - Specification for attaching signed provenance manifests to media, including content produced or edited by AI.

## Tracing and observability

- [Langfuse](https://github.com/langfuse/langfuse) - Open-source platform for tracing, evaluating and debugging LLM applications and agents, with self-hosting.
- [Phoenix](https://github.com/Arize-ai/phoenix) - Arize's open-source observability and evaluation tool for LLM applications, built on OpenTelemetry traces.
- [OpenLLMetry](https://github.com/traceloop/openllmetry) - OpenTelemetry-based instrumentation for LLM providers, vector stores and agent frameworks.
- [OpenLIT](https://github.com/openlit/openlit) - OpenTelemetry-native platform to trace, evaluate and guard LLM and agent applications.
- [AgentOps](https://github.com/AgentOps-AI/agentops) - Python SDK for agent monitoring that records agent sessions, LLM calls and costs across common agent frameworks.
- [Helicone](https://github.com/Helicone/helicone) - Open-source LLM observability platform for monitoring, evaluating and experimenting with logged requests.
- [Laminar](https://github.com/lmnr-ai/lmnr) - Open-source observability platform for AI agents, with traces of agent steps and model calls.
- [Logfire](https://github.com/pydantic/logfire) - Pydantic's OpenTelemetry-based observability SDK for LLM and agent systems.
- [Opik](https://github.com/comet-ml/opik) - Comet's open-source tool to trace, evaluate and monitor LLM applications, RAG systems and agentic workflows.
- [Weave](https://github.com/wandb/weave) - Weights & Biases toolkit for tracing and evaluating AI-powered applications.
- [MLflow Tracing](https://github.com/mlflow/mlflow) - MLflow's tracing records inputs, outputs and intermediate steps of LLM and agent runs alongside experiments and models.

## Durable and replayable execution

- [Temporal](https://github.com/temporalio/temporal) - Durable execution service whose workflow event history records every step and lets a workflow be replayed deterministically.
- [Restate](https://github.com/restatedev/restate) - Platform for durable, fault-tolerant services and workflows that journals each step so execution resumes after failures.
- [DBOS Transact](https://github.com/dbos-inc/dbos-transact-py) - Python library for durable workflows that checkpoints each step in a Postgres database.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Agent orchestration library with persisted checkpoints, which allow inspecting, resuming and replaying a run from a saved state.

## Policy, guardrails and governance

- [Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) - Microsoft's toolkit for agent policy enforcement, zero-trust identity, execution sandboxing and reliability engineering.
- [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) - NVIDIA's toolkit for programmable rails on the inputs, outputs and tool use of LLM applications.
- [Guardrails](https://github.com/guardrails-ai/guardrails) - Python framework that validates LLM inputs and outputs against declared validators.

## Evaluation with recorded runs

- [Inspect](https://github.com/UKGovernmentBEIS/inspect_ai) - The UK AI Security Institute's framework for LLM and agent evaluations, which writes a log of every sample, message and tool call.
- [promptfoo](https://github.com/promptfoo/promptfoo) - CLI and library for testing and red-teaming prompts, agents and RAG pipelines with stored, comparable results.
- [Agenta](https://github.com/Agenta-AI/agenta) - Open-source workspace for building agents and LLM applications with prompt versioning, evaluation and tracing.

## Provenance and tamper-evident logs

- [Rekor](https://github.com/sigstore/rekor) - Sigstore's append-only, verifiable transparency log for signed software supply-chain metadata.
- [in-toto](https://github.com/in-toto/in-toto) - Framework that records signed attestations for each step of a supply chain so the whole chain can be verified.
- [Marquez](https://github.com/MarquezProject/marquez) - Reference implementation of OpenLineage that collects and visualises job and dataset lineage.

## Papers

- [Visibility into AI Agents](https://arxiv.org/abs/2401.13138) - Chan et al., 2024. Proposes agent identifiers, real-time monitoring and activity logging as measures for visibility into deployed agents.
- [IDs for AI Systems](https://arxiv.org/abs/2406.12137) - Chan et al., 2024. Examines identifiers attached to AI system instances so that their outputs and actions can be attributed.
- [AgentOps: Enabling Observability of LLM Agents](https://arxiv.org/abs/2411.05285) - Dong et al., 2024. Taxonomy of the artifacts and data to trace across the lifecycle of LLM agents.
- [Infrastructure for AI Agents](https://arxiv.org/abs/2501.10114) - Chan et al., 2025. Frames attribution, interaction and response as infrastructure functions for agents acting in the world.

## From the maintainers

This list is maintained by 100monkeys.ai. We build the three projects below; they are listed here, separately, so that the entries above stay neutral.

- [AEGIS by 100monkeys.ai](https://github.com/100monkeys-ai/aegis-orchestrator) - AGPL-3.0, self-hosted agent orchestrator, in beta, that enforces manifest-declared network and filesystem policy in the orchestrator and runs agents in isolated runtimes with durable workflow state.
- [Carbon Forge](https://carbonforge.dev/) - Hosted source control and shared record for people and agents, where every revision and changeset is hash-chained and a landing is one all-or-nothing changeset. Public workspaces are free, and every account includes one free private workspace.
- [Zaru](https://github.com/100monkeys-ai/zaru-cli) - Apache-2.0 terminal agent that writes every model reply, tool call, permission decision and tool result to a plain-text transcript. Pre-alpha.

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, 100monkeys.ai has waived all copyright and related or neighboring rights to this work.
