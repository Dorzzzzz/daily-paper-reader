---
title: "A-Mem: Agentic Memory for LLM Agents"
title_zh: A-Mem：面向LLM代理的智能记忆系统
authors: "Wujiang Xu, Zujie Liang, Kai Mei, Hang Gao, Juntao Tan, Yongfeng Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FiM0M8gcct"
tags: ["query:agent-memory"]
score: 10.0
evidence: 面向LLM代理的智能记忆系统，支持动态组织
tldr: 现有LLM代理记忆系统缺乏动态组织能力，本文受卡片盒笔记法启发，提出A-Mem代理记忆系统，通过动态索引和链接创建互联的知识网络。该系统在多种任务上自适应组织记忆，实验表明在工具使用和问题回答等任务中显著提升了代理性能，为智能代理记忆设计提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fim0m8gcct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1292, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fim0m8gcct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fim0m8gcct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1226, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fim0m8gcct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1045, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fim0m8gcct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1290, \"height\": 1357, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1100, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1319, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1026, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 968, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 1029, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fim0m8gcct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1106, \"height\": 284, \"label\": \"Table\"}]"
motivation: 当前LLM代理记忆系统存储检索简单，缺乏动态组织和任务适应性。
method: 基于卡片盒笔记法设计动态索引和链接机制，构建互联知识网络。
result: 在多个代理任务上相比基线方法性能显著提升，记忆组织更灵活。
conclusion: 动态组织记忆是提升LLM代理长期记忆效能的关键方向。
---

