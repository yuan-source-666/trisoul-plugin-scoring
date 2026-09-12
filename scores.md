# 逐项打分与对照（阶段 3）

打分日期：2026-09-12。基准见 [scoring-criteria.md](scoring-criteria.md)，候选池见 [candidates.md](candidates.md)，被评对象 trisoul_x 的事实基础见 [trisoul-facts.md](trisoul-facts.md)。

## 筛选说明
候选池 27 个中，进入逐维打分 **16 个 + trisoul_x 本体**。筛选标准：与 trisoul_x 同属"agent 宿主的记忆/技能层"问题域，且本次已获取到可支撑**至少 6 个维度**取证的公开材料（README/文档/许可/机制描述）。其余 11 个（A-mem、getzep/zep、SimpleMem、memU、memori、google/skills、microsoft skills、awesome-agent-skills、claude-skill-registry、claude-forge、agentregistry）许可证/维护状态/核心机制均未核实，按纪律**不强行给分**，保留在候选池待补证。

## 标记说明
- 无标记 = 有直接证据的给分（证据链接在该项目评述中）。
- **⚠0** = 信息不足记 0 分（非能力否定），"需实测"类维度无公开数据时常见。
- **N/A** = 该项目不具此能力形态，按基准折算 50 分计入总分。

## 总表（行 = 项目，列 = 维度分，总分 /1000）

| 项目 | D1 写入提取 | D2 检索 | D3 作用域 | D4 持久化 | D5 技能协议 | D6 宿主兼容 | D7 可观测 | D8 安全隐私 | D9 性能规模 | D10 生态 | 总分 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| mem0ai/mem0 | 85 | 90 | 85 | 90 | N/A 50 | 95 | 85 | 70 | 85 | 95 | **830** |
| letta-ai/letta | 90 | 65 | 85 | 85 | 90 | 80 | 90 | 65 | 60 | 90 | **800** |
| getzep/graphiti | 90 | 95 | 75 | 90 | N/A 50 | 80 | 60 | 70 | 70 | 90 | **770** |
| basicmachines-co/basic-memory | 65 | 75 | 65 | 80 | 80 | 70 | 60 | 90 | ⚠0 45 | 75 | **705** |
| langchain-ai/langmem | 85 | 75 | 80 | 75 | N/A 50 | 65 | 80 | 70 | ⚠0 40 | 75 | **695** |
| supermemoryai/supermemory | 85 | 70 | 55 | 75 | 75 | 85 | 50 | 65 | ⚠0 45 | 80 | **685** |
| MemTensor/MemOS | 85 | 85 | 65 | 75 | N/A 50 | 70 | 50 | 55 | 75 | 75 | **680** |
| topoteretes/cognee | 85 | 75 | 55 | 85 | N/A 50 | 70 | 50 | 70 | ⚠0 40 | 85 | **665** |
| doobidoo/mcp-memory-service | 75 | 65 | 55 | 75 | 80 | 75 | 60 | 75 | ⚠0 40 | ⚠0 55 | **655** |
| langgenius/dify-plugins | N/A 50 | N/A 50 | 55 | 75 | 90 | 70 | 60 | 70 | 65 | 75 | **660** |
| ComposioHQ/composio | N/A 50 | N/A 50 | 70 | 75 | 95 | 90 | 75 | 75 | 55 | 85 | **720** |
| obra/superpowers | N/A 50 | N/A 50 | 40 | 65 | 90 | 85 | 40 | 65 | N/A 50 | 90 | **625** |
| rohitg00/agentmemory | 70 | ⚠0 50 | 70 | 65 | 75 | 85 | 50 | 55 | ⚠0 40 | 60 | **620** |
| anthropics/skills | N/A 50 | N/A 50 | 40 | 55 | 95 | 90 | 35 | 45 | 60 | 80 | **600** |
| modelcontextprotocol/servers (memory) | 45 | 45 | 30 | 55 | 95 | 85 | 30 | 80 | 40 | 80 | **585** |
| memodb-io/memobase | 75 | 60 | 65 | 60 | N/A 50 | 70 | 45 | 60 | ⚠0 40 | 70 | **595** |
| **gulagala001/trisoul_x (oh-my-dsh)** | 70 | 60 | 75 | 75 | 45 | 50 | 60 | 80 | 35 | 25 | **575** |

> 注：总分不可直接当"综合排名"使用——各项目 ⚠0/N/A 分布不同（见基准文档打分流程第 3 条）。D2/D9 涉及检索命中率与延迟的档位，多为架构定性判断，**均需实测复核**。

---

## 逐项目评述（证据附后）

