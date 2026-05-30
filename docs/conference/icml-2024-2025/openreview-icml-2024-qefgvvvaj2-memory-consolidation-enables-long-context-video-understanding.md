---
title: Memory Consolidation Enables Long-Context Video Understanding
title_zh: 记忆巩固实现长上下文视频理解
authors: "Ivana Balazevic, Yuge Shi, Pinelopi Papalampidi, Rahma Chaabouni, Skanda Koppula, Olivier J Henaff"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=qeFgvVVAJ2"
tags: ["query:long-video"]
score: 10.0
evidence: 通过记忆巩固实现长上下文视频理解
tldr: 针对视频变换器因二次复杂度难以处理长时上下文的问题，本文提出MC-ViT，通过非参数方式从过去激活中提取记忆并利用冗余减少进行记忆巩固，轻松将上下文扩展至远距离过去。该方法只需微调现有预训练视频变换器。在EgoSchema、Perception Test和Diving48上取得了长上下文视频理解的新最佳结果，展示了出色的扩展能力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1756, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-qefgvvvaj2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 627, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-qefgvvvaj2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1190, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qefgvvvaj2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1752, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qefgvvvaj2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qefgvvvaj2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1581, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-qefgvvvaj2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1124, \"height\": 599, \"label\": \"Table\"}]"
motivation: 现有视频变换器因计算复杂度限制了时序上下文长度，需要高效扩展方法。
method: 通过微调预训练视频变换器使其注意力机制关注来自过去激活的非参数记忆，并利用冗余减少。
result: 在EgoSchema等三个长视频理解基准上达到当前最佳性能，且表现出优秀的数据扩展性。
conclusion: 记忆巩固是一种简单有效的长视频理解方法，能大幅提升视频变换器的时域建模能力。
---

## Abstract
Most transformer-based video encoders are limited to short temporal contexts due to their quadratic complexity. While various attempts have been made to extend this context, this has often come at the cost of both conceptual and computational complexity. We propose to instead re-purpose existing pre-trained video transformers by simply fine-tuning them to attend to memories derived non-parametrically from past activations. By leveraging redundancy reduction, our memory-consolidated vision transformer (MC-ViT) effortlessly extends its context far into the past and exhibits excellent scaling behavior when learning from longer videos. In doing so, MC-ViT sets a new state-of-the-art in long-context video understanding on EgoSchema, Perception Test, and Diving48, outperforming methods that benefit from orders of magnitude more parameters.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）
当前基于Transformer的视频编码器因自注意力的二次复杂度，只能处理极短的时序上下文（例如16帧）。尽管已有多种尝试（如掩码、注意力近似、参数化记忆模块）来扩展上下文长度，但这些方法往往增加了概念和计算上的复杂性。本文提出一种更简洁的思路：**重新利用现有预训练的视频Transformer**，通过**非参数方式**从过去的激活中提取并巩固记忆，使模型能够有效处理长视频。该工作不仅降低了复杂度，还在多个长视频理解基准上达到新最优。

### 2. 方法论
- **核心思想**：将视频划分为等长的时间片段，采用流式处理每一段。通过维护一个**非参数记忆库**（Memory Bank），存储经过巩固的过去激活，使当前段能通过交叉注意力关注这些记忆，从而获得长期依赖。
- **关键技术细节**：
  - 基础架构为ViViT（Video Vision Transformer）。
  - **记忆巩固（Memory Consolidation）**：对每个片段的激活进行压缩，得到固定数量的综合表示。论文探索三种非参数方法：
    1. **随机选择（MC-ViT-R）**：随机选取K个激活。
    2. **核心集选择（MC-ViT-CS）**：使用贪心核心集算法选择最具代表性的激活。
    3. **k-means聚类（MC-ViT-KM）**：对激活进行k-means聚类，取K个质心作为巩固记忆（默认方法）。
  - **算法流程（Algorithm 1 简化说明）**：
    1. 将视频嵌入并加入位置编码，分割为片段；
    2. 对每个片段：
       - 通过层归一化；
       - 在每一层，若记忆为空则用自注意力，否则用交叉注意力（查询为当前片段，键/值为当前片段+记忆）；
       - 经过MLP得到输出激活；
       - 将当前片段的激活通过上述方法巩固，并追加到记忆库中；
    3. 所有片段输出拼接作为视频表示。
  - 训练时使用对比学习（噪声对比估计），将视频嵌入与对应文本嵌入对齐。
