---
title: "MMInference: Accelerating Pre-filling for Long-Context Visual Language Models via Modality-Aware Permutation Sparse Attention"
title_zh: MMInference：通过模态感知的排列稀疏注意力加速长上下文视觉语言模型的预填充
authors: "Yucheng Li, Huiqiang Jiang, Chengruidong Zhang, Qianhui Wu, Xufang Luo, Surin Ahn, Amir H. Abdi, Dongsheng Li, Jianfeng Gao, Yuqing Yang, Lili Qiu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=me6PfbATWM"
tags: ["query:long-video"]
score: 8.0
evidence: 通过模态感知的稀疏注意力加速长上下文VLMs的预填充
tldr: 长上下文视觉语言模型应用于视频时面临注意力的二次复杂度问题。本文提出MMInference，利用视频输入的时空局部性形成的Grid稀疏模式，实现模态感知的排列稀疏注意力，显著加速预填充阶段。实验表明在不牺牲性能的情况下大幅提升推理速度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 657, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1711, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1729, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1347, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1653, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 859, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 821, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1083, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1349, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1375, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1373, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 895, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 799, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 901, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 893, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 889, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 895, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 895, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1154, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 894, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 880, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1042, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1686, \"height\": 1799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1690, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1756, \"height\": 986, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 747, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1597, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1323, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 906, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1711, \"height\": 1232, \"label\": \"Table\"}]"
motivation: 长上下文VLMs的预填充阶段注意力二次复杂度成为部署障碍。
method: 分析视频输入的Grid稀疏模式，提出模态感知的动态稀疏注意力方法。
result: 在保持性能的同时显著加速长上下文视频输入的处理速度。
conclusion: MMInference为长视频理解提供高效推理方案。
---

## Abstract
The integration of long-context capabilities with visual understanding unlocks unprecedented potential for Vision Language Models (VLMs). However, the quadratic attention complexity during the pre-filling phase remains a significant obstacle to real-world deployment. To overcome this limitation, we introduce MMInference (Multimodality Million tokens Inference), a dynamic sparse attention method that accelerates the prefilling stage for long-context multi-modal inputs. First, our analysis reveals that the temporal and spatial locality of video input leads to a unique sparse pattern, the Grid pattern. Simultaneously, VLMs exhibit markedly different sparse distributions across different modalities. We introduce a permutation-based method to leverage the unique Grid pattern and handle modality boundary issues. By offline search the optimal sparse patterns for each head, MMInference constructs the sparse distribution dynamically based on the input. We also provide optimized GPU kernels for efficient sparse computations. Notably, MMInference integrates seamlessly into existing VLM pipelines without any model modifications or fine-tuning. Experiments on multi-modal benchmarks-including Video QA, Captioning, VisionNIAH, and Mixed-Modality NIAH-with state-of-the-art long-context VLMs (LongVila, LlavaVideo, VideoChat-Flash, Qwen2.5-VL) show that MMInference accelerates the pre-filling stage by up to 8.3x at 1M tokens while maintaining accuracy. Our code is available at https://ama.ms/MMInference.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：长上下文视觉语言模型（VLM）的预填充阶段面临注意力机制二次复杂度（O(n²)），导致首Token延迟极大（处理1M tokens可能需要数分钟），严重制约实际部署。
- **研究动机**：视频输入具有时空局部性，且多模态混合输入中存在明显的模态边界，现有稀疏注意力方法（如MInference、Sparse Transformer）未能有效利用这些特性，在VLM长上下文场景下性能或效率不足。
- **整体含义**：提出一种即插即用、无需模型修改或微调的动态稀疏注意力方法，专门针对多模态输入的稀疏模式进行优化，在保持精度的前提下显著加速预填充阶段。

## 2. 论文提出的方法论

### 核心思想
- 利用视频/图像输入特有的**Grid稀疏模式**（由帧内空间和帧间时间局部性产生），以及模态边界处的**Q-Boundary**和**2D-Boundary**模式，通过排列（permutation）技术将稀疏索引转为连续块，实现硬件高效的稀疏计算。
- 采用**离线搜索**为每个注意力头确定最优稀疏模式（Grid、Vertical-Slash、A-shape等），然后**在线动态估计**稀疏索引，最后通过优化GPU核完成稀疏注意力。

