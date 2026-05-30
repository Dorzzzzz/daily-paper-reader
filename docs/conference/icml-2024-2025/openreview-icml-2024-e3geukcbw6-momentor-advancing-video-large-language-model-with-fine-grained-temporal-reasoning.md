---
title: "Momentor: Advancing Video Large Language Model with Fine-Grained Temporal Reasoning"
title_zh: Momentor：推动视频大语言模型实现细粒度时序推理
authors: "Long Qian, Juncheng Li, Yu Wu, Yaobo Ye, Hao Fei, Tat-Seng Chua, Yueting Zhuang, Siliang Tang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=e3geukCBw6"
tags: ["query:long-video"]
score: 9.0
evidence: 细粒度时序视频理解
tldr: 针对现有视频大语言模型仅能捕获粗略语义、无法处理具体视频段理解的问题，本文提出Momentor，一种能完成细粒度时序理解的视频LLM。通过自动数据生成引擎构建Moment-10M大规模视频指令数据集（含段级标注），训练Momentor实现准确的片段定位与理解。在多个基准上展示了优越的时序推理能力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 836, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1785, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 817, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 405, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 399, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 917, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-e3geukcbw6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 848, \"height\": 611, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-e3geukcbw6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-e3geukcbw6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-e3geukcbw6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1761, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-e3geukcbw6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-e3geukcbw6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 253, \"label\": \"Table\"}]"
motivation: 现有视频LLM仅能捕捉视频粗糙语义，无法有效完成具体片段的定位与理解任务。
method: 提出Momentor模型，并设计自动数据生成引擎构建段级指令数据集Moment-10M进行训练。
result: Momentor在细粒度时序理解任务上达到先进性能，能准确理解与定位视频片段。
conclusion: 通过细粒度时序训练，视频LLM能显著提升对视频中具体事件的理解能力。
---

## Abstract
Large Language Models (LLMs) demonstrate remarkable proficiency in comprehending and handling text-based tasks. Many efforts are being made to transfer these attributes to video modality, which are termed Video-LLMs. However, existing Video-LLMs can only capture the coarse-grained semantics and are unable to effectively handle tasks related to comprehension or localization of specific video segments. In light of these challenges, we propose Momentor, a Video-LLM capable of accomplishing fine-grained temporal understanding tasks. To support the training of Momentor, we design an automatic data generation engine to construct Moment-10M, a large-scale video instruction dataset with segment-level instruction data. We train Momentor on Moment-10M, enabling it to perform segment-level reasoning and localization. Zero-shot evaluations on several tasks demonstrate that Momentor excels in fine-grained temporally grounded comprehension and localization.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有视频大语言模型（Video-LLMs）仅能捕捉视频的粗粒度语义（如全局描述、简单问答），缺乏对视频中**具体片段（segment）的细粒度理解与定位**能力。具体表现为：（1）缺乏有效的时间表示，无法精确编码或输出时间位置；（2）缺乏基于片段的建模，模型仅关注全局语义，无法处理多片段、长视频中复杂事件序列。
- **研究动机**：解决上述限制，使Video-LLM能够基于用户指令进行**片段级的时间推理（fine-grained temporal reasoning）**，包括读取指定片段、定位含有特定内容的片段、以及跨片段关联推理。
- **整体含义**：提出一种**具有细粒度时间感知能力**的视频LLM——Momentor，并构建大规模段级指令数据集Moment-10M，推动视频理解从全局走向局部、从粗粒走向细粒。

## 2. 论文提出的方法论：核心思想、关键技术细节等

### 核心思想
- **Momentor**：基于LLaMA-7B + CLIP ViT-L/14，在原有视频LLM架构上引入**时间感知模块（Temporal Perception Module, TPM）**，使得模型能够精确表示任意时间点，并输出准确时间戳。
- **两阶段训练**：在标准模态对齐和指令微调之间，插入**Grounded Event-Sequence Modeling（GESM）**预训练，让模型学习以时间戳为锚定的事件序列解码。

### 关键技术细节

#### (1) 时间感知模块（TPM）
- **连续时间令牌空间**：将视频均匀划分为N-1个段，定义N个可学习的锚点特征（作为特殊令牌⟨1⟩…⟨N⟩添加至LLM词表），通过**插值（interpolation）**实现时间线上任意位置的连续特征表示，从而避免用离散令牌表示时间时的量化误差。
- **邻域令牌传播（Neighboring Token Propagation, NTP）**：为强化时间令牌的连续性，每次更新时，将当前令牌的梯度传播至其相邻令牌（指数加权），确保邻近令牌嵌入更相似。公式：
  \[
  \tilde{t}_k = t_k + t_{\text{adj}} - \operatorname{StopGrad}(t_{\text{adj}}), \quad t_{\text{adj}} = \sum_{i=1}^{N} \frac{1}{2^{|i-k|}} t_i
  \]
- **时间信息注入**：将采样帧对应时间点的插值特征直接加到帧特征上，作为时间位置编码。

#### (2) Grounded Event-Sequence Modeling（GESM）
- 在模态对齐之后、指令微调之前，使用**事件序列解码**任务：输入未裁剪长视频，输出每个事件的起止时间戳和通用描述。训练损失为语言建模损失（交叉熵）。

