---
title: Mitigating Semantic Collapse in Partially Relevant Video Retrieval
title_zh: 缓解部分相关视频检索中的语义坍缩
authors: "WonJun Moon, MinSeok Jung, Gilhan Park, Tae-Young Kim, Cheol-Ho Cho, Woojin Jun, Jae-Pil Heo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Wlpf0Vg4yU"
tags: ["query:long-video"]
score: 6.0
evidence: 处理多事件视频检索问题，与长视频分析方法相关
tldr: 部分相关视频检索中，现有方法忽略视频内多事件的语义变化导致嵌入坍缩。本文提出语义坍缩缓解方法，通过建模文本与视频片段间的细粒度对应关系，提升多事件视频检索的准确性，为长视频分析提供了有效工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wlpf0vg4yu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wlpf0vg4yu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wlpf0vg4yu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 561, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 725, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 710, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 660, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 755, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 448, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 893, \"height\": 694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 693, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wlpf0vg4yu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 692, \"height\": 178, \"label\": \"Table\"}]"
motivation: 现有方法忽略视频内多事件的语义多样性，导致嵌入坍缩，限制检索性能。
method: 提出在文本和视频嵌入空间中建模语义对应关系，缓解语义坍缩。
result: 在多个视频检索基准上取得了显著性能提升。
conclusion: 该方法有效缓解了语义坍缩，提高了多事件视频的检索质量。
---

## Abstract
Partially Relevant Video Retrieval (PRVR) seeks videos where only part of the content matches a text query. 
Existing methods treat every annotated text–video pair as a positive and all others as negatives, ignoring the rich semantic variation both within a single video and across different videos. 
Consequently, embeddings of both queries and their corresponding video‐clip segments for distinct events within the same video collapse together, while embeddings of semantically similar queries and segments from different videos are driven apart.
This limits retrieval performance when videos contain multiple, diverse events.
This paper addresses the aforementioned problems, termed as semantic collapse, in both the text and video embedding spaces. 
We first introduce Text Correlation Preservation Learning, which preserves the semantic relationships encoded by the foundation model across text queries.
To address collapse in video embeddings, we propose Cross-Branch Video Alignment (CBVA), a contrastive alignment method that disentangles hierarchical video representations across temporal scales.
Subsequently, we introduce order-preserving token merging and adaptive CBVA to enhance alignment by producing video segments that are internally coherent yet mutually distinctive.
Extensive experiments on PRVR benchmarks demonstrate that our framework effectively prevents semantic collapse and substantially improves retrieval accuracy.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

部分相关视频检索（PRVR）的目标是从未修剪的长视频中检索出与文本查询**仅部分内容匹配**的视频。现有方法将所有标注的文本-视频对视为正例，其余均为负例，忽略了单个视频内部不同事件之间的丰富语义变化，也忽略了不同视频之间可能存在语义相似的片段。这种处理方式导致：

- **文本语义坍缩**：同一视频对应的多个文本查询（即使含义不同）在嵌入空间中聚拢，而不同视频中语义相似的查询却被推远。
- **视频语义坍缩**：同一视频中不同语义的片段（frame/clip）也被迫嵌入到一起，丧失区分度。

该问题严重限制了PRVR在包含多事件视频上的检索性能。本文旨在同时缓解文本和视频嵌入空间中的语义坍缩。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
利用CLIP等基础模型中蕴含的结构化语义关系来正则化文本嵌入，并通过双分支对比对齐来区分视频内部的不同事件，同时引入令牌合并策略来构建语义连贯的视频片段。

### 关键技术细节

- **Text Correlation Preservation Learning (TCPL)**  
  从CLIP文本编码器的[EOS]令牌中提取文本间的成对欧氏距离和三元组角度距离，通过Huber损失将这些关系蒸馏到检索模型的文本嵌入空间。公式（4）（5）定义了蒸馏损失，最终损失为 \( \mathcal{L}_\text{TCPL} = \lambda_E L_E + \lambda_A L_A \)。保留了基础模型中的语义结构，防止文本嵌入坍缩。

- **Cross-Branch Video Alignment (CBVA)**  
  利用PRVR中常见的双分支结构（frame分支和clip分支），对同一时间戳的frame和clip作为正对，不同时间戳作为负对进行对比学习。基本公式（8）为：
  \[
  \mathcal{L}_\text{CBVA} = -\frac{1}{L_f}\sum \log \frac{\exp(\text{sim}(v_f^i, v_c^{\delta(i)}))}{\sum_j \exp(\text{sim}(v_f^i, v_c^j))} - \frac{1}{L_c}\sum \log \frac{\sum_{x}\exp(\text{sim}(F_i[x], v_c^i))}{\sum_j \exp(\text{sim}(v_f^j, v_c^i))}
  \]
  增强视频内部不同事件的判别性。

- **Order-Preserving Token Merging (OP-ToMe)**  
  在clip构建阶段，只合并相邻帧中相似度最高的令牌对（按比例N%），保持时间顺序，生成语义连贯的clip片段。

