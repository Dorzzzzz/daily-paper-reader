---
title: "From RAG to Memory: Non-Parametric Continual Learning for Large Language Models"
title_zh: 从RAG到记忆：面向大型语言模型的非参数持续学习
authors: "Bernal Jiménez Gutiérrez, Yiheng Shu, Weijian Qi, Sizhe Zhou, Yu Su"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LWH8yn4HS2"
tags: ["query:agent-memory"]
score: 8.0
evidence: 解决LLM长期记忆问题，从RAG转向记忆机制
tldr: 现有RAG方法依赖向量检索，难以模拟人类长期记忆的动态互联性，论文提出非参数持续学习框架，在保持事实记忆能力的同时增强关联性，为智能体长期记忆系统设计提供了超越RAG的新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1756, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwh8yn4hs2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 694, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1380, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 787, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 785, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1773, \"height\": 1128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 505, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwh8yn4hs2/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 895, \"height\": 424, \"label\": \"Table\"}]"
motivation: RAG在模拟人类长期记忆的动态性和关联性方面存在不足。
method: 提出非参数持续学习框架，结合结构化知识增强关联记忆。
result: 在事实记忆任务上性能超过标准RAG，同时保持关联性。
conclusion: 非参数方法是构建类人长期记忆的有效途径。
---

## Abstract
Our ability to continuously acquire, organize, and leverage knowledge is a key feature of human intelligence that AI systems must approximate to unlock their full potential. Given the challenges in continual learning with large language models (LLMs), retrieval-augmented generation (RAG) has become the dominant way to introduce new information. However, its reliance on vector retrieval hinders its ability to mimic the dynamic and interconnected nature of human long-term memory. Recent RAG approaches augment vector
embeddings with various structures like knowledge graphs to address some of these gaps, namely sense-making and associativity. However, their performance on more basic factual memory tasks drops considerably below standard RAG. We address this unintended deterioration and propose HippoRAG 2, a framework that outperforms standard RAG comprehensively on factual, sense-making, and associative memory tasks. HippoRAG 2 builds upon the Personalized PageRank algorithm used in HippoRAG and enhances it with deeper passage integration and more effective online use of an LLM. This combination pushes this RAG system closer to the effectiveness of human long-term memory, achieving a 7% improvement in associative memory tasks over the state-of-the-art embedding model while also exhibiting superior factual knowledge and sense-making memory capabilities. This work paves the way for non-parametric continual learning for LLMs. Code and data are available at https://github.com/OSU-NLP-Group/HippoRAG.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：大型语言模型（LLM）在持续学习（continual learning）中面临参数化知识难以更新和灾难性遗忘的问题。检索增强生成（RAG）成为非参数化持续学习的主流方案，但标准RAG依赖向量检索，无法模拟人类长期记忆的两项关键能力：**意义建构（sense-making）**——理解长篇幅、复杂或不明确语境；**关联性（associativity）**——在多段分散知识之间进行多跳推理。现有结构增强型RAG方法（如HippoRAG、RAPTOR、GraphRAG、LightRAG）虽然在这两项能力上有所提升，但在基础事实记忆任务上反而低于标准RAG。
- **整体含义**：本文旨在打破“顾此失彼”的局面，提出HippoRAG 2，使得RAG系统在事实记忆、意义建构和关联性三个方面均优于标准RAG，向类人长期记忆迈进一步，为非参数持续学习开辟新路径。

### 2. 论文提出的方法论

- **核心思想**：基于HippoRAG的神经生物学启发框架（LLM作为新皮层、知识图谱和PageRank作为海马体、检索编码器作为旁海马区），针对其上下文丢失和语义匹配困难进行改进，实现概念与语境的深度融合。
- **关键技术细节**：
    - **稠密-稀疏整合（Dense-Sparse Integration）**：在知识图谱中同时引入短语节点（稀疏编码，代表概念）和段落节点（稠密编码，代表上下文），通过“contains”边连接，使图谱同时保留概念和语境信息。
    - **更深的上下文化（Deeper Contextualization）**：将查询直接与图谱中的三元组而非仅与实体进行匹配（Query-to-Triple），利用三元组包含的关系上下文更全面地理解查询意图。
    - **识别记忆（Recognition Memory）**：先通过嵌入模型检索top-k三元组，再用LLM过滤不相关的三元组，模拟人类记忆的“回忆+再认”两阶段过程。
    - **在线检索流程**：使用过滤后的三元组中的短语节点和所有段落节点作为PageRank的种子节点，并分配不同的重置概率（短语节点按平均排名得分，段落节点按嵌入相似度乘以权重因子0.05），执行个性化PageRank（PPR）算法，依据节点PageRank得分排序段落用于QA。
- **算法流程（文字说明）**：
    - 离线索引：LLM提取三元组 → 构建知识图谱（短语节点+段落节点） → 嵌入模型检测同义词并添加边。
    - 在线检索：查询 → 嵌入模型获取相关三元组 → LLM过滤 → 提取短语节点 + 所有段落节点作为种子 → 分配重置概率 → PPR搜索 → 返回top段落 → LLM生成答案。

### 3. 实验设计

