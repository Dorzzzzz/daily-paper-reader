---
title: "EVEREST: Efficient Masked Video Autoencoder by Removing Redundant Spatiotemporal Tokens"
title_zh: "EVEREST: 通过移除冗余时空令牌实现高效掩码视频自编码器"
authors: "Sunil Hwang, Jaehong Yoon, Youngwan Lee, Sung Ju Hwang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=nn5OPHom8t"
tags: ["query:long-video"]
score: 5.0
evidence: 通过令牌选择实现长视频的高效表示学习
tldr: 掩码视频自编码器随机掩码策略导致大量计算浪费在无信息令牌上。本文提出EVEREST，利用视频中运动信息密度不均，通过选择富含运动特征的令牌并丢弃冗余令牌，显著降低预训练与微调的计算开销。在Kinetics-400等数据集上，EVEREST在精度持平或更优的前提下，计算成本降低数个数量级，为大规模视频特别是长视频的高效表示学习提供了可行方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1571, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1612, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1726, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1252, \"height\": 2130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1253, \"height\": 2132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nn5ophom8t/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1249, \"height\": 1911, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 781, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 849, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 846, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 613, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 593, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 614, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 867, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 848, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 554, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 272, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 854, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 863, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nn5ophom8t/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 696, \"height\": 194, \"label\": \"Table\"}]"
motivation: 现有掩码视频自编码器随机掩码策略浪费大量计算在无信息令牌上。
method: 根据运动特征选择信息密集令牌，丢弃冗余令牌，并采用信息密集帧选择策略。
result: 在多个视频任务上以更少计算量达到或超越现有方法性能。
conclusion: 移除冗余令牌可有效提升视频自编码器的效率。
---

## Abstract
Masked Video Autoencoder (MVA) approaches have demonstrated their potential by significantly outperforming previous video representation learning methods. However, they waste an excessive amount of computations and memory in predicting uninformative tokens/frames due to random masking strategies. (e.g., over 16 nodes with 128 NVIDIA A100 GPUs). To resolve this issue, we exploit the unequal information density among the patches in videos and propose EVEREST, a surprisingly efficient MVA approach for video representation learning that finds tokens containing rich motion features and discards uninformative ones during both pre-training and fine-tuning. We further present an information-intensive frame selection strategy that allows the model to focus on informative and causal frames with minimal redundancy. Our method significantly reduces the computation and memory requirements of MVA, enabling the pre-training and fine-tuning on a single machine with 8 GPUs while achieving comparable performance to computation- and memory-heavy baselines on multiple benchmarks and the uncurated Ego4D dataset. We hope that our work contributes to reducing the barrier to further research on video understanding.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

掩码视频自编码器（MVA）方法在视频表示学习上取得了显著进展，但存在严重效率问题：**随机掩码策略导致大量计算和内存浪费在无信息或冗余的时空令牌上**。例如，VideoMAE 使用 64 块 NVIDIA V100 GPU 预训练 800 轮需 27 小时，ST-MAE 使用 128 块 A100 GPU 训练 800 轮需 35.8 小时。本文旨在通过**选择性保留富含运动信息的令牌、丢弃冗余令牌**，大幅降低预训练和微调的计算/内存开销，使视频自编码器可在单机 8 GPU 上高效训练，同时保持甚至提升下游任务性能，从而降低视频理解研究的硬件门槛。

## 2. 方法论

### 核心思想
利用视频中不同时空令牌的信息密度不均：**令牌的重要性由其与前一帧对应位置令牌的嵌入距离（L2距离）度量**，距离大的令牌代表丰富的运动变化或新信息，应保留；距离小的令牌代表静态背景或冗余信息，应丢弃。

### 关键技术细节
1. **冗余鲁棒令牌选择（Redundancy-robust Token Selection）**  
   - 对输入视频片段 \(v \in \mathbb{R}^{2\tau \times C \times H \times W}\)，每两帧构成一个令牌嵌入向量 \(k_i\)（通过 3D 卷积）。  
   - 对第 \(i+1\) 帧的每个令牌 \(k_{i+1,j}\)，计算其与前一帧同位置令牌 \(k_{i,j}\) 的 L2 距离作为重要性分数 \(I_{i+1,j}\)。  
   - 保留重要性分数最高的 \(\rho_{\text{pre}}\) 比例令牌（默认 0.3），其余丢弃。  
   - 在保留的令牌中，再按 MVA 标准随机采样 \(\rho_{\text{post}}\) 比例令牌输入编码器（总体保持 90% 掩码率，即 \(\rho_{\text{pre}} \cdot \rho_{\text{post}} = 0.1\)）。  
   - 解码器仅重建被保留令牌对应的原始 RGB 像素。  
   - 该策略同时应用于预训练和微调阶段，微调时 \(\rho_{\text{pre}}\) 默认 0.6。

2. **在线信息密集帧选择（On-the-fly Information-intensive Frame Selection）**  
   - 针对未修剪的真实视频（如 Ego4D）中存在的冗余帧，先均匀采样 \(2\alpha\tau\) 帧候选（\(\alpha>1\)，默认 1.5），然后根据每对帧中冗余鲁棒令牌的数量，**按概率 \(c_i / \sum c_i\) 无放回地抽取 \(\tau\) 帧**，使模型更多关注动作密集的帧。

