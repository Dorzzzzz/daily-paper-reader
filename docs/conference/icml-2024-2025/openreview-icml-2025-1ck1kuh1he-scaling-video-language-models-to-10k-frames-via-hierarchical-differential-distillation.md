---
title: Scaling Video-Language Models to 10K Frames via Hierarchical Differential Distillation
title_zh: 通过分层差分蒸馏将视频语言模型扩展到万帧
authors: "Chuanqi Cheng, Jian Guan, Wei Wu, Rui Yan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1CK1kuH1he"
tags: ["query:long-video"]
score: 9.0
evidence: 通过分层差分蒸馏将视频语言模型扩展到万帧
tldr: 长视频处理面临高昂计算成本，现有方法牺牲时序依赖或稀释语义。本文提出差分蒸馏原则，并据此开发ViLAMP，通过差分关键帧选择和差分token合并两种机制，以混合精度处理小时级视频。实验表明可有效处理长达10K帧的视频，保持性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 880, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1728, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 818, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 626, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 622, \"height\": 493, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 1368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 637, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1020, \"height\": 1160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 943, \"height\": 846, \"label\": \"Table\"}]"
motivation: 长视频处理中计算成本高且现有方法损失关键信息。
method: 提出差分蒸馏原则，设计分层ViLAMP模型，包括差分关键帧选择和差分token合并。
result: 成功处理10K帧视频，性能优于现有方法。
conclusion: ViLAMP为长视频理解提供了高效可扩展的解决方案。
---

## Abstract
Long-form video processing fundamentally challenges vision-language models (VLMs) due to the high computational costs of handling extended temporal sequences. Existing token pruning and feature merging methods often sacrifice critical temporal dependencies or dilute semantic information. We introduce differential distillation, a principled approach that systematically preserves task-relevant information while suppressing redundancy. Based on this principle, we develop ViLAMP, a hierarchical video-language model that processes hour-long videos at "mixed precision" through two key mechanisms: (1) differential keyframe selection that maximizes query relevance while maintaining temporal distinctiveness at the frame level and (2) differential feature merging that preserves query-salient features in non-keyframes at the patch level. Hence, ViLAMP retains full information in keyframes while reducing non-keyframes to their most salient features, resembling mixed-precision training. Extensive experiments demonstrate ViLAMP's superior performance across five video understanding benchmarks, particularly on long-form content. Notably, ViLAMP can process ultra-long videos (up to 10K frames) on a single NVIDIA A100 GPU, achieving substantial computational efficiency while maintaining state-of-the-art performance. 
Code and model are available at https://github.com/steven-ccq/ViLAMP.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：长视频理解中，视觉语言模型（VLM）面临高昂计算成本。例如，1分钟视频（24FPS）可产生超过100万视觉token，远超主流LLM的上下文长度（4K-128K）。现有方法（token剪枝、特征合并）要么丢失关键时序依赖，要么稀释语义信息。
- **整体含义**：本文旨在实现**效率与信息保真度的平衡**，使VLM能够处理小时级（高达10000帧）的极长视频，同时保持或提升理解性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想：差分蒸馏原则（Differential Distillation）
- **基本动机**：通过分析发现，约90%的查询注意力集中在5%的帧上，且这些帧内部存在高度视觉冗余；非关键帧中50%的patch贡献80%注意力，且与关键帧patch高度相似。
- **形式化定义**：对于任何视频组件 \(v\)（帧、patch或特征），定义差分信息显著性分数：
  \[
  D(v) = R(v, Q) - T(v, C(v))
  \]
  其中 \(R(v, Q)\) 为查询相关性，\(T(v, C(v))\) 为与上下文的时序冗余度。该分数高意味着v包含独特且任务相关的信息，应分配更多计算资源。

### 关键技术细节：ViLAMP 模型
采用分层“混合精度”处理，包含两个核心模块：

#### (a) 差分关键帧选择（DKS）
- **目的**：从长视频中选择既与查询相关又在时间上独特的帧作为关键帧。
- **过程**：
  1. 使用CLIP编码器将每帧和查询映射为嵌入，计算帧级查询相关性 \(R_f(f_n, Q)\)。
  2. 计算帧与上下文（已选关键帧集合）的最大余弦相似度作为时序冗余 \(T_f(f_n, C(f_n))\)。
  3. 采用贪心算法：按查询相关性降序排序帧，仅当当前帧与已选关键帧的相似度低于阈值 \(\tau\) 且未达到最大关键帧数 \(K\) 时加入。
- **复杂度**：\(O(\max(NK, N\log N))\)，其中 \(N\) 总帧数，\(K\) 关键帧数。

#### (b) 差分特征合并（DFM）
- **目的**：对非关键帧进行压缩，保留查询显著且不与前面关键帧冗余的patch信息，每个非关键帧输出一个token。
- **过程**：
  - 对于非关键帧 \(f_n\) 和最近的前一个关键帧 \(f_k\)，计算每个patch的差分显著性分数：
    \[
    D_p(p_m^n) = R_p(p_m^n, Q) - \lambda \cdot T_p(p_m^n, p_m^k)
    \]
    \(R_p\) 为patch与查询的余弦相似度，\(T_p\) 为与对应关键帧patch的余弦相似度。
  - 通过softmax归一化得到权重 \(w_m^n\)，然后进行加权平均池化得到压缩token \(t_n\)。
