---
title: Multi-Factor Adaptive Vision Selection for Egocentric Video Question Answering
title_zh: 多因子自适应视觉选择用于第一视角视频问答
authors: "Haoyu Zhang, Meng Liu, Zixin Liu, Xuemeng Song, Yaowei Wang, Liqiang Nie"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=u00dmbI8Db"
tags: ["query:long-video"]
score: 7.0
evidence: 面向第一视角视频的问答方法
tldr: 第一视角视频问答面临小目标识别、噪声抑制和时空推理挑战。本文提出MFAS框架，利用补丁划分融合增强小目标识别，先验引导补丁选择抑制背景噪声，层次聚合网络支持问题驱动视觉融合。在CharadesEgo、EPIC-Kitchens等数据集上，MFAS在多种问答指标上取得最佳结果，验证了其有效性与泛化能力，为复杂视频问答任务提供了有力工具。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 828, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1722, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 646, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 772, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1650, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1678, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1621, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1730, \"height\": 191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1753, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1740, \"height\": 182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1736, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1727, \"height\": 212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1735, \"height\": 194, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-u00dmbi8db/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1742, \"height\": 1621, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-u00dmbi8db/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1370, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-u00dmbi8db/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 772, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-u00dmbi8db/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 713, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-u00dmbi8db/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1493, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-u00dmbi8db/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1471, \"height\": 686, \"label\": \"Table\"}]"
motivation: 第一视角视频问答中小目标、噪音和时空推理是主要难点。
method: MFAS包含补丁划分融合、先验引导选择和问题驱动的层次聚合网络。
result: 在多个第一视角数据集上显著优于现有方法。
conclusion: 自适应视觉选择能有效提升第一视角视频问答性能。
---

## Abstract
The challenge of interpreting the world from a human perspective in Artificial Intelligence (AI) is particularly evident in egocentric video question answering, which grapples with issues like small object recognition, noise suppression, and spatial-temporal reasoning. To address these challenges, we introduce the Multi-Factor Adaptive vision Selection (MFAS) framework. MFAS integrates a patch partition and merging module for enhanced small object recognition, a prior-guided patch selection module for noise suppression and focused analysis, and a hierarchical aggregation network to aggregate visual semantics guided by questions. Extensive experiments on several public egocentric datasets have validated the effectiveness and generalization of our framework. Code and data are available in https://github.com/Hyu-Zhang/EgoVideoQA.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：第一视角（egocentric）视频问答（VideoQA）是人工智能理解人类视角世界的关键挑战。不同于第三视角视频，第一视角视频具有场景复杂、信息受限、运动不规则等特性，面临三大独特难题：
  - **小目标识别**：在杂乱场景（如厨房、实验室）中，小物体因遮挡、变形、运动模糊而难以检测。
  - **噪声抑制**：第一视角视频中往往存在大量冗余和噪声区域（如背景），干扰对关键交互区域（如手-物体交互）的注意力。
  - **时空推理**：第一视角限制了完整行为观察，需基于局部观测推断全局活动。
- **整体含义**：现有方法多采用通用框架微调，未针对上述挑战设计专门方案。本文旨在首次同时解决这三个问题，提出自适应视觉选择框架，提升第一视角视频问答性能。

## 2. 论文提出的方法论

### 核心思想
提出**多因子自适应视觉选择（MFAS）** 框架，包含三个主要模块：补丁划分与合并模块（PPM）、先验引导补丁选择模块（PS）、层次聚合网络（HA），分别应对小目标识别、噪声抑制、时空推理挑战。

### 关键技术细节

- **补丁划分与合并模块（PPM）**：
  - 将视频帧划分为补丁（patch），再细分更小的子补丁（sub-patch），实现多尺度处理。
  - 引入双空间信息嵌入：子空间嵌入（sub-spatial embedding）、空间嵌入（spatial embedding）和时间嵌入（temporal embedding）。
  - 设计双分支时空注意力结构（Multi-Scale TimeSformer）：补丁分支和子补丁分支，通过下采样/上采样和可学习参数融合双尺度特征。

- **先验引导补丁选择模块（PS）**：
  - 基于第一视角视频的观察：用户注视和手部活动区域通常位于画面中央偏下，初始化先验矩阵A0，标记感兴趣区域。
  - 利用多尺度空间注意力分数（来自TimeSformer最后一层），合并得到每帧的注意力得分S。
  - 选择过程结合当前帧空间关系、前一帧时间关系和数据先验，通过Top-k和一跳邻域约束生成掩码A，确保时间连续性。

- **层次聚合网络（HA）**：
  - 使用多层时空交叉注意力网络，以问题为线索逐步融合视觉语义。
  - 前R-3层保持子补丁粒度，后3层逐步降采样：子补丁→补丁→帧→视频级别。
  - 降采样时同步调整掩码，实现从细粒度到粗粒度的层次聚合。

