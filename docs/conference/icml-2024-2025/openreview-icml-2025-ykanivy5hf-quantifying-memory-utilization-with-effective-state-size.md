---
title: Quantifying Memory Utilization with Effective State-Size
title_zh: 用有效状态尺寸量化记忆利用
authors: "Rom Parnichkun, Neehal Tumma, Armin W Thomas, Alessandro Moro, Qi An, Taiji Suzuki, Atsushi Yamashita, Michael Poli, Stefano Massaroli"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=YKAnIvY5hf"
tags: ["query:agent-memory"]
score: 6.0
evidence: 记忆利用率度量
tldr: 序列建模架构中记忆利用机理难以量化。本文借鉴信号处理与控制理论，提出有效状态尺寸（ESS）指标，度量模型内部记忆储存与利用效率。ESS适用于线性算子类系统，包括注意力、卷积和循环变体，为比较和设计内存高效架构提供了理论工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 490, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1268, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1295, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 407, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1035, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 569, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 814, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1727, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1099, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1736, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1734, \"height\": 1178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1739, \"height\": 1178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1737, \"height\": 1177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1735, \"height\": 1178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1732, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1740, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1725, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1735, \"height\": 1177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1736, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1732, \"height\": 1178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1733, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1732, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1733, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1740, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1319, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1460, \"height\": 1362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 596, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1316, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 590, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1305, \"height\": 851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1711, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1490, \"height\": 1938, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1598, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1576, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1576, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1580, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1578, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1580, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1580, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1580, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1697, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1394, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1402, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1483, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ykanivy5hf/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1484, \"height\": 636, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1710, \"height\": 995, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 459, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 556, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 566, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 565, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 591, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 568, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 718, \"height\": 781, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ykanivy5hf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 518, \"height\": 451, \"label\": \"Table\"}]"
motivation: 缺乏统一的记忆利用量化指标。
method: 基于信号处理和控制理论，定义有效状态尺寸度量。
result: ESS能有效区分不同架构的记忆利用效率。
conclusion: 为序列模型内存分析提供定量框架。
---

## Abstract
As the space of causal sequence modeling architectures continues to grow, the need to develop a general framework for their analysis becomes increasingly important. With this aim, we draw insights from classical signal processing and control theory, to develop a quantitative measure of *memory utilization*: the internal mechanisms through which a model stores past information to produce future outputs. This metric, which we call ***effective state-size*** (ESS), is tailored to the fundamental class of systems with *input-invariant* and *input-varying linear operators*, encompassing a variety of computational units such as variants of attention, convolutions, and recurrences. Unlike prior work on memory utilization, which either relies on raw operator visualizations (e.g. attention maps), or simply the total *memory capacity* (i.e. cache size) of a model, our metrics provide highly interpretable and actionable measurements. In particular, we show how ESS can be leveraged to improve initialization strategies, inform novel regularizers and advance the performance-efficiency frontier through model distillation. Furthermore, we demonstrate that the effect of context delimiters (such as end-of-speech tokens) on ESS highlights cross-architectural differences in how large language models utilize their available memory to recall information. Overall, we find that ESS provides valuable insights into the dynamics that dictate memory utilization, enabling the design of more efficient and effective sequence models.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：随着因果序列建模架构（如 Transformer、状态空间模型 SSM、线性注意力等）的不断涌现，缺乏一个统一的框架来定量分析它们是如何利用内部“工作记忆”来存储过去信息并产生未来输出的。现有方法要么依赖定性的可视化（如注意力图），要么仅看模型的总记忆容量（如缓存大小、状态尺寸），但这些无法反映模型实际利用了多少记忆。
- **整体含义**：本文借鉴经典信号处理与控制理论中的最小实现概念，提出 **有效状态尺寸（Effective State-Size, ESS）** 作为衡量记忆利用率的通用指标。ESS 量化了模型在实际数据上“真正用到的”状态维度，而不仅仅是理论上的状态容量。该指标适用于所有能表达为线性算子（包括输入不变和输入变线性算子，即 LIV）的模型，涵盖注意力、卷积、循环等变体，为分析、比较和优化序列模型提供了可解释且可操作的工具。

## 2. 论文提出的方法论

