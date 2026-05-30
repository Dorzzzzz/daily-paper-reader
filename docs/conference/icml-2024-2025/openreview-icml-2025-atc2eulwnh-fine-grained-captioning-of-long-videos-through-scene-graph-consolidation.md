---
title: Fine-Grained Captioning of Long Videos through Scene Graph Consolidation
title_zh: 通过场景图聚合实现长视频的细粒度字幕生成
authors: "Sanghyeok Chu, Seonguk Seo, Bohyung Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=aTC2euLwnh"
tags: ["query:long-video"]
score: 9.0
evidence: 通过场景图聚合实现长视频字幕生成
tldr: 现有视觉语言模型因时间感受野有限，难以生成长视频的连贯详细描述。本文提出基于场景图聚合的长视频字幕生成框架，先分割视频并用现成模型生成片段字幕，再通过场景图逐步合并与精炼整合跨片段信息，无需监督微调即可输出全局连贯的字幕。在多个长视频基准上，该方法在BLEU、ROUGE等指标上显著超越基线，且计算开销低，为长视频理解提供了高效实用的新方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1742, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 866, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1771, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1670, \"height\": 2264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 867, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 864, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 862, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 865, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 861, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 863, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1685, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1678, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1681, \"height\": 219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atc2eulwnh/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1681, \"height\": 223, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1795, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1789, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1764, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 823, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atc2eulwnh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1759, \"height\": 873, \"label\": \"Table\"}]"
motivation: 现有模型受限于时间感受野，无法生成长视频的连贯详细字幕。
method: 先生成片段字幕，再通过场景图聚合与精炼获得全局连贯的长视频字幕。
result: 在长视频数据集上字幕质量优于现有方法，且无需监督训练。
conclusion: 场景图聚合是一种高效且有效的长视频字幕生成策略。
---

## Abstract
Recent advances in vision-language models have led to impressive progress in caption generation for images and short video clips. However, these models remain constrained by their limited temporal receptive fields, making it difficult to produce
coherent and comprehensive captions for long videos. While several methods have been proposed to aggregate information across video segments, they often rely on supervised fine-tuning or incur significant computational overhead. To address these challenges, we introduce a novel framework for long video captioning based on graph consolidation. Our approach first generates segment-level captions, corresponding to individual frames or short video intervals, using off-the-shelf visual captioning models. These captions are then parsed into individual scene graphs, which are subsequently consolidated into a unified graph representation that preserves both holistic context and fine-grained details throughout the video. A lightweight graph-to-text decoder then produces the final video-level caption. This framework effectively extends the temporal understanding capabilities of existing models without requiring any additional fine-tuning on long video datasets. Experimental results show that our method significantly outperforms existing LLM-based consolidation approaches, achieving strong zero-shot performance while substantially reducing computational costs.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

现有视觉‑语言模型（VLM）在图像和短视频的字幕生成上已取得显著进步，但其时间感受野有限，无法有效地对长视频（如数分钟甚至更长）生成连贯、全面的描述。已有的跨段信息聚合方法（如记忆式、递归式）大多依赖在目标数据集上的监督微调，泛化能力差；而基于大语言模型（LLM）的摘要方法虽无需微调，但计算开销高、推理慢。为此，本文提出一种**基于场景图聚合（Scene Graph Consolidation）** 的长视频零样本字幕生成框架，利用现成 VLM 生成片段级字幕，再通过图结构建模实现跨段信息的无损整合，最终由轻量级图‑到‑文本解码器输出全局字幕，无需对长视频进行任何监督训练，同时大幅降低计算成本。

## 2. 论文提出的方法论

**核心思想**：将长视频分割为多个片段，对每个片段生成字幕，解析为场景图；通过逐步合并这些场景图得到全局统一图结构，保留细节与上下文；再用图‑到‑文本模型生成视频级字幕。

**关键技术细节**：
1. **片段级字幕生成**：用现成 VLM（如 BLIP、BLIP2、InternVL2.5）为每个帧或短视频片段生成描述性句子。
2. **场景图解析**：用 FACTUAL‑MR 解析器将每段字幕转换为场景图 \(G=(O,E)\)，其中 \(O\) 是对象（含类别 \(c_i\) 和属性集 \(A_i\)），\(E\) 是有向关系边（标签 \(r_{i,j}\)）。
3. **场景图合并**（Algorithm 1）：
   - 使用图编码器 \(\phi(\cdot)\) 获得每个图的对象嵌入。
   - 对两个图 \(G_s, G_t\)，用匈牙利算法（基于对象嵌入余弦相似度）寻找最优匹配 \(\pi^*\)。
   - 保留相似度超过阈值 \(\tau\) 的匹配对，合并对象类标签和属性集，更新边。
   - 迭代选择最相似的两个图合并，直至只剩一个统一图 \(G_{\text{video}}\)。
