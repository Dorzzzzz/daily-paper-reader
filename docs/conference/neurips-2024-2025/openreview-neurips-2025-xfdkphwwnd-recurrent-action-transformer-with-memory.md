---
title: Recurrent Action Transformer with Memory
title_zh: 带有记忆的循环动作Transformer
authors: "Egor Cherepanov, Aleksei Staroverov, Alexey Kovalev, Aleksandr Panov"
date: 2025-05-10
pdf: "https://openreview.net/pdf?id=xFDKphWWnD"
tags: ["query:agent-memory"]
score: 9.0
evidence: 提出具有循环记忆的Transformer用于离线强化学习智能体
tldr: 部分可观测环境中，标准Transformer因上下文长度限制难以保留重要历史信息。本文提出循环动作Transformer（RATE），在Transformer中融入循环记忆机制以调控信息留存，使智能体能够在长期决策中维持状态。实验证明RATE在多种离线RL任务上优于现有方法，为智能体记忆系统设计提供了有效架构。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 729, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 725, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 727, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 724, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 718, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1414, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 598, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1458, \"height\": 1922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 1194, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1445, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1415, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1450, \"height\": 1014, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1440, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 712, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 712, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 471, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 465, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xfdkphwwnd/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 474, \"height\": 247, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 739, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 742, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1458, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1460, \"height\": 882, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 1621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1244, \"height\": 535, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1457, \"height\": 563, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 921, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xfdkphwwnd/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1457, \"height\": 408, \"label\": \"Table\"}]"
motivation: 部分可观测环境中Transformer因上下文限制难以保留历史信息，影响决策。
method: 在Transformer中引入循环记忆机制，调控信息留存以增强长期记忆。
result: 在多个离线RL基准上优于现有方法。
conclusion: RATE为智能体记忆系统设计提供了可扩展的架构。
---

## Abstract
Transformers have become increasingly popular in offline reinforcement learning (RL) due to their ability to treat agent trajectories as sequences, reframing policy learning as a sequence modeling task. However, in partially observable environments (POMDPs), effective decision-making depends on retaining information about past events - something that standard transformers struggle with due to the quadratic complexity of self-attention, which limits their context length. One solution to this problem is to extend transformers with memory mechanisms. We propose the Recurrent Action Transformer with Memory (RATE), a novel transformer-based architecture for offline RL that incorporates a recurrent memory mechanism designed to regulate information retention. We evaluate RATE across a diverse set of environments: memory-intensive tasks (ViZDoom-Two-Colors, T-Maze, Memory Maze, Minigrid-Memory, and POPGym), as well as standard Atari and MuJoCo benchmarks. Our comprehensive experiments demonstrate that RATE significantly improves performance in memory-dependent settings while remaining competitive on standard tasks across a broad range of baselines. These findings underscore the pivotal role of integrated memory mechanisms in offline RL and establish RATE as a unified, high-capacity architecture for effective decision-making over extended horizons.

---

## 论文详细总结（自动生成）

# 论文《Recurrent Action Transformer with Memory》中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在部分可观测环境（POMDPs）中，智能体必须依赖过去事件的信息才能做出有效决策。标准 Transformer 因自注意力机制的二次复杂度，导致上下文窗口受限，难以处理长序列；而经典的循环神经网络（RNN）虽然天然具有记忆，但在长距离依赖和稀疏奖励场景下容易出现梯度消失或容量不足问题。
- **核心问题**：如何在离线强化学习中构建一种既能利用 Transformer 强大的序列建模能力，又能通过轻量级记忆机制突破上下文窗口限制，从而在长时域 POMDP 任务中保留关键历史信息。
- **整体含义**：提出 RATE 模型，将循环记忆集成到 Transformer 架构中，通过三个互补的机制（记忆嵌入、缓存隐藏状态、记忆保持阀）实现信息的选择性保持，为离线 RL 提供了一种统一、高容量的决策架构，在记忆密集型任务上显著优于现有方法，同时在标准 MDP 基准上保持竞争力。

## 2. 论文提出的方法论

- **核心思想**：将长轨迹划分为不重叠的段（segments），每段长度 K 远小于总长度 T。每段前后附加 m 个可学习的记忆嵌入（memory embeddings），经过 Transformer 处理后，通过记忆保持阀（Memory Retention Valve, MRV）过滤并更新记忆，再将更新后的记忆传递给下一段。方案将有效上下文长度扩展为 N×K（N 为段数），远超过普通 Transformer 的固定窗口，同时避免二次复杂度带来的计算爆炸。

