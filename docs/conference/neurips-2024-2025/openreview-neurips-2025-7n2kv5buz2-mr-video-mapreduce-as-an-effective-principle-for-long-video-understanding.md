---
title: "MR. Video: MapReduce as an Effective Principle for Long Video Understanding"
title_zh: MR. Video：将MapReduce作为长视频理解的有效原则
authors: "Ziqi Pang, Yu-Xiong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7n2Kv5BUz2"
tags: ["query:long-video"]
score: 10.0
evidence: 使用MapReduce原理进行长视频理解与问答
tldr: 该论文针对长视频理解中帧数过多难以同时处理局部细节和全局上下文的问题，借鉴大数据处理的MapReduce原则，将视频切分为短片段单独处理，再聚合片段级分析得到最终答案，实现了可扩展的长视频问答。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1388, \"height\": 794, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 789, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 722, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 873, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1425, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1040, \"height\": 1126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7n2kv5buz2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 873, \"height\": 706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7n2kv5buz2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 957, \"height\": 846, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7n2kv5buz2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7n2kv5buz2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1459, \"height\": 178, \"label\": \"Table\"}]"
motivation: 长视频理解受限于上下文长度，无法同时处理大量帧的局部与全局信息。
method: 采用MapReduce范式，将视频分段独立处理（Map）后合并结果（Reduce）。
result: 在多个长视频QA数据集上达到最先进性能，并支持推理时扩展。
conclusion: MapReduce原则为长视频理解提供了一种有效的系统级解决方案。
---

## Abstract
The fundamental challenge of long video understanding, e.g., question answering, lies in the extensive number of frames, making it infeasible to densely understand the local details while comprehensively digest the global contexts, especially within a limited context length. To address this problem, our insight is to process short video segments individually and combine these segment-level analyses into a final response. This intuition is noted in the well-established MapReduce principle in big data processing and is naturally compatible with inference scaling at the system level. Motivated by this, we propose MR. Video (pronounced as "mister video"), a long video understanding framework adopting the MapReduce principle. We define the standard operations of MapReduce in a long video understanding context: the Map steps conduct independent and sequence-parallel dense perception on short video segments, covering local details, while the Reduce steps comprehensively aggregate the segment-level results into an answer with global contexts. Thanks to the low cost and convenience of building video agents, we instantiate such Map and Reduce operations as an effective video agent capable of attending to local details and global contexts. Based on such abilities, we further introduce two critical yet previously under-explored long video understanding designs: (a) consistent character/object names in the captions, benefiting the reasoning of actions and stories across long horizons; (b) question intention analysis, which changes the key-frame retrieval in previous video agents to localizing the relevant information via jointly reasoning the whole video contexts and questions. Our MR. Video achieves a >7% accuracy improvement on the challenging LVBench over state-of-the-art video agents and vision-language models (VLMs) and demonstrates a clear advantage on multiple long video benchmarks, highlighting the potential of the MapReduce principle. The code is at https://github.com/ziqipang/MR-Video}{https://github.com/ziqipang/MR-Video.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：长视频理解（如问答）面临帧数庞大与上下文长度有限的矛盾，模型难以**同时**密集感知局部细节（如具体事件、角色动作）与全面理解全局上下文（如故事主线、时序关系）。现有方法中：
  - **序列到序列 VLM**：受限于上下文长度，只能稀疏采样或压缩帧，丢失细节。
  - **视频代理**：通过多轮关键帧检索绕过长度限制，但顺序探索可扩展性差，且依赖关键段检索可能忽略全局上下文。
- **整体含义**：需要一种既能密集处理局部信息又能有效聚合全局信息的**可扩展框架**。论文借鉴大数据领域成熟的 **MapReduce 原则**，将长视频视为大数据，通过“分而治之”的思路实现兼具细节覆盖和全局理解的长视频问答。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：采用 **MapReduce 原则**，将长视频分解为短片段：
  - **Map 步骤**：对每个短片段进行**独立**、**序列并行**的密集感知，提取局部细节。
  - **Reduce 步骤**：将所有片段的分析结果进行**全局聚合**，形成统一的答案。
- **关键技术细节**：
  - **两个 MapReduce 阶段**：
    - **(A) 字幕生成阶段**：先通过 Map 生成每个场景的详细描述（含过渡检测），然后在 Reduce 中**合并重复角色/物体**，赋予一致性名称（如 `<person_b>`），为后续推理提供稳定实体。
    - **(B) 分析阶段**：
      - **Ⅰ. 问题意图分析**（取代关键帧检索）：Map 中分析每个片段与问题的相关性，Reduce 中综合全局信息确定最相关的候选场景和关键物体/角色。强调**推理**而非检索。
      - **Ⅱ. 目标感知分析**：根据意图分析结果，Map 中对候选片段进行密集或稀疏帧采样（由 LLM 动态生成查询问题），最后 Reduce 汇总生成最终答案。
- **算法流程（文字说明）**：
  1. 输入长视频，切分为短片段（每段约10秒，进一步细分场景）。
  2. **字幕阶段**：并行调用 VLM 为每个短片段生成密集字幕 + 提取角色特征 →  通过 VLM 比较不同片段的角色描述，合并相同角色并更新字幕。
  3. **问题意图阶段**：将问题 + 字幕输入 LLM，对每个片段分析其与问题的相关性（Map）→ LLM 综合所有片段分析，选出最相关片段并输出候选时间区间与关键角色（Reduce）。
  4. **目标感知阶段**：LLM 为每个候选片段设计特定查询（如“请描述该场景中人物的动作”）→ 并行调用 VLM 回答查询 → 最后 LLM 综合所有 VLM 回答得出最终答案。
