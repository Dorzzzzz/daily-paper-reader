---
title: "Long-RVOS: A Comprehensive Benchmark for Long-term Referring Video Object Segmentation"
title_zh: Long-RVOS：长时指代视频对象分割的综合基准
authors: "Tianming Liang, Haichao Jiang, Yuting Yang, Chaolei Tan, Shuai Li, Wei-Shi Zheng, Jian-Fang Hu"
date: 2025-04-29
pdf: "https://openreview.net/pdf?id=txmJldjJUw"
tags: ["query:long-video"]
score: 8.0
evidence: 长时指代视频对象分割基准
tldr: 现有指代视频对象分割数据集集中于短片段。Long-RVOS提供包含2000+视频、平均时长超60秒的大规模基准，覆盖遮挡、消失重现和镜头切换等复杂情况，为长视频分析提供了重要评测平台，推动任务向实用化发展。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 555, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1357, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 719, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 1149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1391, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 577, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txmjldjjuw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 399, \"height\": 199, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-txmjldjjuw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txmjldjjuw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 540, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txmjldjjuw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txmjldjjuw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 425, \"height\": 208, \"label\": \"Table\"}]"
motivation: 现有视频对象分割数据集局限于短视频，无法评估实际长视频场景。
method: 构建包含2000+长视频的大规模基准，涵盖多种对象动态和描述类型。
result: 基准揭示了现有方法在长视频场景下的不足。
conclusion: 该基准为长视频分析研究提供了标准化的评测平台。
---

## Abstract
Referring video object segmentation (RVOS) aims to identify, track and segment the objects in a video based on language descriptions, which has received great attention in recent years. 
However, existing datasets remain focus on short video clips within several seconds, with salient objects visible in most frames.
To advance the task towards more practical scenarios, we introduce \textbf{Long-RVOS}, a large-scale benchmark for long-term referring video object segmentation. 
Long-RVOS contains 2,000+ videos of an average duration exceeding 60 seconds, covering a variety of objects that undergo occlusion, disappearance-reappearance and shot changing.
The objects are manually annotated with three different types of descriptions to individually evaluate the understanding of static attributes, motion patterns and spatiotemporal relationships.
Moreover, unlike previous benchmarks that rely solely on the per-frame spatial evaluation, we introduce two new metrics to assess the temporal and spatiotemporal consistency.
We benchmark 6 state-of-the-art methods on Long-RVOS. The results show that current approaches struggle severely with the long-video challenges.
To address this, we further propose ReferMo, a promising baseline method that integrates motion information to expand the temporal receptive field, and employs a local-to-global architecture to capture both short-term dynamics and long-term dependencies.
Despite simplicity, ReferMo achieves significant improvements over current methods in long-term scenarios. 
We hope that Long-RVOS and our baseline can drive future RVOS research towards tackling more realistic and long-form videos. 
Our dataset and code will be released.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有指代视频对象分割（RVOS）数据集（如A2D-Sentences、Ref-DAVIS17、Refer-YouTube-VOS、MeViS）均局限于短时间视频片段（平均几秒到十几秒），目标对象在大多数帧中清晰可见，无法评估模型在实际长视频场景（如遮挡、消失重现、镜头切换）中的表现。
- **背景**：长视频中的干扰物增多、文本描述可能只涉及短暂片段、训练与推理帧数差异大等问题使现有方法面临挑战；此外，现有评估指标仅关注逐帧空间分割质量（J&F），忽略模型判断目标是否存在的时间一致性能力。
- **整体含义**：作者构建了首个分钟级大规模RVOS基准**Long-RVOS**（2000+视频，平均60.3秒），推动RVOS研究向实用化、长视频场景发展，并提供更全面的评估体系（引入tIoU和vIoU指标）。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：提出基线方法**ReferMo**，将视频分解为多个片段（clip），每个片段包含一个高分辨率关键帧和多个低分辨率运动帧；通过局部感知提取静态外观和短期运动特征，再通过全局交互捕获长期依赖，仅在关键帧上预测掩码，其余帧由预训练跟踪器（SAM2）传播，从而平衡训练成本与长时理解。
- **关键技术细节**：
  - **视频分解**：采用MPEG-4压缩技术提取关键帧和运动向量（motion vectors），运动向量直接来自压缩视频解码过程，无需计算密集光流。
  - **局部感知器**：每个片段内，分别用图像编码器、运动编码器（时空自注意力+可变形空间注意力）、文本编码器提取特征；通过空间门控和通道门控机制融合图像与运动特征（公式3-4），再通过双交叉注意力（公式5）实现视觉-语言融合，得到片段级物体特征。
  - **全局交互**：使用匈牙利算法逐片段对齐物体，再对对齐后的物体特征进行时间自注意力和与语言特征的交叉注意力，实现全局建模；最终在关键帧上输出掩码。
  - **推断**：关键帧掩码作为锚点，由SAM2在后续运动帧中传播产生完整序列掩码。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：Long-RVOS自建，基于TAO、VidOR、Ego-Exo4D等多源长视频，筛选后含2193个视频，平均60.3秒，共6703个物体对象、163个类别、24689句描述（分静态、动态、混合三种类型）。划分为训练集1855视频/20722句，验证集113视频/1379句，测试集225视频/2588句。
