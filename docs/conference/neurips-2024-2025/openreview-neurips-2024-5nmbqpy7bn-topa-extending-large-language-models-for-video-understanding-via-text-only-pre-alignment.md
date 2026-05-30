---
title: "TOPA: Extending Large Language Models for Video Understanding via Text-Only Pre-Alignment"
title_zh: TOPA：通过仅文本预对齐扩展大语言模型用于视频理解
authors: "Wei Li, Hehe Fan, Yongkang Wong, Mohan Kankanhalli, Yi Yang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=5NMbQPY7Bn"
tags: ["query:long-video"]
score: 6.0
evidence: 仅文本预对齐增强视频理解，可推广至长视频
tldr: 针对视频理解中视频-文本数据不足和语言监督效率低的问题，本文提出仅文本预对齐方法TOPA，利用高级LLM生成文本视频模拟真实视频来预训练模型。该方法无需在真实视频数据上预训练，在多个视频理解任务上取得竞争性结果，为长视频理解提供了一种轻量级扩展思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1292, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 1342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1405, \"height\": 177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1385, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1392, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1394, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1397, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1397, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1401, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 2089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1434, \"height\": 2041, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1407, \"height\": 181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1398, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1384, \"height\": 177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1391, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1372, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1112, \"height\": 797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1158, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-5nmbqpy7bn/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1092, \"height\": 804, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 1094, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 641, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 659, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1354, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 673, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1356, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 962, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-5nmbqpy7bn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 931, \"label\": \"Table\"}]"
motivation: 视频理解受限于视频-文本数据质量和数量，且预训练成本高。
method: 使用LLM生成连续文本帧构成的文本视频及对应标注，在文本域预训练后再迁移到真实视频。
result: 无真实视频预训练下在多个视频理解基准上达到可比或更优性能。
conclusion: 文本预对齐是降低视频模型训练成本的有效策略。
---

## Abstract
Recent advancements in image understanding have benefited from the extensive use of web image-text pairs. However, video understanding remains a challenge despite the availability of substantial web video-text data. This difficulty primarily arises from the inherent complexity of videos and the inefficient language supervision in recent web-collected video-text datasets. In this paper, we introduce Text-Only Pre-Alignment (TOPA), a novel approach to extend large language models (LLMs) for video understanding, without the need for pre-training on real video data. Specifically, we first employ an advanced LLM to automatically generate Textual Videos comprising continuous textual frames, along with corresponding annotations to simulate real video-text data. Then, these annotated textual videos are used to pre-align a language-only LLM with the video modality. To bridge the gap between textual and real videos, we employ the CLIP model as the feature extractor to align image and text modalities. During text-only pre-alignment, the continuous textual frames, encoded as a sequence of CLIP text features, are analogous to continuous CLIP image features, thus aligning the LLM with real video representation. Extensive experiments, including zero-shot evaluation and finetuning on various video understanding tasks, demonstrate that TOPA is an effective and efficient framework for aligning video content with LLMs. In particular, without training on any video data, the TOPA-Llama2-13B model achieves a Top-1 accuracy of 51.0% on the challenging long-form video understanding benchmark, Egoschema. This performance surpasses previous video-text pre-training approaches and proves competitive with recent GPT-3.5 based video agents.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：视频理解面临两大挑战：
  - 视频模态的内在复杂性（空间+时间维度），需要大规模数据和高计算成本。
  - 网络收集的视频-文本数据（如Howto100M、WebVid）存在语言监督效率低下的问题（字幕与视觉不对齐、描述过于简单）。
- **背景**：图像-语言理解已借助大规模图像-文本对取得巨大进展（CLIP、MLLMs），但视频领域即使有大量网络视频-文本数据，仍难以应对长视频理解（如EgoSchema基准）。
- **目标**：探索一种无需真实视频预训练的方法，高效地将大型语言模型（LLM）扩展到视频理解领域。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 利用高级LLM（如Gemini Pro 1.0）自动生成**文本视频（Textual Videos, 简称 Tideo）**——连续文本帧序列及其高质量标注（密集描述、多选问答对），在纯文本域预对齐LLM，然后迁移到真实视频推理。

### 关键技术细节
1. **TextVid数据集生成**：
   - 使用Gemini Pro 1.0 API，以多种条件（Howto100M标题、WebVid字幕、Ego4D场景、WordNet对象）生成721K个Tideo。
   - 每个Tideo包含5-15个文本帧（帧描述+对象描述），以及全局描述和3.5M个问答对。

2. **文本预对齐（Text-Only Pre-Alignment）**：
   - 使用CLIP文本编码器提取每个文本帧的特征 \( f_{ti} = F_{fusion}(E_{text}(C_i), E_{text}(D_{i,j})) \)。
   - 设计三个任务：Tideo摘要、Tideo QA、多选Tideo QA，统一的语言建模损失：
     \[
     L_{LM}(\theta_G, \theta_P) = -\frac{1}{|t|} \sum_{i=1}^{|t|} \log G(t_i | P(V_t), Z, t_{<i})
     \]
   - 训练时冻结CLIP和LLM，仅训练线性投影层和LLama-adapter。

