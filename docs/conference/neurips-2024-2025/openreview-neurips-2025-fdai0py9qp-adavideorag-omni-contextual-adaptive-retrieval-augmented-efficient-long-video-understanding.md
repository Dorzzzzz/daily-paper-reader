---
title: "AdaVideoRAG: Omni-Contextual Adaptive Retrieval-Augmented Efficient Long Video Understanding"
title_zh: AdaVideoRAG：全上下文自适应检索增强的高效长视频理解
authors: "Zhucun Xue, Jiangning Zhang, Xurong Xie, yuxuan cai, Yong Liu, Xiangtai Li, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FDAI0PY9Qp"
tags: ["query:long-video"]
score: 9.0
evidence: 自适应检索增强生成用于长视频理解
tldr: 该论文针对长视频理解中固定RAG模式导致冗余或信息丢失的问题，提出自适应RAG框架AdaVideoRAG，根据查询难度动态选择检索结构（简单查询用轻量级检索，复杂查询用图遍历），从而在保证准确性的同时大幅降低延迟。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 667, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1336, \"height\": 184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 84, \"height\": 77, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1339, \"height\": 182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1340, \"height\": 171, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1156, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fdai0py9qp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1010, \"height\": 149, \"label\": \"Table\"}]"
motivation: 现有RAG方案对视频查询采用统一结构，导致效率与准确性失衡。
method: 根据查询复杂度自适应选择检索路径（轻量或全局图遍历）。
result: 在多个长视频基准上取得高性能与低延迟。
conclusion: 自适应检索是平衡长视频理解效率与效果的有效策略。
---

## Abstract
Multimodal Large Language Models (MLLMs) have demonstrated excellent performance in video understanding but suffer from degraded effectiveness when processing long videos due to fixed-length contexts and weaknesses in modeling long-term dependencies. Retrieval-Augmented Generation (RAG) technology can mitigate these limitations through dynamic knowledge expansion, but existing RAG schemes for video understanding employ fixed retrieval paradigms that use uniform structures regardless of input query difficulty. This introduces redundant computational overhead and latency (*e.g.*, complex graph traversal operations) for simple queries (*e.g.*, frame-level object recognition) while potentially causing critical information loss due to insufficient retrieval granularity for multi-hop reasoning. Such single-step retrieval mechanisms severely constrain the model's balance between resource efficiency and cognitive depth. 
To address this, we first propose a novel AdaVideoRAG framework for long-video understanding, which uses a lightweight intent classifier to dynamically and adaptively allocate appropriate retrieval schemes, ranging from the simplest to the most sophisticated, for different video understanding tasks based on query complexity. We introduce an Omni-Knowledge Indexing module to extract valuable information from multi-modal signals for context modeling and build corresponding databases, *i.e.*, a text base from clip captions, ASR, and OCR; a visual base; and a graph for deep semantic understanding. This enables hierarchical knowledge access, integration, and generation from naive retrieval to graph retrieval, achieving an optimal balance between resource consumption and video understanding capabilities.  
Finally, we construct the HiVU benchmark for deep understanding evaluation. Extensive experiments show that our framework enhances the overall efficiency and accuracy of Video-QA for long videos and can be seamlessly integrated with existing MLLMs via lightweight API calls, establishing a new paradigm for adaptive retrieval augmentation in video analysis.

---

## 论文详细总结（自动生成）

# 论文《AdaVideoRAG: Omni-Contextual Adaptive Retrieval-Augmented Efficient Long Video Understanding》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：多模态大语言模型（MLLMs）在视频理解中表现出色，但处理长视频时因固定长度的上下文窗口和长期依赖建模能力不足而导致性能下降。检索增强生成（RAG）通过动态知识扩展可缓解这些局限，但现有视频RAG方案采用**固定检索范式**，对输入查询无论难度均使用统一结构（如复杂图遍历），导致：
  - 简单查询（如帧级物体识别）产生冗余计算开销和延迟；
  - 多跳推理等复杂查询因检索粒度不足而造成关键信息丢失。
- **核心目标**：设计一种能根据查询复杂度**动态自适应**分配检索策略的框架，在资源消耗与视频理解能力之间取得最优平衡。
- **整体意义**：提出了自适应检索增强的新范式，可无缝集成到现有MLLMs中，显著提升长视频问答的效率和准确性。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 2.1 整体框架

