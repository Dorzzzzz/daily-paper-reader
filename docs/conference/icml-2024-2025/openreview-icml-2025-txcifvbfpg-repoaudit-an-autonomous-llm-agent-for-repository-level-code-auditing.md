---
title: "RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing"
title_zh: RepoAudit：用于仓库级代码审计的自主LLM智能体
authors: "Jinyao Guo, Chengpeng Wang, Xiangzhe Xu, Zian Su, Xiangyu Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TXcifVbFpG"
tags: ["query:agent-memory"]
score: 9.0
evidence: 具备智能体记忆的自主代码审计代理
tldr: 大型代码库审计面临上下文窗口限制和幻觉问题。本文提出RepoAudit智能体，配备智能体记忆系统，通过按需数据流分析探索代码库，自主完成仓库级审计，有效缓解上下文限制和幻觉，提升审计效率与质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 72, \"height\": 84, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1330, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-txcifvbfpg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 781, \"height\": 416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1563, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 696, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1334, \"height\": 664, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1335, \"height\": 653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1336, \"height\": 646, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 861, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-txcifvbfpg/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1767, \"height\": 492, \"label\": \"Table\"}]"
motivation: 代码审计面临上下文限制和幻觉问题，影响效率与质量。
method: 提出RepoAudit智能体，利用记忆系统按需探索代码数据流。
result: 在仓库级审计任务中显著提升效率与准确性。
conclusion: 该工作展示了记忆增强型智能体在复杂代码审计中的有效性。
---

## Abstract
Code auditing is the process of reviewing code with the aim of identifying bugs. Large Language Models (LLMs) have demonstrated promising capabilities for this task without requiring compilation, while also supporting user-friendly customization. However, auditing a code repository with LLMs poses significant challenges: limited context windows and hallucinations can degrade the quality of bug reports, and analyzing large-scale repositories incurs substantial time and token costs, hindering efficiency and scalability.

This work introduces an LLM-based agent, RepoAudit, designed to perform autonomous repository-level code auditing. Equipped with agent memory, RepoAudit explores the codebase on demand by analyzing data-flow facts along feasible program paths within individual functions. It further incorporates a validator module to mitigate hallucinations by verifying data-flow facts and checking the satisfiability of path conditions associated with potential bugs, thereby reducing false positives. RepoAudit detects 40 true bugs across 15 real-world benchmark projects with a precision of 78.43%, requiring on average only 0.44 hours and $2.54 per project. Also, it detects 185 new bugs in high-profile projects, among which 174 have been confirmed or fixed. We have open-sourced RepoAudit at https://github.com/PurCL/RepoAudit.

---

## 论文详细总结（自动生成）

# 论文总结：RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：代码审计是发现代码缺陷的关键任务，大型语言模型（LLM）在无需编译的情况下展现出潜力，但直接对代码仓库进行审计面临两大挑战：LLM的上下文窗口有限，无法处理整个仓库；LLM容易产生幻觉，导致错误报告质量下降。此外，大规模仓库的分析时间与token成本高昂，影响效率与可扩展性。
- **整体含义**：本文试图构建一个**自主的LLM智能体**，模仿人类审计员按需探索代码、沿可行程序路径进行数据流分析，并利用验证机制减少幻觉，实现高效、精确的仓库级代码审计。

## 2. 方法论：核心思想、关键技术细节与流程

- **核心思想**：将仓库级代码审计视为对大型程序图的路径敏感遍历，通过**按需需求驱动（demand-driven）**的方式，每次让LLM分析单个函数，利用其内在能力进行程序抽象、指针处理、可行路径探索，并通过**智能体记忆**和**验证器**减少幻觉与错误。
- **技术细节**：
  - **架构三组件**：
    - **Initiator（启动器）**：根据bug定义（如NULL值检测）识别源值（source values），作为扫描起点。
    - **Explorer（探索器）**：迭代地、按需地探索仓库中的函数。对每个函数，利用LLM执行程序抽象（删除无关语句）、指针处理（确定指针指向对象）、可行程序路径探索（识别可行路径及数据流事实）。分析结果存入智能体记忆，若值跨越函数边界，则通过调用图进入调用者或被调用者继续分析。当数据流事实到达汇点（如解引用指针）时生成候选bug报告。
    - **Validator（验证器）**：两个验证机制——(a) **对齐验证**：检查数据流事实是否违背控制流顺序；(b) **路径可行性验证**：跨函数的路径条件是否存在矛盾，通过提示LLM判断。
  - **智能体记忆**：存储函数-值对的映射，包含路径与数据流事实，避免重复分析。
  - **上下文深度上限**：设置K=4（最多跨越4个函数）。
  - **LLM选择**：默认使用Claude 3.5 Sonnet，温度设为0.0。
- **算法流程摘要**：
  1. Initiator根据bug定义匹配源码中的源值。
  2. Explorer从源值所在函数开始，对每个函数：
     - 使用图4所示提示模板，分三步：指针处理、提取关键语句、收集可行路径并模拟执行。
     - 获得数据流事实并存入记忆。
     - 若值逃逸（如通过返回值、全局变量），则查询调用图进入相关函数继续。
  3. 当数据流事实到达汇点（或未到达汇点，如MLK），生成bug候选。
  4. Validator对候选进行对齐验证和跨函数路径可行性验证，通过则报告。

## 3. 实验设计

