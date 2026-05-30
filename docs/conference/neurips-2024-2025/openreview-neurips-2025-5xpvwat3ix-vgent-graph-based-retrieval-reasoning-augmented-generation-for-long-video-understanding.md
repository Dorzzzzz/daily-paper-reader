---
title: "Vgent: Graph-based Retrieval-Reasoning-Augmented Generation For Long Video Understanding"
title_zh: Vgent：基于图的检索推理增强生成用于长视频理解
authors: "Xiaoqian Shen, Wenxuan Zhang, Jun Chen, Mohamed Elhoseiny"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5xPvWat3IX"
tags: ["query:long-video"]
score: 9.0
evidence: 基于图的检索推理增强生成用于长视频理解
tldr: 该论文针对长视频理解中视频标记超出上下文窗口及时序依赖丢失的问题，提出图结构检索推理增强框架Vgent，通过构建视频片段图谱并引导检索聚焦于最相关的时序信息，在长视频问答任务上显著超越了现有模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1414, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1359, \"height\": 742, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5xpvwat3ix/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1366, \"height\": 591, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1372, \"height\": 1057, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1228, \"height\": 851, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1143, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1388, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1149, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5xpvwat3ix/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1391, \"height\": 623, \"label\": \"Table\"}]"
motivation: 现有长视频模型难以处理超长视频并保持时序信息。
method: 构建视频片段图结构，进行检索增强推理。
result: 在多个长视频基准上取得最先进结果。
conclusion: 图结构检索有效解决了长视频理解中的时空信息丢失问题。
---

## Abstract
Understanding and reasoning over long videos pose significant challenges for large video language models (LVLMs) due to the difficulty in processing intensive video tokens beyond context window and retaining long-term sequential information. Retrieval-Augmented Generation (RAG) has demonstrated effectiveness in processing long context for Large Language Models (LLMs); however, applying RAG to long video faces challenges such as disrupted temporal dependencies and inclusion of irrelevant information that can hinder accurate reasoning. To address these limitations, we propose Vgent, a novel \textbf{graph-based retrieval-reasoning-augmented generation framework} to enhance LVLMs for long video understanding. Our approach introduces two key innovations: (i) It represents videos by structured graphs with  semantic relationships across video clips preserved to improve retrieval effectiveness. (ii) It introduces an intermediate reasoning step to mitigate the reasoning limitation of LVLMs, which leverages structured verification to reduce retrieval noise and facilitate the explicit aggregation of relevant information across clips, resulting in more accurate and context-aware responses. We comprehensively evaluate our framework with various open-source LVLMs on three long-video understanding benchmarks. Our approach yielded an overall performance improvement of $3.0\%\sim 5.4\%$ over base models on MLVU, and outperformed state-of-the-art video RAG methods by $8.6\%$. Our code is publicly available at https://xiaoqian-shen.github.io/Vgent.

---

## 论文详细总结（自动生成）

# Vgent：基于图的检索推理增强生成用于长视频理解——论文总结

## 1. 核心问题与整体含义（研究动机与背景）

**研究动机：** 大型视频语言模型（LVLMs）在处理长视频时面临两大挑战：一是视频标记数量远超模型上下文窗口（如30分钟视频超过20万标记），二是现有稀疏帧采样或标记压缩方法导致视觉信息丢失，难以保持长时序依赖。

**背景：** 检索增强生成（RAG）在长文本LLM中表现有效，但直接应用于长视频会破坏实体连续性和时序依赖，且检索到的噪声片段会干扰模型推理。

**整体含义：** 论文提出一种新颖的**图结构检索-推理增强生成框架Vgent**，通过离线构建视频片段图保留语义关系和时序依赖，并通过结构化推理步骤过滤噪声、聚合跨片段信息，从而显著提升LVLMs的长视频理解能力。

## 2. 方法论：核心思想、关键技术细节与流程

**核心思想：** 将视频表示为结构化图，节点为视频片段，边通过共享实体连接；然后在检索后增加一步结构化推理，分解查询、验证每个片段的关联性，并聚合信息用于最终生成。

**关键技术细节与流程（共四个阶段）：**

1. **离线视频图构建：**  
   - 将视频分割为K帧的短片段（K=64，采样率1 FPS）。  
   - 对每个片段，用LVLM提取实体、动作、场景描述（支持字幕输入）。  
   - 通过文本嵌入（BAAI/bge-large-en-v1.5）计算实体描述相似度，合并语义等价的实体（阈值τ=0.7）。  
   - 连接包含相同实体的节点，形成图。

2. **基于图的检索：**  
   - 从用户查询中提取关键词。  
   - 对每个关键词，计算与实体描述的相似度，若大于阈值θ=0.5则检索该实体关联的所有节点。  
   - 根据关键词与节点全部信息（实体、描述、字幕）的相似度对检索节点排序，取Top-N（N=20）个节点。

3. **结构化推理：**  
   - 生成结构化子查询（是/否或计数问题），用于验证每个检索片段是否包含相关实体或事件。  
   - 对Top-N片段分别回答子查询，仅保留至少对一个子查询响应为正的片段（最多保留r=5个）。  
   - 聚合所有结构化查询结果形成推理摘要，作为增强上下文。

4. **多模态增强生成：**  
   - 将筛选后的视频片段（视觉+字幕）与结构化推理结果一起输入LVLM，生成最终答案。

