---
title: "EDELINE: Enhancing Memory in Diffusion-based World Models via Linear-Time Sequence Modeling"
title_zh: "EDELINE: 通过线性时间序列建模增强扩散世界模型中的记忆"
authors: "Jia-Hua Lee, Bor-Jiun Lin, Wei-Fang Sun, Chun-Yi Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ph1V6n7BSv"
tags: ["query:agent-memory"]
score: 6.0
evidence: 通过线性时间序列建模增强世界模型中的记忆，服务于智能体长期记忆需求
tldr: 该论文针对扩散世界模型中固定上下文长度导致记忆容量受限的问题，提出了EDELINE，一种统一的世界模型，利用线性时间序列建模增强记忆容量。该方法在提高视觉保真度的同时，使智能体能够建模更长的环境动态，从而在强化学习任务中提升样本效率。实验表明，增强的记忆能力有助于智能体在长时间任务中保持更好的状态估计。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 1043, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1426, \"height\": 1719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1396, \"height\": 1158, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1402, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1401, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1400, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 983, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ph1v6n7bsv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1461, \"height\": 1817, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 1342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 1126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1175, \"height\": 1121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1389, \"height\": 852, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1514, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1338, \"height\": 936, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1310, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1225, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ph1v6n7bsv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1000, \"height\": 1735, \"label\": \"Table\"}]"
motivation: 扩散世界模型的固定上下文长度限制了记忆容量，无法有效处理长时依赖。
method: 提出EDELINE统一世界模型，采用线性时间序列建模替代固定上下文，扩展记忆窗口。
result: 在多种环境下的强化学习基准测试中，EDELINE优于基线，记忆增强带来性能提升。
conclusion: 线性时间序列建模可有效突破世界模型的记忆瓶颈，提升智能体长期规划能力。
---

## Abstract
World models represent a promising approach for training reinforcement learning agents with significantly improved sample efficiency. While most world model methods primarily rely on sequences of discrete latent variables to model environment dynamics, this compression often neglects critical visual details essential for reinforcement learning. Recent diffusion-based world models condition generation on a fixed context length of frames to predict the next observation, using separate recurrent neural networks to model rewards and termination signals. Although this architecture effectively enhances visual fidelity, the fixed context length approach inherently limits memory capacity.
In this paper, we introduce EDELINE, a unified world model architecture that integrates state space models with diffusion models. Our approach outperforms existing baselines across visually challenging Atari 100k tasks, memory-demanding Crafter benchmark, and 3D first-person ViZDoom environments, demonstrating superior performance in all these diverse challenges. Code is available at https://github.com/LJH-coding/EDELINE.

---

## 论文详细总结（自动生成）

### 中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有扩散世界模型（如 DIAMOND）依赖固定上下文长度（通常为 4 帧）进行下一帧预测，导致记忆容量受限，无法捕获长程时间依赖。此外，奖励/终止信号与观测预测采用分离的网络架构，阻碍了表示共享和优化协调，尤其在部分可观测环境中性能下降明显。
- **研究动机**：状态空间模型（SSM，如 Mamba）具有线性时间复杂度和理论上无限长的记忆能力，能够高效处理长序列。将 SSM 引入扩散世界模型，有望克服固定上下文的限制，同时保持高视觉保真度，提升样本效率。
- **整体含义**：EDELINE 提出了一种集成 SSM 的扩散世界模型统一架构，在多种记忆密集型基准上实现超越现有方法的性能，验证了长时记忆对世界模型的重要性。

#### 2. 论文提出的方法论
- **核心思想**：使用 Mamba 作为循环嵌入模块（Recurrent Embedding Module, REM），处理无界长度的观测-动作历史，生成隐藏状态 \( h_t \)。该隐藏状态同时输入给扩散模型进行下一帧预测，以及给 MLP 进行奖励/终止预测，实现统一架构。
- **关键技术细节**：
  - **REM**：基于 Mamba 的 SSM，在每一步更新输入当前 \( (o_t, a_t) \) 得到 \( h_t = f_\phi(h_{t-1}, o_t, a_t) \)，支持并行扫描计算。
  - **下一帧预测器**：U-Net 结构扩散模型，利用自适应组归一化（AGN）和交叉注意力将隐藏状态 \( h_t \) 与视觉特征融合，条件为最近 \( L \) 帧和 \( h_t \)。
  - **奖励/终止预测器**：简单 MLP，输入 \( h_t \) 输出奖励分布和终止二元分布，统一优化。
  - **动态损失协调**：采用 HarmonyDream 方法自适应加权观测损失 \( L_{obs} \) 和奖励损失 \( L_{rew} \)，避免高维观测主导优化。
  - **训练流程**：从回放缓冲区采样固定长度 T 的片段，使用 Mamba 并行计算所有隐藏状态，随机选择一个时间步（跳过 burn-in）计算观测损失，其他步骤计算奖励/终止损失。
