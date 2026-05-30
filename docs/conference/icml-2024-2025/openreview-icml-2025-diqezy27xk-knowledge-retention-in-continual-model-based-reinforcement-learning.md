---
title: Knowledge Retention in Continual Model-Based Reinforcement Learning
title_zh: 连续基于模型的强化学习中的知识保留
authors: "Haotian Fu, Yixiang Sun, Michael Littman, George Konidaris"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DiqeZY27XK"
tags: ["query:agent-memory"]
score: 7.0
evidence: 持续学习中的知识保留
tldr: 连续任务中世界模型会遗忘先前知识。本文提出DRAGO方法，包含合成经验重放（利用生成模型创建旧任务经验）和探索重拾记忆（内在奖励引导agent回顾相关状态），使agent在奖励函数变化的序列任务中保持并发展世界模型，有效支持长期记忆。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1350, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1516, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1611, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1719, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1529, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1734, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1645, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 1018, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1096, \"height\": 1145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1322, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 963, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 839, \"height\": 203, \"label\": \"Table\"}]"
motivation: 连续任务中世界模型遗忘先前动态知识。
method: 结合合成经验重放和内在探索奖励来维持记忆。
result: agent能保持并持续发展世界模型。
conclusion: 为智能体长期记忆维持提供了有效方法。
---

## Abstract
We propose DRAGO, a novel approach for continual model-based reinforcement learning aimed at improving the incremental development of world models across a sequence of tasks that differ in their reward functions but not the state space or dynamics. DRAGO comprises two key components: *Synthetic Experience Rehearsal*, which leverages generative models to create synthetic experiences from past tasks, allowing the agent to reinforce previously learned dynamics without storing data, and *Regaining Memories Through Exploration*, which introduces an intrinsic reward mechanism to guide the agent toward revisiting relevant states from prior tasks. Together, these components enable the agent to maintain a comprehensive and continually developing world model, facilitating more effective learning and adaptation across diverse environments. Empirical evaluations demonstrate that DRAGO is able to preserve knowledge across tasks, achieving superior performance in various continual learning scenarios.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：在连续模型基础强化学习（Continual MBRL）中，世界模型需要在多个序列任务上增量学习，但任务之间仅有奖励函数不同，状态空间和动力学共享。然而，在无存储先前交互数据的约束下（存储限制、隐私法规、设备部署），现有方法（如 naive MBRL）会出现灾难性遗忘，即学习新任务时完全覆盖先前任务的动力学知识，导致世界模型不完整。
- **意义**：构建一个能持续保留和整合知识的世界模型，对机器人、服务型 AI 等真实动态环境至关重要。该工作旨在让智能体在不保留原始数据的前提下，仍能维持并不断扩展其环境动力学理解。

### 2. 方法论：核心思想、关键技术、算法流程

- **核心思想**：结合两种互补机制——**合成经验重放**（Synthetic Experience Rehearsal）和**探索重拾记忆**（Regaining Memories Through Exploration），使智能体在无旧数据时也能学习完整世界模型。
- **关键技术细节**：
  - **合成经验重放**：使用一个持续学习的生成模型（VAE）从先前的状态-动作分布中合成样本 `(s_hat, a_hat)`，然后利用冻结的旧世界模型 `T_old` 预测下一个状态 `s'_hat`，形成合成的转移 `(s_hat, a_hat, s'_hat)`。再将这部分合成数据与当前任务真实数据混合，共同更新当前世界模型 `T_psi`，损失函数包含当前任务预测误差和合成数据预测误差（加权 λ）。
  - **持续学习生成模型**：为防止生成模型本身遗忘，使用旧生成模型 `G_{i-1}` 生成合成状态-动作对，与当前真实数据混合训练新生成模型 `G_i`（VAE），损失函数为 VAE 重构损失 + KL 散度。
  - **探索重拾记忆**：设计一个内在奖励 `r_cont(s_t, a_t, s_{t+1}) = σ(-log|T_{i-1}(s_t,a_t)-s_{t+1}|) - α·σ(-log|T_i(s_t,a_t)-s_{t+1}|)`。第一项鼓励智能体访问旧模型预测准确的状态（熟悉区域），第二项惩罚当前模型已经掌握较好的状态（防止停滞），从而引导智能体探索连接新旧任务的状态区域。
  - **整体算法**：基于 TDMPC，额外训练一个“审查者”（reviewer）策略来最大化累积内在奖励，而“学习者”（learner）策略最大化环境任务奖励。两者共享世界模型。算法核心流程：每轮先由学习者和审查者分别收集数据（内在奖励由公式计算），然后统一更新世界模型、VAE、Q 函数和策略。