AdaVideoRAG包含四个部分：查询意图分类、全知识索引、自适应检索范式、集成与生成。

### 2.2 查询意图分类

- 使用轻量级大语言模型（Qwen2.5-7B）结合CoT推理对用户查询进行三级难度分类：
  - **Level-1（直接推理）**：问题基本不涉及逻辑关系，答案直接在视频内容中提供（如“第5秒出现的人穿什么颜色衣服”）。直接使用MLLM回答，无需检索。
  - **Level-2（简单推理）**：涉及单步时空/因果推理（如“为什么女人在下雨场景前哭了”）。采用朴素检索（naive retrieval）。
  - **Level-3（困难推理）**：需从长上下文中提取不同主体和关系，构建知识图谱进行多跳推理（如“这部电影传达了哪些人生道理”）。采用图检索（graph retrieval）。
- 分类过程：`L = LLM_intent(Q, prompt_intent)`，耗时占比极低（平均≤5%）。

### 2.3 全知识索引（Omni-Knowledge Indexing）

对长视频按固定间隔（30秒/段）分段，每段均匀采样5帧，提取三类辅助文本：
- **剪辑字幕（TC）**：使用MiniCPM-V生成细粒度文本描述 → 构建字幕数据库DC。
- **ASR文本（TA）**：使用FastWhisper将音频转为文本 → ASR数据库DA。
- **OCR文本（TO）**：使用EASYOCR提取帧内字符 → OCR数据库DO。
- **知识图谱**：针对Level-3，基于TC、TA、TO使用BGE-M3提取实体和关系，构建图结构。
- **视觉库（Vision-Base）**：使用ImageBind图像编码器提取关键帧特征，实现跨模态语义对齐。

### 2.4 自适应检索范式

- **Level-1**：不检索，直接将查询和完整视频输入MLLM。
- **Level-2（朴素检索）**：
  - 将原始查询改写为适用于不同模态的子查询（剪辑字幕、ASR、OCR）。
  - 通过跨模态相似度计算定位相关候选内容。
  - 复用改写后的剪辑字幕作为语义锚点，利用ImageBind计算文本与视觉嵌入的余弦相似度，筛选相似度>0.5的片段，保留Top-K视觉证据。
  - 合并辅助文本检索和视觉特征检索的结果形成证据池。
- **Level-3（图检索）**：
  - 基于Light-RAG，使用改写后的剪辑字幕与实体/关系描述计算相似度，返回最相关的实体和关系。
  - 在图内检索与这些实体/关系关联的其他信息，形成以查询为中心的思维图。
  - 将检索到的视频片段与图检索结果叠加，构成多层次证据池。
- **过滤与排序**：去重、利用小规模LLM（Qwen2.5-7B）细粒度过滤无关结果，并按原始视频时间顺序重排以保留时序因果关系。

### 2.5 集成与生成

根据难度级别将检索到的上下文（文本、视频片段、图信息）与查询一同输入MLLM，生成最终回答R。

## 3. 实验设计

### 3.1 使用的数据集/场景

- **HiVU（自建）**：120个长视频（总时长60小时），覆盖知识教育、信息、娱乐三大领域，包含三级难度查询。
- **Video-MME**：900个视频（11秒至1小时），2700个多选题，覆盖6大视觉领域、30个子领域。
- **MLVU**：多任务长视频理解基准，平均时长12分钟，含9种任务。

### 3.2 对比方法

- 基线MLLMs：Video-LLaVA (7B)、Qwen2.5-VL (7B/72B)、VideoLLaMA3 (7B)，以及GPT-4o、Video-LLaVA。
- 对比RAG方法：VideoRAG [32]（固定检索）。
- 消融实验：移除图检索、视觉检索、文本检索；不同分类器精度对比。

### 3.3 实验内容