- **公式与算法**（文字说明）：
  - 观测损失：\( L_{obs} = \mathbb{E}[\| D_\phi(o^\tau_{t+1}, y^\tau_t) - o^0_{t+1} \|^2] \)
  - 奖励/终止损失：\( L_{rew} = -\ln p_\phi(r_t | h_t) \), \( L_{end} = -\ln p_\phi(d_t | h_t) \)
  - 总损失：\( L = w_o L_{obs} + w_r L_{rew} + L_{end} + \log(w_o^{-1}) + \log(w_r^{-1}) \)
  - 算法伪代码见附录 E（Algorithm 1）。

#### 3. 实验设计
- **数据集/场景**：
  - **Atari 100k benchmark**：26 个 Atari 游戏，严格限制 100k 环境步。
  - **Crafter**：程序化生成的生存环境，强调记忆和推理。
  - **MiniGrid-MemoryS7/S9**：部分可观察的记忆任务。
  - **ViZDoom**：5 个第一人称 3D 场景（Basic, DeadlyCorridor, DefendCenter, HealthGathering, PredictPosition）。
- **基准对比方法**：SimPLe, TWM, IRIS, DreamerV3, STORM, DIAMOND, Drama, ∆-IRIS, HarmonyDream 等模型基和无搜索方法（世界模型类）。
- **评价指标**：人类归一化分数（HNS）、平均分、中位数、IQM、成功率、击杀数、健康值等，3 随机种子。

#### 4. 资源与算力
- **明确说明**：附录 D.7 给出了训练时间剖析，使用 **Nvidia RTX 4090** 单卡。
  - 单次更新：世界模型 148.6 ms，演员-评论家 400 ms，总计 548.6 ms。
  - 每个 epoch 约 219.4 秒。
  - 完整训练（1000 epochs）约 **2.9 天**（包含收集和评估等约 0.4 天）。
- 未说明使用的 GPU 数量，但根据时间推断为单卡。

#### 5. 实验数量与充分性
- **实验数量**：
  - 完整 Atari 100k 26 游戏 × 3 种子（78 runs）。
  - Crafter 1M 环境步，3 种子。
  - MiniGrid MemoryS7/S9 消融与对比。
  - ViZDoom 5 场景各 3 种子。
  - 消融实验：REM 架构（GRU, LSTM, Mamba）、交叉注意力、Harmonizers、帧堆叠、Transformer vs Mamba（附录 D.8）。
  - 线性探测分析（27 个环境）。
  - 生成质量 MSE 比较（27 个环境）。
- **充分性评价**：非常充分。涵盖 2D、3D、记忆任务；标准基准；多层次消融；统计显著性（误差条、置信区间）。实验设计客观公平，使用相同评估协议。

#### 6. 论文的主要结论与发现
- EDELINE 在 **Atari 100k** 达到 **1.87 平均 HNS**（超越人类 13 个游戏），优于所有无搜索方法，尤其提升在需要记忆的游戏中（如 BankHeist, Hero）。
- 在 **Crafter** 中平均回报 11.5（DreamerV3 XL 为 9.2），参数仅 11M（DreamerV3 XL 为 200M），计算效率高。
- 在 **ViZDoom** DeadlyCorridor 等场景中，EDELINE 预测更准确（保留粒子效果、装甲等细节），DIAMOND 则模糊丢失信息。
- 消融证明：SSM（Mamba）优于 GRU/LSTM；交叉注意力带来提升；Harmonizers 平衡视觉和奖励学习；隐藏状态 + 帧堆叠互补有效。

#### 7. 优点
- **架构创新**：首次将 SSM（Mamba）与扩散模型无缝集成，解决固定上下文长度限制，且保持高视觉保真度。
- **统一表示学习**：奖励/终止预测共享 REM 隐藏状态，不再需要独立网络，提高参数效率和优化效果。
- **动态损失协调**：自适应平衡观测与奖励目标，避免大尺度损失主导，提升训练稳定性。
- **广泛验证**：覆盖 2D、3D、记忆密集型环境，消融全面，实验设计严谨。
- **效率平衡**：Mamba 线性时间复杂性使得世界模型更新比 DIAMOND 快 26.8%，总训练时间相近但性能大幅提升。

#### 8. 不足与局限
- **计算开销**：扩散过程仍需多次前向传播（训练 3 步，推理 3 步），总体算力仍较高。
- **部分游戏表现不佳**：在 PrivateEye、Frostbite 等游戏上 EDELINE 低于某些基线，可能存在模型偏差或奖励稀疏问题。
- **未探索大规模 3D 环境**：ViZDoom 场景较小（64×64），未测试更高分辨率或更复杂 3D 场景。
- **超参数敏感性**：虽然文中使用固定超参数，但记忆增强可能引入新的调参挑战（如序列长度 T、burn-in B 的选择）。
- **应用限制**：主要面向 Atari 类图像输入，对连续控制或物理交互任务未验证，泛化性待进一步研究。

（完）
