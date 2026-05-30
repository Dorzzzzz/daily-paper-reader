---
title: "Think Before You Act: Decision Transformers with Working Memory"
title_zh: 三思而后行：带工作记忆的决策Transformer
authors: "Jikun Kang, Romain Laroche, Xingdi Yuan, Adam Trischler, Xue Liu, Jie Fu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=PSQ5Z920M8"
tags: ["query:agent-memory"]
score: 9.0
evidence: 决策Transformer智能体的工作记忆模块
tldr: 决策Transformer在多任务学习中存在遗忘现象。受人类分布式记忆启发，本文提出工作记忆模块，用于存储、融合和检索不同下游任务的信息。评估表明，该模块有效缓解了遗忘，提升了多任务泛化能力，减少了数据和计算需求。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1217, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 1101, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1752, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1321, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-psq5z920m8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1676, \"height\": 1278, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1570, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 632, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1200, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1641, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1509, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 794, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 832, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 791, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 977, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 796, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-psq5z920m8/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1137, \"height\": 287, \"label\": \"Table\"}]"
motivation: 决策Transformer在多任务学习中因参数式记忆导致遗忘，效率低。
method: 提出外挂工作记忆模块，实现信息的显式存储、混合与检索。
result: 在多个任务上减少了遗忘，提升了泛化性能和数据效率。
conclusion: 工作记忆模块为智能体提供更高效的持续学习机制。
---

## Abstract
Decision Transformer-based decision-making agents have shown the ability to generalize across multiple tasks. However, their performance relies on massive data and computation. We argue that this inefficiency stems from the forgetting phenomenon, in which a model memorizes its behaviors in parameters throughout training. As a result, training on a new task may deteriorate the model's performance on previous tasks. In contrast to LLMs' implicit memory mechanism, the human brain utilizes distributed memory storage, which helps manage and organize multiple skills efficiently, mitigating the forgetting phenomenon. Inspired by this, we propose a working memory module to store, blend, and retrieve information for different downstream tasks. Evaluation results show that the proposed method improves training efficiency and generalization in Atari games and Meta-World object manipulation tasks. Moreover, we demonstrate that memory fine-tuning further enhances the adaptability of the proposed architecture.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：基于Decision Transformer（DT）的多任务决策智能体虽然展现出跨任务泛化能力，但其性能严重依赖大规模数据和计算资源。根本原因在于DT将行为“记忆”在模型参数中（隐性记忆），导致训练新任务时出现**遗忘现象**（catastrophic forgetting），即新任务损害旧任务性能。
- **研究动机**：受人类大脑分布式记忆存储机制启发——人类能高效管理和组织多项技能，缓解遗忘。具体而言，人类会“三思而后行”：利用过往经验进行推理，在新情境下生成恰当行为。
- **整体含义**：本文提出显式的工作记忆模块（Working Memory），用于存储、混合和检索不同下游任务的信息，以提升Transformer智能体的训练效率和多任务泛化能力，同时减少模型参数规模和计算需求。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：在标准Decision Transformer架构上增加一个**工作记忆模块**，该模块作为一个固定大小的可寻址矩阵，通过内容寻址的注意力机制实现信息的写入（记忆更新）和读取（记忆检索）。预训练时记忆模块与Transformer端到端联合训练；下游任务适应时仅用LoRA低秩适配方法微调记忆模块。
- **关键技术细节**：
  - **记忆初始化**：记忆矩阵 $M \in \mathbb{R}^{N \times d}$，$N$ 个记忆槽，每个槽 $d$ 维。
  - **输入组织**：将轨迹元组 (return-to-go, state, action) 嵌入到同一隐空间，拼接成输入序列 $E$。
  - **内容寻址**：用记忆 $M$ 作为查询 $Q$，输入 $E$ 作为键 $K$，计算注意力权重 $w = \text{softmax}(QK^T / \sqrt{d})$，定位对应记忆槽。
  - **记忆更新**：
    - 计算擦除向量 $\epsilon_e = w \odot (1 - \beta)$，其中 $\beta = \text{softmax}(\hat{Q}\hat{K}^T / \sqrt{d})$ 为写入强度。
    - 计算添加向量 $\epsilon_a = (w \odot \beta) \hat{W}_v x$。
    - 更新规则：$M_t = M_{t-1} \odot (1 - \epsilon_e) + \epsilon_a$。
  - **记忆检索**：用同一注意力权重读取更新后的记忆：$E_{\text{out}} = w \odot M_t$。
  - **损失函数**：包含动作、奖励、return-to-go三项预测的均方误差之和。
  - **微调策略（LoRA）**：在记忆模块的线性投影层（$W_q, W_k, W_v$等）添加低秩分解矩阵 $B A$，仅更新 $B$ 和 $A$（秩 $r \ll d$），固定预训练Transformer参数。

## 3. 实验设计

