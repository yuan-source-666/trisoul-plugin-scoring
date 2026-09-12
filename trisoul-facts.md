# trisoul_x 事实摘要（阶段 0）

抓取日期：2026-09-12。访问方式：GitHub 页面（web_reader）+ jsDelivr CDN 逐文件读取。
**访问状态**：仓库可访问。`https://github.com/gulagala001/trisoul_x` 已被重命名为 `gulagala001/oh-my-dsh`（旧 URL 302 重定向），插件 ID/package 名仍为 `trisoul_x`。以下"来源"均指 oh-my-dsh 仓库内文件（@main 分支，版本 0.1.1）。

## 1. 形态与宿主
- 形态：DeepSeek Harness（DSH）宿主的**插件 + Agent preset**，不是独立服务、不是 npm 库、不通过插件市场分发。它通过 cordis patch 机制向宿主注入服务 `trisoulX`，并注册默认 Agent preset `trisoul-x`。来源：`cordis.patch.yml`、`presets/trisoul-x/preset.yml`
- 宿主：DeepSeek Harness，适配版本 0.1.5-rc.1。来源：`docs/usage.md`（"当前版本 0.1.1，适配 DSH 0.1.5-rc.1"）
- 运行时依赖全部来自宿主方包：`@deepseek-ai/cordis`（Service 框架）、`@deepseek-ai/dsh-llm`（消息/流式块）、`@deepseek-ai/schemastery`（配置 schema）。来源：`src/hub.mjs`、`src/memory-context.mjs`、`src/config.mjs` 顶部 import
- package.json：`"name": "trisoul_x", "version": "0.1.1", "private": true` —— **未发布到 npm**，以 GitHub 仓库形式分发，装入已有 DSH 宿主（`docs/usage.md` 设有"安装到现有 DSH（推荐）"章节）。来源：`package.json`、`docs/usage.md`

## 2. 记忆能力
- **存储介质**：本地 JSON 文件（`memory.json`、`sessions/<id>.json`、`curation.json`），原子写入（临时文件 + rename），文件权限 0o600。无数据库、无嵌入向量库。来源：`src/hub-store.mjs`
- **作用域**：条目级三层 `scope: global / cross / project`，另有会话层 `sessions/<id>.json`；会话键用 `session:` 前缀隔离。来源：`src/hub-store.mjs`
- **写入**：三条通道——`scribe`（会话中自动记录）、`curate`（整理任务产出）、`user`（用户直写）；支持更新/退役（retire）/恢复（restore），编辑带 `previous`/`supersededBy` 版本血缘。来源：`src/hub-store.mjs`（memoryOps、memoryLineage）
- **检索**：两层、均非向量检索——(a) LLM 选取：`memory-context.mjs` 用 `PICK_SYSTEM` 提示词让模型从候选记忆中挑出与当前用户消息相关的条目注入上下文；(b) 词法兜底/分组：字符 bigram Jaccard 相似度（阈值 0.6），用于跨项目候选聚合与整理分片。来源：`src/memory-context.mjs`、`src/hub-store.mjs`
- **生命周期钩子**：随 DSH 会话事件驱动（`sessionEvents`/`eventText`/`substantive` 判定实质内容后才触发记录）；整理（curation）用分片 + 游标窗口推进；条目带 `at` 时间戳与 usage/touch 统计（召回次数追踪）。来源：`src/hub.mjs`、`src/hub-store.mjs`
- **跨会话**：是（JSON 持久化 + project/global 作用域）。**跨 agent/跨宿主**：未在仓库中说明（实现与 DSH 的 Service/会话模型紧耦合）。
- **可观测**：仓库描述宣称"记忆召回/注入追踪"与"运行监控"。来源：仓库 GitHub 描述、`README.md`
- **配置**：schema 用 schemastery 定义，含 route（provider/model/temperature）与 `FREQUENCY_PRESETS`（频率预设，控制记忆写入/整理节奏）。来源：`src/config.mjs`

## 3. 技能能力
- preset 描述称"配备画布、记忆、技能与按需子代理"。来源：`presets/trisoul-x/preset.yml`
- 已确认注册的能力/工具：记忆读写（note/recall 族）、任务管理 `todo_write` 与 `verify_link`（任务验证）、Canvas（实时预览/批注/素材导出）、Computer Use（网页 + macOS 应用操控，标注预览版）。来源：`src/dsh-agent.mjs`（import MAIN_PERSONA/NOTE_GUIDE/Canvas/registerTasks）、`src/tasks.mjs`、`README.md`
- **技能定义格式 / 技能注册协议：未在仓库中说明**（就我读到的文件而言，"技能"疑似指 prompt 内嵌的行为规范 `MAIN_PERSONA`/`NOTE_GUIDE`，而非独立的技能清单/注册表；`src/prompts.mjs` 未逐字读取，此点待确认）。

## 4. 其他
- 许可证：根目录未见 LICENSE 文件；`THIRD_PARTY_NOTICES.md` 声明 Agent preset 改编自 DeepSeek Harness 0.1.5-alpha.1（commit 5dda764…）并对齐 0.1.5-rc.1（commit 183f08e…）。**项目自身代码许可：未在仓库中说明**。来源：`THIRD_PARTY_NOTICES.md`
- 语言：纯 JavaScript（ESM, `.mjs`），无编译步骤。来源：`package.json`（`"type": "module"`）+ 文件树
- 定位沿革：`AGENTS.md` 称其机制与提示词源自早期项目 "trisoul"（三魂），oh-my-dsh 是向 DSH 宿主的最小适配移植。来源：`AGENTS.md`
