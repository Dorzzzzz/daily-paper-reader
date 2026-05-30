---
title: A Human-Inspired Reading Agent with Gist Memory of Very Long Contexts
title_zh: 具有要点记忆的人类启发式阅读智能体用于超长上下文
authors: "Kuang-Huei Lee, Xinyun Chen, Hiroki Furuta, John Canny, Ian Fischer"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=OTmcsyEO5G"
tags: ["query:agent-memory"]
score: 9.0
evidence: 提出带有要点记忆的ReadAgent用于长上下文处理
tldr: 现有LLM处理长上下文时存在长度限制和不鲁棒的问题，论文提出ReadAgent系统，受人类阅读启发，将内容分片压缩为要点记忆并在需要时回溯，有效上下文长度提升20倍，为智能体长期记忆架构提供了简洁而有效的设计方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 795, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 794, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 797, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-otmcsyeo5g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 797, \"height\": 263, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 820, \"height\": 793, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 1122, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1700, \"height\": 1022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 693, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 843, \"height\": 99, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1072, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 576, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 632, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1650, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 530, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-otmcsyeo5g/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1697, \"height\": 1014, \"label\": \"Table\"}]"
motivation: LLM无法稳健处理超长输入，且上下文长度受限于模型参数。
method: 通过提示系统实现内容分片、要点记忆压缩和按需回溯。
result: 在多个长文档任务上将有效上下文长度提升20倍。
conclusion: 模拟人类阅读的要点记忆是解决长上下文问题的有效途径。
---

## Abstract
Current Large Language Models (LLMs) are not only limited to some maximum context length, but also are not able to robustly consume long inputs. To address these limitations, we propose ReadAgent, an LLM agent system that increases effective context length up to 20x in our experiments. Inspired by how humans interactively read long documents, we implement ReadAgent as a simple prompting system that uses the advanced language capabilities of LLMs to (1) decide what content to store together in a memory episode, (2) compress those memory episodes into short episodic memories called *gist memories*, and (3) take actions to look up passages in the original text if ReadAgent needs to remind itself of relevant details to complete a task. We evaluate ReadAgent against baselines using retrieval methods, using the original long contexts, and using the gist memories. These evaluations are performed on three long-document reading comprehension tasks: QuALITY, NarrativeQA, and QMSum. ReadAgent outperforms the baselines on all three tasks while extending the effective context window by 3.5-20x.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大型语言模型（LLM）不仅受限于显式的最大上下文长度，而且即便输入未超过该长度，模型在长输入上的性能也会显著下降（如“Lost in the Middle”现象）。这导致LLM在超长文档（如整本书、长对话历史）上的推理能力不足。
- **背景启发**：人类阅读长文本时，会采用“交互式”策略——快速遗忘细节但保留“要点”（gist）信息，并在需要时通过查阅原文恢复细节。这种“模糊要点+按需查找”的机制使人类能高效处理超长上下文。论文受此启发，提出ReadAgent系统。

## 2. 方法论

- **核心思想**：将LLM作为智能体，通过三步提示流程模拟人类阅读：  
  1. **情节分页（Episode Pagination）**：让LLM在阅读过程中自主决定自然断点（如段落切换、场景转换），将连续文本划分为“页”（每一页为一个“记忆情节”）。通过插入编号标签将分页转化为多项选择问题。  
  2. **要点记忆压缩（Memory Gisting）**：对每一页，用LLM提示压缩为简短的“要点”（gist），并标注页码，形成有序的“要点记忆”。与直接总结相比，“缩短”指令更利于保留叙事流。  
  3. **交互式查找（Interactive Lookup）**：给定任务（如问答），模型基于要点记忆决定需要重新阅读哪些原始页。支持两种策略：  
     - **ReadAgent-P**：并行查找多页（一次性请求）。  
     - **ReadAgent-S**：顺序查找（每次请求一页，可看到之前展开的页）。  
  最终将要点与展开的原始页合并，用LLM完成回答。

- **关键公式/算法流程**（文字说明）：  
  - 分页算法：将文档拆分为长度在`min_words`到`max_words`之间的块，每步让LLM选择自然断点。  
  - 压缩率定义：CR = 100 * (1 - 最终查询时上下文中的字数 / 原文总字数)。  
  - 计算开销：分页和压缩的额外推理次数线性正比于文档长度；查找步骤仅基于较短要点，开销较低。

## 3. 实验设计

- **数据集与场景**：  
  - **QuALITY**（多项选择题，平均4.1k词，可全文输入8K窗口）  
  - **NarrativeQA**（自由形式问答，分Gutenberg书籍和电影脚本，平均71k/30k词，远超8K窗口）  
  - **QMSum**（基于会议转录的摘要/问答，平均10k词）  
- **基准方法（Benchmark）**：  
  - 全文输入（当能放入窗口时）  
  - 截断文本（仅开头/结尾6k词）  
  - 检索增强生成（RAG）：BM25、基于Gemini API的神经检索（将查询与页面或要点记忆嵌入点积）  
  - 仅使用要点记忆（GistMem，无查找）  
