# 项目方向、改造重点与来源

[返回主页](../README.md#featured-projects) · [演示与验证入口](ai-matrix-demo-mainline.md)

这里介绍主页展示的六个项目，帮助读者按兴趣选择阅读入口。各项目的来源、实现范围与验证条件分别说明。

## Java 后端与业务 Agent

### KnowledgeOps Agent

[项目主页](https://github.com/however-yir/knowledgeops-agent) · [架构](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/architecture-enterprise.md) · [验证入口](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)

- 基础：Spring Boot / Spring AI 与现成的检索、数据库和可观测性组件。
- 工程重点：租户范围内的检索、异步文档入库、引用与证据输出、权限审计和评测流程。
- 状态：面向生产需求设计的平台原型；具体能力和默认路径限制以仓库 README 为准。部署说明与自动化测试需要结合实际运行环境判断。

### Tianji AI Agent

[项目主页](https://github.com/however-yir/tianji-ai-agent) · [来源与改造清单](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/provenance.md) · [已知限制](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/known-limitations.md)

- 继承部分：天机教育平台的课程、交易、用户等业务微服务。
- 新增工作：业务 Agent 路由、动作策略、执行预算与循环检测、SSE 契约、运行记录及回归评测。
- 阅读重点：模型提出动作后，策略和运行时如何控制实际执行；购买流程如何停在订单预确认。
- 验证边界：仓库中的 160 条离线路由用例用于路由与契约回归；真实模型表现及跨仓库集成需按各自运行条件验证。

## 评测门禁、知识运营与云原生工程

### ragproof

[项目主页](https://github.com/however-yir/ragproof) · [架构设计](https://github.com/however-yir/ragproof/blob/main/docs/ARCHITECTURE.md) · [公开 Benchmark 报告](https://github.com/however-yir/ragproof/blob/main/docs/PUBLIC_BENCHMARK_REPORT.md)

- 定位：框架无关的 RAG 质量评测与回归测试 CLI 门禁工具。
- 工程重点：调用既有 RAG HTTP API，计算 Recall@K、MRR、Faithfulness（真实性与幻觉评测）及引用准确率；生成可比版本报告，并在质量退化时通过非零退出码阻断 CI。
- 阅读重点：评测指标如何与 CI/CD 门禁策略绑定，以及如何针对 Prompt、切片规则或模型变更进行免侵入的自动化防退化验证。

### NebulaKB

[项目主页](https://github.com/however-yir/nebula-kb) · [定位与边界](https://github.com/however-yir/nebula-kb/blob/main/docs/repo-positioning.md) · [验证入口](https://github.com/however-yir/nebula-kb/blob/main/docs/evidence/README.md)

- 基础：Django、PostgreSQL、Redis 与仓库保留的知识库及检索组件；第三方组件的来源与许可按各自文件说明。
- 工程重点：文档接入、处理状态、检索反馈、低质量答案回看和知识运营后台。
- 阅读重点：知识资产从入库到反馈的生命周期。它与 KnowledgeOps 的 Java 后端方向互补，单独部署和验证。

### ForgePilot Studio

[项目主页](https://github.com/however-yir/forgepilot-studio) · [与 OpenHands 的差异](https://github.com/however-yir/forgepilot-studio/blob/main/docs/fork-differentiation.md) · [验证入口](https://github.com/however-yir/forgepilot-studio/blob/main/docs/evidence/README.md)

- 继承部分：OpenHands 的 Agent 循环、沙箱运行时、文件编辑和命令执行基础。
- 新增或改造：任务台、审计导出、工具注册表，以及控制平面、团队权限和预算策略等模块。
- 状态：核心治理模块仍为实验性库代码与单元测试，尚未接入默认 OpenHands 执行链路。默认运行时已生效的能力，应与设计目标分别阅读。

### However Microservices Lab

[项目主页](https://github.com/however-yir/however-microservices-lab) · [上游与改造清单](https://github.com/however-yir/however-microservices-lab/blob/main/docs/diff-from-upstream.md) · [验证入口](https://github.com/however-yir/however-microservices-lab/blob/main/docs/evidence/README.md)

- 继承部分：Google Online Boutique 的电商微服务、gRPC 协议及 Kubernetes 部署基础。
- 新增或改造：AI Shopping Assistant、Gemini/Ollama 后端切换、JSON 商品数据兜底、本地演示路径及质量检查。
- 阅读重点：AI 服务如何接入既有业务，依赖不可用时怎样处理，以及如何验证部署组合。
- 状态：云原生集成实验室；不同演示路径有不同依赖与启用条件。

## 项目之间的关系

KnowledgeOps 与 Tianji 提供显式的跨仓库集成路径，入口见 [KnowledgeOps 验证文档](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)。ragproof 可作为独立的评测门禁直接对接 KnowledgeOps 等 RAG 服务的 HTTP 接口。其余项目展示知识运营、工程执行与微服务等方向，分别说明自己的运行条件。

实际阅读可从一个项目的业务问题出发，再看实现、测试与结果。[证据说明](portfolio-governance.md)解释如何区分演示、回归测试和真实运行结果。