- **核心思想**：大多数现代序列模型（包括非线性模型）可以被抽象为线性算子 \(y = T u\)，其中 \(T\) 是严格下三角的因果矩阵。ESS 定义为 \(T\) 的某个子矩阵 \(H_i = T_{i:,\,:i-1}\) 的数值秩，该子矩阵包含了从过去所有输入到当前输出的映射信息。根据最小实现理论，\(H_i\) 的秩决定了在索引 \(i\) 处实现该算子所需的最小状态尺寸，从而度量了模型在时间步 \(i\) 实际使用的记忆。
- **关键技术细节**：
    - 对于输入不变线性系统（如卷积），ESS 就是最小可实现状态尺寸。
    - 对于输入变线性系统（LIV，如注意力、门控 SSM），ESS 依赖于输入，但对实际状态尺寸提供了下界，因此仍是记忆利用率的有效代理。
    - 实际计算时，先对每个通道（SISO 情况）提取算子 \(T^{\alpha\alpha} \in \mathbb{R}^{\ell \times \ell}\)，然后对每个序列索引 \(i\) 取出子矩阵 \(H_i\)，进行 SVD 分解得到奇异值 \(\Sigma_i\)。
    - 定义两种具体形式：
        - **容差-ESS（Tolerance-ESS）**：给定阈值 \(\tau\)，统计奇异值大于 \(\tau\) 的数量。
        - **熵-ESS（Entropy-ESS）**：计算归一化奇异值分布的熵的指数，即 \(\exp\left(-\sum_m p_m \log p_m\right)\)，其中 \(p_m = \sigma_m / \|\sigma\|_1\)。熵-ESS 无需人工选阈值，但容差-ESS 更直观。
    - ESS 可以按序列索引、通道、层、批次进行聚合，得到平均 ESS 或总 ESS。对于多通道模型，计算复杂度可降至 \(O(d\ell^3)\)，对于具有头结构的注意力可进一步降低。

## 3. 实验设计

- **数据集与场景**：
    - **合成任务**：采用多查询关联回忆（MQAR）、选择性复制（Selective Copying）和压缩（Compression）三个任务，它们被证明能近似反映语言模型的大规模性能。任务难度通过 kv 对数量、拷贝长度、序列长度、词表大小等调节。
    - **语言模型分析**：使用开源的预训练模型（Falcon Mamba 7B、Mamba 2.8B、Pythia 2.8B、Phi-2、Mistral 7B、Llama 3 8B 等）以及自训练的 1B 参数模型（LA、WLA、GLA、SA）。
- **Benchmark**：合成任务上以准确率（Accuracy）作为主要性能指标；语言任务上使用标准困惑度（PPL）和基于 bigram recall 的困惑度。
- **对比的方法**：
    - **模型架构**：Gated Linear Attention (GLA)、Weighted Linear Attention (WLA)、Linear Attention (LA)、Softmax Attention (SA)。它们分别属于输入变循环（GLA）、输入不变循环（WLA）、固定循环（LA）和注意力的代表。
    - **记忆指标**：对比 ESS 与 TSS（理论上可实现状态尺寸，即模型容量）作为性能预测器的有效性。
    - **应用场景**：还对比了不同初始化方案（S6 vs GLA vs GLA-S6）、不同正则化强度、不同蒸馏教师 ESS 等。

## 4. 资源与算力

- **未明确说明**：论文在实验部分没有给出具体的 GPU 型号、数量或总训练时长。合成任务均在小规模（最多 128k 训练样本、70 epoch）上进行，语言模型 1B 参数训练了 160k steps（batch size 16，序列长度 32k）。从这些设置可推测使用了适当规模的 GPU 集群（可能为 A100 或 H100），但无法量化。

## 5. 实验数量与充分性

- **实验数量相当充分**：
    - 合成任务空间扫描：覆盖 4 种模型 × 7 种模型宽度/头数（对应不同 TSS）× 5 种 kv/拷贝/词表大小 × 6 种序列长度，每个配置训练多个 epoch，共计数千个实验配置。
    - 初始化分析：对比 S6、GLA、GLA-S6 在不同 TSS 下的 ESS 和性能，并在 GLA-S6 上改变归一化因子 α。
    - 蒸馏实验：以不同难度的 MQAR 训练教师模型（GLA, TSS=256），向 4 种学生 TSS（16/32/64/128）进行蒸馏，测量 ESS 与蒸馏损失的关系。
    - 正则化实验：在 MQAR 上比较 λ‖A-I‖_F 正则化的效果。
    - 语言模型分析：对多个 7B-8B 级开源模型分析状态调制，并自训练 4 个 1B 模型（LA/WLA/GLA/SA）进行对比。
