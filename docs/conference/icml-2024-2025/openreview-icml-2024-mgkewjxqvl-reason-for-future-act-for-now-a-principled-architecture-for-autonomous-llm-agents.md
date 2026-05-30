---
title: "Reason for Future, Act for Now: A Principled Architecture for Autonomous LLM Agents"
title_zh: 为未来推理，为现在行动：自主LLM智能体的原则性架构
authors: "Zhihan Liu, Hao Hu, Shenao Zhang, Hongyi Guo, Shuqi Ke, Boyi Liu, Zhaoran Wang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=MGkeWJxQVl"
tags: ["query:agent-memory"]
score: 4.0
evidence: 具有记忆缓冲区的智能体架构用于规划和推理
tldr: LLM智能体将推理转化为行动面临挑战，论文提出RAFA框架，通过记忆缓冲区学习并规划未来轨迹，在保证遗憾界的同时最小化交互次数，其记忆机制为智能体架构设计提供了理论支撑。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1370, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 456, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 451, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 451, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1379, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 836, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 456, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 450, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 834, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 455, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1430, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1774, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1777, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 767, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1773, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 760, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1767, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 724, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mgkewjxqvl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1756, \"height\": 1042, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 876, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 483, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1184, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1732, \"height\": 1727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1362, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 972, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mgkewjxqvl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1736, \"height\": 2288, \"label\": \"Table\"}]"
motivation: LLM智能体需要将推理转化为行动，且要最小化与环境交互次数。
method: 设计包含记忆缓冲区的推理模板，学习并执行长视界规划。
result: 首次提供具有可证明遗憾界的推理与行动框架。
conclusion: 记忆缓冲区是实现高效LLM智能体的关键组件。
---

## Abstract
Large language models (LLMs) demonstrate impressive reasoning abilities, but translating reasoning into actions in the real world remains challenging. In particular, it is unclear how to complete a given task provably within a minimum number of interactions with the external environment, e.g., through an internal mechanism of reasoning. To this end, we propose the first framework with provable regret guarantees to orchestrate reasoning and acting, which we call *reason for future, act for now* (**RAFA**). Specifically, we design a prompt template for reasoning that learns from the memory buffer and plans a future trajectory over a long horizon (*reason for future*). At each step, the LLM agent takes the initial action of the planned trajectory (*act for now*), stores the collected feedback in the memory buffer, and reinvokes the reasoning routine to replan the future trajectory from the new state. The key idea is to cast reasoning in LLMs as learning and planning in Bayesian adaptive Markov decision processes (MDPs). Correspondingly, we prompt LLMs with the memory buffer to estimate the unknown environment (learning) and generate an optimal trajectory for multiple future steps that maximize a value function (planning). The learning and planning subroutines are performed in an in-context manner to emulate the actor-critic update for MDPs. Our theoretical analysis establishes a $\sqrt{T}$ regret, while our experimental validation demonstrates superior empirical performance.

---

## 论文详细总结（自动生成）

# 论文《Reason for Future, Act for Now: A Principled Architecture for Autonomous LLM Agents》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）虽然具备强大的推理能力，但将推理转化为真实世界中的行动仍然面临挑战。关键问题在于如何通过内部推理机制，以最少的交互次数（即样本效率）完成给定任务，并且需要有理论上的性能保证。
- **研究背景**：现有工作如ReAct、Reflexion、AdaPlanner等将LLM推理与行动结合，但缺乏样本效率的理论保证；而传统强化学习（RL）虽有理论保证，但与LLM的符号系统存在概念鸿沟（数值vs.语言、参数更新vs.上下文学习）。本文旨在弥合这一鸿沟，首次为自主LLM智能体提供可证明的遗憾界。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将LLM的推理过程形式化为贝叶斯自适应马尔可夫决策过程（Bayesian adaptive MDP）中的学习与规划。LLM被用作模型估计器（通过上下文学习），利用记忆缓冲区（memory buffer）中的历史反馈来更新估计，并基于估计进行多步规划。
- **关键技术细节**：
  - **记忆缓冲区**：存储所有历史交互（状态、动作、奖励、下一状态）。
  - **学习子程序**：使用LLM实例（Model和Critic）从记忆缓冲区中推断转移模型、奖励函数或价值函数。
  - **规划子程序**：基于学习到的模型，生成未来多步的最优轨迹（例如通过树搜索、值迭代、MCTS）。规划输出首动作，随后被智能体执行。
  - **切换条件**：当后验熵减少超过一定阈值（如1 bit）时，更新记忆缓冲区并重新规划，以保证策略更新的保守性。
- **算法流程（文字说明）**：
  1. 初始化记忆缓冲区为空，采样初始状态。
  2. 对于每个切换阶段k：
     - 设置时间戳tk。
     - 重复以下步骤直到切换条件满足：
       - 基于当前记忆缓冲区Dtk，通过学习子程序获得Model和Critic，再由规划子程序生成未来轨迹，输出当前动作at。
       - 执行动作at，接收奖励rt和下一状态st+1。
       - 将新反馈加入记忆缓冲区，更新时间t。
  3. 当后验熵减少超过log 2时，进入下一个切换阶段。
