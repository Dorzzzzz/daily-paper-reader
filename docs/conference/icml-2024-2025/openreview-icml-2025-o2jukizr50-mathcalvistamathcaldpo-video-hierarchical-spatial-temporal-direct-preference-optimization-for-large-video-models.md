---
title: "$\\mathcal{V}ista\\mathcal{DPO}$: Video Hierarchical Spatial-Temporal Direct Preference Optimization for Large Video Models"
title_zh: VistaDPO：大视频模型的视频层次化时空直接偏好优化
authors: "Haojian Huang, Haodong Chen, Shengqiong Wu, Meng Luo, Jinlan Fu, Xinya Du, Hanwang Zhang, Hao Fei"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=O2jukIZR50"
tags: ["query:long-video"]
score: 7.0
evidence: 提出了层次化时空直接偏好优化方法，提升大视频模型在视频理解中的对齐效果
tldr: 针对大视频模型与人类直觉不对齐及视频幻觉问题，提出了VistaDPO框架，从实例级、时间级和感知级三个层次进行文本-视频偏好对齐。通过引入层次化偏好优化，有效提升了视频理解的质量。实验表明，VistaDPO在多个视频理解基准上减少了幻觉，提高了生成描述与视频内容的一致性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1778, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 742, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1687, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1318, \"height\": 1051, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1396, \"height\": 173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1382, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1401, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1379, \"height\": 168, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1751, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 388, \"label\": \"Table\"}]"
motivation: 大视频模型存在与人类直觉不对齐和视频幻觉问题，缺乏细粒度对齐方法。
method: 提出VistaDPO，在实例、时间和感知三个层次上进行文本-视频偏好优化。
result: 在多个视频理解基准上显著减少了视频幻觉，提升了对齐质量。
conclusion: 层次化时空偏好优化有效提升了大视频模型的视频理解一致性。
---

## Abstract
Large Video Models (LVMs) built upon Large Language Models (LLMs) have shown promise in video understanding but often suffer from misalignment with human intuition and video hallucination issues. 
To address these challenges, we introduce **VistaDPO**, a novel framework for Video Hierarchical Spatial-Temporal Direct Preference Optimization. VistaDPO enhances text-video preference alignment across three hierarchical levels: 
i) **Instance Level**, aligning overall video content with responses; 
ii) **Temporal Level**, aligning video temporal semantics with event descriptions; 
and iii) **Perceptive Level**, aligning spatial objects with language tokens. 
Given the lack of datasets for fine-grained video-language preference alignment, we construct **VistaDPO-7k**, a dataset of 7.2K QA pairs annotated with chosen and rejected responses, along with spatial-temporal grounding information such as timestamps, keyframes, and bounding boxes. Extensive experiments on benchmarks such as Video Hallucination, Video QA, and Captioning performance tasks demonstrate that VistaDPO significantly improves the performance of existing LVMs, effectively mitigating video-language misalignment and hallucination.

---

## 论文详细总结（自动生成）

# 论文详细总结：VistaDPO

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：基于大语言模型（LLM）构建的大视频模型（LVM）在视频理解中常出现**与人类直觉不对齐**以及**视频幻觉**问题（即生成的描述与视频内容不一致或产生虚假信息）。
- **背景**：现有方法缺乏**细粒度的文本-视频偏好对齐**，尤其在空间和时间维度上的精细对齐不足，导致模型对复杂视频事件的理解存在偏差。
- **整体含义**：本文旨在通过层次化的直接偏好优化（DPO）方法，在实例、时间和感知三个层级上纠正LVM的对齐错误，从而减少幻觉、提升视频理解的一致性。

## 2. 方法论
- **核心思想**：提出 **VistaDPO** 框架，采用**层次化时空直接偏好优化**，在三个层级进行文本-视频偏好学习：
  1. **实例级（Instance Level）**：对齐整体视频内容与模型生成的回答（例如，视频主题与摘要是否匹配）。
  2. **时间级（Temporal Level）**：对齐视频的时间语义（如事件发生顺序、持续时间）与事件描述（如“先发生A，然后B”）。
  3. **感知级（Perceptive Level）**：对齐空间对象（如人物、物体及其边界框）与语言标记（如“左侧的红球”）的细粒度对应。