#### (3) 自动数据生成引擎（Moment-10M构建）
- **结构化信息提取**：用Grounding DINO检测实例、PySceneDetect检测镜头边界，再通过语义一致性（基于实例轨迹及视觉特征）合并相邻子段得到事件段；构建“实例-事件矩阵”。
- **指令生成**：针对矩阵中的时空关联，用Vicuna生成8种类型的指令数据：5种单段任务（段描述、段QA、实例QA、直接定位、推断定位）和3种跨段任务（组合检索、实例活动总结、跨段QA）。

## 3. 实验设计：数据集、Benchmark、对比方法

### 评估任务与数据集（全部为零样本）
| 任务 | 数据集 |
|------|--------|
| 动作分割（Action Segmentation） | Breakfast, 50Salads |
| 密集视频描述（Dense Video Captioning） | ActivityNet Captions |
| 时间定位（Temporal Grounding） | ActivityNet Captions, Charades-STA |
| 高亮检索（Highlight Moment Retrieval） | QVHighlights |
| 视频问答（Video QA） | ActivityNet-QA, MSRVTT-QA, MSVD-QA |

### 对比方法
- Video-ChatGPT (7B)、VideoChat (7B)、Video-LLaMA (7B)、Valley (7B)

## 4. 资源与算力

- **训练硬件**：8张A100 GPU
- **训练时长**：约60小时
- **可训练参数**：仅更新线性投影层和TPM（帧编码器与LLM冻结）
- **帧数**：每个视频均匀采样M=300帧；时间令牌数N=300

## 5. 实验数量与充分性

- **主要实验**：在4个细粒度任务（动作分割、密集描述、时间定位、高亮检索）以及视频QA上均进行了评估，结果列表（Table 2-4）详实。
- **消融实验**（Table 5）：分别移除连续插值、NTP、GESM、跨段任务，在ActivityNet（时间定位+密集描述）、Breakfast（动作分割）、QVHighlights（高亮检索）上验证各组件贡献。
- **数据集验证**（Figure 5）：用Moment-10M训练Video-ChatGPT对比原始版本，证明数据集有效性。
- **数据规模影响**（Figure 6）：从10K到10M的增量训练，观察性能变化。
- **可视化分析**（Figure 8）：PCA/t-SNE展示时间令牌的连续性，对比有无NTP。
- **案例研究**（Figure 7）：定性展示模型理解能力。

**充分性评价**：实验覆盖了主流细粒度视频理解任务，消融全面，且对数据集自身进行了验证，对比方法均为同期代表性视频LLM。但在零样本设置下进行，**未报告在目标数据集上微调后的结果**，对比公平性存在潜在局限（因为对比方法可能未针对时序任务训练）。

## 6. 论文的主要结论与发现

- Momentor在所有四个细粒度时序任务上**显著超越**所有对比方法（如动作分割MoF提升1.5~6倍，时间定位mIoU提升7~10个点，密集描述CIDEr提升10+点）。
- 消融实验表明每个组件（连续插值、NTP、GESM、跨段任务）均对性能有贡献，其中**NTP对定位精度影响最大**，**GESM对序列理解（如密集描述）关键**。
- 可视化证明时间令牌在NTP作用下呈现连续性，而Vid2Seq的离散令牌缺乏此性质。
- 数据规模从10K增至10M时性能持续提升，但百万级后增速放缓。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 提出**连续时间令牌空间**，解决了离散时间令牌的量化误差，使LLM能精确表示和输出时间。
  - **邻域令牌传播**机制巧妙利用令牌间顺序关系，强化嵌入连续性，确保时间表示的一致性。
  - **Grounded Event-Sequence Modeling**作为桥接训练，弥合了粗粒度对齐与细粒度指令跟随之间的鸿沟。
- **数据引擎**：
  - 自动构建大规模段级指令数据集，包含**1.46M段、451.5K实例轨迹**，任务类型丰富（单段+跨段），且未依赖人工标注，可扩展性强。
- **实验设计**：
  - 零样本评估直接展示泛化能力，具有高实用价值。
  - 消融实验设计细致，单独验证每个模块的贡献。
  - 包含可视化分析（时间令牌嵌入）和案例定性分析，增强说服力。

## 8. 不足与局限

- **缺乏空间建模**：论文未集成任何空间定位能力（如目标框），虽然定性示例显示模型能通过文本理解“左侧”等概念，但空间推理能力有限。
- **数据依赖**：自动数据生成依赖Grounding DINO、PySceneDetect等预训练模型，其检测和场景切换的准确度会影响数据集质量；视频源来自YTTemporal-1B，可能存在隐私或偏见风险。
- **零样本仅覆盖部分领域**：未在更复杂的多事件、长视频（>10分钟）上测试；未与最新的、专门针对时序任务的模型（如Vid2Seq）公平对比（因为Vid2Seq在ActivityNet上经过微调，而本文为零样本）。
- **模型规模固定**：仅实验了7B参数版本，未探索更大规模LLM（如13B/70B）下的性能。
- **资源消耗**：采样300帧用于长视频，导致推理速度较慢，实时应用困难。
- **训练设置**：只更新投影层和TPM，未放松冻结策略，可能限制了模型表征能力。

（完）
