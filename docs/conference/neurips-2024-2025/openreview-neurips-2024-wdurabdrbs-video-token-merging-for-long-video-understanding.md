---
title: Video Token Merging for Long Video Understanding
title_zh: 用于长视频理解的视频令牌合并
authors: "Seon-Ho Lee, Jue Wang, Zhikang Zhang, David Fan, Xinyu Li"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=wduRaBDRBS"
tags: ["query:long-video"]
score: 8.0
evidence: 用于长视频分类的令牌合并策略
tldr: 针对长视频Transformer模型中输入采样或丢弃导致信息丢失的问题，本文探索了考虑令牌显著性的视频令牌合并策略，从图像令牌合并扩展至区域集中合并等。实验表明，基于显著性的令牌合并能在减少计算量的同时保持分类性能。该方法为长视频高效理解提供了实用方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1092, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1237, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1351, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1326, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wdurabdrbs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1325, \"height\": 1383, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1152, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1166, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 698, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 713, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 796, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1069, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wdurabdrbs/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 552, \"height\": 208, \"label\": \"Table\"}]"
motivation: 长视频输入在Transformer模型中面临计算开销和信息丢失的权衡。
method: 提出考虑令牌显著性的视频令牌合并策略，包括区域集中合并等。
result: 在长视频分类任务上，基于显著性的合并方法在降低计算量的同时保持了较高性能。
conclusion: 令牌合并是长视频高效处理的有效方法，应结合令牌显著性。
---

## Abstract
As the scale of data and models for video understanding rapidly expand, handling long-form video input in transformer-based models presents a practical challenge. Rather than resorting to input sampling or token dropping, which may result in information loss, token merging shows promising results when used in collaboration with transformers. However, the application of token merging for long-form video processing is not trivial. We begin with the premise that token merging should not rely solely on the similarity of video tokens; the saliency of tokens should also be considered. To address this, we explore various video token merging strategies for long-form video classification, starting with a simple extension of image token merging, moving to region-concentrated merging, and finally proposing a learnable video token merging (VTM) algorithm that dynamically merges tokens based on their saliency. Extensive experimental results show that we achieve better or comparable performances on the LVU, COIN, and Breakfast datasets. Moreover, our approach significantly reduces memory costs by 84% and boosts throughput by approximately 6.89 times compared to baseline algorithms.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：随着视频理解数据和模型的规模迅速扩大，基于Transformer的模型在处理长视频输入时面临严峻挑战。直接对输入进行采样或丢弃令牌会导致信息丢失。虽然令牌合并（token merging）在图像领域展现潜力，但直接应用于长视频并非易事。
- **核心问题**：长视频中时空令牌冗余度高，且包含复杂的局部和全局依赖关系。现有令牌合并方法仅依赖令牌间的相似性，未考虑令牌的显著性，导致重要区域的信息在合并后退化。
- **研究含义**：提出动态、基于显著性的视频令牌合并策略，在减少计算开销的同时保持或提升分类性能，为长视频高效理解提供实用方案。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：令牌合并不应仅依赖相似性，还应考虑每个令牌的显著性（saliency）。对显著区域应保留更多未合并令牌，对背景区域则合并更多令牌。
- **技术路线**：
  - **朴素VTM**：直接扩展图像令牌合并方法，均匀划分目标/源令牌，基于相似性合并。
  - **区域集中VTM**：根据先验知识（如中心区域更重要），对中心区域和边界区域采用不同的划分因子，实现中心集中或边界集中合并。
  - **运动指导VTM**：利用视频编码中已有的运动向量（motion vector）计算每个令牌的采样概率，基于运动幅度选取目标令牌。
  - **可学习VTM（Learnable VTM）**：
    - 引入可学习的显著性估计模块，通过 `S = tanh(K U_s)` 为每个令牌估计显著性分数（范围-1～1）。
    - 基于显著性分数进行目标令牌采样，替代均匀/固定划分。
    - 设计辅助路径：采用显著性引导的自注意力（`softmax((Q_aux K_aux^T + 1S^T)/√C) V_aux`），使高显著性令牌在注意力过程中贡献更大。
    - 辅助路径仅在训练时使用，推理时仅需主路径（额外计算量极低）。
  - **合并操作**：匹配后采用平均池化合并，丢弃加权平均池化（实验显示影响性能）。
