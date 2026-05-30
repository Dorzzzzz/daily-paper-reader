---
title: "G-Memory: Tracing Hierarchical Memory for Multi-Agent Systems"
title_zh: G-Memory：多智能体系统的层次化记忆追踪
authors: "Guibin Zhang, Muxin Fu, Kun Wang, Guancheng Wan, Miao Yu, Shuicheng YAN"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mmIAp3cVS0"
tags: ["query:agent-memory"]
score: 9.0
evidence: 面向多智能体系统的层次化记忆系统
tldr: 当前多智能体系统的记忆机制过于简单，缺乏对协作轨迹的细粒度记录和跨试验定制。G-Memory受组织记忆理论启发，提出三层图记忆架构，管理长程多智能体交互，显著提升智能体的自演化能力。实验验证了其在复杂任务上的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1029, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1421, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 1275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 632, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1465, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 625, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1020, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 988, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mmiap3cvs0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1045, \"height\": 749, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mmiap3cvs0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 984, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mmiap3cvs0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 403, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mmiap3cvs0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 1162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mmiap3cvs0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 966, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mmiap3cvs0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1202, \"height\": 549, \"label\": \"Table\"}]"
motivation: 现有LLM多智能体系统记忆架构过于简单，忽略了智能体间的协作轨迹和个性化需求。
method: 提出G-Memory，一种基于组织记忆理论的层次化图记忆系统，通过三层管理长程多智能体交互。
result: 实验表明G-Memory能有效提升多智能体系统的自演化能力和任务执行效率。
conclusion: 层次化记忆是增强多智能体系统长期协作和进化的关键。
---

## Abstract
Large language model (LLM)-powered multi-agent systems (MAS) have demonstrated cognitive and execution capabilities that far exceed those of single LLM agents, yet their capacity for self-evolution remains hampered by underdeveloped memory architectures. Upon close inspection, we are alarmed to discover that prevailing MAS memory mechanisms (1) are overly simplistic, completely disregarding the nuanced inter-agent collaboration trajectories, and (2) lack cross-trial and agent-specific customization, in stark contrast to the expressive memory developed for single agents. To bridge this gap, we introduce G-Memory, a hierarchical, agentic memory system for MAS inspired by organizational memory theory, which manages the lengthy MAS interaction via a three-tier graph hierarchy: insight, query, and interaction graphs. Upon receiving a new user query, G-Memory performs bi-directional memory traversal to retrieve both \textit{high-level, generalizable insights} that enable the system to leverage cross-trial knowledge, and \textit{fine-grained, condensed interaction trajectories} that compactly encode prior collaboration experiences. Upon task execution, the entire hierarchy evolves by assimilating new collaborative trajectories, nurturing the progressive evolution of agent teams. Extensive experiments across five benchmarks, three LLM backbones, and three popular MAS frameworks demonstrate that G-Memory improves success rates in embodied action and accuracy in knowledge QA by up to $20.89\\%$ and $10.12\\%$, respectively, without any modifications to the original frameworks.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大型语言模型驱动的多智能体系统（MAS）虽在认知和执行能力上远超单一智能体，但其自我演化能力受限于不完善的记忆架构。现有MAS记忆机制存在两大缺陷：(1) 过于简单，完全忽略了智能体间复杂的协作轨迹；(2) 缺乏跨试验和针对特定智能体的个性化定制，与单智能体领域发展出的丰富表达记忆形成鲜明对比。
- **研究动机**：受组织记忆理论启发，作者认为MAS需要一种能够存储、检索和管理长程交互历史的记忆机制，从而使智能体团队能从简洁且有指导意义的经验和洞察中受益，实现渐进式演化。
- **整体含义**：论文旨在填补MAS领域缺乏专用记忆架构的空白，通过提出层次化图记忆系统G-Memory，提升多智能体系统的自演化能力和任务执行效率。

## 2. 论文提出的方法论

### 核心思想
- G-Memory是一种基于图的层次化记忆系统，用于管理MAS的复杂长程交互历史。它通过三层图层次结构（洞察图、查询图、交互图）组织记忆，实现从高层概括性知识到细粒度协作轨迹的多粒度记忆支持。

### 关键技术细节
- **三层图层次架构**：
  - **洞察图（Insight Graph）**：存储从历史经验中抽象出的可泛化洞察，每个洞察节点包含洞察内容和支撑查询集。
  - **查询图（Query Graph）**：存储已解决的问题查询及其元数据（如执行状态、关联的交互图），节点间通过语义关系边连接。
  - **交互图（Interaction Graph）**：存储细粒度的文本通信日志（智能体间的对话），节点为原子话语，边表示时序关系。

