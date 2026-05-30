---
title: "Less Is More, but Where? Dynamic Token Compression via LLM-Guided Keyframe Prior"
title_zh: 更少即是更多，但何处？基于LLM引导关键帧先验的动态令牌压缩
authors: "Yulin Li, Haokun GUI, Ziyang Fan, Junjie Wang, Bin Kang, BIN CHEN, Zhuotao Tian"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=uhFx1RGD1g"
tags: ["query:long-video"]
score: 9.0
evidence: 基于LLM引导关键帧先验的动态令牌压缩以分析长视频
tldr: 针对视频大语言模型处理长视频时令牌序列二次增长导致效率瓶颈，本文提出DyToK方法，利用VLLM自身的注意力机制动态压缩令牌，无需额外训练。该方法通过LLM引导的关键帧先验指导令牌压缩，在保持理解精度的同时大幅降低计算量，实验证明在长视频理解任务上效率显著提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 741, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 1349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 1019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1454, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 773, \"height\": 128, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1459, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 775, \"height\": 131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1455, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1456, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uhfx1rgd1g/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1453, \"height\": 668, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 1167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1052, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1310, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1337, \"height\": 2132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1315, \"height\": 1743, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1129, \"height\": 1411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1351, \"height\": 1649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 836, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1115, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1098, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1127, \"height\": 969, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1371, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1213, \"height\": 858, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1207, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1461, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uhfx1rgd1g/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1384, \"height\": 405, \"label\": \"Table\"}]"
motivation: 长视频视觉令牌序列长导致计算成本高，现有关键帧采样方法引入额外开销且二值选择次优。
method: 利用VLLM内在注意力机制实现免训练动态令牌压缩，结合LLM引导的关键帧先验。
result: 在多个长视频基准上以更低计算量达到与全序列相当或更好的准确率。
conclusion: 动态令牌压缩是提升长视频理解效率的有效途径。
---

## Abstract
Recent advances in Video Large Language Models (VLLMs) have achieved remarkable video understanding capabilities, yet face critical efficiency bottlenecks due to quadratic computational growth with lengthy visual token sequences of long videos. While existing keyframe sampling methods can improve temporal modeling efficiency, additional computational cost is introduced before feature encoding, and the binary frame selection paradigm is found suboptimal. Therefore, in this work, we propose **Dy**namic **To**ken compression via LLM-guided **K**eyframe prior (**DyToK**), a training-free paradigm that enables dynamic token compression by harnessing VLLMs' inherent attention mechanisms. Our analysis reveals that VLLM attention layers naturally encoding query-conditioned keyframe priors, by which DyToK dynamically adjusts per-frame token retention ratios, prioritizing semantically rich frames while suppressing redundancies. Extensive experiments demonstrate that DyToK achieves state-of-the-art efficiency-accuracy tradeoffs. DyToK shows plug-and-play compatibility with existing compression methods, such as VisionZip and FastV, attaining 2.5x faster inference while preserving accuracy across multiple VLLMs, such as LLaVA-OneVision and Qwen2.5-VL. Code and models will be made publicly available.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视频大语言模型（VLLMs）在处理长视频时，面临严重的计算效率瓶颈。主要原因在于视觉令牌序列过长（叠加多帧图像令牌），导致自注意力机制的计算量呈二次增长。现有关键帧采样方法虽能减少帧数，但存在两个缺陷：（1）在特征编码前进行帧选择会引入额外计算开销；（2）二值化的保留/丢弃范式并非最优，会丢失未选中帧中的潜在有用信息，同时选中帧内仍有冗余，造成效率与效用的权衡。
- **整体含义**：需要一种更精细、动态的方式，在保留任务相关关键信息的同时，压缩冗余视觉令牌，从而在有限计算预算下实现更好的效率-准确率平衡。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式与算法