### 3. 实验设计

- **场景/数据集**：
  - **MiniGrid**：27×27 网格世界，包含四个房间的序列任务（Room1-Room4），每个任务要求从固定起始点到达本房间目标位置，房间间有门连接。转移任务要求跨房间移动（如从 Room1 到 Room2）。
  - **DeepMind Control Suite**：**Cheetah**（4个任务：run, jump, backward, 及组合）和 **Walker**（4个任务：run, walk, backward, stand），任务间动力学相同但奖励目标不同，训练任务覆盖部分状态空间，转移任务测试跨模式切换（如 jump2run, jump&run 等）。
- **Benchmark 与对比方法**：
  - 主要基线：**Scratch**（每个任务从头训练 TDMPC）、**Continual TDMPC**（直接顺序训练，无防遗忘）、**EWC**（弹性权重巩固）、**Curiosity + Continual TDMPC**（好奇心内在奖励）。
  - 额外对比：**Replay-based MBRL**（存储有限旧数据重放，内存与生成模型大小相同）、**Pseudo-rehearsal MBRL**（使用预训练 VAE 生成旧数据，无持续训练和内在奖励）。
  - 消融实验：去掉合成经验重放或去掉探索重拾记忆的 DRAGO 版本。
  - 还测试了基于 PETS 的 DRAGO 版本。
- **评估指标**：在转移任务上以平均累积奖励（与环境交互步数）衡量世界模型保留知识的迁移能力；同时可视化世界模型预测误差热图。

### 4. 资源与算力

- 论文未明确说明具体 GPU 型号、数量或训练时长，仅提及使用布朗大学计算与可视化中心（CCV）的计算资源。附录中给出了各域的超参数（如学习率 1e-3、batch size 512、最大步数等），但未提供算力细节。

### 5. 实验数量与充分性

- 涉及 **3 个域**（MiniGrid, Cheetah, Walker），每个域 **4 个训练任务**，共产生 **12 个转移测试任务**（每个域 4 个）。
- 进行了**整体性能对比**（12 个测试任务曲线）、**消融实验**（4 个任务）、**few-shot 转移性能**（8 个任务，表 1）、**定性热图**（MiniGrid 世界模型预测误差）、**额外对比**（好奇心基线、PETS 基线、重放基线等）。
- 实验设计较为充分，对比了多种主流方法，且包含了组件消融和不同的基础 MBRL 框架（TDMPC 和 PETS），结果客观。但实验任务数量有限，且任务复杂度不高（低维状态空间），高维视觉或多任务场景未测试。

### 6. 主要结论与发现

- **DRAGO 能有效缓解灾难性遗忘**，保持并持续发展完整的世界模型，在转移任务上显著优于所有基线（包括 EWC 和重放方法）。
- **两个组件互补**：合成经验重放提供旧任务数据，探索重拾记忆连接不同任务区域，两者结合性能最优。
- **few-shot 转移性能**：DRAGO 在 8 个测试任务中有 6 个获得最佳平均回报，其余任务也具竞争力。
- **定性验证**：热图显示 DRAGO 的世界模型预测误差在多个任务后仍保持较低，而 naive 方法仅在当前任务区域准确。

### 7. 优点

- **方法新颖**：首次将合成经验重放与基于内在奖励的探索相结合，用于连续 MBRL 中无数据存储的场景。
- **实用性强**：无需保存原始数据，符合存储和隐私约束，适合机器人、医疗等真实部署。
- **实验全面**：涵盖多个领域、多种对比、消融、few-shot 以及定性分析，验证了方法的有效性。
- **可扩展性**：方法不限于 VAE，可集成扩散模型等更先进生成模型（虽未实验，但提出方向）。

### 8. 不足与局限

- **生成模型遗忘**：持续训练的生成模型本身可能发生模式崩溃或记忆模糊，论文认为任务数量较少时未观察到，但规模化后可能成为瓶颈，未提出深层解决方案。
- **任务假设局限**：仅考虑奖励函数变化且动力学完全相同，状态空间可能有重叠但较小；未测试动力学本身变化或任务多样性更大的场景。
- **复杂度有限**：当前 MiniGrid、Cheetah、Walker 均为低维状态，高维视觉或真实机器人环境未验证。
- **额外计算开销**：需要训练审查者和额外生成模型，相比 naive 方法增加复杂度，但论文未量化。
- **已知任务切换**：假设智能体知道任务何时切换，在更自然连续变化设置中可能不成立。
- **未提供训练资源统计**：缺少 GPU 小时数、能耗等可复现性细节。

（完）