4. **优先子图提取**：在合并过程中跟踪每个节点的合并次数，保留 Top‑\(k\) 高频节点及其子图，过滤次要细节，用于生成更聚焦的字幕。
5. **图‑到‑文本解码**：轻量级模型（235M 参数，编码器基于 BERT‑base + 注意力掩码限制图拓扑，解码器基于 T5‑base 的解码部分）在外部文本语料（约 250 万 caption）上训练，采用下一个 token 预测损失，输入为场景图序列化后的 token 序列，输出全局字幕。

## 3. 实验设计

- **数据集**：
  - **视频字幕**：MSR‑VTT 测试集、MSVD 测试集。
  - **视频段落字幕**：ActivityNet Captions 的 ae‑val 集（含多个事件的较长视频）。
- **基准方法**：
  - **LLM‑based 方法**：VidIL、Video ChatCaptioner，以及直接对片段级字幕做 LLM 摘要的基线（Mistral‑7B、GPT‑4o mini）。
  - **其他零样本方法**：ZeroCap、MAGIC、Tewel et al.、DeCap、C³ 等（在补充实验中）。
- **评价指标**：BLEU‑4、METEOR、CIDEr、BERTScore（P/R/F₁）。

## 4. 资源与算力

论文**未明确说明**训练图‑到‑文本模型所用的 GPU 数量、总训练时长。在推理性能对比（Table 5）中，实验在单张 **NVIDIA A6000 GPU** 上测量了峰值显存和每视频平均推理时间。此外，图‑到‑文本模型规模为 **235M 参数**，训练数据来源于约 250 万条外部图文/视频 caption，训练迭代 **1K 步**（段落字幕任务额外 400 步微调）。

## 5. 实验数量与充分性

- 完成了 **2 类任务（视频字幕、视频段落字幕）** 共 **3 个数据集**的实验。
- 与 **9 种以上** 基线方法（包括使用参考字幕的方法）进行了对比。
- 进行了**超参数消融**：优先子图提取中的 \(k\)（表6）和合并阈值 \(\tau\)（表7）。
- 提供了**计算成本对比**（表5）和**定性案例**（图2、图3 及附录失败案例）。
- 实验设计**较为充分**：对比方法覆盖了主流 LLM‑based 和其他零样本方法，消融实验验证了核心模块的有效性，且在同一套片段级字幕下与 LLM 摘要进行公平对照。不足在于未在更多长视频数据集（如 VATEX、YouCook2）上验证，也未考虑多语言场景。

## 6. 论文的主要结论与发现

- 本文提出的 **SGVC**（Scene Graph‑based Video Captioning）在 **零样本** 视频字幕和段落字幕任务上**显著优于**所有对比的 LLM‑based 方法（包括使用更强商业模型 GPT‑4o mini 的摘要方法）。
- 场景图聚合能**更完整地保留对象身份与关系**，生成更细粒度、更准确的描述，而 LLM 摘要容易出现幻觉或丢失细节。
- SGVC **计算成本极低**（推理时间与显存均低于 LLM 摘要方法），无需任何长视频监督微调。
- 方法**即插即用**，可与不同 VLM 骨干（BLIP、BLIP2、InternVL2.5）兼容，性能随骨干增强而提升。

## 7. 优点（方法或实验设计的亮点）

- **无需监督微调**：在整个流程中无需在长视频数据集上训练，完全零样本。
- **轻量级**：图‑到‑文本模型仅 235M 参数，远小于 7B 级别的 LLM 摘要方法。
- **结构化信息保留**：场景图比纯文本更能显式建模对象、属性与关系，合并策略避免了信息的模糊或丢失。
- **可扩展性**：支持任意 VLM（开源或 API），且图合并算法可独立更换。
- **实验设计公平**：关键对比（表2、表4）与 LLM 摘要使用完全相同的片段级字幕输入，隔离了图聚合 vs. 纯文本聚合的差异。
- **提供了失败案例分析**（附录 C），展现了方法对 VLM 幻觉的敏感性，增加了诚信度。

## 8. 不足与局限

- **依赖片段级字幕质量**：如果初始 VLM 产生幻觉（如数量错误、物体误识别），错误会通过场景图传播到最终字幕（见失败案例）。
- **场景图解析误差**：FACTUAL‑MR 解析器可能遗失部分语义细节或产生不正确的三元组。
- **仅考虑视觉模态**：未利用音频、语音等信息，对需要多模态线索的场景（如对话）覆盖不足。
- **评估指标局限**：n‑gram 指标（BLEU、CIDEr）无法充分衡量语义正确性；BERTScore 虽更好但仍不能检测上下文连贯性或事实性错误。
- **实验覆盖有限**：仅在英文数据集上评测，未在更大型、多样性更高的长视频基准（如 Ego4D、HowTo100M）上验证。
- **子图提取的 \(k\) 值需调参**：最优 \(k\) 随任务和视频内容变化，缺乏自动选择机制。

（完）