- **优势**：当关键帧patch已包含相似信息时，对应非关键帧patch权重降低，避免冗余。

#### 整体架构
- 关键帧保留全部 \(M\) 个视觉token，非关键帧压缩为1个token，总token数从 \(MN\) 降至 \(MK + (N-K)\)（\(K \ll N\)）。
- 两个独立的MLP分别处理关键帧和非关键帧token，输入LLM进行自回归训练（语言建模损失）。

## 3. 实验设计：数据集、基准、对比方法

### 数据集与基准
- **标准基准（5个）**：
  - **LVBench**（平均4101秒，长时间决策）
  - **EgoSchema**（180秒，自然场景理解）
  - **LongVideoBench**（473秒，引用推理）
  - **MLVU**（651秒，多任务QA）
  - **Video-MME**（1010秒，综合；含长视频子集2386秒）
- **新提出的基准 - VideoNIAH**：灵感来自LLM的“大海捞针”范式，在2K-10K帧的“干草堆”中插入“针”视频片段（30-120秒），需要模型定位并理解内容以回答查询。共3000个测试案例，平衡各类问题。

### 对比方法
- **专有模型**：GPT-4V、GPT-4o、Gemini-1.5-Pro。
- **开源多图像VLM**：LLaVA-OneVision（7B/72B）、InternVL2（8B/76B）、Qwen2-VL（7B）、NVILA（7B）等。
- **开源视频VLM**：LLaVA-Video、LLaMA-VID、VideoChat-Flash、LongVA、LongVU等。

## 4. 资源与算力

- 文中明确说明：训练使用 **32 块 NVIDIA A100 GPU**，采用三阶段训练，总训练轮数为1 epoch，耗时约 **两周**。
- 评估时，ViLAMP可在**单块A100 GPU**上处理高达10K帧的视频，无OOM错误。

## 5. 实验数量与充分性

### 实验数量
- **主要结果**：在5个标准基准上对比多种基线，报告准确率。
- **缩放实验**：在VideoNIAH上测试2K、4K、6K、8K、10K帧场景，评估准确率和内存、FLOPs、时延。
- **消融实验**：分别对DKS（对比均匀采样、查询导向采样）和DFM（对比Q-Former、平均池化）进行消融。
- **超参数分析**：对阈值 \(\tau\) 和 \(\alpha\) 进行网格搜索（表6）。
- **关键帧数量影响**：分析不同数据集上K的变化（图6）。
- **额外任务验证**：视频定位（QVHighlights的Hit@k）和动作识别（ActivityNet、Something-Something V2、UCF-101）的零样本迁移。

### 充分性评价
- **客观公平**：对比方法均为最新或代表性模型，结果从原论文或自行复现（ViLAMP方法部分），基线参数设置一致（如表1注明“所有基线结果来自原论文”）。
- 消融实验设计合理，能验证各组件贡献。
- **潜在不足**：主要依赖自动评估指标（准确率），未在更多样化任务（如视频字幕生成、时序定位）上评估；VideoNIAH基准为自制，可能存在偏差。

## 6. 论文的主要结论与发现

- ViLAMP在**五个标准基准**上均达到同类7B模型的SOTA，尤其在长视频子集（Video-MME长视频提升4.8%）表现突出。
- 在**VideoNIAH极端长视频（10K帧）** 场景下，ViLAMP准确率58.15%，远超VideoChat-Flash的47.25%（提升12.82%），且性能下降幅度最小。
- **计算效率**显著：内存增长平缓；在8192帧时FLOPs仅为VideoChat-Flash的18.4%，时延相当。
- **关键帧选择与特征合并**均对性能有正向贡献，且无需额外长视频训练数据即可良好泛化。
- 差分蒸馏原则为长视频理解提供了理论指导，能动态分配计算资源。

## 7. 优点：方法或实验设计上的亮点

- **理论创新**：提出差分蒸馏原则，将信息显著性简洁定义为查询相关性减去时序冗余，统一帧级和patch级操作。
- **工程创新**：混合精度处理（关键帧全token + 非关键帧单token）大幅减少计算量，同时利用贪心算法保证高效性。
- **实验全面**：不仅覆盖多种标准基准，还自建了更具挑战性的VideoNIAH基准，且对比了10+种基线，消融和超参分析完整。
- **可扩展性**：能在单GPU上处理10K帧，且性能稳定，具有实际部署潜力。
- **代码开源**：提供GitHub仓库，促进复现与后续研究。

## 8. 不足与局限

- **训练开销大**：需要32块A100 GPU训练两周，对资源要求高。
- **依赖外部编码器**：DKS使用CLIP-ViT-B-32，性能受限于该编码器对长视频的表示能力；未探索更高效的编码器或无查询设定。
- **任务覆盖有限**：主要评估视频QA，未涉及时序定位（除Hit@k初步）、视频单帧检索、多模态生成等任务；动作识别仅做零样本，未微调。
- **VideoNIAH基准局限性**：针视频取自Video-MME，可能已包含在模型训练数据中导致过拟合；干草堆长度仅到10K帧，未探索更大规模。
- **实际应用风险**：模型可能产生不准确、有偏见或冒犯性输出，需部署时严格验证。
- **未探索多模态融合**：仅处理视觉帧，忽略音频和字幕（仅Video-MME有字幕实验，ViLAMP未使用），未充分利用多模态信息。

（完）
