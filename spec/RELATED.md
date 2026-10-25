# 相近项目

这些项目都在保存「关于一个人或一个 Agent 的记忆」。living-record 只规定判断能不能引用某条记录。它不提供存储服务，也不提供一个会替人说话的运行时。

| 项目 | 它做什么 | 和本协议的差别 |
|------|----------|----------------|
| [linfan003/session-canon](https://github.com/linfan003/session-canon) | 多个会话如何共用一份文件、如何只写自己的记忆卡 | 姊妹协议。对方管会话和写入权；本协议管一条个人记录能否被拿来做判断 |
| [SleepSweet/auditable-memory-record](https://github.com/sleepsweet/auditable-memory-record) | 给每条 Agent 记忆规定类型、出处、发生时间和记录时间，并要求用新行替代旧行 | 最接近的字段设计。对方是一行一条的通用记忆；本协议按范围隔开记录，过复核日就停用，并禁止把记录做成替身 |
| [Universal Memory Protocol](https://universalmemoryprotocol.io/specification/) | 跨厂商的记忆交换，出处对齐 W3C PROV | 对方是交换格式。本协议是人能手改的 Markdown 约定 |
| [OMEM Testimony Record](https://infrastructure.omem-cloud.com/spec/testimony-record/) | 只追加的证词记录：证据、分歧、审批和防篡改分级 | 对方偏行动审计。本协议偏个人判断前的引用 |
| [mem0ai/mem0](https://github.com/mem0ai/mem0) | 从对话里抽取可检索的事实 | 对方会自动抽取。本协议要求人确认后才写入，推断不能冒充本人说过 |
| [getzep/zep](https://github.com/getzep/zep) | 带时间的 Agent 记忆服务 | 对方是服务。本协议不要求服务器 |
| [letta-ai/letta-code](https://github.com/letta-ai/letta-code) | Agent 自己编辑的持久记忆运行时 | 对方让 Agent 决定记住什么。本协议里，范围和停用由记录上的字段决定，不由当次模型决定 |

查对日期：2026-10-25。各仓库以当时的 README 为准。
