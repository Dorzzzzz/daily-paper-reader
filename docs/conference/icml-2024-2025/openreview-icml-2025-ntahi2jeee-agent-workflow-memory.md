---
title: Agent Workflow Memory
title_zh: 智能体工作流记忆
authors: "Zora Zhiruo Wang, Jiayuan Mao, Daniel Fried, Graham Neubig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NTAhi2JEEE"
tags: ["query:agent-memory"]
score: 9.0
evidence: 提出了Agent Workflow Memory方法用于智能体记忆系统设计
tldr: 针对语言模型智能体在长期任务中难以复用经验的问题，提出了Agent Workflow Memory方法。该方法通过从训练示例或测试查询中归纳出常用的任务工作流，并在生成时选择性地提供给智能体，从而指导后续动作。在Mind2Web等基准上取得了显著提升，证明了记忆驱动的工作流复用能有效增强智能体的长期任务处理能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1417, \"height\": 709, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1485, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1247, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 512, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 834, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1058, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1592, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 890, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 791, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有语言智能体在长时程复杂任务中难以利用过往经验，缺乏高效的工作流复用机制。
method: 提出Agent Workflow Memory (AWM)方法，从经验中归纳可重用的工作流，并在推理时选择性提供给智能体。
result: 在Mind2Web等网络导航基准上，AWM显著提升了长时程任务的完成成功率。
conclusion: 工作流记忆是一种有效的智能体记忆系统设计方法，可提升长期任务性能。
---

## Abstract
Despite the potential of language model-based agents to solve real-world tasks such as web navigation, current methods still struggle with long-horizon tasks with complex action trajectories. In contrast, humans can flexibly solve complex tasks by learning reusable task workflows from past experiences and using them to guide future actions. To build agents that can similarly benefit from this process, we introduce Agent Workflow Memory (AWM), a method for inducing commonly reused routines, i.e., workflows, and selectively providing workflows to the agent to guide subsequent generations. AWM flexibly applies to both offline and online scenarios, where agents induce workflows from training examples beforehand or from test queries on the fly. We experiment on two major web navigation benchmarks — Mind2Web and WebArena — that collectively cover 1000+ tasks from 200+ domains across travel, shopping, and social media, among others. AWM substantially improves the baseline results by 24.6% and 51.1% relative success rate on Mind2Web and WebArena while reducing the number of steps taken to solve WebArena tasks successfully. Furthermore, online AWM robustly generalizes in cross-task, website, and domain evaluations, surpassing baselines from 8.9 to 14.0 absolute points as train-test task distribution gaps widen.

---

## 论文详细总结（自动生成）

# Agent Workflow Memory (AWM) 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前基于语言模型（LM）的智能体在处理长时程、复杂动作轨迹的 Web 导航任务时仍存在困难。现有方法通常依赖固定示例（训练或上下文学习），无法像人类那样从过往经验中抽象出可重用的任务工作流，导致缺乏对任务变化或环境变化的鲁棒性。
- **整体含义**：本文提出让智能体通过“工作流记忆”机制，自主地从经验中归纳、存储并应用常用的子流程（workflows），从而提升复杂任务的完成成功率，并实现跨任务、网站和领域的泛化。

## 2. 论文提出的方法论：核心思想、关键技术细节、流程

- **核心思想**：将过去成功（或经过验证）的任务轨迹归纳为抽象的、可重用的子例程（workflows），存入智能体记忆，在后续推理时提供上下文指导。
- **关键技术细节**：
  - **工作流表示**：每个工作流包含两部分：
    - 文本描述（自然语言说明该工作流的功能）。
    - 轨迹步骤序列，每步含三项：环境状态描述（NL）、推理过程、可执行动作（如 `click('id')`）。
  - **工作流归纳模块 I**：可使用两种方法：
    - **基于 LM 的归纳**：将多个经验（指令+轨迹）输入 LM，提示其提取共同子例程，并将具体值替换为变量（如 `{product-name}`）以增强抽象性。
    - **基于规则的归纳**：去重动作序列、过滤无效步骤后直接作为工作流。
  - **记忆更新与使用**：工作流归纳后加入 agent memory。推理时，agent 同时使用原始 memory 和工作流 memory 生成动作。
- **应用场景**：
  - **离线场景**：从训练集示例中预先归纳工作流，然后用于测试集。
  - **在线场景**：无额外标注数据，仅使用测试查询流式处理：对每个测试任务先推测动作，用评估器判断是否成功，若成功则归纳工作流并加入 memory，用于后续任务。
- **流程图说明**：图2展示了从经验到工作归纳再到整合进 memory 的流程；图3展示了离线与在线两种模式。

## 3. 实验设计：使用的数据集、基准、对比方法