- **Adaptive CBVA**  
  估计每个视频内部不同上下文的数量，通过二分令牌合并（bipartite merging）动态调整clip数量，使对比学习更精准。

整体训练目标：\( \mathcal{L}_\text{overall} = \mathcal{L}_\text{base} + \mathcal{L}_\text{TCPL} + \lambda_\text{CBVA} \mathcal{L}_\text{CBVA} \)，其中 \( \mathcal{L}_\text{base} \) 是标准的InfoNCE + triplet loss。

## 3. 实验设计

### 数据集
- QVHighlights、TVR、ActivityNet Captions、Charades-STA。每个视频平均与3.3~5个文本查询配对。
- 评价指标：Recall@K（K=1,5,10,100）及SumR（四项之和）。

### 对比方法
包括：MS-SL、GMMFormer、GMMFormer-v2、AMDNet、BGMNet、ProtoPRVR、ARL等。同时报告了零样本CLIP的结果。

### 实验设置
- 主干网络：CLIP-B/32（QVHighlights）或CLIP-L/14（其他数据集），另用SlowFast特征。
- 超参数：损失系数 \( \lambda_E=15, \lambda_A=30, \lambda_\text{CBVA}=0.1 \)，合并率N=75%，阈值τ因数据集而异（0.7~0.85）。
- 所有实验在单个RTX A6000 GPU上进行。

## 4. 资源与算力

- GPU：单张RTX A6000（48GB显存）。
- CPU：Intel Xeon Gold 6338 (2.00GHz)。
- 训练时间：每epoch约62,641 ms（Table 7），模型参数量32.14M，FLOPs 2.78G。相比基线GMMFormer-v2，训练时间增加（约17,223 ms→62,641 ms），但推理阶段无额外开销（Table 6显示推理时间与GMMFormer-v2相当）。

## 5. 实验数量与充分性

论文共进行了**多组充分的实验**：
- **组件消融**（Table 1）：基线→+TCPL→+Naïve CBVA→+OP-ToMe→+Adaptive CBVA，逐步验证每个模块贡献。
- **视频相关性保持学习对比**（Table 2）：与Retrieved segment、Uniform Sampling两种VCPL变体对比。
- **超参数消融**（Table 3 & Table A1）：TCPL比例、系数、来源模型；CBVA系数、合并率N、阈值τ；各数据集上的阈值敏感性。
- **与SOTA对比**（Table 4、5）：在四个数据集上与多个方法对比。
- **相似性结构分析**（Table 8）：量化文本/视频的Intra Sim、Total Sim及Diff.Norm，证明语义坍缩缓解。
- **Spearman秩相关**（Table 9）：与CLIP的语义结构保持程度，本文达68.18，远高于其他方法。
- **定性结果**（Figure 3）及**CLIP失败模式分析**（Table A2）：显示本文能纠正CLIP在复杂查询上的错误。

实验设计客观公平：所有对比方法均为官方或复现结果，超参数统一或分别调优，评价指标为标准Recall。消融实验系统全面。

## 6. 主要结论与发现

- 本文提出的TCPL和CBVA能有效缓解文本和视频嵌入空间的语义坍缩，在四个标准PRVR数据集上均达到当前最优（SOTA）。
- TCPL通过蒸馏CLIP的语义关系结构，显著提升了文本嵌入的质量；CBVA通过区分视频内部不同事件，加上OP-ToMe和自适应合并，极大地增强了视频表示的多事件判别力。
- 方法对超参数（阈值、系数）不敏感，鲁棒性好。
- 推理效率与现有最优方法（GMMFormer-v2）持平，训练开销虽增加，但属于离线成本。

## 7. 优点

- **问题定义清晰**：首次系统性地在文本和视频两个模态中同时解决语义坍缩，思路完整。
- **方法创新**：TCPL创新地利用基础模型进行关系蒸馏；CBVA利用双分支对比对齐，并设计OP-ToMe和自适应合并来增强语义一致性。
- **实验充分**：覆盖四个数据集，大量消融和可视化分析，证明各模块有效性。
- **效率平衡**：训练成本可接受，推理无额外延迟，实用性强。
- **代码开放**：论文承诺开源代码，易于复现。

## 8. 不足与局限

- **依赖CLIP**：方法继承了CLIP的弱点，例如对细粒度的空间/方向查询（如“left of” vs “right of”）表现不佳。但论文指出该方法能纠正CLIP在多实体和时间组合查询上的部分失败（R@1恢复28%失败案例，R@10恢复57%）。
- **训练成本增加**：相比GMMFormer-v2，每epoch时间增加约3.6倍，内存增加约25%。但论文认为该成本发生在离线训练阶段，不影响部署推理。
- **实验局限性**：仅涉及四个PRVR数据集，未在更广泛的长视频理解任务（如视频问答、时序定位）上验证泛化性。另外，所有实验使用固定的超参数设置（如合并率N=75%），可能对其他类型视频（如极短或极长视频）不一定最优。
- **未讨论公平性与隐私风险**：论文在附录中提及了负面社会影响（监控滥用），但未提出具体缓解措施。

（完）
