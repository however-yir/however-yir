<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/profile-banner-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/profile-banner-light.png">
  <img src="assets/profile-banner-light.png" alt="however-yir · AI Engineer · Java Backend Developer — 深空极光横幅" width="100%">
</picture>

<p align="center">让知识问答有据可查，让业务 Agent 的动作可控，让系统改动有验证依据。</p>

<p align="center">
  <a href="#代表项目">代表项目</a> ·
  <a href="#开源贡献">开源贡献</a> ·
  <a href="docs/ai-matrix-demo-mainline.md">阅读路线</a> ·
  <a href="mailto:liuhowever@gmail.com">联系我</a>
</p>

已向 **Dify、LangChain4j、Spring AI Alibaba examples 和 MiniMax CLI** 贡献并合并 **10 个外部 PR**，涵盖 MCP Schema 处理、数据库 Session 重构、回归测试、文档与示例配置。[查看贡献明细 ↓](#开源贡献)

## 代表项目

从知识检索、业务执行到质量评测，三个项目分别展示 AI 应用工程的不同环节。

### [KnowledgeOps Agent](https://github.com/however-yir/knowledgeops-agent) · 知识检索

面向团队文档问答的 **Spring AI 平台原型**，让回答附带可追溯的引用。

- **实现重点：** 租户范围内的检索、异步文档入库，以及答案引用与评测流程。
- **适合了解：** Java 后端如何组织知识入库、检索与权限边界。

[演示指南](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/demo-script.md) · [架构设计](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/architecture-enterprise.md) · [验证材料](https://github.com/however-yir/knowledgeops-agent/blob/main/docs/evidence/README.md)

### [Tianji AI Agent](https://github.com/however-yir/tianji-ai-agent) · 业务执行

基于既有教育业务后端构建的 **课程顾问 Agent**，把课程咨询连接到订单预确认流程。

- **实现重点：** 意图路由、动作策略、执行预算与 SSE 流式交互契约。
- **适合了解：** 模型提出动作后，业务规则如何控制工具调用与实际执行。

[演示指南](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/demo-script.md) · [Agent 设计](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/agent-design.md) · [验证材料](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/evidence/README.md) · [来源与改造](https://github.com/however-yir/tianji-ai-agent/blob/main/docs/provenance.md)

### [ragproof](https://github.com/however-yir/ragproof) · 质量评测

框架无关的 **RAG 评测与回归测试 CLI**，在 Prompt、切片规则或模型变更后检查质量是否退化。

- **实现重点：** 调用既有 RAG HTTP API，计算检索与引用指标、比较版本报告，并通过退出码让 CI 在未达标时失败。
- **适合了解：** 如何把质量要求变成可重复执行的评测流程与合并条件。

[CLI 快速上手](https://github.com/however-yir/ragproof#run-a-gate-in-30-seconds) · [架构设计](https://github.com/however-yir/ragproof/blob/main/docs/ARCHITECTURE.md) · [公开基准报告](https://github.com/however-yir/ragproof/blob/main/docs/PUBLIC_BENCHMARK_REPORT.md)

## 更多项目

| 项目 | 解决的问题与实现范围 | 阅读入口 |
|---|---|---|
| [NebulaKB](https://github.com/however-yir/nebula-kb) | 基于 Django 的知识运营：文档接入、检索反馈与低质量答案回看。 | [演示指南](https://github.com/however-yir/nebula-kb/blob/main/docs/demo-script.md) · [定位与边界](https://github.com/however-yir/nebula-kb/blob/main/docs/repo-positioning.md) |
| [ForgePilot Studio](https://github.com/however-yir/forgepilot-studio) | 基于 OpenHands 的工程工作台：任务台、审计工具及实验性治理模块。核心治理模块尚未接入默认执行链路。 | [产品预览](https://github.com/however-yir/forgepilot-studio#产品预览) · [来源与改造](https://github.com/however-yir/forgepilot-studio/blob/main/docs/fork-differentiation.md) |
| [Microservices Lab](https://github.com/however-yir/however-microservices-lab) | 扩展 Google Online Boutique：接入 AI 购物助手、本地模型回退与 Kubernetes 部署。 | [本地演示指南](https://github.com/however-yir/however-microservices-lab/blob/main/docs/local-demo.md) · [来源与改造](https://github.com/however-yir/however-microservices-lab/blob/main/docs/diff-from-upstream.md) |

[全部项目的演示、设计与验证入口](docs/ai-matrix-demo-mainline.md) · [项目来源与实现范围](docs/core-project-grouping.md) · [如何阅读验证材料](docs/portfolio-governance.md)

## 开源贡献

**10 个已合并的外部 PR：5 个代码贡献，5 个文档与示例配置贡献。**

| 上游项目 | 已合并 PR | 贡献内容 |
|---|---:|---|
| **LangChain4j** | 1 | 实现 MCP 工具输入 Schema 中 `allOf` 对象子 Schema 的合并，并补充回归测试。 |
| **Dify** | 4 | 数据库 Session 显式传递与模型访问器重构。 |
| **Spring AI Alibaba examples** | 4 | 快速上手、故障排查与 MCP / RAG / 工具调用示例环境配置。 |
| **MiniMax CLI** | 1 | 修正文档中的视频下载示例，说明凭据位置。 |

<details>
<summary>展开全部 10 个 PR：改动说明与合并记录</summary>

### 代码与测试

- **LangChain4j [#6320](https://github.com/langchain4j/langchain4j/pull/6320)：** 合并 MCP 工具输入 Schema 的 `allOf` 对象子 Schema，补充回归测试。
- **Dify [#41882](https://github.com/langgenius/dify/pull/41882)：** 向 `ApiToolProvider.user` 显式传入数据库 Session。
- **Dify [#41883](https://github.com/langgenius/dify/pull/41883)：** 移除 Message 反馈与标注访问器中的旧式 `db.session` 包装。
- **Dify [#41885](https://github.com/langgenius/dify/pull/41885)：** 向 `AppAnnotationSetting.collection_binding_detail` 显式传入数据库 Session。
- **Dify [#41886](https://github.com/langgenius/dify/pull/41886)：** 移除其他 Message 访问器中的旧式 `db.session` 包装。

### 文档与示例配置

- **Spring AI Alibaba examples [#452](https://github.com/spring-ai-alibaba/examples/pull/452)：** 补充模块快速上手索引。
- **Spring AI Alibaba examples [#453](https://github.com/spring-ai-alibaba/examples/pull/453)：** 添加 MCP、RAG 与工具调用示例的环境配置模板。
- **Spring AI Alibaba examples [#457](https://github.com/spring-ai-alibaba/examples/pull/457)：** 完善入门与故障排查说明。
- **Spring AI Alibaba examples [#458](https://github.com/spring-ai-alibaba/examples/pull/458)：** 为更多 DashScope 示例补充环境配置模板。
- **MiniMax CLI [#84](https://github.com/MiniMax-AI/cli/pull/84)：** 修正视频下载示例，说明认证凭据的存放位置。

</details>

## 联系我

欢迎交流 **AI 应用、Java 后端与开源协作机会**。

**邮箱：** [liuhowever@gmail.com](mailto:liuhowever@gmail.com)  
**代码之外：** 历史、旅行、电影、足球。