## Abstract
While large language model (LLM) agents can effectively use external tools for complex real-world tasks, they require memory systems to leverage historical experiences. Current memory systems enable basic storage and retrieval but lack sophisticated memory organization, despite recent attempts to incorporate graph databases. Moreover, these systems' fixed operations and structures limit their adaptability across diverse tasks. To address this limitation, this paper proposes a novel agentic memory system for LLM agents that can dynamically organize memories in an agentic way. Following the basic principles of the Zettelkasten method, we designed our memory system to create interconnected knowledge networks through dynamic indexing and linking. When a new memory is added, we generate a comprehensive note containing multiple structured attributes, including contextual descriptions, keywords, and tags. The system then analyzes historical memories to identify relevant connections, establishing links where meaningful similarities exist. Additionally, this process enables memory evolution -- as new memories are integrated, they can trigger updates to the contextual representations and attributes of existing historical memories, allowing the memory network to continuously refine its understanding. Our approach combines the structured organization principles of Zettelkasten with the flexibility of agent-driven decision making, allowing for more adaptive and context-aware memory management.
Empirical experiments on six foundation models show superior improvement against existing SOTA baselines. The code is available at \url{https://anonymous.4open.science/r/AgenticMemory-76B4}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：大型语言模型（LLM）代理在执行复杂现实任务时依赖外部工具，但现有记忆系统仅提供基本存储与检索，缺乏对记忆的动态组织和自适应能力。尽管最新尝试引入图数据库，但固定操作和结构限制了跨任务泛化性。
- **核心问题**：如何设计一个灵活、通用的记忆系统，使LLM代理能够在不依赖预定义操作的情况下，长期管理并利用经验。
- **整体含义**：本文提出**A-Mem**（Agentic Memory），受卡片盒笔记法（Zettelkasten）启发，使记忆能够自主生成上下文描述、动态建立链接、并随新经验持续演化，为LLM代理提供更智能、自适应的长期记忆能力。

## 2. 方法论

- **核心思想**：模仿卡片盒笔记法的原子化笔记、灵活链接和知识演化原则，使记忆系统具备“代理性”（Agentic），即记忆本身可以自主决策如何组织与更新。
- **关键技术与流程**：
  1. **Note Construction（笔记构建）**：每当代理与环境交互，LLM基于预设计模板生成结构化记忆笔记，包含：原始内容 `c_i`、时间戳 `t_i`、关键词 `K_i`、标签 `G_i`、上下文描述 `X_i`、嵌入向量 `e_i`、链接集合 `L_i`。嵌入向量由文本编码器（all-minilm-l6-v2）对所有文本组件编码得到。
  2. **Link Generation（链接生成）**：新记忆加入时，先通过余弦相似度从历史记忆中检索top-k最近邻，再由LLM判断是否建立链接，并更新链接集合 `L_i`。公式：`s_{n,j} = (e_n · e_j) / (|e_n||e_j|)`；`M_near = {mj | rank(s_{n,j}) ≤ k}`。
  3. **Memory Evolution（记忆演化）**：对新记忆的最近邻，LLM根据新记忆和邻域信息决定是否更新其上下文、关键词和标签，实现历史记忆的动态调整。
  4. **Retrieve Relative Memory（相对记忆检索）**：交互时，对查询文本编码，检索top-k最相关记忆作为上下文提供给LLM代理。
- **算法流程**：输入交互 → 笔记构建（LLM生成属性） → 嵌入存储 → 链接生成（检索+LLM判断） → 记忆演化（更新邻域） → 交互时检索相关记忆。

## 3. 实验设计

- **数据集**：
  - **LoCoMo**：长程对话数据集，平均9K tokens，最多35轮对话，含5种问题类型（单跳、多跳、时间推理、开放域、对抗性），共7,512个问答对。
  - **DialSim**：多轮多参与者对话QA数据集（源自电视剧），1,300轮，约350K tokens，超过1,000个问题。
- **基准（Baseline）**：LoCoMo、ReadAgent、MemoryBank、MemGPT。
- **评估指标**：F1、BLEU-1（主表）；附录中增加了ROUGE-L、ROUGE-2、METEOR、SBERT相似度。
- **基座模型**：6种：GPT-4o-mini、GPT-4o、Qwen2.5-1.5B、Qwen2.5-3B、Llama3.2-1B、Llama3.2-3B；附录中还测试了DeepSeek-R1-32B、Claude 3.0 Haiku、Claude 3.5 Haiku。
- **对比方式**：所有方法使用相同的系统提示，本地模型通过Ollama部署，结构化输出通过LiteLLM管理；检索时默认k=10（某些类别调优）。

## 4. 资源与算力

- **计算资源**：文中提到使用Ollama本地部署和LiteLLM管理；GPT模型使用官方结构化输出API。未明确给出GPU型号和数量。
- **处理时间**：A-Mem每个记忆操作平均约1,200 tokens，处理时间平均5.4秒（GPT-4o-mini），1.1秒（Llama 3.2 1B在单GPU上）。
- **存储与检索**：扩展性分析显示，从1,000到1,000,000条记忆，A-Mem的检索时间仅从0.31μs增长到3.70μs，内存线性增长且与其他方法相当。
- **成本**：使用商业API时，每次记忆操作成本低于$0.0003。
- **注意**：论文未报告训练算力（因为方法是基于现有LLM的推理式应用，不是训练新模型）。

## 5. 实验数量与充分性

- **实验组数**：
  - 主实验（Table 1）：6个基座模型 × 5种方法 × 5种问题类型，共150项F1/BLEU-1结果。
  - DialSim实验（Table 2）：3种方法在6个指标上对比。
  - 消融实验（Table 3）：移除链接生成和记忆演化模块，在GPT-4o-mini上对比。
  - 超参数分析（Figure 3）：k从10到50对5种任务类型的影响。
  - 扩展性分析（Table 4）：4个存储规模下时间/空间对比。
  - 可视化分析（Figure 4 & Appendix Figure 5）：10个对话的t-SNE。
  - 附录中额外指标（ROUGE、METEOR、SBERT）和额外模型（DeepSeek-R1、Claude）实验。
- **充分性**：实验覆盖广泛，包括不同模型大小、不同任务难度、有效性和效率分析，消融验证各模块贡献。基准选择代表性，评估指标多样。实验结果客观、公平。

## 6. 主要结论与发现

- **性能优势**：A-Mem在所有6个基座模型上均优于所有基线；在多跳推理任务上提升尤为显著（F1提升2倍以上）；在DialSim上F1达3.45，比LoCoMo高35%，比MemGPT高192%。
- **成本效益**：相比LoCoMo和MemGPT（需~16,900 tokens），A-Mem仅需~1,200 tokens，减少85-93% token用量，成本显著降低。
- **记忆组织**：t-SNE可视化显示A-Mem的记忆嵌入聚类更紧凑有序，说明动态链接和演化机制实现了结构化记忆管理。
- **模块贡献**：消融表明链接生成是基础，记忆演化提供进一步优化，两者互补。
- **超参数规律**：检索数k增大性能提升但逐渐饱和，需平衡信息丰富度与噪声。

## 7. 优点

- **创新性**：首次将卡片盒笔记法系统性地引入LLM代理记忆系统，实现记忆的自主组织与演化，摆脱预定义结构。
- **多属性记忆表示**：结合LLM生成的关键词、标签、上下文描述和嵌入向量，丰富记忆语义，便于多角度检索和链接。
- **动态链接与演化**：不仅建立记忆间联系，还能根据新经验更新旧记忆的上下文和标签，模拟人类学习。
- **高性价比**：极低的token消耗和快速响应，适合大规模部署。
- **扩展性强**：检索时间随记忆规模增长极慢（3.70μs/百万条），不影响实际应用。
- **可视化验证**：t-SNE直观展示记忆结构改善，证明方法的有效性。

## 8. 不足与局限

- **LLM依赖性**：记忆组织质量受底层LLM能力影响，不同模型可能产生不同质量的上下文描述和链接判断。
- **单模态限制**：当前仅支持文本交互，未探索图像、音频等多模态信息。
- **未讨论社会影响**：论文仅聚焦技术，未分析潜在偏见、隐私或滥用风险。
- **实验局限性**：主要基于对话QA场景；超参数k的调优未覆盖所有模型组合；部分实验仅使用单一模型进行消融。
- **缺少统计显著性**：因API调用成本，未提供误差条或置信区间，结果可靠性未量化。

（完）
