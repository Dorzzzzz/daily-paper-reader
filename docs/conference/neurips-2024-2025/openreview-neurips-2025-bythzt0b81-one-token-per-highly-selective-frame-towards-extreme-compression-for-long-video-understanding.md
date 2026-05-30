---
title: "One Token per Highly Selective Frame: Towards Extreme Compression for Long Video Understanding"
title_zh: 每高度选择帧仅需一个token：面向长视频理解的极端压缩
authors: "Zheyu Aqa Zhang, Ziqi Pang, Shixing Chen, Xiang Hao, Vimal Bhat, Yu-Xiong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=bythzT0b81"
tags: ["query:long-video"]
score: 9.0
evidence: 针对长视频理解的极端token压缩方法
tldr: 该论文针对长视频理解中帧数过多导致上下文窗口受限的问题，提出极端视频token压缩方法LP-Comp，将每帧压缩为单个token。关键在于利用可学习且渐进式的层间压缩模块替代启发式压缩，避免信息损失。实验表明，该方法在多个长视频理解基准上以极少的token数达到或超过现有方法性能，显著提升了VLM处理长视频的能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1351, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1352, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1140, \"height\": 378, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1376, \"height\": 802, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 921, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1142, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 543, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 778, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1481, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1016, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1426, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 981, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1216, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1366, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1370, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1419, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1188, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bythzt0b81/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1012, \"height\": 339, \"label\": \"Table\"}]"
motivation: 长视频帧数过多，现有压缩方式信息损失大，限制LLM上下文利用。
method: 提出LP-Comp，在LLM最终层进行可学习、渐进式的token级压缩，实现每帧一个token。
result: 在长视频理解任务上，LP-Comp以极低token数取得与多token方法相当或更优的结果。
conclusion: 可学习压缩是长视频理解中高效利用上下文的关键。
---

## Abstract
Long video understanding is inherently challenging for vision-language models (VLMs) because of the extensive number of frames. With each video frame typically expanding into tens or hundreds of tokens, the limited context length of large language models (LLMs) forces the VLMs to perceive the frames sparsely and lose temporal information. To address this, we explore extreme video token compression towards *one token per frame* at the final LLM layer. Our key insight is that heuristic-based compression, widely adopted by previous methods, is prone to information loss, and this necessitates supervising LLM layers into *learnable* and *progressive* modules for *token-level compression* (LP-Comp). Such compression enables our VLM to digest 2x-4x more frames with improved performance. To further increase the token efficiency, we investigate *frame-level compression*, which selects the frames most relevant to the queries via the internal attention scores of the LLM layers, named *question-conditioned compression* (QC-Comp). As a notable distinction from previous studies, we mitigate the position bias of LLM attention in long contexts, *i.e.*, the over-concentration on the beginning and end of a sequence, by splitting long videos into short segments and employing local attention. Collectively, our combined *token-level* and *frame-level* leads to an e**x**treme compression model for long video understanding, named **XComp**, achieving a significantly larger compression ratio and enabling denser frame sampling. Our XComp is finetuned from VideoChat-Flash with a data-efficient *supervised compression tuning* stage that only requires 2.5\% of the supervised fine-tuning data, yet boosts the accuracy from 42.9\% to 46.2\% on LVBench and enhances multiple other long video benchmarks.

---

## 论文详细总结（自动生成）

## 论文总结：One Token per Highly Selective Frame

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：长视频理解中，每一帧被编码为数十到数百个token，导致视觉-语言模型（VLM）受限于大型语言模型（LLM）的有限上下文长度，只能稀疏地采样帧，丢失了大量时间信息。
- **目标**：探索极端视频token压缩，在LLM最终层将每帧压缩为仅一个token，从而允许模型处理更多帧（2–4倍），提升长视频理解性能。
- **现有方法局限**：以往采用启发式压缩（如特殊token选择、池化）在高压压缩比下易丢失信息，因为LLM层未接受过显式的压缩监督。

### 2. 论文提出的方法论
- **核心思想**：通过监督式压缩微调，让LLM层学会逐步、可学习地压缩视频token，而非依赖训练时不可用的启发式规则。
- **关键技术细节**：
  - **Token级压缩（LP-Comp）**：设计一个余弦调度公式，在全部LLM层中平滑减少每帧token数量，最终在最后一层达到每帧1个token。压缩时保留每帧的后缀token（适合因果注意力架构）。
  - **帧级压缩（QC-Comp）**：利用LLM内部注意力分数，选择与查询最相关的帧。为解决长上下文中的“lost in the middle”位置偏差，将长视频分割为短片段（窗口大小为64帧），在片段内独立计算注意力分数。
  - **数据效率**：仅使用VideoChat-Flash原始SFT数据集的2.5%进行监督压缩微调，即达到显著性能提升。
