一句话定位（必须先改清楚）

现在的定位：

“一个用于 complex spatial query 的数据集 + 生成框架”

KDD Dataset Track 高分定位（建议）：

“一个可复现、可扩展、可控难度的复杂空间查询基准生成 环境（dataset + generator + benchmark protocol）”

👉 关键词要从 dataset 升级为 benchmarking environment / data generator。

1️⃣ Accessibility（这是 Dataset Track 的硬门槛）
你现在的问题

数据是 Melbourne 实例 + 框架

reviewer 会问：
“我不用墨尔本还能不能用？”

必须修改

把 paper 结构从「一个数据集」改成「三层可用性」：

明确写成三种可获取方式（强烈建议单独一个 Section）
We release:
(1) A ready-to-use real-world dataset (Melbourne, N=1930)
(2) A region-adaptable dataset construction pipeline
(3) A fully synthetic generator with controllable distributions

强调：

无需人工申请

GitHub + Zenodo / HuggingFace

一条命令生成新城市

📌 reviewer checklist 对应：
✅ Accessible without personal requests
✅ Open-source tools

2️⃣ Quality & Documentation（你现在写得“像系统论文”，不够 dataset）
你现在的问题

你现在重点在：

query 类型

LLM / spatial reasoning motivation

但 Dataset Track reviewer 要的是：

“我能不能 复现、理解、修改 你的数据？”

必须补的内容（非常关键）
（1）明确的数据 schema（表格）

加一个 Schema Table，例如：

Component	Fields	Description
POI	id, lat, lon, category, tags	From OSM / Maps
Route	polyline, length, toll_flag	Derived
Query	template_id, constraints, NL_text	Generated
Answer	POI_id(s), route_segment	Verified

👉 Dataset track reviewer 非常吃 schema clarity。

（2）Query 生成流程图（不是系统架构图）

你现在是系统 workflow 图
👉 改成 Dataset Construction Pipeline

明确三步：

Location / Route Sampling

Constraint Injection（detour / toll / semantic）

Ground-truth Derivation（规则 + API 校验）

并写清：

哪一步是 deterministic

哪一步是 stochastic

（3）质量控制（Quality Control）必须显式

单独一个 subsection：

Quality Control
- Route feasibility validation
- Constraint satisfiability check
- Ambiguity filtering
- Deduplication


👉 Dataset Track reviewer 非常在意 noise & ambiguity。

3️⃣ Impact（这是你最有优势的部分，但现在没“打到点上”）
你现在写法的问题

你强调：

LLM 能解决复杂 spatial intent

现有系统不行

但 Dataset Track 更关心：

“这个数据 除了你，别人还能干嘛？”

建议你明确写 5 类 Impact（直接列 bullet）
示例（可以直接用）
This dataset enables:
1. Benchmarking spatial databases beyond point/range queries
2. Evaluating Spatial-RAG pipelines under route-aware constraints
3. Studying query decomposition and planning strategies
4. Controlled ablation of spatial vs semantic difficulty
5. Cross-region generalization studies


📌 强调 generalizability & reuse，不是你的系统多聪明。

4️⃣ Ethics & Fairness（不写会被扣分）
必须加一个 Section（哪怕 0.5 页）
你可以这样写（非常 Dataset Track 友好）：

不包含个人数据

POI / map 数据来自公开来源（OSM / Maps API）

不包含用户轨迹

潜在 bias：

城市中心 vs 郊区

商业 POI 丰富度

Mitigation：

支持 density-aware sampling

支持 synthetic rebalancing

👉 reviewer 看到这一节会直接打 ✅。

5️⃣ Benchmark 化（这是冲高分的关键一步）

现在你是：

dataset + example evaluation

要升级成：

benchmark protocol

必须补三样东西
（1）Difficulty 控制维度（强烈建议）

像这样定义：

Dimension	Levels
Route length	short / medium / long
Detour tolerance	5% / 10% / 20%
Semantic constraints	0 / 1 / 2
Operator count	2 / 3 / 4

👉 直接对标 ANN hardness / workload control（KDD reviewer 会很喜欢）。

（2）Baseline 不是“模型”，而是“能力下界”

Dataset Track 不要求 SOTA，但要求 reference points：

Rule-based planner

Zero-shot LLM

Single-step spatial query baseline

👉 强调：用于 sanity check，而非 SOTA。

（3）Evaluation metrics 要“dataset-centric”

少谈 accuracy，多谈：

feasibility rate

constraint satisfaction

reproducibility across regions

6️⃣ 标题 & 摘要必须一起改（非常重要）
现在的标题问题

太像 systems / LLM paper

Dataset Track reviewer 容易误投

建议标题风格

A Benchmarking Environment for Complex Spatial Queries with Route and Semantic Constraints

或

Generating and Benchmarking Complex Spatial Queries at Scale

摘要里要明确出现：

dataset

generator

benchmark

reuse

最后给你一个 KDD Dataset Track 高分 checklist

如果 reviewer 能在文中直接找到下面这些点，基本是 Strong Accept：

 一句话说清楚 dataset / benchmark / generator 是什么

 明确可下载、可运行、可生成新数据

 清晰 schema + pipeline

 明确质量控制

 多种 reuse 场景（不只是你自己的系统）

 Ethics & bias 讨论

 Benchmark protocol（不是 demo）

如果你愿意，下一步我可以帮你：

🔧 直接重写 Abstract（Dataset Track 版）

📑 重排 Section 结构（按 KDD Dataset Track 口味）

🧑‍⚖️ 模拟一个 Dataset Track reviewer 的打分表

你选一个，我继续。