- **核心思想**：利用VLLMs自身注意力机制中内嵌的“查询条件化关键帧先验”（query-conditioned keyframe prior），动态调整每帧的令牌保留比例，将更多令牌分配给语义丰富的重要帧，并抑制冗余帧的令牌数量。该方法无需额外训练（training-free），且可作为即插即用模块集成到现有令牌压缩方法中。
- **关键技术细节**：
  - **Temporal Importance Estimation（时序重要性估计）**：使用一个轻量级辅助LLM（与主模型同架构但参数量小14倍）的深层注意力层，计算最后一个查询令牌与所有视觉令牌的交叉注意力分数，聚合得到每帧的重要性权重 \( \hat{w}_f \)。公式：
    \[
    \hat{w}_f = \frac{1}{|L'|}\sum_{l \in L'} \text{Softmax}\left( \frac{Q_l K_l^\top}{\sqrt{D}} \right)
    \]
    其中 \( L' \) 为所选深层子集（实验表明后1/3层最优）。
  - **Dynamic Frame-Level Compression（动态帧级压缩）**：根据帧权重分配全局令牌预算 \( T_{\text{total}} \)：
    - 初始分配：\( a_f = \lfloor \hat{w}_f \times T_{\text{total}} \rfloor \)
    - 剩余令牌分配：按小数部分 \( r_f = \hat{w}_f \times T_{\text{total}} - a_f \) 降序轮次分配。
    - 设置每帧上限 \( T_{\text{max}} \)（如98），超额令牌按重要性重新分配。
    - 最后调用任意兼容的压缩函数 Compression(\( x_f, a_f \)) 对每帧进行剪枝（如VisionZip、FastV等）。
- **算法流程**（文字描述）：
    1. 输入各帧特征、帧权重、总预算和每帧上限；
    2. 计算初始分配 \( a_f \)；
    3. 计算剩余令牌；
    4. 按小数部分降序分配剩余令牌至未达上限的帧；
    5. 将超出上限的令牌重新分配；
    6. 对每帧执行压缩，输出压缩后的令牌序列。

### 3. 实验设计：数据集、Benchmark、对比方法

- **数据集与基准**：
  - VideoMME（长视频理解，含短/中/长三类）
  - LongVideoBench（超长视频推理）
  - MLVU（多任务长视频理解）
  - EgoSchema（第一视角长视频，仅部分实验使用）
  - VideoChatGPT（描述性查询评估）
- **对比方法**：
  - **编码器特征类**：VisionZip（CVPR 2025）、DyCoke（CVPR 2025，仅编码器侧）
  - **LLM注意力类**：FastV（ECCV 2024）、DyCoke（仅LLM侧）
  - 对VisionZip进行了适配（记为VisionZip†）以兼容池化操作。
- **主模型**：LLaVA-OneVision（7B 和 0.5B）、Qwen2.5-VL（3B、7B、32B）
- **评估指标**：多选问答准确率，并转换为相对基线（Vanilla 100%）的百分比。

### 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量及训练时长（因方法为训练-free，仅需推理）。
- 在效率分析部分（附录C），报告了在LLaVA-OneVision 7B模型上使用32帧输入的GPU内存、FLOPs和预填充时间，但未提及具体硬件配置。
- 需要指出：资源开销依赖于现有压缩方法的实现，DyToK本身仅增加极少量辅助模型推理（0.5B vs 7B，约1/14）。

### 5. 实验数量与充分性

- **实验数量**：丰富且成体系。包括：
  - 主实验（Tab.1 & Tab.2）：集成到3种压缩方法（VisionZip、FastV、DyCoke），覆盖6种压缩率（25%~90%），在3个基准上报告短/中/长/总体分数。
  - 消融实验（Section 4.3 & 附录）：
    - 不同层位置对关键帧先验的影响（Tab.3 & Tab.12）
    - 辅助模型大小（Base 7B vs Tiny 0.5B，Tab.4）
    - 每帧令牌上限（Tab.13）
    - 重要性估计策略（附录A.8）
    - 文本令牌选择（附录A.9）
    - 帧数扩展（32帧 vs 64帧，附录A.3）
    - 跨模型泛化（Qwen2.5-VL，附录A.2）
    - 大模型引导（3B → 32B，附录A.4）
  - 描述性查询实验（附录A.5）
  - 效率分析（附录C）
- **充分性和公平性**：
  - 实验较为充分，覆盖了不同方法、不同模型、不同压缩率、不同视频长度。
  - 计算预算通过等FLOPs对齐（附录G.2），确保比较公平。
  - 但缺少在更大模型（如LLaVA-OV 34B）上的验证，部分极端压缩率下方法退化为0令牌（FastV 90%），未比较。
  - 辅助模型的选择（0.5B）是否最优？作者仅测试了一种，未系统探索不同大小。

### 6. 论文的主要结论与发现

- **原始发现**：VLLM的注意力层天然编码了查询条件化的关键帧先验，即使模型回答错误，注意力仍然指向正确答案对应的帧（Fig.1）。
- **深层注意力优势**：深层（后1/3）注意力层提供更可靠的关键帧先验，浅层噪声大。
- **轻量辅助模型有效性**：0.5B辅助模型可替代7B主模型进行重要性估计，性能损失极小（~1.5%），计算开销降低14倍。
- **性能提升**：
  - 在20%令牌保留下，DyToK使VisionZip在LongVideoBench上相对提升2.6%。
  - 在10%极端压缩下，DyToK相比基线平均提升18.9%（VisionZip）。
  - 在64帧输入、90%压缩下，DyToK提升达24.0%。
- **即插即用兼容性**：DyToK能无缝增强编码器特征类和LLM注意力类的多种压缩方法，保持或提升精度。
- **效率-精度权衡**：50%保留时保持99.6%相对精度，2.1倍加速；25%保留时保持98.5%精度，4.3倍加速。

### 7. 优点

- **训练-free**：无需额外训练或微调，降低部署成本。
- **动态自适应**：根据帧级重要性非均匀分配令牌，优于固定压缩率方法。
- **即插即用**：可集成到VisionZip、FastV、DyCoke等多种现有方法，无侵入性。
- **轻量辅助**：使用0.5B模型产生关键帧先验，计算开销极小（约1/14主模型）。
- **实验全面**：覆盖多个基准、多种模型、多种压缩率，并包含详细的消融和可视化分析。
- **理论洞察**：揭示了VLLM注意力中的关键帧先验现象及深层注意力优势，具有学术价值。
- **开源**：提供代码，便于复现和扩展。

### 8. 不足与局限

- **辅助模型依赖**：尽管轻量，仍引入了额外模型。作者在局限性中也承认“尚未提出避免引入额外模型的更好方法”。
- **注意力偏差问题**：论文发现VLLM存在“时序注意力异常值”（初始帧、末尾帧、中间帧的非语义突出），虽通过设置每帧上限缓解，但未彻底解决。该偏差可能导致少数不相关帧分配到过多令牌。
- **极端压缩场景**：当压缩率极高（如90%），部分方法（FastV）的令牌预算变为0，DyToK无法工作。
- **模型泛化有限**：主要采用LLaVA-OneVision系列，虽拓展到Qwen2.5-VL，但未在更广的VLLM家族（如LLaVA-Video、InternVideo2.5等）上全部验证。
- **推理加速由底层压缩方法贡献**：DyToK本身不直接减少FLOPs，而是通过调整分配使底层方法更高效。实际加速效果取决于所选压缩方法。
- **缺少与更多关键帧选择方法的对比**：未与传统CLIP-based keyframe selection（如AKS）在主流基准上进行公平比较（仅在附录A.5中简要对比了VideoChatGPT）。
- **实验复现细节**：部分实现细节（如VisionZip的适配策略、DyCoke的改造）依赖作者补全，可能影响独立复现。

（完）