### 1. mem0ai/mem0 — 830
开源核心（Apache-2.0，[LICENSE](https://github.com/mem0ai/mem0/blob/main/LICENSE) 已核）+ 托管平台双轨。D1/D2：自动提取 + 多层次存储，README 自报 LoCoMo 评测较 OpenAI Memory 提升约 26%（**自报数据**）。D6 最强项：REST API、OpenMemory MCP、十余框架集成、托管/自托管任选。短板在 D5（记忆库形态，无技能协议）与 D8（托管模式的数据外流面文档未逐条核实）。

### 2. letta-ai/letta — 800
前 MemGPT（Apache-2.0 已核）。D1/D3 突出：memory blocks 由 agent 自编辑、可跨 agent 共享（[官方博客](https://www.letta.com/blog/introducing-the-letta-agent-sdk/) 与 [社区教程](https://www.reddit.com/r/AI_Agents/comments/1glzob6/tutorial_on_building_agent_with_memory_using_letta/)）。D5/D7 强：原生 tools + ADE 可视化开发环境。D2 弱于 graphiti/mem0——有 archival 向量检索但本次未见公开基准数字（⚠需实测）。D9：Postgres 服务化架构撑得起规模，但无公开性能数据。

### 3. getzep/graphiti — 770
时序知识图谱记忆（Apache-2.0 已核）。D2 本次最高分之一：bi-temporal 图 + 混合检索，且有正式发表的 arXiv 论文（[Zep: A Temporal Knowledge Graph Architecture for Agent Memory](https://arxiv.org/html/2501.13956v1)）给出对比基准。D4：Neo4j/FalkorDB 等多后端 + 边失效时间（[issue #1300](https://github.com/getzep/graphiti/issues/1300) 讨论时间衰减）。D7/D9 证据不足（无仪表板/公开压测证据）。官方页自述 20,000+ stars（2026-09-12）。

### 4. basicmachines-co/basic-memory — 705
本地优先 markdown 语义图（**AGPL-3.0** 已核——商用集成需注意 copyleft）。D8 本次最高：数据全部留本地标准文件。D4/D5 良好：MCP server 工具面（write_note/search_notes/build_context）+ 同步引擎。D2 有独立 [benchmark 仓库](https://github.com/basicmachines-co)（具体数字未逐项核实，给 75 而非 90）。D9 记 ⚠0：文件型架构的规模上限无公开数据。

### 5. langchain-ai/langmem — 695
LangChain 官方记忆 SDK（MIT 已核）。D1/D3/D7 好：热路径/后台双模式提取、namespace 三元组、天然挂 [LangSmith](https://langchain-ai.github.io/langmem/) 可观测。D6 受限于 LangGraph 生态内最优、跨宿主一般。D9 ⚠0。

### 6. supermemoryai/supermemory — 685
Memory & context engine（MIT 已核）。D6 强：API + [supermemory-mcp](https://github.com/supermemoryai/supermemory-mcp) + claude/opencode 插件矩阵。宣称"免嵌入管线、可全本地"，若属实 D8 应更高，但数据流文档未逐条核实，暂记 65。D2/D9 缺公开评测（⚠需实测）。

### 7. MemTensor/MemOS — 680
"记忆操作系统"（Apache-2.0 已核）。D1/D2：MemCube 多型记忆 + 公开评测集（[HuggingFace: MemOS_eval_result](https://huggingface.co/datasets/MemTensor/MemOS_eval_result)），自报 token 节省约 35%。学术出身，D6/D7 工程化程度弱于 mem0/letta，D8 文档不足。

### 8. topoteretes/cognee — 665
自托管 KG+向量记忆平台（Apache-2.0 已核）。D1/D4 好：ECL 管线、多图/向量后端、API 四动词（remember/recall/forget/improve）。D2/D9 公开评测与性能数据未核实（⚠）。D10 加分：同为 [awesome-ai-memory](https://github.com/topoteretes/awesome-ai-memory) 维护方。

### 9. doobidoo/mcp-memory-service — 655
最接近 trisoul_x 形态的对照物之一：宿主旁挂的持久记忆服务（MCP + REST + 知识图谱 + 自动整理）。topic 页显示 2026-04-15 有更新（活跃）。**许可证未核实** → D10 记 ⚠0/55。D9 ⚠0。

### 10. langgenius/dify-plugins — 660
Dify 插件市场生态（许可证未核实）。D5/D4 是所有候选中最完整的插件协议之一：manifest + [dify-plugin-daemon](https://github.com/langgenius/dify-plugin-daemon) 生命周期守护 + SDK + 市场分发——正是 trisoul_x 缺失的"插件生态位"参照。D6 被单宿主（Dify）锁死，与 trisoul_x 同病但市场成熟度高得多。

### 11. ComposioHQ/composio — 720
技能/工具层最高分（MIT 已核，master 分支 LICENSE）。D5/D6：1000+ 工具箱、工具搜索、OAuth 托管、沙箱、SDK ×2 + [Claude Code 插件](https://github.com/ComposioHQ/composio-plugin-cc)。D9 无公开数字（55，定性给分）。纯工具层，D1/D2 按 N/A 折算。

### 12. obra/superpowers — 625
技能方法论库（MIT 已核）。D5/D6/D10 强：可组合 SKILL.md + hooks/commands、v6 已适配 Claude Code 与 Codex（[HN 讨论](https://news.ycombinator.com/item?id=48739459)）。~226k stars 为第三方转述**未核实**。D3/D7 弱：技能无隔离/审批模型，无内省工具。

### 13. rohitg00/agentmemory — 620
编码 agent 记忆服务（Apache-2.0 已核）：hooks + MCP + REST 三通道、Claude Code 原生插件 + 12 hooks。D6/D5 与 trisoul_x 高度同构，是**最有用的直接对照**。D2/D7/D9 证据不足（⚠）。维护主体疑似单人（D10 60）。

### 14. anthropics/skills — 600
SKILL.md 事实标准的发源地。D5 满档区（95）：定义格式 + 渐进披露 + 可注册为插件市场（[仓库](https://github.com/anthropics/skills)）。D3/D7/D8 弱：无隔离模型、无扫描/签名（GitHub 官方 changelog 已提示供应链风险），**根目录未核实到 LICENSE 文件**（jsDelivr @main 404）。纯静态技能资产，D1/D2 N/A。

### 15. modelcontextprotocol/servers (memory) — 585
MCP 官方参考实现（Apache-2.0 + MIT + CC-BY-4.0，已核）。D5 满分区（95）：它就是协议本身。但 memory server 本体功能极简：手动建图、单图无隔离（D3 30）、JSONL 存储（D4 55）、无可观测（D7 30）——是"协议完备、实现最简"的底线参照。

### 16. memodb-io/memobase — 595
用户画像型记忆（Apache-2.0 已核）。D1 写入管线完整（自动 profile 更新），D2/D9 无公开评测（⚠），D7/D8 文档偏弱。整体是"管线完整但证据链薄"的典型。

---

## trisoul_x 的相对位置与短板

**位置**：575/1000，16 个对照项目中垫底——但需正确解读：它的对照池里 5 个是 GitHub 数万 star 量级、组织化维护的头部项目，而 trisoul_x 是单人维护的宿主插件。**同形态对照**（agentmemory 620、mcp-memory-service 655、MCP memory server 585）与它的差距在 20–80 分之间，说明"单人宿主插件"形态的正常水位大致就在 550–650。

**按维度看它的相对位置**：

| 维度 | 分 | 相对位置 |
|---|---|---|
| D8 安全隐私 | 80 | **强项**：纯本地 JSON、0600 权限、原子写，数据外流面最小；仅弱于 basic-memory(90)/MCP server(80) |
| D3 作用域与隔离 | 75 | 中上：global/cross/project/session 四层在对照池里属前列（多数同类只有 user/agent 两层） |
| D4 持久化与生命周期 | 75 | 中上：血缘/退役/恢复/分片整理比多数同类的"append+查询"完整 |
| D1/D2 记忆机制 | 70/60 | 中游：LLM 选取 + bigram 兜底无评测支撑，输给有论文/基准的 graphiti/MemOS/mem0 |
| D7 可观测 | 60 | 中游：有召回/注入追踪宣称，无仪表板 |
| D5 技能协议 | 45 | **明显短板**：技能无独立定义格式/注册协议（疑似 prompt 内嵌），对照池里做得好的（SKILL.md 生态、composio、dify-plugins）已跑到 90+ |
| D6 宿主兼容 | 50 | **明显短板**：单宿主（DSH）锁死，无 REST/MCP 等宿主无关接口 |
| D9 性能规模 | 35 | **明显短板**：JSON 全量文件 + bigram 线性扫描，无索引无数字 |
| D10 生态维护 | 25 | **最大短板**：无 LICENSE、package private、单人、无测试证据 |

**一句话结论**：trisoul_x 的记忆内核（分层作用域 + 血缘 + 整理）设计并不落后，真正的结构性短板是三件事——**没有许可证与生态位（D10/D6）、技能侧无协议（D5）、规模上限未解决（D9）**。前两者补齐成本低（加 LICENSE、抽 REST/MCP 面、把技能定义格式化），第三件则受其"纯文件存储"选型约束，属架构级决策。

## 未打分候选（11 个，待补证后可按同一基准计分）
A-mem、getzep/zep、SimpleMem、memU、memori、google/skills、microsoft skills、VoltAgent/awesome-agent-skills、majiayu000/claude-skill-registry、sangrokjung/claude-forge、agentregistry-dev/agentregistry。未打分原因：许可证、维护状态与核心机制均未在本次核实到可溯源材料，按"信息不足不给分"纪律处理。