- **理论贡献**：在假设LLM具有后验对齐（Posterior Alignment）的前提下，证明了RAFA的贝叶斯遗憾界为Õ(√T)，并给出了两种高效探索变体（乐观奖励、后验采样）的类似保证。

## 3. 实验设计：数据集/场景、Benchmark、对比方法

- **数据集/场景**：
  - **Game of 24**：数学谜题，用四个数和算术运算得到24。
  - **ALFWorld**：文本化具身智能体任务，涉及134个家庭任务，分为6大类（如pick、clean、heat、cool、examine、pick2）。
  - **BlocksWorld**：积木重排问题，包含4步和6步任务。
  - **Tic-Tac-Toe**：井字棋，竞争性游戏。
- **Benchmark/对比方法**：
  - Game of 24：ToT（Tree of Thoughts）、Reflexion、CoT。
  - ALFWorld：ReAct、AdaPlanner、Reflexion、BUTLER。
  - BlocksWorld：CoT、RAP（Reasoning via Planning）。
  - Tic-Tac-Toe：直接使用GPT-4作为基线。
- **评估指标**：成功率和样本效率（随交互步数/轮次的变化曲线）。

## 4. 资源与算力

- **文中未明确说明**：未提及使用的GPU型号、数量或训练时长。模型主要调用API（GPT-4、GPT-3.5-turbo、GPT-3、Vicuna-13B/33B），未涉及大规模自训练。因此，算力开销主要体现在API调用次数和少量推理成本上。

## 5. 实验数量与充分性

- **实验数量**：
  - Game of 24：在100个任务上测试，使用两种LLM（GPT-4、GPT-3.5-turbo）和两种规划宽度（B=1,2）。
  - ALFWorld：6个任务类别，共134个任务，报告平均成功率随轮次变化。
  - BlocksWorld：4-step和6-step任务，使用Vicuna-13B和33B，报告随步骤的成功率曲线。
  - Tic-Tac-Toe：与GPT-4对战，报告X胜率、平局、O胜率，以及随轮次的得分曲线。
  - **消融实验**：在ALFWorld上对搜索深度U和搜索宽度B进行了消融；在Game of 24上对比了不同B和不同LLM；在Tic-Tac-Toe上对比了B=3和B=4。
- **充分性评估**：
  - **优点**：四个任务覆盖了推理、导航、规划、博弈等多种场景，对比方法全面，消融实验针对关键超参数。
  - **不足**：所有任务均为文本环境，未在真实物理环境或连续控制任务上验证；Tic-Tac-Toe仅以GPT-4为对手，泛化性有限；未对所有基线在所有任务上测试（如RAP仅在BlocksWorld，AdaPlanner仅在ALFWorld）。理论假设（后验对齐）在实验中未验证是否符合。

## 6. 论文的主要结论与发现

- RAFA在所有任务上显著优于现有方法，尤其在样本效率方面，能够在更少的交互次数内达到更高成功率。
- 理论分析证明了RAFA的√T遗憾界，为首个为LLM智能体提供可证明样本效率保证的框架。
- 实验验证了Claim 2.1（更多反馈可提高LLM估计准确性），例如在Game of 24中，价值估计准确度随交互步数单调增加。
- RAFA通过记忆缓冲区和切换机制，有效缓解了LLM的幻觉问题（如重复使用数字、错误状态预测），并提高了规划最优性。

## 7. 优点

- **理论贡献突出**：首次为LLM智能体建立与RL的严格对应，并给出可证明的遗憾界，为后续研究提供了理论基石。
- **无需参数更新**：利用LLM的上下文学习能力，仅通过提示工程实现学习与规划，避免了传统RL中的梯度更新。
- **模块化设计**：学习、规划、行动三个模块可独立替换（如可采用不同规划算法：树搜索、值迭代、MCTS），具有灵活性。
- **实验验证充分**：在多个任务上展示了显著优势，且通过消融实验分析了关键组件的作用。
- **实用性强**：提供的提示模板和代码（https://agentification.github.io/RAFA/）便于复现和扩展。

## 8. 不足与局限

- **理论假设较强**：后验对齐假设（Assumption 5.1）在实际LLM中未必成立，虽然附录D.6尝试放松，但依赖预训练数据覆盖等额外条件，可操作性有限。
- **实验场景有限**：所有任务均为文本或符号环境，未涉及视觉、物理交互或连续动作空间，距离真实机器人应用有差距。
- **记忆缓冲区受限**：受token限制，无法存储完整长历史，实验中ALFWorld使用了部分历史，可能损失信息。
- **未分析规划次优性ϵ的影响**：理论中假设ϵ=O(1/√T)，但实验中未明确报告ϵ值或对其的影响。
- **可复现性**：代码仅提供网址，未详细说明所有超参数和随机种子设置，可能存在复现难度。
- **对比方法不完全公平**：部分基线（如AdaPlanner）使用了手工设计的程序，而RAFA未使用领域知识，但在某些任务（如Pick2）上仍有差距。

（完）