- **基准与评估**：采用J&F（空间）、tIoU（时间重合度）、vIoU（时空体积IoU）三个指标，并按描述类型分别报告。
- **对比方法**：共6种SOTA方法，分为两类：
  - **不含SAM/SAM2**：SOC（2023）、MUTR（2024）、ReferDINO（2025）
  - **含SAM/SAM2**：VideoLISA（2024）、GLUS（2025）、SAMWISE（2025）
- **其他实验**：
  - **Oracle分析**：用GT第一帧的框/点/掩码提示SAM2跟踪，对比MeViS和Long-RVOS上的性能差距。
  - **消融实验**：①在关键帧上比较ReferMo与ReferDINO，并分析去除运动信息的影响；②改变运动帧长度（0,1,3,5,8,11帧）。

## 4. 资源与算力
- **训练资源**：ReferMo在8张Nvidia A6000 GPU上训练6个epoch，耗时24小时。
- **输入尺寸**：最长边640像素，最短边360像素。
- **骨干网络**：Swin-Tiny图像编码器；SAM2采用sam2.1_hiera_large版本。

## 5. 实验数量与充分性
- **实验数量**：主要包含一张总体对比表（表2，6个方法×3种描述类型×3个指标）、一张Oracle分析表（表3a）、一张关键帧消融表（表3b）、一张运动长度消融图（表3c）。此外还报告了推理速度FPS。
- **充分性与公平性**：所有对比模型均在Long-RVOS训练集上重新训练，使用一致设置，保证了公平性；消融实验系统验证了运动信息、关键帧监督的有效性。Oracle分析揭示了长视频的固有难度。实验设计较为充分，但未在现有短期基准（如MeViS）上对比泛化性，整体足够支撑主要结论。

## 6. 论文的主要结论与发现
- 当前RVOS方法在长视频场景下表现**显著下降**（Oracle分析显示与MeViS差距近25% J&F），说明长视频的挑战远大于短视频。
- 基于SAM2的方法（GLUS、SAMWISE）提升主要来自跟踪能力，而非语言理解，在长视频中反而下降更多。
- 所有模型在“动态”描述类型上的性能普遍低于“静态”和“混合”，表明存在**静态偏置**。
- 各模型的tIoU相对接近，说明现有方法在时序一致性（判断物体是否存在）上缺乏差异化能力。
- **ReferMo**在J&F和vIoU上大幅超越所有对比方法（+2.6% J&F vs 次优ReferDINO），但在tIoU上略低于ReferDINO，推测因仅关键帧推理导致运动帧识别不佳。
- 运动信息是关键：仅引入1帧运动即可提升1.6% J&F，3帧最佳。

## 7. 优点：方法或实验设计上的亮点
- **基准创新**：首个分钟级RVOS数据集，提供三种明确描述类型，引入tIoU和vIoU指标，填补长视频评估空白。
- **方法简洁高效**：利用MPEG-4运动向量代替光流，无需额外计算；局部-全局架构有效扩展时间感受野，训练成本仅需8×A6000×24h。
- **实验严谨**：统一训练设置，Oracle分析揭示难度来源，消融实验清晰证明运动信息和关键帧监督的有效性。
- **实用导向**：仅关键帧监督的设计使得长视频训练可行，SAM2传播保证了全帧输出。

## 8. 不足与局限
- **tIoU局限**：ReferMo在tIoU上未达最优，因为语言推理仅发生在关键帧，运动帧依赖SAM2跟踪，可能存在目标切换或丢失风险。
- **运动表示依赖**：MPEG-4运动向量依赖于视频编码格式，不适用于所有视频（如未压缩视频），且空间分辨率低（1/16），可能丢失精细运动细节。
- **数据偏差**：Long-RVOS中人类实例占71.9%，可能偏向人类相关属性（如动作、衣着）；其他类别（动物、物体）相对较少，存在类别不平衡。
- **评估指标覆盖不全**：新指标tIoU和vIoU尚未在现有短期基准中验证；仅从帧级空间和时空体积角度评估，未考虑实例级长时间跟踪的鲁棒性（如ID切换）。
- **未验证跨数据集泛化**：实验仅在Long-RVOS上训练和测试，未在MeViS等短期数据集上评估模型的迁移能力，限制了结论的泛化范围。
- **缺少更广泛的消融**：未探索不同骨干（如Swin-B）、不同片段数、不同关键帧选择策略的影响。

（完）