- **数据集/场景**：
  - **Atari游戏**：使用Multi-Game DT（MDT）相同的DQN轨迹数据集，覆盖17个训练游戏（按字母顺序选取），4个保留游戏（Alien, Ms. Pac-Man, Space Invaders, Star Gunner）用于零样本泛化测试，另选9个游戏用于微调适应性评估。
  - **Meta-World ML45**：包含45个训练任务和5个测试任务（如物体操作），每个任务1000个回合的离线数据集。
- **对比方法**：
  - Atari：对比MDT（多游戏DT，同参数规模及更大规模）、RMDT（循环记忆DT）。
  - Meta-World：对比HDT（超网络DT）、PDT（提示DT）。
- **评估指标**：DQN归一化分数、人类归一化IQM分数、平均成功率等。

## 4. 资源与算力

- **训练设备**：8块V100 GPU用于预训练，1块V100 GPU用于微调。
- **训练步数**：预训练10M步，微调100k步。
- **模型规模**：DT-Mem-20M（Transformer 13M + 记忆模块 7M参数）；对比MDT-13M、MDT-40M、MDT-200M等。
- **训练时间**：DT-Mem-20M约50小时，MDT-13M约200小时，MDT-200M约1600小时（节省4-32倍）。
- **微调参数量**：LoRA仅147K参数（占原始模型0.7%）。

## 5. 实验数量与充分性

- **实验组数**：
  - Atari零样本泛化：4个保留游戏，每个16次不同随机种子运行，报告均值与95%置信区间。
  - Atari微调适应性：9个未见游戏，对比DT-Mem、RMDT、MDT。
  - Atari训练性能：17个游戏上相对基准数据集最优分数的提升。
  - Meta-World：5个测试任务上对比HDT、PDT，报告训练、零样本、微调结果。
  - 消融实验：
    - 记忆槽数量的影响（Bayes优化）。
    - LoRA vs. 全微调 vs. 超网络变体。
    - LoRA超参数（rank, dropout, alpha）的敏感度分析。
    - 输入组织方式（Trajectory Transformer vs. Decision Transformer类型）。
    - 不同微调数据量下的对比。
    - 噪声鲁棒性测试（添加高斯噪声）。
- **充分性与公平性**：
  - 所有对比方法在相同环境、相同数据集、相同评估协议下进行。
  - 多次随机种子取平均，减少偶然性。
  - 对比基线包括同规模及更大规模模型，结果具有说服力。
  - 消融实验覆盖主要设计选择，分析深入。

## 6. 主要结论与发现

- **泛化能力**：DT-Mem在4个保留Atari游戏上的DQN归一化分数远高于MDT和RMDT（如Alien: 51.0% vs 3.8% vs 22.3%），表明工作记忆模块显著提升零样本泛化。
- **训练效率**：DT-Mem-20M达到与MDT-200M相当的IQM分数，但仅需1/10参数和1/32训练时间；且DT-Mem-50M超越MDT-200M 16.7%。
- **适应能力**：LoRA微调仅用147K参数（0.7%），在Meta-World上取得最高测试集成功率（0.95），优于HDT（0.92）和PDT（0.09）。
- **记忆规模影响**：记忆槽数量存在最优范围（约1200-1800），过大或过小都会降低性能。
- **LoRA优势**：相比全微调，LoRA更适应小数据场景，有效缓解灾难性遗忘。

## 7. 优点

- **新颖视角**：将认知科学中的“工作记忆”概念引入Transformer决策智能体，显式存储跨任务知识，避免依赖参数隐性记忆导致的遗忘。
- **高效轻量**：记忆模块参数仅占Transformer的约54%（7M vs 13M），但带来显著的性能/效率提升；LoRA微调极轻量（147K），便于任务切换。
- **强实验论证**：在多种环境（Atari, Meta-World）、多种对比基线（同规模/大规模/记忆变体）下验证，消融实验完整，结果统计稳健。
- **可扩展性**：DT-Mem性能随模型参数增加而提升，且学习曲线陡峭，表明记忆模块充分利用数据。
- **鲁棒性**：对输入噪声具有较好容忍度（std=0.5时性能几乎不变）。

## 8. 不足与局限

- **样本效率仍有限**：微调使用了10%数据集（约50k步），仍有提升空间；低数据场景下泛化能力未知。
- **缺乏在线交互**：仅适用于离线数据，未设计在线数据收集或探索策略，限制了真实环境适应能力。
- **理论解释不足**：工作记忆为何能缓解遗忘、如何组织技能等内在机理缺乏正式理论分析。
- **记忆可视化有限**：仅对两游戏可视化，未展示所有任务下的记忆分布模式。
- **超参数敏感**：记忆槽数量、LoRA秩等需仔细调优（尤其记忆槽数），最优值可能依赖任务集。
- **基准选择局限**：未与更多当代可扩展记忆方法（如Infinity-former, kNN-Transformer等）直接对比（因无法直接应用于DT）。
- **应用限制**：当前仅在模拟环境验证，未考虑真实机器人部署中的安全性和伦理问题。

（完）