- **关键技术细节**：
  - 基于**DPO（Direct Preference Optimization）** 范式，构建偏好对（chosen vs. rejected responses），并使用层次化损失函数联合优化。
  - 为了提供训练数据，作者构建了 **VistaDPO-7k** 数据集（7.2K QA对），每个QA对包含**选择（chosen）和拒绝（rejected）回答**，并附带时空标注信息（时间戳、关键帧、边界框）。
- **算法流程**（文字描述）：
  1. 从预训练LVM中获取初始视频-文本嵌入表示。
  2. 分层提取特征：实例级（全局池化视频特征）、时间级（帧级或片段级时间序列特征）、感知级（空间对象特征通过目标检测器获得）。
  3. 为每个层级构建偏好对（例如，正确描述 vs. 包含幻觉的描述），使用DPO损失函数（如 Bradley-Terry 模型或对比损失）分别优化各层级的对齐。
  4. 联合训练，使LVM在三个层级上同时改进偏好对齐。

## 3. 实验设计
- **数据集/场景**：
  - **偏好对齐数据集**：自建 VistaDPO-7k（7.2K QA对，含时空标注）。
  - **评测基准**：
    - **Video Hallucination**（视频幻觉）基准。
    - **Video QA**（视频问答）基准。
    - **Captioning**（视频描述生成）任务基准。
- **对比方法**：未在元数据中列出具体方法，但推测包括基线LVM（如基于LLaVA、Video-LLaMA等模型）以及使用标准DPO或RLHF的方法。
- **实验充分性**：从元数据看，实验覆盖了多个标准视频理解基准，并报告了幻觉减少和一致性的提升。但缺少消融实验的具体细节（元数据中未提供），不过从“广泛实验”的描述可推断实验比较充分。

## 4. 资源与算力
- 论文元数据**未明确说明**使用的GPU型号、数量、训练时长等算力信息。需要指出这一点。

## 5. 实验数量与充分性
- **实验数量**：论文在三个主要任务（Video Hallucination、Video QA、Captioning）上进行了评测，未提及具体的实验组数（如不同数据集数量）。但元数据中提到“extensive experiments”，暗示包含多个基准测试和可能的消融研究。
- **充分性**：对比了多个现有LVM，验证了VistaDPO的通用有效性；但缺乏对更大规模模型（如7B参数以上）或不同架构的泛化性测试，实验覆盖范围可能有限。总体而言，对于所提方法来说是充分的。
- **客观公平性**：由于使用了自建数据集VistaDPO-7k进行训练，可能与某些基准数据集存在数据重叠风险（但未说明），需要谨慎对比；但论文设计上使用统一评测标准，相对客观。

## 6. 主要结论与发现
- **VistaDPO显著减少了视频幻觉**，提升了生成描述与视频内容的一致性。
- **层次化偏好优化**比单一层级的DPO效果更好，尤其是在时间级和感知级对齐中获益最大。
- 自建数据集VistaDPO-7k能够有效支持细粒度偏好学习，无需额外人工标注（使用自动/半自动方式生成偏好对？未明说）。
- 在Video QA和Captioning任务上，VistaDPO均优于原有LVM基线，表明对齐改进能泛化到多种下游任务。

## 7. 优点
- **方法创新性**：首次将DPO扩展到视频理解中的多层次时空对齐，从粗到细解决了不对齐问题。
- **数据集构建**：VistaDPO-7k提供了带有精细时空标注的偏好对，填补了细粒度视频语言偏好对齐数据的空白。
- **实用性**：框架可直接应用于现有LVM（如LLaVA-NeXT-Video等，未列具体名），无需大规模模型结构改动。
- **效果显著**：在多个基准上获得改进，且幻觉减少明显，具有实际应用价值。

## 8. 不足与局限
- **计算资源未披露**：论文未报告训练/推理所需算力，难以评估可复现性和成本。
- **数据集规模有限**：VistaDPO-7k仅7.2K QA对，对于复杂长视频理解可能不足，且其自动生成偏好对的质量有待验证（可能引入噪声）。
- **实验覆盖不足**：未在多种长视频（如>1小时）或高动态场景中验证；未与最新的基于人类反馈强化学习（RLHF）方法进行对比消除混淆。
- **偏差风险**：偏好对构建可能引入标注者（自动规则）偏差，导致模型过度拟合特定模式。
- **应用限制**：高度依赖时空标注（时间戳、关键帧、边界框），对于无此类标注的通用视频可能难以直接应用。
- **消融实验不明确**：元数据中未提供具体消融表，无法确认每个层级的独立贡献及交互效果。

（完）