- **关键技术细节**：
  1. **记忆嵌入**：每段起始和结束处添加 m 个可学习向量，用于在段间传递信息。
  2. **缓存隐藏状态**：对于需要连续密集反馈的环境（如 ViZDoom），缓存上一段 Transformer 的隐藏状态，作为额外输入。
  3. **记忆保持阀 (MRV)**：核心创新。采用交叉注意力机制，以上一段的记忆嵌入作为 Query，当前段更新后的记忆嵌入作为 Key 和 Value，通过 softmax 加权组合生成新的记忆。公式化表示为：  
     `M_{n+1} = FFN( MultiHead( Query = M_n, Key = M_{n+1}^raw, Value = M_{n+1}^raw ) )`  
     这种设计允许旧记忆控制新信息的写入，防止重要信息被覆盖。
  4. **算法流程**（文字说明）：
     - 编码：对每个时间步的 (返回-目标, 观测, 动作) 使用模态特定编码器进行编码。
     - 分段：将完整轨迹分割成多个长度 K 的段。
     - 段处理：对每个段，在序列前后添加记忆嵌入 M_n（初始为零或随机），送入 Transformer 解码器。
     - MRV 更新：用 MRV 从旧记忆 M_n 和新原始记忆 M_{n+1}^raw 生成最终记忆 M_{n+1}。
     - 迭代：将 M_{n+1} 作为下一段的记忆输入，直到处理完所有段。
  5. **理论保证**：定理 1 给出 MRV 更新后的记忆保留下界。在 α-对齐条件下，每次更新至少保留 `1 - sqrt(2(1 - α/m))` 比例的原始记忆范数，防止灾难性遗忘。

## 3. 实验设计

- **使用的数据集 / 场景**：
  - **记忆密集型环境**：ViZDoom-Two-Colors（需记忆支柱颜色）、T-Maze（稀疏线索需保持到末尾）、Memory Maze（3D 迷宫需空间记忆）、Minigrid-Memory（类似 T-Maze 但包含寻物）、POPGym（46 个部分可观测任务，包括记忆谜题和反应式 POMDP）。
  - **标准 MDP 基准**：Atari 游戏（Breakout, Qbert, SeaQuest, Pong）、MuJoCo 控制任务（HalfCheetah, Hopper, Walker2d，来自 D4RL 的 Medium、Medium-Replay、Medium-Expert 数据集）。

- **Benchmark**：所有实验均采用离线 RL 设定，数据集由训练好的策略（A2C、PPO、Dreamer、DQN 等）收集。评估指标包括平均回报、成功率、不平衡度（红/绿支柱表现差异）、归一化分数等。

- **对比方法**：覆盖广泛：
  - 基于 Transformer：Decision Transformer (DT)、Recurrent Memory Transformer (RMT)、Transformer-XL (TrXL)、Long-Short DT (LSDT)
  - 经典离线 RL：CQL、BC（MLP 和 LSTM 骨干）
  - RNN 类：BC-LSTM、CQL-LSTM、Decision LSTM (DLSTM)、DGRU
  - 状态空间模型：Decision Mamba (DMamba)、MambaDM
  - 随机基准和 Oracle 变体（OracleDT：提供完美记忆信息的 DT）

## 4. 资源与算力

- **明确信息**：论文在附录 I 中说明：“训练使用单张 NVIDIA A100 80GB 显卡。在 Table 13 中给出了各环境下 RATE 与 DT 的训练时间/epoch、推理延迟和 GPU 内存占用。例如，T‑Maze 下 RATE 每 epoch 训练时间 16.17±2.75 秒，GPU 内存 3,148 MiB；DT 使用 95.75±0.49 秒和 8,608 MiB。训练总 epoch 数等未给出，但根据超参数表（Table 8），不同环境下 epoch 数在 10–500 之间变化。”
- **未明确说明**：总训练计算量（例如 GPU 小时数）、多次运行的总资源消耗未量化报告。但提供了清晰的模型参数数量（RATE 比 DT 少 1–8%）和内存节省（RATE 约使用 DT 的 1/2 到 1/3 的 GPU 内存）。

## 5. 实验数量与充分性