### 关键技术细节
1. **Grid头**：
   - 在线搜索步长（stride）和相位（phase），基于最后64个查询向量估计近似注意力矩阵。
   - 通过行/列排列将Grid形式的稀疏块聚拢，再执行块稀疏注意力。
2. **Q-Boundary头**：
   - 按查询维度（row-wise）根据模态类型排列Q，使同模态查询连续。
   - 对各模态内部应用离线选定的稀疏模式（如Vertical-Slash），并利用该模态最后一段查询动态估计稀疏索引。
3. **2D-Boundary头**：
   - 对Q、K均按模态排列，然后遍历所有模态对（如Vision→Vision、Vision→Text等），分别应用动态稀疏注意力和注意力掩码。
4. **模态感知稀疏模式搜索算法**：
   - 先搜素**模态内**模式（考虑Grid、Vertical-Slash、A-shape等），再搜索**跨模态**模式，最后结合结果选择**模态间**模式。
   - 搜索空间包含多种配置（步长、窗口大小等），评估标准为注意力召回率（attention recall），使用真实注意力输出作为目标。

### 算法流程（文字说明）
- 输入：Q、K、V，模态类型索引
- 对每个注意力头，根据离线搜索选定的模式（Grid / Q-Boundary / 2D-Boundary / 等）：
  - 若为Grid头：用最后64个Q近似注意力矩阵，在线搜索最优步长和相位，然后排列Q、K、V，执行块稀疏注意力。
  - 若为Q-Boundary头：对Q按模态排列，对每个模态内部应用模态内稀疏注意力（利用该模态最后一段Q估计索引）。
  - 若为2D-Boundary头：对Q和K均按模态排列，构造模态对掩码，对每对模态执行动态稀疏注意力。
- 使用Triton实现优化GPU核，避免显式张量转置的开销。

## 3. 实验设计

### 使用数据集/场景
- **长视频理解任务**（六项）：Video Detail Caption (VideoDC)、ActivityNet-QA、EgoSchema、NExT-QA、PerceptionTest、VideoMME。输入长度：Llava-Video 110帧（约20K tokens）、LongVILA 256帧（约66K tokens）。
- **Video Needle in a Haystack (V-NIAH)**：检索任务，最长6K帧（约1.1M tokens），测试检索准确性随深度变化。
- **Mixed-Modality NIAH (MM-NIAH)**：本文提出的混合模态检索测试，在长视频中插入文本段落（25%内容为文本），最长4.5K帧（约1.1M tokens）。

### 对比的方法（baselines）
1. **FlashAttention-2**（全注意力，作为上限参考）
2. **SparseTransformer（Fixed）**：块内加初始token注意力
3. **SparseTransformer（Strided）**：局部窗口加间隔注意力
4. **A-Shape**：保留sink token + 局部窗口
5. **Tri-Shape**：A-Shape基础上增加最后窗口的查询全注意力
6. **Vertical-Slash（MInference）**：垂直线和斜线索引
7. **VisionZip**：视觉token压缩方法（降低每帧token数）

### 测试的VLM模型
- LongVILA-7B-1M（256帧版本和1M版本）
- Llava-Video-7B（110帧）
- Qwen2.5-VL-7B-Instruct（256帧）
- VideoChat-Flash（512帧，已用token压缩）

## 4. 资源与算力

- **GPU型号**：单张NVIDIA A100（80GB）。
- **精度**：bfloat16，贪婪解码。
- **模式搜索**：约15分钟（在单个A100上，使用EgoSchema子集，约25K tokens）。
- **推理测试**：在单张A100上进行，未使用多卡或多节点。
- **公开代码**：提供在 https://aka.ms/MMInference。
- **训练**：无需训练，方法为无训练加速。