- **初始化**：权重来自预训练的ViViT（在16帧短视频上训练），仅位置嵌入通过插值适应更长的视频。

### 3. 实验设计
| 数据集 | 任务与特点 | 对比方法 |
|--------|------------|----------|
| **Diving48** | 细粒度动作识别，平均158帧，需长期时序推理 | 联合空时注意力、Streaming ViT、MeMViT、ORViT、AIM等 |
| **EgoSchema** | 长视频问答（3分钟），需长时序证书 | ShortViViT、LongViViT、SeViLA、Flamingo、Bard+PALI、GPT-4V等 |
| **Perception Test** | 多选视频QA（物理/记忆/语义），30秒但高帧率 | 同上类模型 |
| **Next-QA** | 因果/时序推理多选QA，平均44秒 | SeViLA、InternVideo等 |

实验中包含了消融研究（巩固方法、记忆大小、训练帧数、记忆与视频长度解耦）、效率对比（内存/FLOPs与准确率关系）、以及与大规模专有模型的比较。

### 4. 资源与算力
论文未明确说明GPU型号、数量及总训练时长。仅提供了训练参数（如批量大小、学习率、训练步数）：
- EgoSchema: batch=128, steps=5k；Diving48: batch=256, steps=30k；Next-QA: batch=128, steps=20k。
- 使用的模型规模：MC-ViT-B约203M参数，MC-ViT-L约424M参数。

未公开具体算力投入，因此无法准确评估训练成本。

### 5. 实验数量与充分性
- **实验数量丰富**：涵盖4个主要基准，进行了大量消融实验：
  - 不同记忆巩固方法（随机、核心集、k-means）对比；
  - 不同记忆大小（8到2048个记忆）对比；
  - 训练帧数对性能影响（16、32、64、128帧）；
  - 记忆大小与视频长度解耦（固定总记忆量）实验；
  - 与多种基线（Streaming ViT、联合注意力、MeMViT、Late fusion）比较；
  - 与大规模专有模型（GPT-4V、Bard+PALI）对比，并计算“视觉”性能（减去盲模型的得分）。
- **充分性与公平性**：实验设计较为系统，控制变量（如固定训练帧数），对比方法包括公开顶会模型和大规模专有模型，且注意避免数据泄露（EgoSchema使用无重叠训练集）。结论可靠。

### 6. 主要结论与发现
- MC-ViT在Diving48、EgoSchema、Perception Test上达到**新的最优**，尽管参数比对比模型少1~2个数量级。
- MC-ViT能够有效从更长视频中学习：训练帧数越多，性能越好；而普通联合注意力和Streaming ViT无法受益。
- MC-ViT在效率上显著优于联合注意力：同等准确率下，内存和FLOPs均降低10倍以上。
- 非参数记忆巩固（尤其是k-means和核心集）比随机选择和参数化方法（MeMViT）更有效，且能以16倍压缩率超越基线。
- 即使使用极少的记忆（128个），MC-ViT就能超越全段联合注意力，展示了出色的压缩能力。
- 通过解耦总记忆量，发现保存整个历史中均匀采样的记忆比仅保留最近若干段更优。

### 7. 优点
- **方法简洁**：无需修改架构或增加大量参数，仅需微调即可将标准ViViT用于长视频。
- **高效**：计算复杂度与视频长度呈线性关系，非常适用于超长视频。
- **强泛化性**：在不同数据集（动作识别、QA）和不同数据规模下均表现优异。
- **可解释性**：非参数记忆过程类似认知记忆的建构，易于理解。
- **与LLM兼容**：输出的视频表示可直接供LLM使用。

### 8. 不足与局限
- **语言偏置问题**：在Next-QA上，MC-ViT未超越SeViLA，该数据集可能更依赖文本推理而非长视频理解（SeViLA仅用1帧）。
- **记忆机制简单**：非参数方法虽然高效，但可能丢失细微时序模式；更复杂的参数化方法（如Compressive Transformer）在部分场景可能更有优势。
- **仅限视觉任务验证**：未在NLP或音频等其他序列领域检验，领域迁移效果未知。
- **对超长视频的扩展性待验证**：文中最长测试256帧（约8秒@30fps），对于数分钟甚至数小时的视频，当前记忆巩固策略（固定段长度、总记忆量上限）可能需要进一步调整。
- **未提供足够算力细节**：不利于研究复现与成本评估。

（完）
