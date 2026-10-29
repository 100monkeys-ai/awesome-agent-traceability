# Awesome Agent Traceability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Open tools, standards and papers for building AI agent systems whose actions can be traced, audited and replayed.

An agent that acts on real systems should leave a record a person can follow: what it was asked, what it called, what it changed, under which policy, and how to run it again. This list collects open work on that record: tracing and observability, durable and replayable execution, policy enforcement, tamper-evident logs and provenance, and the research that frames them.

Entries are chosen for what they make traceable, not for popularity. Each description says what the project does, in neutral words.

## Contents

- [Standards and specifications](#standards-and-specifications)
- [Regulation, frameworks and policy](#regulation-frameworks-and-policy)
- [Tracing and observability](#tracing-and-observability)
- [Gateways and proxies](#gateways-and-proxies)
- [Durable and replayable execution](#durable-and-replayable-execution)
- [Policy, guardrails and governance](#policy-guardrails-and-governance)
- [MCP and tool security](#mcp-and-tool-security)
- [Sandboxes and isolation](#sandboxes-and-isolation)
- [Agent memory and state](#agent-memory-and-state)
- [Evaluation with recorded runs](#evaluation-with-recorded-runs)
- [Provenance and tamper-evident logs](#provenance-and-tamper-evident-logs)
- [Papers](#papers)
- [From the maintainers](#from-the-maintainers)

## Standards and specifications

- [Agent2Agent (A2A) Protocol](https://github.com/a2aproject/A2A) - Open protocol for communication and interoperability between agent applications, with defined task and message objects exchanged between agents.
- [C2PA specification](https://c2pa.org/specifications/specifications/2.1/index.html) - Specification for attaching signed provenance manifests to media, including content produced or edited by AI.
- [CycloneDX ML-BOM](https://cyclonedx.org/capabilities/mlbom/) - CycloneDX bill-of-materials format for machine learning models, datasets and their provenance.
- [in-toto Attestation Framework](https://github.com/in-toto/attestation) - Specification for signed, typed statements about software artifacts, used to carry provenance such as SLSA predicates.
- [Model Context Protocol specification](https://modelcontextprotocol.io/specification) - Specification of the protocol through which models and agents discover and call external tools, resources and prompts.
- [OpenInference](https://github.com/Arize-ai/openinference) - Semantic conventions and OpenTelemetry instrumentation for tracing LLM calls, retrievals, tools and agent steps.
- [OpenLineage](https://github.com/OpenLineage/OpenLineage) - Open standard for collecting lineage metadata about jobs, runs and the datasets they read and write.
- [OpenTelemetry semantic conventions for agent spans](https://opentelemetry.io/docs/specs/semconv/gen-ai/gen-ai-agent-spans/) - Span names and attributes for creating and invoking agents, part of the OpenTelemetry generative AI conventions.
- [OpenTelemetry semantic conventions for generative AI](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - Shared attribute and span names for model calls, agent steps and tool invocations, so traces from different frameworks can be read the same way.
- [SCITT](https://datatracker.ietf.org/wg/scitt/about/) - IETF working group on Supply Chain Integrity, Transparency and Trust, defining signed statements registered in append-only transparency services.
- [SLSA](https://slsa.dev/) - Framework of levels and requirements for build provenance, describing how an artifact was produced and by what.
- [W3C PROV-O](https://www.w3.org/TR/prov-o/) - W3C ontology for expressing provenance: which agent carried out which activity that used or generated which entity.

## Regulation, frameworks and policy

- [EU AI Act, Article 12: Record-keeping](https://artificialintelligenceact.eu/article/12/) - Requires high-risk AI systems to allow the automatic recording of events (logs) over their lifetime.
- [EU AI Act, Article 14: Human oversight](https://artificialintelligenceact.eu/article/14/) - Requires high-risk AI systems to be designed so that natural persons can effectively oversee them while in use.
- [MITRE ATLAS](https://atlas.mitre.org/) - Knowledge base of adversary tactics and techniques against AI-enabled systems, drawn from real-world observations and demonstrations.
- [NIST AI 100-2 E2025](https://csrc.nist.gov/pubs/ai/100/2/e2025/final) - NIST taxonomy and terminology of attacks on machine learning systems and their mitigations.
- [NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) - Generative AI profile of the NIST AI Risk Management Framework, listing risks specific to generative AI and suggested actions.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) - Voluntary framework organised around the Govern, Map, Measure and Manage functions for managing risks of AI systems.
- [NIST AI RMF Playbook](https://www.nist.gov/itl/ai-risk-management-framework/nist-ai-rmf-playbook) - Suggested actions, references and documentation practices for each outcome of the NIST AI Risk Management Framework.
- [OECD AI Principles](https://oecd.ai/en/ai-principles) - Intergovernmental principles for trustworthy AI, including transparency, explainability and accountability.
- [OWASP Agentic AI Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/) - OWASP GenAI Security Project guide to threats specific to agentic AI systems and their mitigations.
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) - OWASP list of the most critical security risks for applications built on large language models.

## Tracing and observability

- [AgentOps](https://github.com/AgentOps-AI/agentops) - Python SDK for agent monitoring that records agent sessions, LLM calls and costs across common agent frameworks.
- [AgentSight](https://github.com/eunomia-bpf/agentsight) - System-level observability for AI agents that uses eBPF to capture model traffic and process activity from outside the agent.
- [Evidently](https://github.com/evidentlyai/evidently) - Open-source framework to evaluate, test and monitor ML and LLM systems, with tracing for LLM applications.
- [Helicone](https://github.com/Helicone/helicone) - Open-source LLM observability platform for monitoring, evaluating and experimenting with logged requests.
- [Jaeger](https://github.com/jaegertracing/jaeger) - CNCF distributed tracing platform that stores and visualises OpenTelemetry traces.
- [Laminar](https://github.com/lmnr-ai/lmnr) - Open-source observability platform for AI agents, with traces of agent steps and model calls.
- [Langfuse](https://github.com/langfuse/langfuse) - Open-source platform for tracing, evaluating and debugging LLM applications and agents, with self-hosting.
- [Langtrace](https://github.com/Scale3-Labs/langtrace) - Open-source, OpenTelemetry-based tracing and evaluation tool for LLM applications and frameworks.
- [LangWatch](https://github.com/langwatch/langwatch) - Open-source platform for tracing, evaluating and testing LLM agents.
- [Logfire](https://github.com/pydantic/logfire) - Pydantic's OpenTelemetry-based observability SDK for LLM and agent systems.
- [MLflow Tracing](https://github.com/mlflow/mlflow) - MLflow's tracing records inputs, outputs and intermediate steps of LLM and agent runs alongside experiments and models.
- [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) - Multi-agent framework with built-in tracing of agent runs, model calls, tool calls, handoffs and guardrails.
- [OpenLIT](https://github.com/openlit/openlit) - OpenTelemetry-native platform to trace, evaluate and guard LLM and agent applications.
- [OpenLLMetry](https://github.com/traceloop/openllmetry) - OpenTelemetry-based instrumentation for LLM providers, vector stores and agent frameworks.
- [OpenTelemetry Collector](https://github.com/open-telemetry/opentelemetry-collector) - Vendor-neutral service to receive, process and export traces, metrics and logs, including those from instrumented LLM applications.
- [Opik](https://github.com/comet-ml/opik) - Comet's open-source tool to trace, evaluate and monitor LLM applications, RAG systems and agentic workflows.
- [Phoenix](https://github.com/Arize-ai/phoenix) - Arize's open-source observability and evaluation tool for LLM applications, built on OpenTelemetry traces.
- [RagaAI Catalyst](https://github.com/raga-ai-hub/RagaAI-Catalyst) - Python SDK for agent observability that traces agent, LLM and tool calls and shows them as a timeline and execution graph.
- [SigNoz](https://github.com/SigNoz/signoz) - OpenTelemetry-native observability platform for traces, metrics and logs.
- [Tempo](https://github.com/grafana/tempo) - Grafana's distributed tracing backend that stores traces in object storage.
- [TruLens](https://github.com/truera/trulens) - Library for evaluating and tracking LLM experiments and agents, with tracing of each step.
- [Weave](https://github.com/wandb/weave) - Weights & Biases toolkit for tracing and evaluating AI-powered applications.

## Gateways and proxies

- [agentgateway](https://github.com/agentgateway/agentgateway) - Proxy for agent-to-tool and agent-to-agent traffic over MCP and A2A, with authorisation policy and observability.
- [LiteLLM](https://github.com/BerriAI/litellm) - Gateway and SDK that calls many LLM APIs in one format, with logging callbacks, cost tracking and guardrails.
- [Portkey Gateway](https://github.com/Portkey-AI/gateway) - AI gateway that routes requests to many LLM providers, with guardrails and request logging.
- [Traceloop Hub](https://github.com/traceloop/hub) - LLM gateway written in Rust that emits OpenTelemetry traces for each request.

## Durable and replayable execution

- [Burr](https://github.com/apache/burr) - Apache library for building decision-making applications as state machines, with persisted state and a UI to trace and replay each step.
- [Cadence](https://github.com/cadence-workflow/cadence) - Durable orchestration engine for long-running workflows, with a recorded workflow history.
- [Dapr Agents](https://github.com/dapr/dapr-agents) - Framework for agents built on Dapr workflows, with durable execution, state and telemetry.
- [DBOS Transact](https://github.com/dbos-inc/dbos-transact-py) - Python library for durable workflows that checkpoints each step in a PostgreSQL database.
- [Golem](https://github.com/golemcloud/golem) - Platform for durable agents and applications that persists execution state so work resumes without loss or duplication.
- [Hatchet](https://github.com/hatchet-dev/hatchet) - Orchestration engine for background tasks, AI agents and durable workflows.
- [Inngest](https://github.com/inngest/inngest) - Workflow orchestration platform for durable, stateful step functions and AI workflows.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Agent orchestration library with persisted checkpoints, which allow inspecting, resuming and replaying a run from a saved state.
- [Restate](https://github.com/restatedev/restate) - Platform for durable, fault-tolerant services and workflows that journals each step so execution resumes after failures.
- [Temporal](https://github.com/temporalio/temporal) - Durable execution service whose workflow event history records every step and lets a workflow be replayed deterministically.
- [Trigger.dev](https://github.com/triggerdotdev/trigger.dev) - Platform for building and running durable AI agents and workflows in TypeScript, with run logs and traces.

## Policy, guardrails and governance

- [Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) - Microsoft's toolkit for agent policy enforcement, zero-trust identity, execution sandboxing and reliability engineering.
- [AI Verify](https://github.com/aiverify-foundation/aiverify) - Testing toolkit from the AI Verify Foundation for checking AI systems against governance principles and producing reports.
- [Cedar](https://github.com/cedar-policy/cedar) - Policy language and evaluation engine for authorisation decisions that can be analysed and audited.
- [Guardrails](https://github.com/guardrails-ai/guardrails) - Python framework that validates LLM inputs and outputs against declared validators.
- [Invariant](https://github.com/invariantlabs-ai/invariant) - Guardrails for agent systems, written as rules over agent traces and tool calls.
- [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) - NVIDIA's toolkit for programmable rails on the inputs, outputs and tool use of LLM applications.
- [Open Policy Agent](https://github.com/open-policy-agent/opa) - General-purpose policy engine with a declarative language and decision logs that record each policy decision.
- [Presidio](https://github.com/data-privacy-stack/presidio) - Framework for detecting and redacting personal data in text, images and structured data, useful before traces and logs are stored.
- [Purple Llama](https://github.com/meta-llama/PurpleLlama) - Meta's set of tools, including Llama Guard and CyberSecEval, to assess and improve LLM security.

## MCP and tool security

- [agent-scan](https://github.com/snyk/agent-scan) - Security scanner for AI agents, MCP servers and agent skills.
- [MCP Inspector](https://github.com/modelcontextprotocol/inspector) - Visual testing tool for MCP servers that calls their tools, resources and prompts and shows the responses.
- [mcp-audit](https://github.com/P4ST4S/mcp-audit) - Proxy for MCP clients and servers that records signed audit trails for tool calls and other protocol messages, with redaction and policy controls.
- [ToolHive](https://github.com/stacklok/toolhive) - Platform for running and managing MCP servers in isolated containers with access controls.

## Sandboxes and isolation

- [E2B](https://github.com/e2b-dev/E2B) - Open-source sandboxed cloud environments for running agent-generated code.
- [Firecracker](https://github.com/firecracker-microvm/firecracker) - Virtual machine monitor for lightweight microVMs that isolate workloads with hardware virtualisation.
- [gVisor](https://github.com/google/gvisor) - Application kernel that runs containers behind a user-space reimplementation of the Linux system call interface.
- [Kata Containers](https://github.com/kata-containers/kata-containers) - Lightweight virtual machines that run as containers, giving each workload its own kernel.
- [Landlock](https://landlock.io/) - Linux security module that lets an unprivileged process restrict its own filesystem and network access.
- [microsandbox](https://github.com/superradcompany/microsandbox) - Local-first microVM runtime and library for running untrusted code.
- [nsjail](https://github.com/google/nsjail) - Process isolation tool built on Linux namespaces, cgroups, resource limits and seccomp-bpf filters.
- [Sandbox Runtime](https://github.com/anthropics/sandbox-runtime) - Anthropic's tool for enforcing filesystem and network restrictions on arbitrary processes at the OS level, without a container.
- [Wasmtime](https://github.com/bytecodealliance/wasmtime) - WebAssembly runtime that runs code with only the capabilities the host grants it.

## Agent memory and state

- [Graphiti](https://github.com/getzep/graphiti) - Framework for temporally aware knowledge graphs for agents, which record when each fact held and the episode it came from.
- [Letta](https://github.com/letta-ai/letta) - Platform for stateful agents whose memory and state are persisted and can be inspected.
- [Mem0](https://github.com/mem0ai/mem0) - Memory layer for AI agents that stores, updates and retrieves memories, with a history of changes to each memory.

## Evaluation with recorded runs

- [Agenta](https://github.com/Agenta-AI/agenta) - Open-source workspace for building agents and LLM applications with prompt versioning, evaluation and tracing.
- [AgentDojo](https://github.com/ethz-spylab/agentdojo) - Environment for evaluating prompt injection attacks and defences on tool-using LLM agents.
- [ControlArena](https://github.com/UKGovernmentBEIS/control-arena) - UK AI Security Institute's settings and protocols for AI control experiments, built on Inspect.
- [DeepEval](https://github.com/confident-ai/deepeval) - Framework for unit-testing LLM outputs and agents with metrics, with tracing of components.
- [garak](https://github.com/NVIDIA/garak) - LLM vulnerability scanner that probes models and logs every attempt and result.
- [Giskard](https://github.com/Giskard-AI/giskard-oss) - Open-source evaluation and testing library for LLM agents.
- [HELM](https://github.com/stanford-crfm/helm) - Stanford CRFM framework for holistic, reproducible and transparent evaluation of foundation models.
- [Inspect](https://github.com/UKGovernmentBEIS/inspect_ai) - The UK AI Security Institute's framework for LLM and agent evaluations, which writes a log of every sample, message and tool call.
- [Language Model Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness) - EleutherAI framework for evaluating language models on many tasks, with options to log every sample.
- [OpenAI Evals](https://github.com/openai/evals) - Framework and registry of benchmarks for evaluating LLMs and LLM systems.
- [promptfoo](https://github.com/promptfoo/promptfoo) - CLI and library for testing and red-teaming prompts, agents and RAG pipelines with stored, comparable results.
- [PyRIT](https://github.com/microsoft/PyRIT) - Microsoft's Python Risk Identification Tool for red-teaming generative AI systems, with stored conversations and scores.
- [Ragas](https://github.com/vibrantlabsai/ragas) - Library for evaluating LLM applications, including retrieval-augmented generation and agents.
- [τ-bench](https://github.com/sierra-research/tau-bench) - Benchmark of tool-agent-user interaction in simulated customer service domains.

## Provenance and tamper-evident logs

- [c2pa-rs](https://github.com/contentauth/c2pa-rs) - Rust SDK for reading, writing and validating C2PA provenance manifests.
- [Cosign](https://github.com/sigstore/cosign) - Sigstore tool for signing and verifying containers, binaries and attestations, with entries recorded in a transparency log.
- [Dolt](https://github.com/dolthub/dolt) - SQL database with Git-style version control: every write is a commit that can be diffed, branched and reverted.
- [DVC](https://github.com/treeverse/dvc) - Data Version Control: versions data, models and experiments alongside Git so a result can be reproduced.
- [immudb](https://github.com/codenotary/immudb) - Database with an immutable, cryptographically verifiable history of every change.
- [in-toto](https://github.com/in-toto/in-toto) - Framework that records signed attestations for each step of a supply chain so the whole chain can be verified.
- [lakeFS](https://github.com/treeverse/lakeFS) - Version control for data lakes, with commits, branches and reproducible snapshots of object storage.
- [Marquez](https://github.com/MarquezProject/marquez) - Reference implementation of OpenLineage that collects and visualises job and dataset lineage.
- [Model Transparency](https://github.com/sigstore/model-transparency) - Library and CLI for signing and verifying machine learning models.
- [Rekor](https://github.com/sigstore/rekor) - Sigstore's append-only, verifiable transparency log for signed software supply-chain metadata.
- [SLSA Verifier](https://github.com/slsa-framework/slsa-verifier) - Tool for verifying SLSA build provenance against an artifact.
- [SynthID Text](https://github.com/google-deepmind/synthid-text) - Google DeepMind's reference implementation of a watermark for generated text and its detector.
- [Tessera](https://github.com/transparency-dev/tessera) - Go library for building tile-based transparency logs.
- [Trillian](https://github.com/google/trillian) - Verifiable data store built on Merkle trees, used to run transparency logs.

## Papers

- [A Survey on Trustworthy LLM Agents: Threats and Countermeasures](https://arxiv.org/abs/2503.09648) - Yu et al., 2025. Surveys threats to LLM agents and the countermeasures proposed for them.
- [Agent Security Bench (ASB)](https://arxiv.org/abs/2410.02644) - Zhang et al., 2024. Formalises and benchmarks attacks and defences for LLM-based agents.
- [Agent-SafetyBench: Evaluating the Safety of LLM Agents](https://arxiv.org/abs/2412.14470) - Zhang et al., 2024. Benchmark of interaction environments and test cases for the safety of LLM agents.
- [AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents](https://arxiv.org/abs/2406.13352) - Debenedetti et al., 2024. Introduces an extensible environment of tasks and attacks for tool-using agents.
- [AgentMonitor: A Plug-and-Play Framework for Predictive and Secure Multi-Agent Systems](https://arxiv.org/abs/2408.14972) - Chan et al., 2024. Captures agent inputs and outputs at each step to predict task performance and correct unsafe behaviour.
- [AgentOps: Enabling Observability of LLM Agents](https://arxiv.org/abs/2411.05285) - Dong et al., 2024. Taxonomy of the artifacts and data to trace across the lifecycle of LLM agents.
- [AI Control: Improving Safety Despite Intentional Subversion](https://arxiv.org/abs/2312.06942) - Greenblatt et al., 2023. Evaluates protocols, such as trusted monitoring, that keep a model safe even if it tries to subvert them.
- [Auditing large language models: a three-layered approach](https://arxiv.org/abs/2302.08500) - Mökander et al., 2023. Proposes governance, model and application audits as complementary layers.
- [Black-Box Access is Insufficient for Rigorous AI Audits](https://arxiv.org/abs/2401.14446) - Casper et al., 2024. Argues that audits need white-box and outside-the-box access, such as to training and deployment information.
- [Closing the AI Accountability Gap](https://arxiv.org/abs/2001.00973) - Raji et al., 2020. Defines an end-to-end framework for internal algorithmic auditing across the development lifecycle.
- [Datasheets for Datasets](https://arxiv.org/abs/1803.09010) - Gebru et al., 2018. Proposes documenting each dataset's motivation, composition, collection process and recommended uses.
- [Defeating Prompt Injections by Design](https://arxiv.org/abs/2503.18813) - Debenedetti et al., 2025. Introduces CaMeL, which separates control and data flows so untrusted data cannot change an agent's program.
- [Fully Autonomous AI Agents Should Not be Developed](https://arxiv.org/abs/2502.02649) - Mitchell et al., 2025. Argues that risks grow with agent autonomy and that human control should be kept.
- [Governing AI Agents](https://arxiv.org/abs/2501.07913) - Kolt, 2025. Applies principal-agent theory and agency law to the governance of AI agents, including visibility and monitoring.
- [Identifying the Risks of LM Agents with an LM-Emulated Sandbox](https://arxiv.org/abs/2309.15817) - Ruan et al., 2023. Introduces ToolEmu, which emulates tool execution to find risky agent behaviour.
- [IDs for AI Systems](https://arxiv.org/abs/2406.12137) - Chan et al., 2024. Examines identifiers attached to AI system instances so that their outputs and actions can be attributed.
- [Infrastructure for AI Agents](https://arxiv.org/abs/2501.10114) - Chan et al., 2025. Frames attribution, interaction and response as infrastructure functions for agents acting in the world.
- [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993) - Mitchell et al., 2018. Proposes short documents that report a model's intended use, evaluation and limitations.
- [Non-Determinism of "Deterministic" LLM Settings](https://arxiv.org/abs/2408.04667) - Atil et al., 2024. Measures how much LLM outputs vary across runs with settings meant to be deterministic.
- [R-Judge: Benchmarking Safety Risk Awareness for LLM Agents](https://arxiv.org/abs/2401.10019) - Yuan et al., 2024. Benchmarks whether LLMs can judge safety risks from records of agent interactions.
- [τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains](https://arxiv.org/abs/2406.12045) - Yao et al., 2024. Measures agent reliability over repeated trials with simulated users and domain policies.
- [The Data Provenance Initiative](https://arxiv.org/abs/2310.16787) - Longpre et al., 2023. Audits the licensing and attribution of fine-tuning datasets and traces their lineage.
- [Toward Trustworthy AI Development: Mechanisms for Supporting Verifiable Claims](https://arxiv.org/abs/2004.07213) - Brundage et al., 2020. Recommends institutional, software and hardware mechanisms, including audit trails, for verifiable claims about AI systems.
- [TRiSM for Agentic AI](https://arxiv.org/abs/2506.04133) - Raza et al., 2025. Reviews trust, risk and security management for LLM-based multi-agent systems.
- [Visibility into AI Agents](https://arxiv.org/abs/2401.13138) - Chan et al., 2024. Proposes agent identifiers, real-time monitoring and activity logging as measures for visibility into deployed agents.
- [Watson: A Cognitive Observability Framework for the Reasoning of LLM-Powered Agents](https://arxiv.org/abs/2411.03455) - Rombaut et al., 2024. Recovers the implicit reasoning behind agent actions to make it observable for debugging.
- [Which Agent Causes Task Failures and When?](https://arxiv.org/abs/2505.00212) - Zhang et al., 2025. Defines automated failure attribution, finding the agent and step responsible from multi-agent logs.
- [Why Do Multi-Agent LLM Systems Fail?](https://arxiv.org/abs/2503.13657) - Cemri et al., 2025. Builds a taxonomy of multi-agent failure modes from annotated execution traces.

## From the maintainers

This list is maintained by 100monkeys.ai. We build the three projects below; they are listed here, separately, so that the entries above stay neutral.

- [AEGIS by 100monkeys.ai](https://github.com/100monkeys-ai/aegis-orchestrator) - AGPL-3.0, self-hosted agent orchestrator, in beta, that enforces manifest-declared network and filesystem policy in the orchestrator and runs agents in isolated runtimes with durable workflow state.
- [Carbon Forge](https://carbonforge.dev/) - Hosted source control and shared record for people and agents, where every revision and changeset is hash-chained and a landing is one all-or-nothing changeset. Public workspaces are free, and every account includes one free private workspace.
- [Zaru](https://github.com/100monkeys-ai/zaru-cli) - Apache-2.0 terminal agent that writes every model reply, tool call, permission decision and tool result to a plain-text transcript. Pre-alpha.

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) first.