**公式说明：** 实体合并使用`sim(t_ij, t_u) > τ`；检索使用`sim(k, t_u) > θ`；保留节点集合`R' = {vi ∈ R | ∃ qj ∈ Q, f(vi, qj) > 0}`。

## 3. 实验设计

**数据集/基准：**
- **MLVU**：视频长度3分钟~2小时，平均12分钟，含多种子任务（Count, Order, Needle, PlotQA等）。  
- **VideoMME**：视频11秒~1小时，分无字幕/有字幕两个子集。  
- **LongVideoBench (LVB)**：侧重长时序推理的多选题。

**对比方法：**
- **基线LVLMs**：InternVL2.5 (2B/7B)、Qwen2-VL (2B/7B)、Qwen2.5-VL (3B/7B)、LongVU (7B)、LLaVA-Video (7B)等。  
- **RAG基线**：NaïveRAG（按Goldfish）、Video-RAG（CLIP关键帧+目标检测+OCR）。  
- **闭源API方法**（仅参考）：VideoAgent、LLoVi、DrVideo、VideoTree（使用GPT-4等）。  
- **消融组件**：GraphRAG vs NaïveRAG；结构化推理 vs 置信度筛选。

**实验充分性：**
- 共在3个基准上测试，涉及7种LVLM（规模2B~7B）。  
- 进行完整消融（表3、表4、表7），包括检索数N、阈值τ、嵌入类型、保留片段数r等。  
- 分析了推理时间（表5）、失败案例、定性示例（图3、5、6）。  
- 实验设计客观公平，所有超参数在三个基准上保持一致。

## 4. 资源与算力

论文仅说明“所有实验在A100 80G GPU上进行”，**未明确指明使用的GPU数量、训练时长或浮点运算量**。从推理时间分析表（表5）可见，离线图构建每分钟视频需20.13秒，在线处理每分钟视频需3.93秒。由于仅做推理（无模型训练），算力需求较低。总体而言，资源描述不够详细。

## 5. 实验数量与充分性

**实验数量：** 相当充足。  
- 主结果表1（MLVU、VideoMME、LVB上对比7种LVLM）。  
- RAG方法对比表2（3种LVLM + 与Video-RAG、闭源方法比较）。  
- 消融实验：  
  - 表3：NaïveRAG vs GraphRAG vs SR vs 完整框架。  
  - 表4：保留片段数r从1到6的详细子任务影响。  
  - 表7：结构化推理 vs 置信度推理。  
  - 图4：嵌入类型、检索数N、阈值τ的消融。  
- 类别级性能（表6）、推理时间分析（表5）、定性示例（图3、5、6）。  
- 附录中还提供了提示词模板和输出示例。

**充分性评价：** 实验设计系统，覆盖了核心组件、超参数敏感性和不同模型规模，结论稳健。但缺少对更多随机运行的误差棒报告，也未提供统计显著性检验；实验仅在单一固定种子下运行，可能未完全反映模型波动。

## 6. 主要结论与发现

1. 提出的Vgent框架在MLVU上对8种LVLM提升3.0%~5.4%，在VideoMME上提升1.0%~3.8%，在LVB上提升2.5%~3.7%。  
2. 基于图的检索（GraphRAG）比朴素RAG（NaïveRAG）平均提升2.9%，特别是在需要跨片段推理的Count和Order任务上提升显著。  
3. 结构化推理（SR）在GraphRAG基础上额外提升2.6%，有效过滤检索噪声（论文指出约40%失败案例中正确片段虽被检索到但模型仍答错）。  
4. 整体框架在MLVU上比现有最佳视频RAG方法（Video-RAG）提升8.6%（Qwen2.5-VL 7B上72.1% vs 63.4%）。  
5. 小模型（Qwen2.5-VL 3B）借助Vgent达到70.4%，超越其7B原模型（68.8%），表明框架可缩小模型规模差距。  
6. 离线图构建可重复使用，在多查询场景下比Video-RAG快1.73倍。

## 7. 优点

- **创新性**：首次提出基于图结构视频RAG + 结构化推理的后检索增强范式，有效解决长视频时序依赖和检索噪声两大难题。  
- **实践性**：模型无关、无需额外训练，可直接应用于任意LVLM；图构建为离线可复用，在线效率高。  
- **实验全面**：覆盖多种LVLM、三个主流基准、多维度消融，代码开源。  
- **解释性强**：通过定性示例清晰展示图构建如何连接相关片段、结构化推理如何纠正错误回答（如“打开笔记本”案例）。  
- **成本可控**：不依赖闭源API，全部基于开源模型，资源开销合理。

## 8. 不足与局限

- **图表示依赖文本描述**：图节点只保存实体文本描述，未融入视觉特征或帧级嵌入，可能丢失细粒度视觉信息（作者自身指出这一点）。  
- **超参数通用性**：阈值τ、θ、N、r对所有基准统一设置，但最优值可能因视频类型而异，缺乏自动选择机制。  
- **无误差棒报告**：固定随机种子运行，未提供统计显著性检验或多次运行的标准差，结果鲁棒性未充分验证。  
- **资源描述不完整**：未提供GPU数量、总计算时间等细节，影响可复现性评估。  
- **长视频极端场景**：视频最长2小时（MLVU），但更长的视频（如数小时）下图构建时间线性增长，未讨论扩展性。  
- **模型能力上限**：框架性能受限于基座LVLM的质量（作者承认），未来更强模型可能需调整检索策略。

（完）
