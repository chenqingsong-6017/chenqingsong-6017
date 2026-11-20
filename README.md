# xxx

**一个人的 DeepSeek Harness 体系**：一个人 + 一个 agent 团队，用「工作区分权 + 插件补能力 + 能红的检查」把日常工程做成可验证的系统。

## 公开的仓库

| 仓库 | 是什么 |
| --- | --- |
| **[one-person-harness](https://github.com/chenqingsong-6017/one-person-harness)** | 体系文档：插件地图、工作区地图、方法论、公开边界、实测数据（**先读这个**） |
| **[dsh-bundles](https://github.com/chenqingsong-6017/dsh-bundles)** | 26 个自制 DeepSeek Harness 插件源码：记忆 / 环境 / 安全 / 观测 / 会话生命周期 / 研究学习 / 客户端体验 |
| **[dsh-eval](https://github.com/chenqingsong-6017/dsh-eval)** | 自证式本地编码 agent 评测套件：固定任务 + 自动检查 + 污染审计 |
| **[homelab](https://github.com/chenqingsong-6017/homelab)** | 实验环境与运维笔记 |

## 这套东西在解决什么

模型不缺聪明，缺的是**边界与证据**：

- **边界**：哪些动作要审批、哪些路径红线永不可碰、批量改动如何先预览后落盘、删除能否撤销；
- **证据**：每个机制都要有观测 → 判定 → 动作 → 再观测，检查必须能失败；永远绿的检查等于没有；
- **寿命**：记忆分层（热层注入 / 冷层检索）、会话归档前先沉淀、删除进可恢复隔离区。

## 规模（口径：2026-11-16 实测）

- 26 个自制插件（另注配置口径「自研 27」含 2 个补丁挂载项）
- 5 个工作区，各有独立规则与验收
- 14 道门的体检编排；`check` 23 条命令、`check:full` 另加结构与质量两闸
- 50 个插件测试、89 个模型工具契约检查
- 近 7 天 356 次调用、约 ¥7.09（人民币，含缓存读）

## 怎么验证我说的

每个仓库都带可复核的检查，而不是自说自话：

- 文档里的每个数字都标了日期与口径；
- 插件自带 `*_status` 诊断与最小测试；
- 质量/结构两闸都带反例自检，且「存量只许减不许增」。

---

*Most of this system is in Chinese. Structural summary: workspaces own their own rules and acceptance; plugins own one capability each and expose a `*_status`; every gate is expected to fail when it should. Start with [one-person-harness](https://github.com/chenqingsong-6017/one-person-harness).*
