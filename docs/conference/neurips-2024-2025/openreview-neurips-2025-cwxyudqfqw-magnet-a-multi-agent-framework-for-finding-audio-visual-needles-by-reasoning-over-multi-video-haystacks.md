---
title: "MAGNET: A Multi-agent Framework for Finding Audio-Visual Needles by Reasoning over Multi-Video Haystacks"
title_zh: MAGNET：多智能体框架实现多视频海量数据中的音视频细针检索
authors: "Sanjoy Chowdhury, Mohamed Elmoghany, Yohan Abeysinghe, Junjie Fei, Sayan Nag, Salman Khan, Mohamed Elhoseiny, Dinesh Manocha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CwXyUdqFqW"
tags: ["query:long-video"]
score: 8.0
evidence: 多视频问答基准与框架
tldr: 现有视频问答基准局限于单视频片段，无法应对实际应用中的多视频检索与推理需求。本文提出MAGNET多智能体框架，通过跨视频推理定位音视频片段并生成答案，同时构建AVHaystacksQA基准。在多个视频集合上的实验表明，该方法能有效整合音视频线索，显著提升长视频多片段理解能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1398, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 1011, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1155, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1152, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1155, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1157, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1434, \"height\": 1012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 1448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1435, \"height\": 1001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1442, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1435, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1433, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1398, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 881, \"height\": 1095, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 886, \"height\": 1130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 874, \"height\": 1126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 714, \"height\": 1093, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 924, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 511, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 658, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 800, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1356, \"height\": 1203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1325, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1461, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1461, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1180, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1462, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1198, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1382, \"height\": 104, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1422, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1406, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cwxyudqfqw/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1446, \"height\": 515, \"label\": \"Table\"}]"
motivation: 现有视频问答任务局限于单视频片段，缺乏面向多视频集合的推理基准。
method: 提出MAGNET多智能体框架，通过跨视频检索与推理回答音视频问题。
result: 在AVHaystacksQA基准上，该方法能有效定位并整合多个视频中的相关片段。
conclusion: 为多视频开放域问答提供了新范式与基准，推动长视频理解发展。
---

## Abstract
Large multimodal models (LMMs) have shown remarkable progress in audiovisual understanding, yet they struggle with real-world scenarios that require complex reasoning across extensive video collections. Existing benchmarks for video question answering remain limited in scope, typically involving one clip per query, which falls short of representing the challenges of large-scale, audiovisual retrieval and reasoning encountered in practical applications. To bridge this gap, we introduce a novel task named AVHaystacksQA, where the goal is to identify salient segments across different videos in response to a query and link them together to generate the most informative answer. To this end, we present AVHaystacks, an audio-visual benchmark comprising 3100 annotated QA pairs designed to assess the capabilities of LMMs in multi-video retrieval and temporal grounding task. Additionally, we propose a model-agnostic, multi-agent framework MAGNET to address this challenge, achieving up to 89% and 65% relative improvements over baseline methods on BLEU@4 and GPT evaluation scores in QA task on our proposed AVHaystacks. To enable robust evaluation of multi-video retrieval and temporal grounding for optimal response generation, we introduce two new metrics, STEM, which captures alignment errors between a ground truth and a predicted step sequence and MTGS, to facilitate balanced and interpretable evaluation of segment-level grounding performance.

---

## 论文详细总结（自动生成）

# 论文总结：MAGNET：多智能体框架实现多视频海量数据中的音视频细针检索

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有大型多模态模型（LMM）在音视频理解上进展显著，但在面对需要跨大量视频集合进行复杂推理的真实场景时表现不佳。现有视频问答基准通常每个查询仅涉及一个短片，无法反映实际应用（如个人视频档案检索、教程库查询）中对大规模音视频检索与推理的挑战。
- **核心问题**：缺乏系统评估LMM在多视频检索、时间定位和跨视频答案合成能力的任务与基准。
- **整体含义**：提出新任务**AVHaystacksQA**，要求模型在多达500个视频片段中识别并整合相关片段，生成信息丰富的答案。该任务更贴近真实信息检索需求，推动音视频理解和推理研究。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 提出**MAGNET**，一个模型无关的多智能体检索增强生成（RAG）框架。通过两步检索流程（粗粒度视频级检索 + 细粒度帧级选择）和多智能体推理，从海量视频中定位关键片段并合成答案。

### 关键技术细节
1. **音视频预处理 (AV-RAG)**：
   - 使用ImageBind编码查询和视频的音视频特征（Hadamard融合）及音频-视频字幕特征（由Gemini 1.5 Pro生成）。
   - 计算余弦相似度，取两者平均得到`Sim_avg`，排序后选取top-k相关视频。

2. **显著帧选择模块 (SFS)**：
   - 目的：从长视频中高效定位关键事件，避免均匀采样带来的信息冗余。
   - 步骤：
     - 均匀采样m帧，计算每帧的音视频融合嵌入。
     - 计算帧间余弦相似度矩阵`Γ`。
     - 引入时间分离惩罚`Δ`（基于正弦函数），得到亲和矩阵`Q = Γ + Δ`。
     - 使用动态规划（Algorithm 1）选择k个代表性帧，最小化相邻选中帧的成对总相似度（即鼓励视觉多样性和时间分散）。

3. **多智能体问答**：
   - 对每个候选视频，实例化一个Qwen 2.5 Omni智能体进行独立分析，预测相关时间片段及部分答案。
   - **元智能体**（GPT-4o）聚合所有智能体输出，合成最终的上下文相关答案。

