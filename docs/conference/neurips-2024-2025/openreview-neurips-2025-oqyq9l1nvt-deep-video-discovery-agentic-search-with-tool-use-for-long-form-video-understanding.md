---
title: "Deep Video Discovery: Agentic Search with Tool Use for Long-form Video Understanding"
title_zh: 深度视频发现：借助工具使用的代理搜索实现长视频理解
authors: "Xiaoyi Zhang, Zhaoyang Jia, Zongyu Guo, Jiahao Li, Bin Li, Houqiang Li, Yan Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oQYq9L1NVT"
tags: ["query:long-video"]
score: 9.0
evidence: 使用工具进行长视频理解的代理搜索
tldr: 长视频理解面临时间和空间复杂性以及问答困难，本文提出Deep Video Discovery代理，采用智能体搜索策略在视频片段上自主探索，而不预设固定工作流。该方法利用工具使用增强视频分析能力，在长视频问答基准上取得优越性能，展示了自主智能体在长视频解析中的潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1465, \"height\": 1045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1467, \"height\": 1835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1464, \"height\": 1824, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 613, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1278, \"height\": 1002, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 863, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 742, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 644, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 752, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 644, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oqyq9l1nvt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1358, \"height\": 387, \"label\": \"Table\"}]"
motivation: 现有长视频理解方法依赖固定流程，缺乏自主探索能力。
method: 构建代理以智能搜索策略在视频片段上自动定位并回答相关问题。
result: 在长视频问答数据集上优于现有方法，验证了自主搜索的有效性。
conclusion: 智能体搜索范式为长视频理解提供了新的解决路径。
---

## Abstract
Long-form video understanding presents significant challenges due to extensive temporal-spatial complexity and the difficulty of question answering under such extended contexts. 
While Large Language Models (LLMs) have demonstrated considerable advancements in video analysis capabilities and long context handling, they continue to exhibit limitations when processing information-dense hour-long videos. 
To overcome such limitations, we propose the $\textbf{D}eep \ \textbf{V}ideo \ \textbf{D}iscovery \ (\textbf{DVD})$ agent to leverage an $\textit{agentic search}$ strategy over segmented video clips. Different from previous video agents manually designing a rigid workflow, our approach emphasizes the autonomous nature of agents.
By providing a set of search-centric tools on multi-granular video database,
our DVD agent leverages the advanced reasoning capability of LLM to plan on its current observation state, strategically selects tools to orchestrate adaptive workflow for different queries in light of the gathered information.
We perform comprehensive evaluation on multiple long video understanding benchmarks that demonstrates our advantage.
Our DVD agent achieves state-of-the-art performance on the challenging LVBench dataset, reaching an accuracy of $\textbf{74.2\%}$, which substantially surpasses all prior works, and further improves to $\textbf{76.0\%}$ with transcripts.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义（研究动机和背景）

*   **核心问题**：长视频（如电影、会议记录、体育赛事）理解面临巨大挑战，包括时间和空间复杂性高、信息密度大、上下文长度长。现有的大语言模型（LLM）虽然具备长上下文处理能力，但在处理数小时密集信息的视频时仍显不足。
*   **研究动机**：已有的视频代理方法（如 VideoTree、VCA）依赖人工预设的固定工作流，对所有查询统一应用相同的搜索策略，缺乏适应性和自主性。论文认为，不同查询需要不同的搜索路径，利用 LLM 的推理能力进行自适应规划才是关键。
*   **整体意义**：将长视频理解重新定义为**多步信息搜索问题**，通过构建一个自主代理（Agent），将视频视为可探索的环境，利用多粒度工具进行迭代式推理和证据收集，从而提升极端长视频上的问答准确性。

## 方法论：核心思想、关键技术细节与算法流程

### 核心思想
*   **Deep Video Discovery (DVD)**：一个自主、自适应搜索代理。将长视频转换为多粒度结构化数据库，提供三组搜索工具（全局浏览、片段检索、帧级检查），由 LLM 作为核心推理引擎，在“观察-推理-行动”循环中动态规划工具调用序列，自主收集信息直至给出答案。
*   **关键创新**：与手动设计固定工作流不同，DVD 强调**自主性**和**适应性**，让 LLM 根据当前推理状态自由选择下一个工具，从而为每类查询定制最优搜索路径。