- **充分性与公平性**：
    - 实验设计系统，控制了多个变量（任务难度、模型容量、特征器类型），并重复种子。
    - ESS 与准确率的跨任务-模型相关性分析显示了 ESS 优于 TSS 的解释力，且在多任务上一致。
    - 消融实验（熵-ESS 与容差-ESS、不同归一化因子、不同正则化层）进一步验证了方法的稳健性。
    - 但实验主要集中在合成任务和有限的语言模型上，未在大规模真实语言预训练场景中验证所有应用（如蒸馏、正则化）。此外，语言分析中的文本样本数量有限（仅几段句子），可能存在偏差。

## 6. 论文的主要结论与发现

1. **ESS 是记忆利用率的有效度量**：在合成任务（MQAR、选择性复制、压缩）上，ESS/kv 与模型准确率的跨任务-模型相关性显著高于 TSS/kv，说明实际使用的状态比理论容量更能解释性能。
2. **两种训练失败模式**：通过 ESS 诊断出“状态饱和”（ESS 接近 TSS，容量不足）和“状态崩溃”（ESS 过低，容量未有效利用）。GLA 和 WLA 在困难任务上易发生状态崩溃，而 LA 相对更稳定。
3. **ESS 可指导模型设计**：
    - **初始化**：S6 的 ESS 随 TSS 增加而下降或停滞，而 GLA 的 ESS 单调上升，解释了 S6 在 MQAR 上完全失效的原因；通过调整归一化因子可改善 GLA-S6 的 ESS 和性能。
    - **正则化**：对 GLA/WLA 添加 ‖A-I‖_F 正则化可缓解状态崩溃，使其在困难任务上超越 LA。
    - **蒸馏**：教师 ESS 越高，蒸馏到小学生的难度越大，ESS 可作为模型可压缩性的指标。
4. **状态调制与语言模型性能**：注意力模型具有更强的状态调制能力（对分隔符 token 如 <eos> 敏感），其 ESS 在遇到上下文分界点时显著下降，而线性注意力模型几乎无调制。状态调制能力与大词二元召回困惑度相关，解释了为什么软注意力在 recall 任务上更好。
5. **混合网络分析**：在 GLA-SA 混合网络中，ESS 的分布揭示了为什么某些混合拓扑（如注意力不在第一层）性能更好，为混合架构设计提供了新视角。

## 7. 优点

- **理论根基扎实**：从经典控制论和信号处理中的最小实现定理出发，将记忆利用问题转化为矩阵秩问题，推导严谨。
- **通用性强**：适用于大部分现代因果序列模型（注意力、SSM、卷积等），不依赖模型内部非线性细节。
- **可解释且可操作**：ESS 提供了直观的数值，能够揭示状态饱和、状态崩溃、状态调制等微观现象，并直接用于初始化、正则化、蒸馏等环节，切实改进模型性能。
- **实验全面**：在合成和语言任务上都进行了多维度扫描和消融，结果一致性高，证明了 ESS 作为分析工具的有效性。
- **提出新概念**：如状态利用（ESS/TSS）、状态调制，丰富了序列模型记忆研究的理论视角。

## 8. 不足与局限

- **计算开销**：ESS 的计算需要对每个序列索引的子矩阵进行 SVD，对于长序列（ℓ 较大）和宽模型（d 大）可能昂贵，尽管 SISO 假设和头结构可降低复杂度，但实时使用仍有限制。
- **适用范围局限**：仅适用于能提取线性算子的模型（如注意力、线性 SSM），不适用于传统非线性 RNN（LSTM、GRU 等），限制了其通用性。
- **合成任务与现实差距**：合成任务（尤其是 MQAR）虽能近似语言 recall 能力，但语言建模还涉及更多复杂因素，ESS 与最终语言性能的相关性有待在更大规模的预训练中验证。
- **应用验证不够充分**：正则化和蒸馏实验仅在 GLA 模型、小规模合成任务上验证，未在多种架构和大规模模型上测试。语言分析中样本量极少（仅几段句子），不足以代表模型在处理真实长文档时的动态。
- **未提供硬件资源细节**：无法评估计算代价和可复现性。
- **未讨论超参数影响**：容差-ESS 的阈值 τ 和熵-ESS 的数值稳定性（如 p_m 接近 0 时）对结果的影响分析不够深入。

（完）