4. **两个新评估指标**：
   - **STEM (Step-wise Error Metric)**：量化预测步骤序列与真实步骤序列的对齐错误，包括缺失步、幻觉步、顺序错乱、视频ID误检、时间交并比（IoU）等。
   - **MTGS (Matched Temporal Grounding Score)**：对匹配的相同视频ID，计算预测时间区间与真实时间区间的平均IoU，若没有匹配则得分为0。

## 3. 实验设计：数据集、Benchmark、对比方法

### 数据集与Benchmark
- **AVHaystacks**：自主构建的基准，包含500个YouTube视频（覆盖27类，如烹饪、旅行、乐器、语言等），总计103小时；3100个QA对（训练/测试：2k/1k）；82%的QA对需引用至少两个不同视频的证据。
- **两个子集**：
  - **AVHaystacks-50**：小规模子集用于基线实验。
  - **AVHaystacks-Full**：完整集合。

### 对比方法
- **基线模型**：VideoRAG、Video-RAG、Qwen 2.5 Omni、Unified IO2、Video-SALMONN。
- **MAGNET变体**：分别结合上述模型的零样本（ZS）和微调（FT）版本，以及使用Gemini 1.5 Pro作为上界参考。

### 评估指标
- **回答对齐**：BLEU@4、CIDEr、文本相似度（GTE-L）、GPT-as-a-Judge（10分制）、人工评估（1-5分）。
- **检索**：R@1、R@3、R@5。
- **时间定位**：MTGS_avg、STEM（包含SM、SH、SO、SFP、SFN）。

## 4. 资源与算力

- **训练**：4张A100 GPU，5个epoch。
- **微调方式**：LoRA（秩=8，alpha=32）。
- **优化器**：AdamW，学习率1e-4，批量大小1（每个设备），梯度累积16步。
- **调度器**：余弦学习率调度，预热比例0.05。
- **说明**：论文明确给出了训练配置和硬件信息。

## 5. 实验数量与充分性

- **主要实验**：在主表（Table 2~4）上评估了多种模型在AVHaystacks-50和AVHaystacks-Full上的回答对齐、定位误差和检索性能。
- **消融实验**：
  - 模态重要性（音频/视觉单独 vs 联合）。
  - 采样策略（SFS vs 均匀采样）。
  - 惩罚超参数γ（5,10,15,20,25）。
  - Top-k视频选择（k=1,3,6,10）。
  - 元智能体类型（Reka、Qwen、Claude、GPT、Gemini）。
  - 帧采样函数（余弦、指数、正弦逆函数）。
  - 帧数量（15,50,75）。
  - 文本相似度阈值（0.3,0.5,0.7）。
- **定性分析**：提供了多个案例（图9-13）及失败案例（图15）。
- **人机评价**：20名评估者验证STEM指标与人类判断的相关性（Cohen's κ=0.82）。
- **充分性**：实验覆盖全面，从检索、时间定位到回答生成均进行了多维度评估，消融实验系统。但仅在自建基准上测试，未在现有其他音视频基准（如AVQA、Music-AVQA）上进行跨验证，可能存在领域偏差。

## 6. 主要结论与发现

1. **MAGNET显著优于所有基线**：在AVHaystacks-Full上，MAGNET+Qwen 2.5 Omni-FT相对于最佳基线在BLEU@4上相对提升89%，GPT评估提升65%。
2. **多模态融合不可或缺**：同时使用音频和视觉模态效果最佳（Table 5）。
3. **SFS策略优于均匀采样**：显著提升时间定位和答案质量（Table 6）。
4. **微调带来大幅增益**：微调后的AVLLM（Qwen 2.5 Omni-FT）零样本和微调版本差距显著（BLEU@4从30.54提升至55.82）。
5. **检索性能提升**：MAGNET的检索模块在R@3和R@5上超过现有检索方法（如VideoRAG）。
6. **新指标STEM与MTGS有效**：与人类评估高度相关，能捕捉步骤顺序、缺失等错误。

## 7. 优点

- **任务创新**：首次系统定义并构建多视频链接的音视频问答任务，填补了现有基准的空白。
- **框架模块化与模型无关**：MAGNET可灵活替换不同AVLLM作为智能体，且SFS模块可适配封闭源模型。
- **评估全面**：引入STEM和MTGS两个细粒度指标，超越传统整体文本相似度，能诊断具体错误类型。
- **消融充分**：详细分析了模态、采样、帧数、阈值等超参数影响，为实际部署提供指导。
- **人工验证**：进行了多轮人工评估，确保数据质量和指标可靠性。

## 8. 不足与局限

- **基准覆盖有限**：仅基于YouTube的27类教程/教育视频，未涵盖新闻、体育、电影等更广泛场景，可能存在域偏差。
- **检索失败实例**：当不同物体在视觉和听觉上相似（如小提琴与大提琴）时，检索模块易混淆（见Fig.15）。
- **计算成本**：每个查询需实例化多个AVLLM智能体（top-k视频），推理延迟较高，未详细分析实时性。
- **未与其他音视频基准比较**：仅在AVHaystacks上评估，未在AVQA、Music-AVQA等现有基准上验证，难以对比通用性。
- **元智能体依赖**：当前使用GPT-4o作为元智能体，可能引入闭源模型的偏见和不可复现性；论文也未探讨完全开源替代方案。
- **微调样本量较小**：训练集仅2k QA对，尽管使用LoRA缓解，但模型泛化能力可能受限。

（完）