### 关键技术细节
1.  **多粒度视频数据库构建（Stage 1）**
    *   **时间分割**：将长视频均匀切分为 5 秒的非重叠片段（`v_i`），按 2 fps 提取帧 `f_i`。
    *   **信息提取**：
        *   **全局层（Global）**：通过大视觉语言模型（VLM）渐进式生成主体注册表 `S`，包含主体名称、外貌、身份、时间跨度和动作描述，最终形成全局摘要。
        *   **片段层（Clip）**：为每个片段生成详细字幕 `c_i`，并利用嵌入模型转换为稠密向量 `e_i`，便于语义检索。
        *   **帧层（Frame）**：保留原始解码帧 `f_i`，用于后续细粒度分析。
    *   **输出**：数据库 `D = {S, {f_i, c_i, e_i}_{i=1}^N}`。

2.  **代理搜索与回答阶段（Stage 2）— Agentic Search and Answer (ASA)**
    *   **搜索工具集 `T`**：
        *   `Global Browse`：提供全局摘要（主体和事件），返回高层上下文。
        *   `Clip Search`：根据代理合成的查询 `\hat{Q}`，计算与片段字幕嵌入的余弦相似度，返回 top-k 相关片段和字幕。
        *   `Frame Inspect`：给定时间范围 `[t_s, t_e]` 和子问题，调用 VLM 对像素级帧进行精细的视觉问答。
    *   **代理推理算法**（类似 ReAct）：
        *   初始化历史 `H_0`，包含用户查询 `Q` 和动作空间 `A = T ∪ {ANSWER}`。
        *   循环（最大步数 `N`）：
            *   LLM `M` 基于历史 `H_{i-1}` 推理产生 `R_i`。
            *   选择一个动作 `A_i ∈ A` 及其参数 `P_i`。
            *   如果 `A_i = ANSWER`，则终止并输出答案。
            *   否则执行 `A_i` 获得观察 `O_i`。
            *   将 `(R_i, A_i, O_i)` 加入历史。
        *   若达到最大步数，强制生成最终答案。
    *   **关键设计**：代理自主分解查询、合成子查询、迭代调用工具，无需人工干预路径。

## 实验设计：数据集、基准与对比方法

### 数据集与基准
| 数据集 | 任务规模 | 备注 |
|--------|----------|------|
| LVBench | 103 个视频，1549 道多选题（时长约 1 小时） | 主要基准，最挑战 |
| LongVideoBench | 长时长子集（900s-3600s）：188 视频，564 题 | 强调极长视频 |
| Video MME | 长时长子集（无字幕）：300 视频，900 题 | 专注长视频理解 |
| EgoSchema | 验证集：500 视频，500 题 | 诊断性基准 |

### 对比方法
*   **商业 VLM**：Gemini-1.5-Pro、Gemini-2.0-Flash、GLM-4V-Plus、GPT-4o、OpenAI o3
*   **开源 VLM**：InternVL2.5-78B、VideoLLaMA3-7B、Qwen2.5-VL-72B、VideoChat-Flash、AdaRETAKE
*   **视频代理**：VideoTree、VideoAgent、VCA、MR. Video
*   **评估指标**：准确率（%）。

## 资源与算力

*   论文未提供明确的 GPU 型号、数量或训练时长信息。整个方法主要依赖**闭源 API 调用**：
    *   数据库构建使用 GPT-4.1（LVBench）或 GPT-4.1-mini（其他基准）。
    *   推理代理使用 OpenAI o3（也包含 Frame Inspect 中的 VLM）。
    *   通过 Azure OpenAI Service 调用，受到**最大图像数（50张/请求）** 和**安全内容过滤**的限制。
*   **成本数据**：在 LVBench 上平均每问题 $2.05、平均 20,803 tokens。反映了迭代推理的高计算开销。

## 实验数量与充分性

