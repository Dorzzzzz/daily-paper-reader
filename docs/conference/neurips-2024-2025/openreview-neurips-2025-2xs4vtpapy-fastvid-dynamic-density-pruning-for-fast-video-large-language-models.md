---
title: "FastVID: Dynamic Density Pruning for Fast Video Large Language Models"
title_zh: FastVID：面向快速视频大语言模型的动态密度剪枝
authors: "Leqi Shen, Guoqiang Gong, Tao He, Yifeng Zhang, pengzhang liu, Sicheng Zhao, Guiguang Ding"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2xS4VtpApy"
tags: ["query:long-video"]
score: 7.0
evidence: 动态密度剪枝加速视频大语言模型
tldr: 该论文分析了视频中时空冗余信息，提出动态密度剪枝框架FastVID，通过时序分段和密度基剪枝策略，去除了大量冗余视频标记，在不明显损失性能的情况下显著加速了视频LLM的推理速度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1408, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 736, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1352, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 2243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 2348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2xs4vtpapy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1423, \"height\": 2254, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 652, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1290, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 696, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 503, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 727, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 792, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 881, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2xs4vtpapy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 542, \"height\": 195, \"label\": \"Table\"}]"
motivation: 视频LLM推理成本高，因视频标记存在大量时空冗余。
method: 将视频按时序分段，并基于密度对标记进行选择性剪枝。
result: 在多个视频理解基准上，速度提升显著且性能损失极小。
conclusion: 利用视频冗余特性进行剪枝是提升视频LLM效率的有效途径。
---

## Abstract
Video Large Language Models have demonstrated strong video understanding capabilities, yet their practical deployment is hindered by substantial inference costs caused by redundant video tokens. 
Existing pruning techniques fail to effectively exploit the spatiotemporal redundancy present in video data. 
To bridge this gap, we perform a systematic analysis of video redundancy from two perspectives: temporal context and visual context. 
Leveraging these insights, we propose Dynamic Density Pruning for Fast Video LLMs termed FastVID.
Specifically, FastVID dynamically partitions videos into temporally ordered segments to preserve temporal structure and applies a density-based token pruning strategy to maintain essential spatial and temporal information.
Our method significantly reduces computational overhead while maintaining temporal and visual integrity. 
Extensive evaluations show that FastVID achieves state-of-the-art performance across various short- and long-video benchmarks on leading Video LLMs, including LLaVA-OneVision, LLaVA-Video, Qwen2-VL, and Qwen2.5-VL.
Notably, on LLaVA-OneVision-7B, FastVID effectively prunes $\textbf{90.3\%}$ of video tokens, reduces FLOPs to $\textbf{8.3\%}$, and accelerates the LLM prefill stage by $\textbf{7.1}\times$, while maintaining $\textbf{98.0\%}$ of the original accuracy. 
The code is available at https://github.com/LunarShen/FastVID.

---

## 论文详细总结（自动生成）

# FastVID：面向快速视频大语言模型的动态密度剪枝 — 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

视频大语言模型（Video LLMs）在视频理解任务中表现出强大能力，但其实际部署面临巨大的推理成本，主要原因是视频标记（tokens）数量庞大，存在大量时空冗余。现有剪枝技术（如FastV、VisionZip等）主要针对单张图像或空间冗余，未能充分利用视频数据中帧间的时域依赖关系，导致在极端压缩率下性能急剧下降。因此，论文的核心动机是设计一种高效的、推理时的剪枝方法，在显著降低计算开销的同时，保持视频理解任务的准确率。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：从“时域上下文”和“视觉上下文”两个角度分析视频冗余，提出动态密度剪枝框架FastVID。其核心是保持视频的时间结构不变，同时在每个高冗余片段内进行密度基的标记剪枝，保留代表性特征和关键细节。

**关键技术细节**：

- **动态时间分割（DySeg，Dynamic Temporal Segmentation）**：  
  基于相邻帧之间的余弦相似度（`t_i = cos(f_i, f_{i+1})`）自适应地将视频划分为时间有序的片段。设定最小片段数 `c` 和相似度阈值 `τ`，选取最不相似的 `c-1` 个过渡以及所有低于 `τ` 的过渡作为分割边界，确保片内帧高度相似、片间差异明显，从而保留时间结构并利于后续剪枝。

- **密度时空剪枝（STPrune，Density Spatiotemporal Pruning）**：  
  在每个高冗余片段内进行剪枝，包含两个互补模块：
  - **密度基令牌合并（DTM，Density-based Token Merging）**：  
    先在片段内按固定间隔选取锚帧（anchor frames），在每个锚帧上计算每个令牌的局部密度 `ρ_i` 和到更高密度令牌的距离 `δ_i`，选择密度峰值令牌作为锚令牌。然后将片段内所有其余令牌分配给最近的锚令牌（余弦相似度），通过锚心聚合（Anchor-centric Aggregation）更新锚令牌：`a^* = β a + (1-β)/n Σ b_i`，保留原始位置信息，维持时空结构。该模块提取片段内的代表性视觉上下文。
  - **基于注意力的令牌选择（ATS，Attention-based Token Selection）**：  
    利用预训练的SigLIP头的[CLS]注意力分数（因Video LLMs常用SigLIP编码器，需重新集成其轻量头部）选出每帧中注意力分数最高的若干令牌，保留显著细节。两个模块通过参数 `d` 控制分配比例（实验最佳 `d=0.4`）。

