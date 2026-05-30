---
title: "CAM: A Constructivist View of Agentic Memory for LLM-Based Reading Comprehension"
title_zh: CAM：基于建构主义视角的LLM阅读理解智能体记忆
authors: "Rui Li, Zeyu Zhang, Xiaohe Bo, Zihang Tian, Xu Chen, Quanyu Dai, Zhenhua Dong, Ruiming Tang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ACSOnSHiWe"
tags: ["query:agent-memory"]
score: 9.0
evidence: 为基于LLM的阅读理解设计智能体记忆系统
tldr: 该论文针对大语言模型在处理长文档时信息过载的问题，借鉴皮亚杰建构主义理论，提出了智能体记忆（agentic memory）的系统设计原则：结构化图式、灵活同化和动态顺应。基于此实现了CAM原型，使LLM成为自主阅读智能体。实验证明该记忆模块能显著提升长文档阅读理解性能，为智能体记忆系统设计提供了理论指导和实践方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-acsonshiwe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 537, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-acsonshiwe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1416, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-acsonshiwe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 678, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-acsonshiwe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 671, \"height\": 448, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1021, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1338, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 879, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1305, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-acsonshiwe/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 813, \"height\": 326, \"label\": \"Table\"}]"
motivation: LLM面对长文档时信息过载，缺乏系统的记忆模块来支持自主阅读。
method: 提出建构主义记忆原则（结构化图式、灵活同化、动态顺应），并实现CAM原型。
result: 在阅读理解基准上，CAM使LLM长文档理解准确率显著提升。
conclusion: 建构主义理论为智能体记忆设计提供了有效蓝图，CAM证明了其可行性。
---

## Abstract
Current Large Language Models (LLMs) are confronted with overwhelming information volume when comprehending long-form documents. This challenge raises the imperative of a cohesive memory module, which can elevate vanilla LLMs into autonomous reading agents. Despite the emergence of some heuristic approaches, a systematic design principle remains absent. To fill this void, we draw inspiration from Jean Piaget's Constructivist Theory, illuminating three traits of the agentic memory---structured schemata, flexible assimilation, and dynamic accommodation. This blueprint forges a clear path toward a more robust and efficient memory system for LLM-based reading comprehension. To this end, we develop CAM, a prototype implementation of Constructivist Agentic Memory that simultaneously embodies the structurality, flexibility, and dynamicity. At its core, CAM is endowed with an incremental overlapping clustering algorithm for structured memory development, supporting both coherent hierarchical summarization and online batch integration. During inference, CAM adaptively explores the memory structure to activate query-relevant information for contextual response, akin to the human associative process. Compared to existing approaches, our design demonstrates dual advantages in both performance and efficiency across diverse long-text reading comprehension tasks, including question answering, query-based summarization, and claim verification.

---

## 论文详细总结（自动生成）

# 论文总结：CAM: 一种基于建构主义视角的LLM智能体记忆机制

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：当前大语言模型（LLM）在处理超长文档时面临信息过载，其有限的上下文窗口和难以感知分散在长文本各处的关键信息，导致阅读理解能力不足。现有方法（如MemGPT、RAPTOR、GraphRAG等）虽尝试引入显式记忆模块，但缺乏系统化的设计原则，多停留在启发式模仿人类记忆的层面。
- **整体含义**：该论文认为，一个有效的LLM阅读智能体记忆模块应当具备**结构化图式（structured schemata）**、**灵活同化（flexible assimilation）** 和**动态顺应（dynamic accommodation）** 三大特质。这一蓝图借鉴了皮亚杰的建构主义理论，为设计更鲁棒、高效的记忆系统提供了理论指导，并据此实现原型CAM（Constructivist Agentic Memory），旨在将LLM提升为自主阅读智能体。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：基于建构主义理论，记忆系统应主动将接收到的信息组织成层次化的图式（schemata）。新信息通过同化（灵活地融入多个相关高层抽象）和顺应（动态调整部分结构以适应无法直接融入的信息）两个过程，维持认知平衡，从而实现高效的信息整合、存储与检索。
- **关键技术细节**：
  - **CAM的记忆构建**：采用**增量重叠聚类算法**，分三步实现：
    1. **基础网络扩展**：将新文本块（Vnew）整合到基础语义网络G0中，定义复合相似度函数（结合语义余弦相似度和位置高斯相似度），为每个块连接top-k相关节点。
    2. **以自我为中心的解缠**：对每个节点提取其自我网络（ego-network），将其分解为连通分量，并为每个分量复制该节点，从而显式建模节点可能属于多个高层抽象（灵活同化）。
    3. **在线聚类更新**：在解缠后的副本网络上执行增量标签传播算法，仅更新受影响的节点，然后对修改后的簇进行LLM摘要生成，形成下一层记忆节点。该过程在层次间递归。
  - **记忆检索**：采用**剪枝与增长（Prune-and-Grow）** 策略：
    1. **快速定位**：全局语义匹配选出与查询最相似的top-s节点。
    2. **关联探索**：LLM从候选集中选择有帮助的节点激活，然后扩展其同层邻居和下层子节点，LLM继续从中选择，迭代直到不再增长，最后将所有激活节点送入LLM生成响应。