### 算法流程（文字说明）
1. 输入视频片段，通过 3D 卷积得到所有令牌嵌入。
2. 计算相邻帧同位置令牌的 L2 距离，选出距离最大的 \(\rho_{\text{pre}}\) 比例令牌。
3. 从这些令牌中随机采样 \(\rho_{\text{post}}\) 比例输入编码器。
4. 编码器输出后，解码器重建被保留令牌的原始 RGB 值。
5. 损失函数为重建像素的 p 范数误差。
6. 微调时仅执行令牌选择（不需要再采样），输入比例 \(\rho_{\text{pre}}=0.6\)。

## 3. 实验设计

- **数据集**：UCF101、HMDB51、Something-Something v2 (SSv2)、Kinetics-400 (K400)、Ego4D（对象状态变化分类 OSCC 任务）。
- **基准（Benchmark）**：视频动作识别（Top-1 准确率）、对象状态变化分类（准确率）。
- **对比方法**：
  - 自监督 MVA 方法：VideoMAE、ST-MAE、MME、MVD。
  - 其他 VRL 方法：VCOP、CoCLR、Vi²CLR、RSPNet、ρSwAV/ρMoCo/ρBYOL、K-centered 等。
  - 对 Ego4D OSCC：Egocentric VLP、SViT、TarHeels。
- **评估协议**：严格遵循 VideoMAE 的设置（输入尺寸 16×224²，多视角测试等），公平比较计算量（GFLOPs）、内存占用和训练时间。

## 4. 资源与算力

- **EVEREST 训练配置**：单节点 8 块 GPU（A100 80GB 或 A6000 48GB），单机可完成预训练和微调。
- **对比耗能**：
  - VideoMAE 使用 64 块 V100 (32GB) 预训练 800 轮需 27 小时；ST-MAE 使用 128 块 A100 (80GB) 预训练 800 轮需 35.8 小时。
  - K400 上，EVEREST（ViT-B）预训练每轮仅 8 分 18 秒（8×A6000），而 VideoMAE 需 18 分 42 秒，MME 10 分 15 秒，MVD 51 分 55 秒。
  - 内存占用：ViT-L 批大小 256 时，EVEREST 仅 164.1 GB，VideoMAE 需 634.1 GB（降低约 74%）。

## 5. 实验数量与充分性

- **多数据集覆盖**：5 个代表性数据集（K400、SSv2、UCF101、HMDB51、Ego4D），涵盖固定视角、运动密集、第一人称等场景。
- **多模型规模**：ViT-S、ViT-B、ViT-L 三种 backbone。
- **消融实验**：
  - 距离函数选择（L2 vs. L1 vs. 余弦相似度 vs. CKA）。
  - 预训练/微调掩码率 \(\rho_{\text{pre}}\) 的影响（表 10）。
  - 帧选择比例 \(\alpha\) 的消融（表 13）。
  - 嵌入层设计（Conv3D 层数，表 15）。
  - 排序策略（降序 vs. 升序选择，表 16）。
  - 运行单元掩码对比（表 17）。
  - 预训练模型迁移（VideoMAE 预训练 + EVEREST 微调，表 11）。
  - 长帧数设置（16→24 帧，表 12）。
- **公平性**：所有比较均使用相同训练协议、相同硬件、相同输入尺寸，对比模型源码公开。实验设计客观充分。

## 6. 主要结论与发现

1. **效率大幅提升**：在 K400 上，EVEREST 比 VideoMAE 节省预训练计算量 26%~45%，微调 44%~48%，内存降低最高 81%，训练时间减少 55% 以上。
2. **性能持平或更优**：在 UCF101 上，EVEREST 以仅 800 轮预训练（14% 计算成本）达到 VideoMAE 3200 轮性能；在 HMDB51 上提升 3.2% Top-1；在 K400 上各规模 backbone 均与 VideoMAE 持平或略高。
3. **对未修剪视频（Ego4D）有效**：OSCC 任务准确率 76.2%，超越之前最佳（含视觉+文本的 Egocentric VLP 73.9%）。
4. **所选令牌富含运动信息**：可视化显示，保留的令牌集中在运动物体上，丢弃静态背景。

## 7. 优点

- **方法简洁高效**：无需额外可学习参数或预计算光流等密集信息，仅基于相邻帧令牌的 L2 距离即可在线选择。
- **普适性强**：可同时应用于预训练和微调，且可与任何 MVA 预训练模型兼容（表 11 显示用 VideoMAE 预训练权重 + EVEREST 微调仍高效）。
- **显著降低硬件门槛**：使单机 8 GPU 即可训练 ViT-L 模型，而基线需要多节点大规模 GPU 集群。
- **环境友好**：大幅减少能耗和碳足迹。
- **实验全面且公平**：覆盖多种数据集、多种 backbone，消融完备，对比方法源代码公开，结果可信。

## 8. 不足与局限

- **依赖相邻帧运动信号**：对于完全静止或缓慢变化的视频，L2 距离可能无法有效识别关键信息，但论文通过固定最小保留比例缓解。
- **未与其他更高效的掩码策略（如运行单元掩码）在更大计算预算下充分比较**：仅做了少量对比（表 17），且对比不够深入（如训练轮数、模型规模）。
- **Ego4D 实验仅针对 OSCC 任务**：其他第一人称任务（如动作识别、目标跟踪）未验证，结论的泛化性需更多证据。
- **帧选择策略需要超参数 α**：α=1.5 虽经消融确定，但不同数据集可能需调整，未提供自动选择机制。
- **对极短视频（≤4 帧）可能无效**：因为需要至少两帧计算距离。
- **理论分析不足**：未从信息论或梯度优化角度解释为什么丢弃冗余令牌反而提升性能。

（完）