- **对比方法**：ReadAgent-P和ReadAgent-S的不同查找上限（1~6页），以及消融实验（LLM分页 vs. 均匀长度分页、压缩率权衡等）。  
- **评估指标**：  
  - QuALITY：准确率（chance 25%）  
  - NarrativeQA 和 QMSum：ROUGE-1/2/L F1 和自定义LLM评分（LLM-Rating-1严格匹配、LLM-Rating-2宽松匹配）  
- **基础模型**：主要使用PaLM 2-L（8K上下文），附录中部分实验使用GPT-3.5 Turbo。

## 4. 资源与算力

- **论文未明确说明**使用的GPU型号、数量、训练时长等计算资源。文中仅提及使用PaLM 2-L和GPT-3.5 Turbo进行推理，所有方法均无需模型训练（zero-shot提示）。因此无法报告具体的算力开销。但可推断：由于涉及多次推理（分页、压缩、查找、回答），总体推理令牌数比单次全文处理多，但通过压缩率可节省后续多任务处理时的总令牌数。

## 5. 实验数量与充分性

- **总体实验组数**：  
  - 3个主数据集，每个数据集包含多个子集（如NarrativeQA分Gutenberg和Movie的验证/测试集），共约10个评测子集。  
  - ReadAgent-P和ReadAgent-S各有6种查找上限配置（1~6页），加上8种基线方法（全文、截断、BM25 top-k、神经检索 top-k、GistMem）。  
  - 消融实验：LLM分页 vs. 均匀长度分页（表5）、压缩率权衡（表6）、检索质量对比（表4）、GPT-3.5验证（附录B）、Web导航适应性实验（附录E）。  
- **充分性与公平性**：  
  - 实验覆盖了长文档的多种任务类型（多项选择、自由形式QA、摘要）。  
  - 基线设置合理，包含传统检索（BM25、神经检索）和简化版（仅要点记忆）。  
  - 实验进行了多次运行（通常3次）并报告标准差，表明结果可靠。  
  - 但是：  
    - 未与当时最新的长上下文模型（如GPT-4-128k、Claude-100k）直接比较（仅使用参数量较小的PaLM 2-L）。  
    - 未在不同大小或家族的其他模型上充分验证泛化性（仅附录GPT-3.5一个模型）。  
    - 消融实验主要在QuALITY上进行，其他数据集消融不足。

## 6. 主要结论与发现

- ReadAgent在所有三个长文档任务上优于所有基线方法。  
  - 在NarrativeQA Gutenberg测试集上，有效上下文长度提升约20倍，LLM评分+12.97%，ROUGE-L+31.98%（对比最佳检索基线）。  
  - 在QuALITY上，ReadAgent-S（1-6页）准确率87.17%，超过满文本输入（85.83%），压缩率58.53%（约3.5×可放更多令牌）。  
  - 在QMSum上，ReadAgent-S的LLM-Rating-2达91.54%，优于所有检索和仅要点方法。  
- LLM能够生成有用且紧凑的要点记忆（压缩率85%~97%），并可通过交互式查找进一步提升性能。  
- 顺序查找（ReadAgent-S）在非结构化文本（会议记录）上优势明显，并行查找（ReadAgent-P）在更结构化文档上效果接近。  
- 计算效率：在QuALITY上，使用ReadAgent共减少20.4%的总处理字数（对比全文），且多任务时节省更为显著。

## 7. 优点

- **方法简洁有效**：完全通过提示实现，无需模型微调或架构修改，可即插即用。  
- **创新性启发**：从人类认知理论（模糊痕迹理论）出发，提出“要点记忆+交互查找”范式，区别于传统RAG的固定检索策略。  
- **广泛的实验验证**：在多个长文档基准上取得一致优势，包括多项选择、自由问答和摘要任务。  
- **消融和分析深入**：包括分页策略对比、压缩率-性能权衡、检索质量分析、案例研究等。  
- **良好的扩展性**：可适配Web导航等决策任务（附录E），并支持条件/无条件变体。

## 8. 不足与局限

- **上下文长度仍受限**：虽然有效窗口显著扩展，但要点记忆本身不能无限长，当原文极长时仍可能溢出上下文。  
- **潜在的幻觉风险**：要点记忆省略了细节，若模型需要未被记忆的关键信息，可能自行生成错误内容（论文在Impact Statement中提及）。  
- **计算成本**：迭代推理（分页、压缩、查找）增加了延迟和令牌消耗，在单任务场景下可能不如直接检索高效。  
- **模型依赖与泛化**：主要基于PaLM 2-L，GPT-3.5实验结果较弱，未在其他更大模型（如GPT-4、Claude）上验证。  
- **实验覆盖不全面**：  
  - 未与真正的超长上下文模型（如128k GPT-4）比较。  
  - 消融实验仅在QuALITY上系统进行，NarrativeQA和QMSum上的消融有限。  
  - 对查找策略的探索不够深入（如为什么QMSum上顺序查找优于并行）。  
- **伦理与应用风险**：可能放大LLM的偏见或误导性信息，尤其是在医疗、法律等高风险领域的不当使用。

（完）
