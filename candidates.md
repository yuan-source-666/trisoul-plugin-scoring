# GitHub 同类项目候选清单（阶段 2）

抓取日期：2026-09-12。检索路径（按顺序）：
1. WebSearch：`github agent memory plugin LLM long-term memory framework`、`github agent skills plugin skill registry SKILL.md tool registry for LLM agents`、`letta-ai/letta github memory blocks`、`getzep graphiti github`、`ComposioHQ composio / modelcontextprotocol servers / dify-plugins`、`cognee / supermemory / basic-memory / langmem`、`MemOS / A-mem / memobase`
2. GitHub topic 页：`topics/agent-memory`、`topics/mcp-memory`、`topics/skill-md`、`topics/agent-skills`
3. 直接抓取仓库 README（mem0，经 jsDelivr CDN）

**数据可信度说明**：GitHub API（api.github.com）在本次环境中不可达，GitHub 仓库页渲染不含 star 数，故 **star 数除注明来源外一律记"未核实"**；"最近活动"仅在 topic 页或搜索结果明确给出时记录；**许可证一律未逐仓核实**（阶段 3 对进入打分的重点项目用 CDN 补核）。更新时间基准：今日为 2026-09-12。

## 一、记忆类（16）
| # | 仓库 | 一句话定位 | Star | 最近活动 | 语言 | 维护状态 |
|---|---|---|---|---|---|---|
| 1 | [mem0ai/mem0](https://github.com/mem0ai/mem0) | "The Memory Layer for AI Agents"，托管平台 + OpenMemory MCP + REST API，自称 LoCoMo 上较 OpenAI Memory 提升约 26%（README 自报） | 未核实 | 活跃（README 多版本迭代痕迹） | Python/TS | 活跃 |
| 2 | [agiresearch/MemOS](https://github.com/agiresearch/MemOS) | 记忆操作系统：MemCube 抽象、混合检索，评测数据公开在 HuggingFace | 未核实 | 未核实 | Python | 活跃（有公开评测迭代） |
| 3 | [agiresearch/A-mem](https://github.com/agiresearch/A-mem) | Agentic Memory：Zettelkasten 式动态记忆网络，配套 arXiv 2502.12110 | 未核实 | 未核实 | Python | 未核实 |
| 4 | [memodb-io/memobase](https://github.com/memodb-io/memobase) | 用户画像（profile）型长期记忆，面向 LLM 应用 | 未核实 | 未核实 | Python | 未核实 |
| 5 | [letta-ai/letta](https://github.com/letta-ai/letta) | 有状态 agent 平台（前 MemGPT），memory blocks 可在多 agent 间共享 | 未核实 | 活跃（Letta Code/SDK 2025-2026 持续发布） | Python | 活跃 |
| 6 | [getzep/graphiti](https://github.com/getzep/graphiti) | 时序知识图谱记忆框架（bi-temporal），配套 arXiv 2501.13956 | 20,000+（[官方页面自述](https://www.getzep.com/ai-agents/temporal-knowledge-graph/)，2026-09-12 抓取） | 未核实 | Python | 活跃 |
| 7 | [getzep/zep](https://github.com/getzep/zep) | Zep Cloud 的记忆 API 配套仓库（示例/框架集成） | 未核实 | 未核实 | TypeScript | 未核实 |
| 8 | [langchain-ai/langmem](https://github.com/langchain-ai/langmem) | LangChain 官方记忆 SDK：从对话提取信息存长期记忆，深度绑定 LangGraph | 未核实 | 未核实 | Python | 未核实 |
| 9 | [topoteretes/cognee](https://github.com/topoteretes/cognee) | 自托管知识图谱 + 向量检索的记忆平台，API 四动词 remember/recall/forget/improve | 未核实 | 1.0 已发布（2025-06 起） | Python | 活跃 |
| 10 | [supermemoryai/supermemory](https://github.com/supermemoryai/supermemory) | "Memory & context engine"：自动提取记忆+用户画像，可全本地运行；生态含 supermemory-mcp、claude-supermemory 插件 | 未核实 | 未核实 | TypeScript | 活跃 |
| 11 | [basicmachines-co/basic-memory](https://github.com/basicmachines-co/basic-memory) | 本地优先（local-first）markdown 语义图记忆，MCP server（write_note/search_notes/build_context）；有独立 benchmark 仓库 | 未核实 | 未核实 | Python/TS | 活跃（配套 docs/benchmarks 仓库） |
| 12 | [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory) | 面向编码 agent 的持久记忆：hooks + MCP + REST 三通道，Claude Code 原生插件 + 12 hooks | 未核实 | 未核实 | 未核实 | 未核实 |
| 13 | doobidoo/mcp-memory-service | 开源持久记忆服务：REST API + 知识图谱 + 自动整理（consolidation），对接 LangGraph/CrewAI/AutoGen/Claude | 未核实 | topic 页显示 Updated 2026-04-15 | Python | 活跃（6 个月内有更新） |
| 14 | [aiming-lab/SimpleMem](https://github.com/aiming-lab/SimpleMem) | 终身记忆：语义无损压缩存储/检索，支持多模态输入 | 未核实 | 未核实 | Python | 未核实 |
| 15 | NevaMind-AI/memU | 面向 24/7 主动型 agent（openclaw 类）的记忆层 | 未核实 | topic 页显示 Updated 2026-03-23 | Python | 活跃（6 个月内有更新） |
| 16 | GibsonAI/memori（仓库名据 topic 页 logo "Memori" 推断，**归属未核实**） | agent 原生记忆基础设施，宣称 LLM 无关、自带数据可移植性 | 未核实 | topic 页显示 Updated 2026-04-14 | Python | 活跃（6 个月内有更新） |

## 二、技能类（8）
| # | 仓库 | 一句话定位 | Star | 最近活动 | 语言 | 维护状态 |
|---|---|---|---|---|---|---|
| 17 | [anthropics/skills](https://github.com/anthropics/skills) | Anthropic 官方 Agent Skills 仓库，可注册为 Claude Code 插件市场 | 未核实 | 活跃（SKILL.md 已成事实标准） | Markdown | 活跃 |
| 18 | [google/skills](https://github.com/google/skills) | Google 官方 agent skills 仓库 | 未核实 | 未核实 | Markdown | 未核实 |
| 19 | [microsoft skills](https://microsoft.github.io/skills/)（仓库入口） | Microsoft 官方 agent skills 站点/仓库 | 未核实 | 未核实 | Markdown | 未核实 |
| 20 | [obra/superpowers](https://github.com/obra/superpowers) | 面向编码 agent 的可组合技能方法论（TDD/计划/调试/验证），有 v6 与 Codex 适配 | 约 226k（**第三方文章转述**，未核实；[HN 讨论](https://news.ycombinator.com/item?id=48739459)） | v6 发布（2026） | Markdown | 活跃 |
| 21 | [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) | 1000+ 社区/官方技能的精选索引，兼容 Claude Code/Codex/Gemini CLI/Cursor | 未核实 | 未核实 | Markdown | 活跃（父项目 voltagent 10.6k star，2026-09-12 搜索快照） |
| 22 | [majiayu000/claude-skill-registry](https://github.com/majiayu000/claude-skill-registry) | Claude Code 技能的可搜索聚合索引（web + CLI） | 未核实 | 未核实 | 未核实 | 未核实 |
| 23 | [ComposioHQ/composio](https://github.com/composiohq/composio) | 1000+ 工具箱（toolkits）+ 工具搜索 + 认证 + 沙箱工作台；含 composio-plugin-cc（Claude Code 插件） | 未核实 | 活跃 | Python/TS | 活跃 |
| 24 | [sangrokjung/claude-forge](https://github.com/sangrokjung/claude-forge) | "oh-my-zsh for Claude Code"：16 agents + 35 commands + 33 skills + 22 hooks 的一体化环境 | 未核实 | 未核实 | Markdown | 未核实 |

## 三、两者兼有（3）
| # | 仓库 | 一句话定位 | Star | 最近活动 | 语言 | 维护状态 |
|---|---|---|---|---|---|---|
| 25 | [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | MCP 官方参考实现集（含 **memory server**：知识图谱型持久记忆）+ 社区目录；配套 [MCP Registry](https://github.com/modelcontextprotocol/registry) | 未核实 | 活跃 | TypeScript/Python | 活跃 |
| 26 | [langgenius/dify-plugins](https://github.com/langgenius/dify-plugins)（含 dify-official-plugins、dify-plugin-daemon、dify-plugin-sdks） | Dify 插件市场生态：工具/模型/Agent 策略插件 + 生命周期守护进程 + SDK | 未核实 | 活跃 | Python | 活跃 |
| 27 | [agentregistry-dev/agentregistry](https://github.com/agentregistry-dev/agentregistry) | 一个入口查找/管理/运行 MCP server、AI agent 与 skills 的开源平台 | 未核实 | 未核实 | 未核实 | 未核实 |

## 归类歧义说明
- **letta**：既是记忆框架（memory blocks）也是带工具调用的完整 agent 平台。按其主要暴露面（有状态 agent 服务）归入记忆类，评述中注明双重属性。
- **modelcontextprotocol/servers**：memory server 是记忆类，但仓库主体是工具/协议生态 → 归入两者兼有。
- **supermemory / basic-memory**：记忆核心 + MCP/插件分发层，归记忆类，其分发面在 D5/D6 计分。
- **检索词与命中数记录**：GitHub topic `agent-memory` 显示 3,371 个仓库、`mcp-memory` 显示 8 个仓库（2026-09-12）；候选集主要来自搜索结果的交叉验证，未为凑数收录无法核实定位的项目（如若干 topic 页仅出现 logo、仓库不可辨识者）。