- **算法流程**（文字说明）：输入文档 → 分块 → 构建基础网络 → 解缠 → 增量聚类 → 生成摘要节点 → 递归构建层次结构 → 检索时先全局匹配再局部关联探索。

## 3. 实验设计：数据集、场景、Benchmark与对比方法

- **数据集与场景**：
  - **单文档场景**：NovelQA（问答，平均200K tokens）、QMSum（查询式摘要，~10K words）、FABLES（声明验证，121K tokens）。
  - **多文档场景**：MultiHop-RAG（问答，609篇文章）、ODSum-Story（摘要，1190篇故事）、ODSum-Meeting（摘要，232篇会议记录）。
- **基准方法**：
  - **无结构记忆**：FullContext（直接截断输入全文）、MemGPT、ReadAgent。
  - **结构化记忆**：RAPTOR、GraphRAG、HippoRAG、MemTree。
- **评估指标**：ROUGE F-Measures（R-1, R-L）、LLM-as-judge准确率（ACC-L）、Exact Match (EM)及F1。
- **公平性保证**：统一使用GPT-4o-mini作为LLM骨干，text-embedding-3-small作为嵌入模型，确保性能差异源于记忆设计。

## 4. 资源与算力

- 论文未明确报告完整实验的总算力消耗。但指出在消融实验中，使用开源LLM（Llama-3.1-8B-Instruct、Qwen2.5-7B-Instruct）时运行在单张NVIDIA A100 GPU上；默认使用GPT-4o-mini（API调用），未说明GPU数量及训练时长。实验中LLM仅用于摘要生成和检索选择，未涉及大规模训练，因此算力需求相对较低。

## 5. 实验数量与充分性

- **实验数量丰富**：覆盖6个数据集（3个单文档+3个多文档）、三类任务（问答、摘要、声明验证）。主实验（Table 2）报告了所有方法的完整指标。另包含：
  - **在线场景效率分析**（Figure 3）：不同batch大小下的插入时间和ACC-L稳定性。
  - **消融与变体分析**（Table 3）：替换LLM骨干、嵌入模型、检索策略、是否使用层次结构、是否使用灵活同化（无解缠）、是否引入细粒度知识建模。
  - **按问题类型分析**（Appendix F）：在NovelQA上按复杂度和语义类别拆解性能。
  - **额外事实型QA测试**（Appendix G）：在HotpotQA、2Wiki、MuSiQue上验证。
- **充分性评价**：实验设计较为全面，对比了多种主流方法，并控制了骨干模型一致，消融实验覆盖关键组件，公平性较好。但缺乏统计显著性检验（如误差线）的说明（仅在Figure 3b中显示稳定性）。整体实验充分，可信度较高。

## 6. 主要结论与发现

- CAM在全部6个基准数据集上均取得最优或次优结果，平均比最佳基线（RAPTOR/GraphRAG）高出约3.0%的指标。
- 结构化记忆（RAPTOR、CAM）明显优于无结构记忆（MemGPT、ReadAgent），证实结构化的重要性。
- 灵活同化（允许节点属于多个簇）是关键：RAPTOR优于严格层次的MemTree，CAM通过解缠实现灵活同化进一步超越RAPTOR。
- 动态顺应（增量更新）使CAM支持batch-level在线处理，效率远高于离线重建方法（如RAPTOR、GraphRAG）和逐块插入的MemTree，且性能稳定。
- 检索策略“Prune-and-Grow”优于纯层次遍历或全局检索。
- CAM对LLM骨干敏感度较低，使用开源模型仍有竞争力；更好的嵌入模型可进一步提升。

## 7. 优点

- **理论驱动**：从皮亚杰建构主义提炼出明确的设计原则（结构化、灵活同化、动态顺应），避免了纯启发式方法。
- **方法创新**：增量重叠聚类算法将同化与顺应统一实现，支持在线batch整合，兼具效率与效果。
- **检索策略高效**：结合全局定位和局部关联探索，仿人类联想记忆，适合长文本、多跳推理。
- **实验全面**：涵盖多种任务、多种基线、消融与变体，并在在线场景下验证了动态性。
- **代码开源**：提供匿名仓库，便于复现。

## 8. 不足与局限

- **应用范围有限**：仅针对文本阅读理解，未扩展到行为规划、长序列生成、多模态任务。
- **缺乏主动行为**：记忆系统仅被动响应查询，未引入自我提问、反思等更高级的智能体行为。
- **幻觉传播风险**：LLM生成的摘要可能包含幻觉，且会沿层次向上传播，影响可靠性。
- **假设信息一致性**：未处理多源文档中的矛盾信息，实际场景需专门的冲突检测与调和机制。
- **手动超参数**：聚类阈值、相似度权重等需手动调整，缺乏自适应或学习机制。
- **未报告统计显著性**：除Figure 3b外，未提供误差线或置信区间，对结果随机性的考量不足。
- **计算成本分析不完整**：仅给出在线/离线插入时间对比，未详细报告总实验算力消耗及单次推理延迟。

（完）