- **数据集**：
    - **简单QA（事实记忆）**：NaturalQuestions（NQ, 1000 queries）、PopQA（1000 queries）。
    - **多跳QA（关联性）**：MuSiQue（1000）、2WikiMultihopQA（1000）、HotpotQA（1000）、LV-Eval（124，减少知识泄露）。
    - **话语理解（意义建构）**：NarrativeQA（293 queries，基于10部长篇故事）。
- **基准对比**：
    - 简单基线：BM25、Contriever、GTR（T5-base）。
    - 大型嵌入模型：GTE-Qwen2-7B-Instruct、GritLM-7B、NV-Embed-v2（7B）。
    - 结构增强型RAG：RAPTOR、GraphRAG、LightRAG、HippoRAG（均使用相同LLM和检索器复现）。
- **评估指标**：段落Recall@5（检索）、精确匹配（EM）和F1（QA）。使用Llama-3.3-70B-Instruct和GPT-4o-mini作为QA阅读器。

### 4. 资源与算力

- 论文附录F明确说明：运行Llama-3.3-70B-Instruct时使用4块NVIDIA H100 GPU，采用张量并行（vLLM）。
- 索引时间：对于MuSiQue语料（11,656段落），HippoRAG 2约99.5分钟；NV-Embed-v2约12.1分钟；RAPTOR约100.5分钟；LightRAG约235分钟；GraphRAG约277分钟；HippoRAG约57.5分钟。
- QA每查询耗时：HippoRAG 2约1.2秒；NV-Embed-v2约0.3秒；RAPTOR约0.6秒；LightRAG约13.3秒；GraphRAG约10.7秒；HippoRAG约0.9秒。
- QA GPU内存：HippoRAG 2约9.9 GB；NV-Embed-v2约1.7 GB；LightRAG约4.5 GB；GraphRAG约3.7 GB；HippoRAG约6.0 GB。

### 5. 实验数量与充分性

- **实验组数**：
    - 主实验：在7个数据集上对比了11种方法（包括多个大型嵌入模型和结构增强方法），使用两种QA阅读器（Llama-3.3-70B-Instruct和GPT-4o-mini），报告了EM/F1和Recall。
    - 消融实验：包括三种链接方式（NER-to-Node、Query-to-Node、Query-to-Triple）、是否使用段落节点、是否使用三元组过滤，共6组对比（表4）。
    - 超参数实验：重置概率权重因子0.01~0.5的调优（表5）。
    - 鲁棒性实验：不同密集检索器（GTE-Qwen2、GritLM、NV-Embed-v2）下HippoRAG 2的表现（表7）。
    - 持续学习模拟实验：将NQ和MuSiQue分为4段，逐步添加新数据，观察性能变化（图3）。
    - 定性分析（表6）和错误分析（100个样本，附录E）。
- **充分性与公平性**：实验覆盖事实、多跳、长文本三类任务，对比方法均使用相同LLM和检索器复现，采用统计显著性检验（p<0.05）；但消融实验仅在一个指标（Recall@5）上报告，QA任务上的消融效果未展示；持续学习实验仅分析两种方法（HippoRAG 2 vs NV-Embed-v2），对比不够广泛。

### 6. 论文的主要结论与发现

- HippoRAG 2在所有三类基准任务上均优于标准RAG（NV-Embed-v2）和其他结构增强方法，平均F1在简单QA上63.3 vs 61.9，多跳QA上提升显著（如2Wiki 71.0 vs 61.5），话语理解上25.9 vs 25.7。
- 在持续学习实验（语料不断扩展）中，HippoRAG 2相对NV-Embed-v2的改进保持稳定。
- 方法对不同的密集检索器具有鲁棒性（表7）。
- 消融实验验证了Query-to-Triple链接、段落节点引入和三元组过滤均有效提升检索性能。

### 7. 优点

- **全面超越**：首次在事实、意义建构和关联性三个维度上同时超越标准RAG，克服了之前结构增强方法顾此失彼的问题。
- **神经科学启发**：将稠密-稀疏编码、识别记忆等认知机制融入RAG设计，理论依据扎实。
- **开放源码与可复现**：代码和数据集公开，使用开源LLM（Llama-3.3-70B）即可复现，降低门槛。
- **效率可接受**：虽然索引和查询时间、GPU内存高于标准RAG，但远低于GraphRAG和LightRAG，性能提升带来的收益大于额外开销。

### 8. 不足与局限

- **实验覆盖不均衡**：话语理解任务仅使用NarrativeQA（仅293 queries），且方法在该任务上的提升幅度较小（25.9 vs 25.7），统计显著性存疑。
- **消融实验不完整**：消融研究仅报告检索Recall@5，未在QA F1上进行验证；仅使用一个数据集（MuSiQue/2Wiki等混合），未在所有数据集上做完整消融。
- **大规模语料扩展性未全面测试**：仅模拟了4段增量，未测试更长期或无限扩展场景；对超大规模语料（百万级）的索引开销未充分讨论。
- **依赖LLM的质量**：三元组过滤依赖LLM的判别能力，实验使用70B模型，但更小模型或更高延迟场景下的表现未知。
- **与其他持续学习方法对比不足**：仅与RAG类方法对比，未与模型编辑（model editing）或持续微调进行比较，无法定位非参数方法的相对优势。
- **偏差风险**：所有数据集均来自英文维基百科（除LV-Eval外），可能存在知识分布偏差，对非英语或特定领域泛化性未知。

（完）