- **解码器**：分为判别式（MLP）和生成式（LSTM）两种，分别用于选择答案或生成答案。
- **优化**：交叉熵损失；对QAEgo4D数据集额外加入排序损失（LSE loss）。

### 公式或算法流程（文字说明）
- 视频采样得到张量v，经PPM输出多尺度表示和注意力分数。
- 问题经RoBERTa提取表示。
- PS模块根据先验、空间注意力、时间注意力生成视频级掩码A。
- HA模块将视频表示、问题表示、掩码A输入交叉注意力网络，输出问题增强的视频表示和视频增强的问题表示。
- 解码器输出答案。

## 3. 实验设计

- **数据集**：
  - **EgoTaskQA**：2,336个真实视频，平均时长36.9秒，40,000个问答对，分为直接（direct）和间接（indirect）两种子集。
  - **QAEgo4D**：1,325个视频，平均时长495.1秒（长视频），14,513个问答对，专注于情景记忆任务。
- **Benchmark**：在开放集（Open）和二元集（Binary）上评估准确率；在QAEgo4D上还采用BLEU、METEOR、ROUGE指标。
- **对比方法**：包括Most Likely、HGA、BERT、PSAC、VisualBERT、HME、ClipBERT、HCRN、CMCIR、EgoVLP、EgoVLPv2等。对部分方法进行了复现（标注⋆）。

## 4. 资源与算力

- 论文明确说明：所有实验基于PyTorch框架，使用8块V100 GPU。训练40个epoch，batch size为32。
- 未给出具体训练时长，但提及使用8块V100 GPU集群。

## 5. 实验数量与充分性

- **实验数量**：在两个数据集上进行了全面对比（表1、表2）；在EgoTaskQA间接分割上进行了消融实验（表3）；在QAEgo4D上分别测试了生成式和判别式设置；对问题类型（描述、预测、解释、反事实）进行了细粒度对比（附录表4、表5）；对参数k、λ、训练轮数进行了分析（图7）；提供了可视化案例和注意力图（图5、图6、附录图8-12）。
- **充分性**：实验覆盖了不同数据集、不同任务设置、不同问题类型，消融实验验证了每个模块的贡献，参数分析探索了关键超参数影响，可视化展示了机制有效性。实验设计较为充分、客观，对比了多种基线方法（包括经典和最新方法），并复现了部分方法以保证公平性。

## 6. 论文的主要结论与发现

- MFAS在EgoTaskQA上直接/间接全指标上分别比最强基线EgoVLPv2提升2.43%和3.12%。
- 在QAEgo4D上，判别式准确率提升2.2%，生成式准确率提升0.8%。
- 消融实验表明，先验引导补丁选择模块贡献最大（1.45%），补丁划分与合并模块贡献0.69%，层次聚合网络贡献0.88%。
- 可视化显示，先验引导补丁选择能有效抑制噪声，聚焦关键区域（如手-物体交互），并动态适应时间变化。
- 验证了同时解决小目标识别、噪声抑制、时空推理三大挑战的必要性和有效性。

## 7. 优点

- **方法创新性强**：首次针对第一视角视频问答的特定难点设计统一框架，提出了多因子自适应视觉选择机制。
- **模块设计合理**：补丁划分与合并兼顾多尺度；先验引导选择结合先验、空间和时间信息，具有物理可解释性；层次聚合逐步降维，符合认知规律。
- **实验全面且具有说服力**：在两个不同尺度、不同任务的数据集上验证，覆盖多种问题类型和模型变体，消融和参数分析完整。
- **可视化分析有洞察**：展示了注意力图的变化，直观解释了模块如何抑制噪声、聚焦关键区域。
- **代码开源**：提供了GitHub仓库，便于复现和后续研究。

## 8. 不足与局限

- **实验覆盖的局限性**：仅在两个第一视角数据集（EgoTaskQA和QAEgo4D）上测试，未在其他第一视角视频问答数据集（如EgoVQA）上验证，泛化性有待进一步考察。
- **性能上限不明显**：尽管取得了提升，但在某些问题类型（如直接设置中的“action”类别）上不如CMCIR，表明模型在简单动作识别上仍有不足。
- **对长视频的适应性**：QAEgo4D视频平均时长近500秒，但采样仅32帧，可能丢失关键信息。模型对长视频的实时处理能力未讨论。
- **先验假设的局限性**：先验矩阵A0假设视觉焦点在画面中央偏下，但实际应用场景可能变化（如用户转头看向侧面），可能导致错误选择。
- **计算成本**：多尺度TimeSformer和层次交叉注意力可能带来额外计算开销，论文未详细分析推理速度或参数量。
- **评价指标单一**：主要依赖准确率，缺乏对模型鲁棒性、可解释性等方面的量化评估。

（完）