## 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 在**6个视频理解基准**上比较了5+种baseline + 全注意力 + 本文方法（表1）。
  - 在**V-NIAH**（6K帧）和**MM-NIAH**（4.5K帧）上做了详细消融（图5、13、14），包括A-shape、Tri-shape、SF-fixed、SF-strided、MInference、MMInference等。
  - 在**Qwen2.5-VL**和**VideoChat-Flash**上额外验证（表1底部、表2）。
  - **延迟分析**：不同上下文长度下（16K~1M）的核级和端到端延迟（图7、16）。
  - **稀疏模式分析**：注意力头分布、索引跨模态泛化实验（图8）。
  - 消融研究：去掉模态间处理（w/o Inter-modality）的对比（图14d）。
- **公平性**：
  - 对比方法使用其最优配置（MInference使用其推荐参数，使其FLOPs约为本文方法的2倍）。
  - 将本文的FLOPs与baseline对齐而非追求最低FLOPs（表1中显示FLOPs百分比）。
  - 采用官方评测脚本和指标。
- **结论**：实验覆盖了单模态（纯视频）和混合模态任务、短上下文（20K）和极长上下文（1M），验证全面，结论可信。

## 6. 论文的主要结论与发现

1. **性能保持**：MMInference在视频理解六个基准上平均得分与全注意力几乎相同（差异<1%），同时FLOPs仅为全注意力的31%~47%（MInference为47%~78%）。
2. **极长上下文加速**：在1M tokens（约6000帧）长度下，端到端加速达8.3×（对比FlashAttention-2），核加速达12×；对比MInference加速1.7×。
3. **混合模态鲁棒**：在MM-NIAH任务中，MMInference保持召回率91.3%（全注意力90.9%），而MInference和Tri-shape分别降至88.0%和73.8%。
4. **模式转换规律**：纯文本输入时模型倾向于Vertical-Slash模式，一旦加入视觉输入则转为Grid模式，体现了多模态输入的结构性变化。
5. **模态内索引可泛化**：在视觉模态内构建的稀疏索引可泛化到被文本边界分隔的其他视觉区域，证明了模态内部连续性的假设。

## 7. 优点

- **无需修改模型或微调**：即插即用，可直接集成到现有VLM pipeline。
- **系统-算法协同设计**：基于GPU硬件特性（稀疏加载 + 密集计算）设计排列策略，避免不规则内存访问。
- **模态意识全面**：不仅处理视频的Grid模式，还创新性解决模态边界（Q-Boundary和2D-Boundary），适应混合输入场景。
- **高效搜索**：离线搜索仅需15分钟，在线开销极小（仅最后64个Q的近似注意力计算）。
- **与token压缩方法兼容**：实验显示可无缝结合VideoChat-Flash的视觉token压缩。
- **开源代码**：促进可复现性和社区应用。

## 8. 不足与局限

- **实验覆盖范围**：主要测试了LLaVA-Video和LongVILA（基于Qwen2和LLaMA架构），仅额外验证了Qwen2.5-VL和VideoChat-Flash。更广泛架构（如Gemini、GPT-4V等闭源模型）无法验证。
- **极长文精度损失**：在MM-NIAH中，MMInference在4.5K帧（约1.1M tokens）时召回率91.3%略低于全注意力90.9%（实际略高），但其他baseline下降更显著；然而在V-NIAH中MMInference略低于全注意力（97.7% vs 98.3%），说明仍有微小差距。
- **动态分辨率支持**：仅测试了固定帧率采样，未全面评估动态分辨率/不规则帧输入。
- **注意力头模式多样性**：部分VLM的某些低层头稀疏性较低，Grid模式可能适用性减弱，文中注意到此现象但未专门优化。
- **音频等多模态**：虽在附录中提及Audios LMs，但未做定量实验。
- **硬件依赖**：当前优化基于NVIDIA A100的Tensor Core和WGMMA，可能在低端GPU或非NVIDIA平台效果受限。
- **搜索空间手工**：离线搜索需要针对每个模型手动配置搜索空间，可能增加部署成本。

（完）