- **可扩展性**：Map 步骤可完全并行，关键路径仅 3 个 MapReduce 阶段，支持线性扩展。

### 3. 实验设计：数据集、基准、对比方法

- **主要数据集**：
  - **LVBench**（最挑战）：103 个视频（30 min–2 h），1549 个问题，覆盖 6 类问题（实体识别、事件理解、关键信息检索、时间定位、推理、总结）。
  - **LongVideoBench**（长子集，900–3600 s）、**Video-MME**（无字幕长视频子集）、**EgoSchema**（验证集，180 s 视频）。
- **基准**：各数据集官方准确率。
- **对比方法**：
  - **专有 VLM**：Gemini-1.5-Pro、GPT4o、Gemini-2.0-Flash。
  - **开源 VLM**：InternVL2-40B、TimeMarker、Qwen2-VL-72B、VideoLLaMA3-7B、VideoChat-Flash、AdaReTaKe 等。
  - **视频代理**：VideoAgent、VideoTree、VCA（均使用 GPT4o 等更强 VLM）。
- **实现细节**：MR. Video 使用 Gemini-2.0-Flash（VLM） + GPT4o（文本处理），每次 VLM 查询控制 < 40 帧，显著低于其他 VLM 的 256+ 帧，保证了公平性。

### 4. 资源与算力

- **文中明确说明**：
  - 平均处理 1 小时视频生成密集字幕约需 **$0.8** 的 Gemini-2.0-Flash API 费用。
  - 回答每个 LVBench 问题平均需 **$0.4** 的 GPT4o API 费用。
  - 未提及 GPU 型号、数量、训练时长（因为使用的是 API 而非本地训练/推理）。
- **注意**：本文为**零样本**方法，无需训练，所有计算均为推理成本。

### 5. 实验数量与充分性

- **实验组数**：
  - 主要对比在 **4 个基准**（LVBench、LongVideoBench、Video-MME、EgoSchema）上报告准确率。
  - **消融实验**：在 LVBench 子集（6 个视频，98 个问题）上进行了 3 组消融：
    1. 移除一致角色名称 → 准确率从 63.3% 降至 58.2%。
    2. 移除目标感知分析 → 从 63.3% 降至 52.0%。
    3. 问题意图分析与关键帧检索（MM-Embed）对比：命中率 70.4% vs 34.4%。
  - **案例分析**：展示计数问题与多跳推理的定性示例。
- **充分性评价**：
  - **优点**：覆盖多个长时间基准，消融设计干净，对比基线全面（包含官方成绩与复现）。
  - **不足**：仅运行一次，未报告误差棒（受限于资金）；消融子集规模较小；部分基线引用官方数字而非完全复现。
  - **总体**：实验较为充分，结论可靠，但统计意义略有欠缺。

### 6. 论文的主要结论与发现

- MapReduce 原则能**有效解决**长视频理解中局部细节与全局上下文的矛盾，带来显著性能提升。
- MR. Video 在 **LVBench 上提升 >7%**（60.8% vs 第二名 53.3%），并在其他基准上一致优于视频代理，且**超过其基础 VLM（Gemini-2.0-Flash）**，而其他视频代理大多低于其基础 VLM（GPT4o）。
- 两个关键设计（**一致角色名称**和**问题意图分析**）被证明对长视频推理至关重要，前者辅助跨片段追踪，后者提供比关键帧检索更全面的上下文。

### 7. 优点：方法或实验设计上的亮点

- **创新性**：将 MapReduce 原则从分布式系统引入长视频理解，提供系统级别的可扩展框架。
- **弱化 key-frame 检索**：通过全局上下文推理替代简单检索，更贴合复杂问答需求。
- **低成本验证**：利用现有 API（Gemini 与 GPT）快速构建强代理，无需训练，适合学术探索。
- **序列并行**：Map 步骤完全并行化，关键路径短，推理扩展性好。
- **充分消融**：清晰证明每个组件的贡献，并与检索方法对比凸显意图分析优势。
- **公平对比**：控制 VLM 每次感知帧数（<40 帧），确保不依赖长上下文作弊。

### 8. 不足与局限

- **实验局限**：
  - 仅单次运行，无误差棒，统计鲁棒性不足。
  - 消融子集较小（6 个视频），可能无法完全代表长视频多样性。
  - 所有结果基于 API 调用，不可完全复现（依赖第三方模型版本）。
- **方法局限**：
  - **LLM 代理范式**：依赖文本作为中介，可能丢失细粒度视觉信息（如微表情、物体小细节）。
  - LLM 未经视频理解对齐，可能产生幻觉或错误推理。
  - VLM 失败时代理无法恢复（如案例中的 noodle 识别错误）。
- **成本**：虽然比传统 VLM 更可扩展，但生成密集字幕仍需较大 API 开销（每视频约 $0.8，每个问题约 $0.4）。
- **适用性**：未在实时/低延迟场景下验证；不涉及训练范式，不能内生学习视频结构。
- **风险**：继承底层 LLM/VLM 的社会偏见（文中提及）。

（完）
