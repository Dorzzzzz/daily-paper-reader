---
title: "FlexSelect: Flexible Token Selection for Efficient  Long Video Understanding"
title_zh: FlexSelect：面向高效长视频理解的灵活令牌选择
authors: "Yunzhuzhang, Yu Lu, Tianyi Wang, Fengyun Rao, Yi Yang, Linchao Zhu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0D3ja9s17M"
tags: ["query:long-video"]
score: 9.0
evidence: 面向长视频理解的高效令牌选择
tldr: 长视频理解受限于计算和内存开销。本文提出FlexSelect，一个灵活高效的令牌选择策略。首先利用跨模态注意力权重进行无训练的重要性排序，然后训练轻量级选择器复制该排序以过滤冗余令牌。在多个长视频基准上，FlexSelect在保持甚至提升模型性能的同时，大幅减少处理令牌数，实现加速与内存节省。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 692, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 696, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 695, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 115, \"height\": 113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 114, \"height\": 113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1083, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1336, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1276, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1337, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0d3ja9s17m/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1466, \"height\": 2116, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1327, \"height\": 1337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1370, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 677, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 676, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1320, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1310, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1307, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1283, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0d3ja9s17m/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1291, \"height\": 283, \"label\": \"Table\"}]"
motivation: 视频LLM处理长视频时面临巨大的计算与内存压力。
method: 提出FlexSelect，结合无训练排名与轻量选择器过滤冗余令牌。
result: 在保持性能的同时大幅降低计算开销，实现高效长视频理解。
conclusion: 为视频LLM高效处理长视频提供了通用令牌选择框架。
---

## Abstract
Long-form video understanding poses a significant challenge for video large language models (VideoLLMs) due to prohibitively high computational and memory demands. 
In this paper, We propose $\textbf{FlexSelect}$, a flexible and efficient token selection strategy for processing long videos.
FlexSelect identifies and retains the most semantically relevant content by leveraging cross-modal attention patterns from a reference transformer layer.
It comprises two key components: (1) $\textbf{a training-free token ranking pipeline}$ that leverages faithful cross-modal attention weights to estimate each video token’s importance, and (2) $\textbf{a rank-supervised lightweight selector}$ that is trained to replicate these rankings and filter redundant tokens.
This generic approach can be seamlessly integrated into various VideoLLM architectures, such as LLaVA-Video, InternVL and Qwen-VL, serving as a plug-and-play module to extend their temporal context length. Empirically, FlexSelect delivers strong gains across multiple long-video benchmarks – including VideoMME, MLVU, LongVB, and LVBench. Morever, it achieves significant speed-ups ($\textit{e.g.,}$ up to 9 $\times$ on a LLaVA-Video-7B model), highlighting FlexSelect’s promise for efficient long-form video understanding. Project page: https://flexselect.github.io

---

## 论文详细总结（自动生成）

以下是基于论文《FlexSelect: Flexible Token Selection for Efficient Long Video Understanding》的详细中文总结，按照要求的要点依次展开。

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：长视频理解中，视频大语言模型（VideoLLMs）处理大量视觉令牌导致计算和内存开销极高，难以扩展到长序列。
- **研究动机**：现有方法要么需要大量训练（如压缩模块），要么使用基于注意力的启发式剪枝，但存在跨层注意力不一致、性能下降等问题。
- **整体含义**：本文提出一种灵活、高效的令牌选择策略 FlexSelect，通过利用预训练 VideoLLM 内部跨模态注意力的语义相关性，仅保留与查询最相关的视觉令牌，从而在不修改原模型的前提下显著降低计算开销，同时提升或保持性能。该方法可作为即插即用模块集成到多种 VideoLLM 架构中。

## 2. 论文提出的方法论

- **核心思想**：利用预训练 VideoLLM 中特定参考层的跨模态注意力权重作为令牌重要性的可靠排序信号，选择与文本查询最相关的视觉令牌，并通过轻量级选择器模仿该排序以加速推理。
- **关键技术细节**：
  - **参考层的确定**：通过“针在干草堆”实验（Recall@K 指标）找出最能恢复语义相关令牌的中间层作为参考层（如 LLaVA-Video-7B 的第19层）。
  - **训练无关的令牌排序流水线**：将长视频分成多个帧集（Frame Sets），在每个帧集内使用参考层的跨模态注意力分数对令牌排序，保留 top-k 令牌。
  - **轻量级排序监督选择器**：训练一个小型 Transformer 网络（约0.5B参数），以参考层的排序为目标，通过 Spearman 秩相关系数损失进行监督，从而快速预测令牌重要性。
  - **集成流程**：训练无关模式直接使用参考层排序；轻量级模式使用训练好的选择器，无需再通过大模型进行注意力计算。

## 3. 实验设计