### 实验数量
*   **主实验**：在 4 个长视频基准上对比了 9 种以上基线方法（表2、3）。
*   **消融实验**（表4、5、6、7）：
    *   不同模型组合（M_database, M_reasoning, M_tool）的影响。
    *   不同推理模型（o3, o4-mini, GPT-4o, DeepSeek-R1, Qwen3-32B）的对比。
    *   三个搜索工具的独立贡献（去除每个工具导致准确率下降 2.9%~12.3%）。
    *   最大步数限制（8/12/15）和与手工工作流（VideoAgent）的对比。
*   **行为分析**：对推理模型的 5 种行为模式进行统计（图3）。
*   **统计显著性**：在 LVBench 上重复 3 次，平均 74.0%，方差 0.125（附录B.1）。

### 充分性与公平性
*   **充分**：覆盖了主流长视频基准和代表性方法，消融实验系统全面。
*   **公平**：基线结果来自官方排行榜或已发表论文，OpenAI o3 基线使用与 DVD 相同的帧采样策略（256帧），通过 Azure API 统一评估。但内容过滤问题可能导致部分基线数据偏低（论文对此进行了单独分析，见表8）。

## 主要结论与发现

1.  **性能领先**：在 LVBench 上达到 **74.2%**（加字幕 76.0%），比之前最佳方法（MR. Video 60.8%）提升 13.4%，比基座 VLM（OpenAI o3 57.1%）提升 17.1%。在 LongVideoBench、Video MME、EgoSchema 上也分别达到 SOTA。
2.  **推理模型最关键**：消融表明推理模型是系统最重要的组件，更换为 GPT-4o 导致 13.7% 下降，而数据库 VLM 降级影响较小。
3.  **工具组合有效性**：三个工具各有不可替代的作用，Clip Search 贡献最大（缺失下降 12.3%），Frame Inspect 次之（下降 8.4%），Global Browse 最小但也重要（下降 2.9%）。
4.  **自适应工作流优于固定流程**：与手工设计的 VideoAgent 工作流相比，DVD 在更少步骤下获得更高准确率（7.3 步 vs 11.1 步，准确率 74.2% vs 70.2%）。
5.  **行为模式洞察**：简单直接搜索最高效；过度使用 Frame Inspect 或陷入 Clip Search 循环会导致低准确率；GPT-4o 过度自信、提前终止是性能差的主因。

## 优点：方法与实验设计的亮点

*   **自主自适应搜索范式**：放弃预设工作流，让 LLM 自主规划工具序列，显著提升了对不同查询的适应能力。
*   **多粒度工具设计**：全局浏览、片段检索、帧级检查三者互补，平衡了效率与细节把握。
*   **模块化与可扩展性**：数据库构建和代理推理可独立升级，便于融入更强模型。
*   **深入的行为分析**：通过聚类工具调用模式，揭示了推理长度与准确率的双面关系以及过度自信陷阱，为未来代理设计提供指导。
*   **实验覆盖全面**：涵盖多个长视频基准，消融实验系统，且对 API 内容过滤做了单独分析，确保了对比公平。

## 不足与局限

*   **计算开销高**：迭代推理调用多次 API，平均每问题超过 $2，且需要大型 VLM 预处理数据库，实际应用成本较高。论文也承认这是主要局限性之一。
*   **依赖 API 安全过滤**：Azure 内容过滤机制错误拦截了 10%~25% 的查询（不同数据集中），影响了部分性能，且论文的缓解策略（随机选取答案）不够严谨。
*   **信息损失风险**：字幕生成和全局摘要会引入感知压缩，丢失原始视频细节，尽管帧级工具可部分弥补。
*   **实验未覆盖所有类型**：主要针对多选问答，未在开放式生成任务上验证；视频类型以纪录片、电影等为主，多样性有限。
*   **公平性隐患**：模型（尤其是闭源 LLM）训练数据中的偏见可能影响解释，且缺乏公开的偏差分析。论文在 Broader Impacts 中承认了这一点。
*   **未提供开源训练资源**：虽然代码已开源，但模型本身是 API 调用，复现需要付费 API，可复现性受限于服务可用性。

（完）