总体流程：输入视频 → 均匀采样帧 → 视觉编码器提取令牌 → FastVID（DySeg + STPrune）压缩 → 保留令牌与查询令牌输入LLM生成答案。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集/基准**：  
  - MVBench（多模态视频理解基准）  
  - LongVideoBench（长视频基准）  
  - MLVU（多任务长视频理解基准）  
  - VideoMME（长短中三个子集）  
  覆盖不同时长（数秒至数十分钟）和复杂度，全面评估泛化能力。

- **对比方法**：  
  - 图像剪枝方法：FastV、VisionZip及其适配版（VisionZip*）  
  - 视频剪枝方法：DyCoke、PruneVID及其变体（PruneVID*）  
  - 此外与PyramidDrop、SparseVLM、LLaVA-PruMerge等进行了额外比较（见附录）

- **模型**：在四种主流Video LLMs上测试：LLaVA-OneVision、LLaVA-Video、Qwen2-VL、Qwen2.5-VL。

## 4. 资源与算力

论文中明确说明：所有评估使用LMMs-Eval框架，在 **A100 GPU** 上完成。但未提及具体使用的GPU数量、训练时长（因为本方法为推理时剪枝，无需训练）。附录中提供了TFLOPs的估计方法，但未给出实际硬件资源消耗的详细统计。总体而言，算力信息不完整。

## 5. 实验数量与充分性

**实验数量**：  
- 主实验（表1-4）：在4个模型、4个基准（多个子集）上比较了5种以上方法，覆盖不同保留率（R=25%、20%、15%、10%）。  
- 效率对比（表5）：与PruneVID比较预填充延迟、FLOPs、准确率。  
- 消融实验（表6-9，图6-7）：对动态分割模块（DySeg vs 固定间隔 vs 聚类）、密度令牌合并（DTM vs Uniform vs 聚类）、注意力选择（d的比例）、SigLIP头的作用、超参数（c, τ, p, β）等进行系统性分析。  
- 额外实验（附录表11-12）：在ANet-QA上进行长上下文生成，并与PyramidDrop、SparseVLM、LLaVA-PruMerge比较。

**充分性与公平性**：实验设计较为充分，覆盖多种架构、多种复杂度、多种压缩率；对比方法均按其官方实现重新实现或适配（如VisionZip*、PruneVID*）以保证公平；消融全面。但部分实验仅在一个模型上验证（如表11-12），没有跨模型重复，可能影响结论泛化性。另外，未报告多次运行的误差棒（如标准差），但遵循了先前工作的评估惯例。

## 6. 主要结论与发现

- FastVID能在剪除90.3%视频令牌的条件下，保持原始模型98.0%的平均准确率，LLM预填充阶段加速7.1倍，FLOPs降至8.3%。  
- 动态时间分割（DySeg）优于固定间隔或聚类分割，因同时保持了时序顺序和片内高相似性。  
- 密度基令牌合并（DTM）结合基于注意力的令牌选择（ATS）互补效果最佳（d=0.4），优于单独使用任一模块。  
- FastVID在LLaVA-OneVision、LLaVA-Video、Qwen2-VL、Qwen2.5-VL等不同架构上均取得最优或接近最优的结果，显示出强泛化性。  
- 通过FastVID压缩后，可以用等量令牌处理更多帧（长度外推），进一步提升性能（表10）。

## 7. 优点

- **创新性**：首次系统分析视频时域和视觉上下文的冗余特性，并提出针对性的动态密度剪枝框架。  
- **效率与性能平衡**：在极端压缩率下仍能保持极高精度，实际部署价值高。  
- **即插即用**：作为推理时加速方法，无需额外训练，兼容FlashAttention、KV缓存、多轮对话等特性。  
- **泛化性强**：在多个主流Video LLMs（含架构差异大的Qwen系列）上均验证有效。  
- **可解释性**：提供了丰富的可视化结果（如图5、8-10），展示分割和合并效果，直观说明方法合理性。

## 8. 不足与局限

- **查询不可知性**：FastVID是查询无关的剪枝，在长视频中，当关键内容仅出现在少数帧中时，高频压缩可能导致丢失与查询相关的细节，影响答案准确性（论文承认此局限，并提及未来可结合查询引导）。  
- **依赖预训练头部**：ATS需要集成SigLIP头部，虽轻量但增加了额外依赖，且未见在无[CLS]头部模型（如Qwen系列）上如何最佳适配（论文通过平均patch token模拟[CLS]）。  
- **超参数较多**：方法涉及c、τ、d、p、β等多个超参数，经验设定（c=8, τ=0.9, d=0.4, p=4, β=0.6）虽经消融验证，但不同数据集或模型是否需要调优未充分讨论。  
- **实验覆盖有限**：主要基准集中在一组标准benchmark，未在更多真实场景（如视频对话、时序定位）中评估；仅在ANet-QA上进行了长上下文生成测试。  
- **公平性局限**：部分对比（如PruneVID）仅在一两个模型上比较，未在所有模型/压缩率下逐一对比；缺乏统计显著性检验。  
- **效率衡量**：FLOPs仅考虑与视频令牌相关部分，未纳入编码器或其他开销，实际加速效果可能略低于理论值。此外，密度计算（DTM）在极端帧数下可能成为瓶颈（论文通过并行和限制锚帧缓解）。

（完）