- **使用的数据集/场景**：
  - **四个长期视频理解基准**：VideoMME（无字幕）、MLVU、LongVideoBench（LongVB）、LVBench。
  - **额外评估**：视频描述任务（VideoDC）、开放式问答（VideoEvalPro）。
- **对比的方法**：
  - 开放源码 VideoLLMs：LongVU, mPLUG-Owl3, NVILA, VideoLLaMA3, Aria, Oryx-1.5, Video-XL-Pro, SF-LLaVA, TPO, Quato, ViLAMP, VideoChatFlash, LLaVA-Video, InternVL2.5, Qwen2.5-VL 等。
  - 专有模型：GPT-4o, Gemini-1.5-Pro。
  - 令牌剪枝方法：FastV, FrameFusion, DyCoke, VisionZip, BOLT（帧选择）。
- **评估指标**：各基准的标准准确率（如 VideoMME 的总体和长视频准确率、MLVU 的 M-Avg、LongVB 验证集准确率、LVBench 测试集准确率），以及响应时间、FLOPs 估计。

## 4. 资源与算力

- **实验资源**：论文在附录 A.4 中说明主要实验在 **8 张 96G H20 GPU** 上使用 LMMS-Eval 框架进行。
- **训练数据**：轻量级选择器训练使用 LLaVA-Video-178K 数据集中随机抽取的 **5% 子集（约67k样本）**。
- **训练步数**：LLaVA-Video 和 InternVL 的选择器训练 1 epoch；Qwen2.5VL 的选择器训练 3 epoch（因从语言模型初始化）。
- **模型规模**：轻量级选择器初始化自 0.5B/1B/2B/4B 的小型 VideoLLM（具体取决于基础模型）。

## 5. 实验数量与充分性

- **实验组数**：
  - 主要结果（表1）：在4个基准上对比5种模型规模（7B/8B/72B），包括与众多 SOTA 方法的比较。
  - 与令牌剪枝方法对比（表2）：在3种基础模型上、不同帧数/保留率下比较。
  - 消融实验（表3-9）：
    - 参考层选择的影响（图6）。
    - 输入帧数和最大选择令牌数的消融（表3）。
    - 训练数据规模和指令类型的消融（表4）。
    - 选择器参数规模的影响（表5）。
    - 与多数投票方法的对比（表6）。
    - 与帧选择方法 BOLT 的对比（表7）。
    - 在描述任务和开放式任务上的评估（表8、9）。
  - 附加分析：Recall@K 实验、PCA 可视化。
- **充分性**：实验覆盖了多种架构、多种规模、多种任务类型（多项选择、开放问答、描述），并进行了充分的消融和对比，结论可靠、客观。

## 6. 论文的主要结论与发现

- **主要结论**：FlexSelect 通过选择语义相关的视觉令牌，显著提升了 VideoLLM 在长视频理解上的性能，同时大幅减少计算开销（高达 9 倍加速）。
- **关键发现**：
  - VideoLLM 中中间层的跨模态注意力能最可靠地反映令牌与查询的语义相关性。
  - 仅保留约 6.25% 的令牌即可达到甚至超越原始全令牌的性能。
  - 轻量级选择器能以极低成本近似参考层的排序，进一步加速推理。
  - 方法具有架构无关性，在 LLaVA-Video、InternVL、Qwen2.5-VL 等模型上均有效。

## 7. 优点

- **方法上的亮点**：
  - 无需修改或重训基础 VideoLLM，即插即用。
  - 参考层的发现基于系统性实验，而非经验选择，具有可解释性。
  - 轻量级选择器的排序监督训练效率高（仅需 5% 训练数据）。
  - 帧集划分保证长视频覆盖，避免一次性处理所有帧。
- **实验设计上的亮点**：
  - 对比全面：包括多种 SOTA 模型和令牌剪枝方法。
  - 消融细致：验证了参考层、数据量、选择器规模等关键因素。
  - 评估多样化：覆盖多项选择、开放问答、描述任务，以及短中长视频。
  - 提供了 FLOPs 估计和实际时间分析，直观展示效率提升。

## 8. 不足与局限

- **实验覆盖**：未测试更大规模模型（如 72B 以上）的轻量级选择器训练（因内存限制）；未在真实视频流或在线应用中评估。
- **偏差风险**：方法依赖参考层注意力的质量，若基础模型训练不充分或注意力模式不稳定，选择可能不准确。
- **应用限制**：
  - 性能受限于基础 VideoLLM 自身的理解能力（论文中提及）。
  - 轻量级选择器性能略低于直接使用参考层（训练无关模式），存在 trade-off。
  - 帧集划分需手动设定超参数（每集帧数、最大选择令牌数），可能需针对不同视频长度调整。
  - 论文未讨论对时序推理任务（如计数、顺序判断）的潜在影响，仅关注语义相关性选择。

（完）
