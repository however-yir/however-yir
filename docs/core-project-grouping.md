# 项目方向、改造重点与来源

[返回主页](../README.md#代表项目) · [演示与验证入口](ai-matrix-demo-mainline.md)

这里介绍主页当前置顶的两个项目：**KnowledgeOps Agent** 与 **Tianji AI Agent**，分别展示知识检索平台与业务 Agent 的工程实践。两个项目的来源、实现范围与验证条件分别说明。

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

## 项目之间的关系

KnowledgeOps 与 Tianji 提供显式的跨仓库集成路径，入口见 [KnowledgeOps 验证文档](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)。KnowledgeOps 侧重知识入库、检索与引用，Tianji 侧重意图路由、受控工具执行与业务交互。两个项目各自保留运行条件与验证材料，跨仓库集成需要单独验证。

实际阅读可从一个项目的业务问题出发，再看实现、测试与结果。[证据说明](portfolio-governance.md)解释如何区分演示、回归测试和真实运行结果。
