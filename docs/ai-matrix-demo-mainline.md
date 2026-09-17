# 演示、设计与验证阅读路线

[返回主页](../README.md#代表项目) · [项目来源与改造重点](core-project-grouping.md)

下面的入口对应主页当前置顶的两个项目：**KnowledgeOps Agent** 与 **Tianji AI Agent**，可以直接在线阅读。演示说明中的启动命令是复现入口；是否执行，以及使用什么环境和模型，由读者按需决定。

## 按项目进入

| 项目 | 演示与使用 | 设计与改造 | 验证材料 |
|---|---|---|---|
| KnowledgeOps Agent | [演示脚本](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/demo-script.md) | [企业架构](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/architecture-enterprise.md) | [证据索引](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md) |
| Tianji AI Agent | [业务演示](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/demo-script.md) | [Agent 设计](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/agent-design.md) | [证据索引](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/evidence/README.md) |

## 快速了解：约 10 分钟

1. 从 [KnowledgeOps 演示](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/demo-script.md)了解文档问答，再看[架构](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/architecture-enterprise.md)中的租户、入库与检索边界。
2. 从 [Tianji Agent 设计](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/agent-design.md)了解课程咨询和预下单链路，再看[验证材料](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/evidence/README.md)。

## 深入阅读：约 30 分钟

选择一个项目，对照阅读三个方面：

- **业务问题**：输入、输出和失败情形是什么？
- **实现取舍**：哪些组件来自上游，项目新增了哪些逻辑，为什么这样设计？
- **验证依据**：测试或报告针对哪个版本、什么数据与环境，哪些能力尚未验证？

Tianji 的 Agent 工作与业务底座区分见[来源说明](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/provenance.md)。KnowledgeOps 的平台能力与默认路径限制，以其 [README](https://github.com/however-yir/knowledgeops-agent#readme) 和[验证材料](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)为准。

## 跨仓库集成

KnowledgeOps 与 Tianji 的集成有独立的启用条件和降级路径，见 [KnowledgeOps 跨仓库验证材料](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)。分别构建成功与两个服务实际连通，是不同的验证结论。

两个项目也可以分别阅读和复现。完整的验证口径见[证据说明](portfolio-governance.md)。