- **Table 1**：在MLVU_test上，AdaVideoRAG显著提升各MLLM的准确率（如Qwen2.5-VL-7B提升近40%，VideoLLaMA3提升11.6%，甚至与GPT-4o可比）。
- **Table 2**：在Video-MME上，AdaVideoRAG优于VideoRAG [32]（Qwen2.5-VL-7B + AdaVideoRAG总体59.9% vs. 55.0%）。
- **Table 3**：LLM仲裁器选择实验，DeepSeek-32B效果最好。
- **Table 4**：在HiVU上，AdaVideoRAG在Level-3任务优势明显，整体胜率69.42% vs. 30.58%。
- **Table 5**：消融实验表明各模块（图、视觉、文本）均有效。
- **Table 6**：不同分类器性能对比，Qwen2.5-7B最佳（精度0.81，总体得分68.5）。
- **效率分析**：数据库构建时间（Level-2: 351s, Level-3: 412s）；单进程推理时间（Level-1: 8s, Level-2: 26s, Level-3: 27s，AdaVideoRAG平均20s）；多进程/多GPU可加速。

## 4. 资源与算力

- **明确信息**：
  - 分类器使用Qwen2.5-7B（轻量级）。
  - 效率分析中提及单张H20 GPU（96GB）。
  - 多进程实验中采用单GPU双进程（~2×加速），以及8 GPU（~8×加速）。
- **未说明**：
  - 训练MLLM的算力需求（论文中使用的是预训练模型，未重新训练）。
  - 数据库构建和推理的具体GPU型号、数量及总耗时（仅给出平均值）。
  - 消融实验的算力开销。

## 5. 实验数量与充分性

- **实验数量**：包含6个主要表格（Table 1~6）及效率分析，覆盖多个基准、多种模型、多种消融场景。
- **充分性**：
  - **多基准**：HiVU（自建）、Video-MME、MLVU，覆盖短/中/长视频。
  - **多模型**：不同参数量（7B~72B）和架构的MLLMs，包含开源和闭源。
  - **多消融**：分类器精度、检索组件（图/视觉/文本）、难度级别路由。
  - **公平性**：使用相同的输入帧数和采样策略，与VideoRAG [32]在同一设置下对比。
- **评价**：实验设计较为全面，验证了方法的通用性和有效性。但在HiVU上仅对比了VideoLLaMA3，缺少更多模型在该基准上的结果。

## 6. 主要结论与发现

1. **自适应检索显著提升长视频理解能力**：在MLVU、Video-MME、HiVU上，AdaVideoRAG均优于固定检索方法和纯MLLM基线。
2. **效率与精度平衡**：简单查询避免不必要的检索（如Level-1仅8秒），复杂查询通过图检索保证准确性，整体平均响应时间20秒（单H20）。
3. **全知识索引有效性**：联合使用字幕、ASR、OCR和视觉特征可提供更丰富的上下文，消融实验证明各组件贡献。
4. **HiVU基准价值**：三级难度划分能有效区分模型推理能力，L3任务中AdaVideoRAG优势更显著。
5. **通用性**：可无缝集成到多种开源MLLMs（如Video-LLaVA、Qwen2.5-VL、VideoLLaMA3），无需微调。

## 7. 优点

- **自适应路由**：创新性地将查询复杂度引入RAG，避免了“一刀切”的低效或信息缺失。
- **多模态全知识索引**：融合字幕、ASR、OCR、视觉特征和知识图谱，提升检索语义精确度。
- **轻量高效**：使用7B分类器，检索组件可并行加速，总开销可控。
- **新基准HiVU**：覆盖长视频、三级难度、多领域，填补了现有基准在复杂推理评估上的空白。
- **与现有MLLMs兼容**：通过API调用即可集成，无需重新训练。
- **消融分析全面**：清晰展示了各模块贡献，验证了设计合理性。

## 8. 不足与局限

- **计算资源限制**：仅评估到32B参数模型，更大模型（如72B以上）的表现未充分探讨。
- **路由层级**：仅实现三级，实际应用可能需要更细粒度分类（如四级或连续难度）。
- **HiVU规模**：仅120个视频，60小时，领域覆盖可进一步扩展（如技术教程、医学视频等）。
- **评估指标**：采用LLM作为仲裁器（Win-Rate），可能存在评估偏差；未使用人类评估或传统指标（如ROUGE、BLEU）。
- **社会风险**：可能用于生成虚假信息或操纵舆论，论文虽提及但未提供具体缓解措施。
- **数据库构建时间**：Level-3需412秒（单GPU），虽然可并行化但在实时场景中仍可能成为瓶颈。
- **未与其他RAG变体对比**：仅与VideoRAG [32]对比，未对比如Wiki-LLaVA、Corrective RAG等更复杂的RAG方法。

（完）