3. **适配真实视频**：
   - **零样本推理**：使用CLIP图像编码器提取真实视频帧特征 \( f_{vi} \)，通过**support memory**（公式2）将CLIP视觉特征投影到文本特征空间，以弥合模态间隙：
     \[
     f_{v\to t} = \sum_{i=1}^{N} \frac{\exp(m_i^\top f_v / \tau)}{\sum_k \exp(m_k^\top f_v / \tau)} \cdot m_i
     \]
   - **监督微调**：在真实视频数据上，直接使用CLIP视觉特征作为输入（无需投影），进一步微调。

## 3. 实验设计

### 数据集与Benchmark
- **零样本多选QA**：EgoSchema（长视频，5000题）、NExT-QA（因果时序推理）、STAR（情景推理）、TVQA、MVBench（20个任务）。
- **微调多选QA**：NExT-QA、STAR、TVQA。
- **零样本视频字幕**：MSR-VTT、VATEX。

### 对比方法
- **Web视频预训练**：FrozenBiLM、InternVideo、LongViViT、MC-ViT-L、InternVideo2。
- **图像MLLM适配**：SeViLA、MVU、IG-VLM。
- **LLM-based视频代理**：LangRepo、Vamos、MoReVQA、LLoVi、VideoAgent、LifelongMemory。
- **纯文本预训练**：DeCap（基线）。
- **自基线**：无文本预对齐的Baseline。

### 主要实验结果
- **零样本EgoSchema**：TOPA-Llama2-13B达51.0%，超越所有Web视频预训练方法，接近GPT-3.5/4视频代理。
- **零样本MVBench**：在高层次理解任务（场景转换、意外动作、动作定位）表现优异，但在细粒度任务（移动方向、动作反义词）较弱。
- **微调**：TOPA在所有数据集上一致提升，较无预对齐基线（Baseline）高出2-9个百分点。
- **数据效率**：仅用10%训练数据即超过Baseline用全部数据时的性能。

## 4. 资源与算力

- **训练硬件**：4块40G A100 GPU。
- **训练时间**：
  - Llama2-7B / Llama3-8B：约1天。
  - Llama2-13B：约2天。
- **冻结策略**：CLIP和LLM主干冻结，仅训练投影层（linear）和LLama-adapter（50个adaptation embedding）。
- **零样本推理**：使用2M CLIP文本特征构建support memory（训练无关）。

## 5. 实验数量与充分性

- **实验组数**：涵盖5大基准、多种任务类型（零样本/微调/字幕/消融），共约10张主表和若干消融图表。
- **消融实验**：包括：
  - 盲测（无视觉输入）分析LLM先验（表6）。
  - 输入帧数的影响（表7）。
  - 多选择题训练任务的作用（表8）。
  - 模态投影（Eq.2）的影响（表9）。
  - 数据效率微调（图3）。
- **充分性**：实验覆盖主流视频理解场景，对比方法类型全面（预训练、MLLM、代理），结果统计指标（Top-1准确率、CIDEr）标准，且多次与公开来源结果对比（标注出处），客观公平。

## 6. 主要结论与发现

1. **仅文本预对齐可有效替代真实视频预训练**：无需任何真实视频数据，即可在长视频理解任务上达到甚至超越千万级视频预训练方法的性能。
2. **高质量语言监督比数据量更重要**：721K文本视频的高质量标注优于百万级网络视频的噪声字幕。
3. **端到端视频-LLM优于代理方法**：TOPA（端到端）在使用相同规模LLM（Llama2-13B）时，显著优于Vamos等代理方法，且不依赖强大闭源LLM（如GPT-4）。
4. **文本预对齐可作为通用预训练阶段**：微调时性能一致提升，且在低数据场景下效果显著。
5. **CLIP模态间隙可通过简单投影（support memory）有效缓解**。

## 7. 优点

- **创新性强**：首次提出“文本视频”概念，仅用文本域预训练实现视频-LLM对齐，极大降低对真实视频数据的需求。
- **高效**：仅需4 GPU * 1~2天训练，即可获得竞争力性能，计算成本远低于传统视频预训练。
- **数据自动生成、可扩展**：利用LLM生成无限量、多样化的高质量语言监督，避免手动标注。
- **框架通用**：支持零样本推理和微调，可用于多种视频任务（QA、字幕、描述）。
- **实验扎实**：在多个基准上全面评估，消融充分，与多种方法公平对比。

## 8. 不足与局限

- **CLIP模态间隙**：文本特征与图像特征仍存在偏差，导致细粒度视觉理解（如物体位置、动作方向、计数）表现欠佳。
- **帧级处理限制**：仅使用10帧关键帧，无法处理高帧率精细动作（如动作计数）。
- **语义细节丢失**：CLIP文本特征无法完全保留图像中的细节（如颜色、空间关系）。
- **依赖强LLM生成数据**：使用Gemini Pro 1.0生成数据，可能引入生成偏差；小模型生成质量可能下降。
- **零样本推理需额外存储**：需要2M support memory，占用一定内存。
- **未在极端长视频（如LVBench）上验证**：仅测试了平均3分钟的EgoSchema，更长的视频可能面临挑战。

（完）