- **算法流程**：
  1. 输入视频通过视觉编码器（UMT-L）和token合并器得到每帧16个token。
  2. 每个LLM层之后，根据余弦公式计算目标token数，若需减少则保留后缀token。
  3. 推理阶段，QC-Comp对视频分段、计算帧相关性分数，选择top-k相关帧输入模型生成回答。

### 3. 实验设计
- **数据集/benchmark**：
  - 主要benchmark：LongVideoBench（平均473s）、MLVU（651s）、VideoMME Long（2386s）、LVBench（4101s）。
  - 额外评估：CLEVRER（因果关系推理）、VDC（视频描述）、MME-VideoOCR（文本感知）、Multi-Hop NIAH（多跳“大海捞针”）。
- **对比方法**：
  - 同规模VLM：VideoChat-Flash-2B、InternVL3-2B。
  - 更大规模VLM（3B~9B）：Qwen2.5VL-3B、mPLUG-Owl3-7B、VideoChat-Flash-7B、Eagle2.5-8B、Kangaroo、TimeMarker、InternVL3-9B。
  - 专有模型：GPT-4V、GPT-4o、Gemini-1.5-Pro（仅参考）。
- **实验场景**：多选问答、视频描述、文本提取、多跳推理。

### 4. 资源与算力
- 论文明确指出训练使用 **8×NVIDIA H100 GPU**，训练时长约 **24小时**。
- 推理效率测试在一张 **NVIDIA H200** 上进行，记录了不同帧数下的TFLOPs和延迟。

### 5. 实验数量与充分性
- **实验数量**：覆盖5个主要长视频QA benchmark（LVB、MLVU、VideoMME Long、LongVideoBench）以及CLEVRER、VDC、MME-VideoOCR、Multi-Hop NIAH等额外任务；包含充分的消融实验（表2-7）。
- **充分性与公平性**：
  - 消融实验对比了可学习vs.训练无关压缩、渐进vs.阶梯式压缩、后缀保留vs.均匀丢弃、局部注意力vs.全局注意力、以及各组件（LP-Comp和QC-Comp）的单独贡献。
  - 对比基线采用同规模模型，并在相同数据条件下与微调版本比较（表D），确保性能提升来自方法本身而非额外数据。
  - 局限性：所有实验基于2B规模的VideoChat-Flash微调，未在大规模VLM上验证；仅报告单次运行结果，未提供统计误差棒。

### 6. 论文的主要结论与发现
- **可学习的、渐进的压缩**比启发式压缩显著更优，证明了监督LLM层进行压缩的必要性。
- **后缀保留策略**与因果注意力兼容，优于均匀保留。
- **分段局部注意力**有效缓解了长上下文中的位置偏差，提升帧选择质量。
- 所提XComp在2B规模下达到SOTA，在LVBench上从42.9%提升至46.2%，在多个benchmark上优于同规模甚至更大规模的模型。
- 极端压缩（每帧1 token）不仅节省计算，还允许处理更多帧，从而进一步提升性能。

### 7. 优点
- **创新性**：首次系统性地探索将每帧压缩到1个token的极限，并提出可学习、渐进的压缩范式。
- **有效性**：仅用2.5%数据微调即获得显著提升，数据利用效率高。
- **全面性**：在多个长视频benchmark上验证，并涵盖消融、效率分析、泛化性测试（LLaVA-Next-Video）。
- **实践价值**：同时降低计算开销和内存占用，使长视频模型更实用。

### 8. 不足与局限
- **规模限制**：仅基于2B模型实验，未验证在更大VLM（如7B、13B）上的效果。
- **统计可靠性**：未报告多次运行的误差棒，结果可能存在波动。
- **训练框架限制**：QC-Comp仅在推理时应用，未与LLM层联合训练，可能限制进一步压缩。
- **应用边界**：对极长视频（>1小时）仅使用固定帧数选择（如2048帧），未讨论更动态的选择策略。
- **偏差风险**：未详细讨论模型对特定视频内容（如不同语言、文化场景）的公平性。

（完）