- **实验数量**：极为丰富。
  1. **主实验**：在 6 个记忆密集型环境（含 POPGym 的 46 个子任务）以及 Atari（4 个游戏）、MuJoCo（9 个任务-数据集组合）上进行，总计超过 60 个独立实验设置。
  2. **消融实验**：
     - 记忆组件消融（T‑Maze 中加噪声破坏记忆嵌入或隐藏状态）。
     - MRV 配置消融（5 种变体：交叉注意力两种方向、门控、GRU、LSTM）。
     - 超参数消融（层数、头数、嵌入维度、段长度 K 与段数 N、是否使用前馈网络）。
     - 课程学习消融、记忆嵌入噪声影响、记忆大小等。
  3. **上限估计**：引入 OracleDT 提供完美记忆时的性能上限。
  4. **统计严谨性**：每个实验均报告多次运行（Nruns=3–10）和多种子评估（Nseeds=100–400），结果给出均值±标准误或标准差，置信区间明确。例如 Figure 5 的 T‑Maze 热力图显示了 11×11 网格的详细成功率。

- **充分性与客观性**：实验设计系统，覆盖了从极度稀疏（T‑Maze）到密集奖励（ViZDoom）、从图像输入到低维向量的多种模态，以及从短期到超长推断（9600 步）的场景。对比基线涵盖主流类别，并复现了原始论文的评估协议。消融实验验证了各个组件的必要性。总体而言，实验充分、公平，结论可靠。

## 6. 论文的主要结论与发现

- RATE 在所有记忆密集型环境中一致优于所有基线，特别是在 T‑Maze 上达到 100% 成功率，并在推断长达 9600 步（28,800 个 token）时保持性能，而 DT 等基线一旦超出上下文窗口就急剧下降至随机水平。
- 在标准 MDP 基准（Atari 和 MuJoCo）上，RATE 与专门设计的方法（CQL、TT、DMamba 等）竞争力相当，在多个子任务上取得了最佳或次佳结果，表明其记忆机制不会损害全观测任务的表现。
- MRV 交叉注意力方案（MRV-CA-2）被证明是防止记忆覆盖最有效的设计；无 MRV 时 RATE 在长走廊上退化至 50%。
- 记忆嵌入负责保存稀疏的关键线索（如 T‑Maze 的初始方向），而缓存隐藏状态对密集连续反馈环境更重要——两者分工明确。
- 理论分析保证了 MRV 更新下记忆的下界保留，支持了实验观察。

## 7. 优点

- **方法创新**：首次将 Transformer 与具有显式信息流控制的循环记忆相结合，MRV 设计新颖且理论支撑充分。
- **综合记忆机制**：巧妙融合了三种互补策略，既能处理稀疏事件（记忆嵌入），又能处理密集反馈（缓存隐藏状态），并通过 MRV 防止信息丢失。
- **强大的泛化能力**：在训练时未见过的大幅超出上下文的数据上（T‑Maze 从 900 步推断到 9600 步）表现优异，展示了出色的外推能力。
- **广泛的适用性**：不仅在专门的记忆任务上领先，在标准 MDP 上也同样强大，是一个统一的离线 RL 架构。
- **实验系统性**：覆盖多种环境类型、大量基线和详细消融，结果统计可靠。
- **实用效率**：与 DT 相比，参数更少、GPU 内存占用显著降低（约 30–40%），计算更高效。

## 8. 不足与局限

- **过设计风险**：在完全可观测或短程任务中，RATE 的额外记忆机制可能显得冗余。尽管实验表明它仍能与简单模型竞争，但可能会带来不必要的复杂度。
- **超参数敏感性**：如附录所述，记忆令牌数量、缓存长度、是否使用前馈网络等需针对环境调优，缺乏自适应调节机制。
- **实验覆盖略有限制**：
  - 标准 MDP 基准仅涉及 4 个 Atari 游戏和 3 个 MuJoCo 任务/3 个难度，未覆盖更广泛的 D4RL 数据集（如 Ant、Kitchen 等）。
  - POPGym 虽包含 46 个任务，但评估仅使用了归一化平均分数，未对每个任务进行详细消融（尽管附录表 9 给出了完整结果）。
- **可扩展性讨论不足**：论文未详细分析 RATE 在极大规模离线数据集（如多任务数据池）上的表现，也缺乏与大模型（如 multi-game DT）的对比。
- **理论假设的局限**：Theorem 1 依赖于 α-对齐条件，该条件在训练中经验成立，但未提供严格的收敛保证或更一般的误差界。
- **缺乏在线 RL 评估**：RATE 仅用于离线 RL，其在在线微调或环境交互场景中的表现未知。

（完）