- **工作流程**：
  - **粗粒度检索**：新查询到达时，先通过嵌入相似性在查询图中检索相似查询，再通过1-hop邻居扩展获得相关查询集合。
  - **双向记忆遍历**：
    - 向上遍历（查询图→洞察图）：提取与当前任务相关的洞察，提供高层策略指导。
    - 向下遍历（查询图→交互图）：利用LLM驱动的图稀疏化方法，从历史交互图中提取核心协作子图，保留关键对话元素。
  - **记忆增强**：为每个智能体根据其角色和任务，筛选并提供个性化的洞察和交互片段。
  - **层次更新**：任务完成后，交互图、查询图和洞察图均基于环境反馈进行更新：添加新查询节点、建立边连接、生成新洞察并更新支撑查询集。

### 公式或算法流程（文字说明）
- 公式(4)通过余弦相似度选取top-k相似查询；公式(5)通过1-hop邻居扩展；公式(6)通过投影函数从查询集映射到洞察集；公式(7)利用LLM评估历史查询相关性并稀疏化交互图；公式(8)通过评估函数为每个智能体初始化内存；公式(9)~(11)描述了三层结构的更新规则。

## 3. 实验设计

- **数据集/场景**：使用五个广泛采用的基准测试，覆盖三个领域：
  - 知识推理：HotpotQA（多跳问答）、FEVER（事实验证）
  - 具身行动：ALFWorld（文本化家庭任务）、SciWorld（交互式科学任务）
  - 游戏：PDDL（战略游戏）
- **对比方法**：包括四种单智能体记忆基线（无记忆、Voyager、MemoryBank、Generative Agents）和三种多智能体记忆实现（MetaGPT-M、ChatDev-M、MacNet-M）。
- **MAS框架与LLM骨干**：采用三种代表性MAS框架（AutoGen、DyLAN、MacNet）和三种LLM骨干（GPT-4o-mini、Qwen-2.5-7b、Qwen-2.5-14b）。
- **参数配置**：嵌入函数使用ALL-MiniLM-L6-V2；最相关交互图数量M在{2,3,4,5}中选择；相关查询数量k在{1,2}中选择。

## 4. 资源与算力

- 论文未明确说明GPU型号、数量、训练时长等具体算力信息。仅提到部署Qwen系列通过Ollama本地实例化，GPT模型通过OpenAI API访问。未提供详细的硬件资源消耗报告。

## 5. 实验数量与充分性

- **实验数量**：大量实验覆盖了三个LLM骨干、三个MAS框架、五个基准测试，并结合了多种基线方法。此外还进行了敏感性分析（对hop扩展参数和k参数）、消融研究（隔离洞察模块和交互模块的影响）、成本分析（性能与token消耗的权衡）、案例研究。
- **充分性与公平性**：
  - 实验设计较为全面，跨多种配置验证了方法的通用性。
  - 所有实验结果报告为三次运行的平均值，以消除随机偏差。
  - 消融实验和敏感性分析有效论证了关键组件的贡献和参数鲁棒性。
  - 成本分析显示G-Memory在性能提升的同时token消耗增加适度，优于部分基线。
  - 总体而言，实验设计客观、充分，结论可靠。

## 6. 论文的主要结论与发现

- G-Memory在五个基准测试、三种LLM骨干和三种MAS框架上均一致提升了性能，在具身行动任务上最高提升20.89%，在知识QA任务上最高提升10.12%。
- 多智能体系统需要专门的记忆设计，现有单智能体记忆机制直接移植到MAS场景时表现不稳定，甚至造成性能下降。
- G-Memory的层次化结构（高层洞察+细粒度交互轨迹）和角色定制化是有效MAS记忆的关键。
- G-Memory实现了高性能集体记忆，且没有过度增加token消耗，在资源效率上具有优势。

## 7. 优点

- **创新性**：首次系统性地识别了MAS记忆机制的瓶颈，并提出了基于组织记忆理论的层次化图记忆架构，与现有工作有显著差异。
- **通用性**：作为即插即用模块，可无缝集成到主流MAS框架（AutoGen、DyLAN、MacNet）中，无需修改原有框架。
- **全面性**：在多个领域（具身行动、知识推理、游戏）和多种LLM骨干上进行了广泛验证，实验设计严谨。
- **实用性**：通过双向记忆遍历提供多粒度记忆支持（抽象洞察+具体轨迹），同时保持了token效率。
- **可解释性**：案例研究展示了G-Memory如何检索和提供有效的记忆线索，增强了方法的可信度。

## 8. 不足与局限

- **实验覆盖有限**：虽然用了五个基准，但作者承认进一步在更多样化任务（如医学QA）上的验证会加强结论的说服力。
- **算力信息缺失**：未提供具体的GPU型号、数量、训练时长等资源消耗数据，不利于可重复性。
- **参数敏感性**：虽然进行了敏感性分析，但M和k等参数仍需针对具体任务调节，可能存在最优参数适应性问题。
- **长期演化验证不足**：论文主要评估了单次任务性能，但对长期连续交互下的记忆演化效果缺乏深入分析。
- **潜在偏差风险**：LLM的固有偏见可能通过记忆机制被放大，论文未充分讨论公平性和安全性问题。
- **应用限制**：G-Memory的层次更新依赖环境反馈，在反馈不可靠或缺失的场景中可能效果受限。

（完）