- **数据集与场景**：
  - **基准项目**：15个真实世界开源项目（C/C++），取自已有研究的bug报告，包含5个NPD、5个MLK、5个UAF类型，平均规模251 KLoC。
  - **额外项目**：9个高知名度开源项目（如nginx、memcached、libuv等），规模14K~1.7M LoC，用于发现新bug。
- **Benchmark**：基于历史已知bug的复现能力、新bug发现、以及与其他工具的对比。
- **对比方法**：
  - **工业级工具**：Meta Infer（需编译，比较TP/FP）、Amazon CodeGuru（无需编译，只支持NPD和UAF）。
  - **LLM驱动方法**：
    - 端到端少样本CoT提示（单函数级别和多函数级别）。
    - 智能体方法LLMDFA（对相关函数做数据流分析，比较计算开销）。
  - **消融变体**：无抽象（NoAbs）、无验证器（NoVal）、无缓存（NoCache）。
  - **不同LLM**：DeepSeek R1、Claude 3.7 Sonnet、OpenAI o3-mini。
  - **不同温度**：0.0, 0.25, 0.5, 0.75, 1.0。
- **评估指标**：True Positives (TP)、False Positives (FP)、Precision、Recall、时间、token消耗、金钱成本、prompt轮数。

## 4. 资源与算力

- 论文**未明确说明GPU型号、数量或训练时长**。智能体基于闭源LLM（Claude 3.5 Sonnet等）的API调用运行，不涉及模型训练。仅提到使用tree-sitter解析库等轻量级工具。因此计算资源主要消耗在LLM推理上，但具体硬件细节未给出。

## 5. 实验数量与充分性

- **实验数量**：总体上非常充分。
  - 主实验：15个基准项目 + 9个额外项目。
  - 对比实验：与Meta Infer（8个项目成功分析）、Amazon CodeGuru（10个项目）对比。
  - 消融实验：3种变体（NoAbs, NoVal, NoCache）在15个基准项目上对比TP、FP、时间、token。
  - 多模型实验：4种LLM（Claude 3.5, DeepSeek R1, Claude 3.7, o3-mini）在15个基准项目上对比。
  - 温度敏感性实验：5种温度设置。
  - 附录中还有与LLMDFA的对比（两种设置下计算开销比率）。
- **充分性与公平性**：
  - 实验项目选取源自已有研究，具有代表性；对比工具（Infer, CodeGuru）为工业标准；比较TP/FP较为客观。
  - 消融实验验证了每个组件的必要性。
  - 多模型实验显示了方法的泛化性。
  - 温度实验证明了稳定性。
  - 但受限于LLM API调用费用，可能未对超大规模仓库（如Linux完整源码）进行全面测试；且对比LLMDFA时仅计算了部分函数，低估了其真实成本。

## 6. 主要结论与发现

- **主结论**：RepoAudit在15个基准项目上检测出40个真阳性（21个已知、19个新发现），精度78.43%，平均每项目仅需0.44小时和$2.54。在9个高知名度项目中检测出185个新bug，其中174个已被确认或修复。
- **与其他工具对比**：
  - Meta Infer在8个可分析项目上仅发现7个TP、2个FP，且5个项目编译失败或崩溃。
  - Amazon CodeGuru报告18个FP，无TP。
  - CoT提示在多函数级别上仅能检测10个TP，而RepoAudit检测全部。
  - LLMDFA的计算开销（prompt轮数、token）是RepoAudit的百倍以上。
- **消融效果**：无抽象时TP减少47.5%，FP增加181.8%；无验证器时FP增加245.5%；无缓存时时间/token成本增加3-4倍。
- **不同LLM表现**：DeepSeek R1精度最高（88.46%），Claude 3.7 Sonnet次之（86.79%），o3-mini（82.35%）。成本和时间有所差异。
- **温度影响**：精度始终≥72.92%，召回≥85.71%，表现稳定。

## 7. 优点

- **方法创新**：模仿人类审计员的按需路径探索，结合LLM固有抽象、指针处理、路径可行性判断能力，克服了LLM上下文限制和幻觉问题。
- **架构设计合理**：初始化、探索、验证三组件分工明确，智能体记忆和验证器有效提升效率和精度。
- **工程实用性**：无需编译、支持IDE开发阶段审计；成本低廉（每bug约$0.95），可扩展至大规模项目。
- **实验全面**：覆盖多种bug类型、多个项目、对比工业工具、消融、多模型、温度敏感性，论证充分。
- **开放源码**：提供代码仓库，便于复现和扩展。

## 8. 不足与局限

- **依赖LLM质量**：精度仍受限于底层LLM的推理能力，不同模型表现有差异；存在假阳性和假阴性（附录F给出示例）。
- **路径深度限制**：K=4的上限可能导致错过长调用链的bug。
- **源值数量敏感**：若仓库中存在大量源值（如大量NULL赋值），时间与token成本会显著增加。
- **不支持所有bug类型**：当前仅针对NPD、MLK、UAF三类内存错误；需针对新类型设计新的初始匹配器。
- **实验覆盖率**：主要针对C/C++代码，对其他语言（如Python、JavaScript）的适用性仅在展望中提及；未与更多静态分析器（如CodeQL）或基于学习的漏洞检测工具对比。
- **可复现性限制**：由于使用闭源LLM API且温度设为0.0，但API行为可能随时间变化，结果可能难以完全复现。
- **未报告GPU/训练资源**：无法评估自身训练或微调成本（实际也未进行微调，仅使用预训练LLM）。

（完）