- **数据集**：
  - **WebArena**：812 个任务，涵盖 5 个网站（购物、CMS、Reddit、GitLab、地图），提供基于功能正确性的严格评估。
  - **Mind2Web**：强调跨任务、跨网站、跨域泛化，提供训练集和三个测试集（cross-task、cross-website、cross-domain）。
- **基准（Baseline）**：
  - WebArena：BrowserGym（当前 SOTA 自主方法）、SteP（使用人类专家编写的工作流）、AutoEval 等。
  - Mind2Web：MindAct、Synapse、CogAgent。
- **对比方法**：本文提出的 AWM（包括离线、在线、规则/LM 归纳等多种变体），以及消融实验中的文本工作流、HTML 环境表示等。

## 4. 资源与算力

- **未明确说明**：论文未提及具体使用的 GPU 型号、数量、训练时长等硬件信息。
- **模型选择**：使用 GPT-4o（`gpt-4o-2024-05-13`）和 GPT-3.5-turbo，温度设为 0.0。所有实验均通过 API 调用完成，未进行本地模型训练。

## 5. 实验数量与充分性

- **实验数量**：总量丰富，包括：
  - 主实验：WebArena 表1、Mind2Web 表3。
  - 跨模板子集实验（表2）。
  - 在线累积成功率曲线（图4）。
  - 消融实验：
    - 规则 vs LM 工作流归纳（表5、表6）。
    - 文本 vs 代码格式工作流（表7）。
    - 不同环境状态表示（NL/HTML/两者，表8）。
    - 工作流作为动作空间（表13）。
    - 示例顺序敏感性（表12）。
    - 离线+在线整合（表C）。
    - 计算成本分解（表11）。
- **充分性与公平性**：实验覆盖了多种场景（跨任务、跨网站、跨域、泛化等），消融实验设计系统，对比方法为当前公开 SOTA，控制模型、温度等超参数一致。但部分消融（如环境抽象）仅在 Mind2Web 上执行，未在 WebArena 重复。总体充分、客观。

## 6. 论文的主要结论与发现

- **AWM 显著提升任务成功率**：在 WebArena 上相对提升 51.1%（总体成功率从 23.5% 提升到 35.5%），在 Mind2Web cross-task 上提升 24.6%（步骤成功率从 36.2% 至 45.1%）。
- **超越人类专家工作流方法**：AWM 无需人工干预，仍超越使用 14 个专家编写工作流的 SteP 方法（7.9% 相对提升）。
- **高效学习**：仅需数十个示例即可快速提升性能（图4），且逐步归纳更复杂的工作流（图5）。
- **优秀泛化能力**：在线 AWM 在跨任务、跨网站、跨域评估中稳定优于基线，且随分布差异增大优势更明显（8.9–14.0 绝对点）。
- **抽象工作流优于具体示例**：与 Synapse（检索具体示例）相比，AWM 的抽象表示减少了元素选择偏差，获得更高元素准确率。
- **工作流格式不敏感**：文本格式与代码格式性能相近（表7）。
- **环境状态描述使用 NL 比 HTML 更有效**（表8），同时使用两者反而下降。

## 7. 优点

- **方法创新性**：提出无需人工标注、可离线/在线灵活使用的工作流归纳与记忆机制，填补了智能体从经验中学习可重用子流程的空白。
- **实验设计全面**：在两个主流基准上开展系统性实验，涵盖跨场景消融、泛化测试、效率分析、顺序敏感性等。
- **结果显著且稳健**：不仅提升成功率，还减少步骤数（WebArena 从 7.9 步降至 5.9 步），展示了实用价值。
- **可解释性与案例展示**：通过具体工作流示例（如“查找地点”→“获取邮政编码”）直观展示逐步学习过程（图5）。
- **开源贡献**：代码已公开（GitHub 链接），促进后续研究。

## 8. 不足与局限

- **计算资源未公开**：未报告 API 调用量、GPU 型号等，影响可复现性评估。
- **部分性能短板**：在 Mind2Web 上 Action F1 略低于 MindAct（57.3 vs 60.6），说明工作流有时会引导 agent 采取非最优动作。
- **在线错误传播**：在线模式下，若评估器误判错误轨迹为成功，会引入错误工作流，损害性能。
- **环境抽象局限**：同时提供 NL 描述和 HTML 反而导致性能下降，可能因上下文过长或 HTML 噪声。
- **工作流作为动作空间使用率低**：仅 18.5% 的任务调用了工作流动作，受限于动态环境（如弹出选项）的适应性不足。
- **泛化性验证有限**：仅在 Web 导航任务上测试，未在机器人控制、桌面操作等其他智能体领域验证。
- **示例顺序鲁棒性**：在 Mind2Web 小规模数据上示例顺序影响不大，但在更大数据集上可能仍存敏感性（论文提及）。
- **未与更复杂的记忆机制对比**：如持续学习库（DreamCoder、LILO）或在更多方法上的对比（如 Reflexion 的反思机制）。

（完）
