# AI Matrix Demo Mainline

This document gives one coherent review path across the five AI engineering repositories.

## Story

The matrix shows a full AI engineering stack:

1. `knowledgeops-agent` provides the governed AI platform baseline: RAG, workflow state, evidence, memory, graph retrieval, evaluation, and observability.
2. `tianji-ai-agent` consumes that platform layer as a business Agent case: routing, tool calling, customer-service flow, structured SSE events, and card UI.
3. `nebula-kb` manages knowledge assets before and after retrieval: ingestion lifecycle, governance, feedback, quality review, and operations dashboards.
4. `forgepilot-studio` demonstrates an AI engineering execution workspace: task protocol, runtime execution, tool governance, audit replay, and delivery reports.
5. `however-microservices-lab` shows the cloud-native deployment layer: multi-language services, Kubernetes, gRPC, local model fallback, and AI service integration.

## 10-Minute Pass

1. Start with the [Featured Projects](../README.md#featured-projects) overview.
2. Open `knowledgeops-agent` and scan the README hero, architecture, evidence links, and release.
3. Open `tianji-ai-agent` and scan the RouteAgent diagram, SSE event flow, and demo GIF.
4. Open each repository's `docs/evidence/README.md`.

## 30-Minute Pass

1. Run or inspect the `knowledgeops-agent` demo path and observability docs.
2. Run or inspect the `tianji-ai-agent` dev-demo path and frontend screenshots.
3. Review `nebula-kb` lifecycle demo and operations screenshots.
4. Review `forgepilot-studio` task console, runtime log, and module map.
5. Review `however-microservices-lab` local demo, CI workflows, and deployment docs.

## Source Deep Dive

- KnowledgeOps Agent: workflow, RAG, retrieval, memory, graph, evidence, and observability modules.
- Tianji AI Agent: `AgentServiceImpl`, `RouteAgent`, business sub-agents, tools, SSE event models, and React visualizations.
- NebulaKB: knowledge lifecycle services, document ingestion, feedback, and operations boundaries.
- ForgePilot Studio: control plane, task protocol, audit timeline, model configuration, and MCP tooling.
- However Microservices Lab: shopping assistant service, model provider abstraction, K8s manifests, CI, SBOM, and local demo path.