- **网络结构**：基线为3个Transformer块，每个块后插入VTM层逐步减少令牌数。采用ViT-L/Swin-B作为编码器。

## 3. 实验设计
- **数据集**：
  - **LVU**：约30K视频（来自MovieClips），时长1-3分钟，9个任务（内容理解：relationship, speaking style, scene/place；元数据预测：director, genre, writer, year；用户参与：like ratio, popularity）。
  - **Breakfast**：1,712个视频，平均2.32分钟，10类复杂烹饪活动。
  - **COIN**：11,827个视频，平均2.36分钟，180个程序性任务。
- **对比方法**：
  - 长视频理解基线：Obj. T4mer, VideoBERT, Performer, Orthoformer, LSTM, ViS4mer, S5, S5+LSMCL。
  - 令牌选择/合并：ToMe（图像级）、ToMe视频扩展等。
- **评估指标**：分类任务使用top-1准确率，用户参与任务使用MSE，同时记录GPU内存和吞吐量。

## 4. 资源与算力
- **计算资源**：8块NVIDIA Tesla V100 GPU（32GB显存）。
- **训练配置**：AdamW优化器，batch size 16，weight decay 0.01，学习率0.001，余弦学习率调度（10 epochs热身），共70 epochs。
- 论文明确提供了硬件和训练超参数。

## 5. 实验数量与充分性
- **实验总量**：涵盖3个数据集、对比8+方法、多组消融实验（包括不同γ值、不同令牌数R、不同帧分区策略(L1,L2,L3)、加权平均池化、运动加权平均池化），以及训练/推理时的吞吐量和内存对比。
- **充分性**：实验设计较为全面，每个关键设计均经过消融验证，且与SOTA方法进行了公平比较（使用相同预训练设置、相同输入帧数）。在COIN数据集上因视频失效导致部分对比不完美，但作者已说明。
- **客观性**：结果报告了多个指标，未发现选择性报告或遗漏负面结果。

## 6. 主要结论与发现
- **性能提升**：可学习VTM在LVU的9个任务中7个取得最佳或第二佳，在Breakfast上达到91.26%准确率（超越S5+LSMCL），在COIN上达到88.55%（与S5相当但数据有缺失）。
- **效率提升**：相比基线（LVU场景预测），GPU内存减少84%（从10GB降至1.6GB），吞吐量提升约6.89倍（从6.52升至44.94样本/秒）。
- **关键发现**：令牌显著性比单纯的相似性更重要；固定区域集中合并（如中心集中）优于均匀合并，但可学习方案进一步超越手工设计；辅助路径可有效训练显著性估计模块。

## 7. 优点
- **创新性**：首次在长视频令牌合并中引入显著性概念，摆脱单纯依赖相似性的局限。
- **实用性**：运动信息可直接从压缩视频中零成本获取（0.3ms/帧），可学习方法额外计算量极小。
- **有效性**：在多个长视频数据集上优于或持平SOTA，同时大幅降低计算开销。
- **设计巧妙**：辅助路径用于训练显著性估计，推理时只保留轻量主路径，兼顾训练效率和推理速度。

## 8. 不足与局限
- **实验覆盖**：未在S4等替代架构上验证（作者声明留作未来工作），因此结论主要适用于标准Transformer。
- **数据依赖**：COIN数据集中部分视频已不可用，导致对比不完全公平；虽然作者已说明，但仍影响结论的绝对可靠性。
- **任务局限**：仅在分类任务上验证，未扩展到检测、分割或视频生成等下游任务。
- **解释性**：显著性分数的物理意义未深入分析，合并后的令牌语义解释性不足。
- **预处理依赖**：使用ImageNet-21K或Kinetics-600预训练的编码器，未探索从零训练的影响。

（完）
