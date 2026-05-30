---
title: "VAGEN: Reinforcing World Model Reasoning for Multi-Turn VLM Agents"
title_zh: VAGEN：通过强化学习增强多轮VLM智能体的世界模型推理
authors: "Kangrui Wang, Pingyue Zhang, Zihan Wang, Yaning Gao, Linjie Li, Qineng Wang, Hanyang Chen, Yiping Lu, Zhengyuan Yang, Lijuan Wang, Ranjay Krishna, Jiajun Wu, Li Fei-Fei, Yejin Choi, Manling Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xpjWEgf8zi"
tags: ["query:agent-memory"]
score: 4.0
evidence: VLM智能体的世界模型推理，包含状态与转移记忆
tldr: 该论文针对VLM智能体在部分可观察视觉环境中的推理问题，通过强化学习强制智能体进行显式的世界模型推理，将推理过程分解为状态估计和转移建模两个步骤，实验表明这种结构显著提升了多轮交互中的决策性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1170, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1425, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1144, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 234, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 237, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 246, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 244, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 235, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 238, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 235, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 244, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 234, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 235, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 232, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 238, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 232, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 236, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 235, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 232, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 235, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpjwegf8zi/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 237, \"height\": 233, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1295, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1303, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1415, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1415, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1474, \"height\": 968, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1386, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1282, \"height\": 117, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1532, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1387, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1722, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1551, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1502, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1501, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1500, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1629, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1533, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1441, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1444, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1445, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1130, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 773, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpjwegf8zi/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1206, \"height\": 284, \"label\": \"Table\"}]"
motivation: VLM智能体在视觉观察下存在部分可观察性，需要更强的世界建模能力。
method: 将推理拆分为状态估计和转移建模，并通过强化学习进行奖励和约束。
result: 在多个VLM任务上，显式世界模型推理优于基线。
conclusion: 结构化推理是提升VLM智能体鲁棒性的关键。
---

## Abstract
A major challenge in training VLM agents, compared to LLM agents, is that states shift from simple texts to complex visual observations, which introduces partial observability and demands robust world modeling. We ask: can VLM agents build internal world models through explicit visual state reasoning? In this work, we architecturally enforce and reward VLM agent’s reasoning process via reinforcement learning (RL), formulating the problem as a Partially Observable Markov Decision Process (POMDP). We demonstrate that structuring agent’s reasoning into StateEstimation (“what is the current state?”) and TransitionModeling (“what is next?”) is critical by studying five reasoning strategies. Investigating how agents should ground visual states and represent these internal beliefs, we reveal the optimal representations are task-dependent: Natural Language excels at capturing semantic relationships for general tasks, while Structured formats are essential for high-precision manipulation. These insights motivate our approach to reward shaping and credit assignment. We leverage a WorldModeling Reward to densely rewards the agent’s turn-by-turn state predictions, while our Bi-Level General Advantage Estimation (Bi-Level GAE) enables turn-aware credit assignment. Through such world model reasoning, we enable a 3B model to achieve performance of 0.82 on a set of five diverse agent tasks, nearly 3× improvement over its untrained counterpart (0.21) and surpassing proprietary reasoning models like GPT-5 (0.75), Gemini 2.5 Pro (0.67) and Claude 4.5 (0.62). All experiments are supported by our VAGEN framework, a scalable system for training and analyzing multi-turn VLM agents across diverse visual environments

---

## 论文详细总结（自动生成）

# 论文总结：VAGEN: Reinforcing World Model Reasoning for Multi-Turn VLM Agents

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉-语言模型（VLM）智能体在多轮交互任务中，面临从复杂视觉观测获得部分可观察性（POMDP问题）的挑战，相比文本智能体（LLM）更难。现有方法缺乏显式的内部世界建模来强化视觉状态推理。
- **核心问题**：如何有效训练VLM在视觉环境中构建内部世界模型，通过显式的视觉状态推理（状态估计和转移建模）来提升多轮决策能力？
- **整体含义**：本文提出通过强化学习（RL）让VLM智能体进行结构化推理（状态估计+转移建模），并结合奖励塑形和信用分配技术，显著提升多轮视觉任务性能，使得3B小模型超越GPT-5等大模型。

## 2. 方法论

### 核心思想
- 将多轮VLM智能体任务建模为**部分可观察马尔可夫决策过程（POMDP）**，智能体需先估计世界状态（StateEstimation），再预测下一状态（TransitionModeling）。
- 在RL训练中，强制智能体在输出中显式包含结构化推理令牌（`<observation>`, `<reasoning>`, `<prediction>`），并利用格式奖励、任务奖励和世界模型奖励进行优化。

### 关键技术细节
1. **推理策略对比**：设计了五种推理策略：
   - NoThink: 仅输出执行动作
   - FreeThink: 自由自然语言推理
   - StateEstimation: 仅估计当前状态
   - TransitionModeling: 仅预测下一状态
   - WorldModeling: 同时估计当前状态和预测下一状态（最佳）
2. **奖励设计**：
   - 格式奖励（r_format）：鼓励结构化输出
   - 环境任务奖励（R(s_t,a_t)）：稀疏的二进制或连续相似度
   - **WorldModeling Reward**：利用LLM-as-a-Judge（GPT-4.1 nano）评估智能体状态描述和预测的准确性，提供密集的逐轮奖励
3. **信用分配**：
   - **Bi-Level Generalized Advantage Estimation (Bi-Level GAE)**：先计算轮级优势（turn-level），再反向传播到轮内令牌级别，解决长程信用分配不稳定问题。
4. **训练流程**：基于PPO算法，采用actor-critic架构，使用verl框架。智能体生成`<think>...<observation>...<reasoning>...<prediction>...</think><answer>...</answer>`格式的输出。

### 算法流程（文字描述）
- 在每个回合t，VLM根据当前观测o_t生成动作a_t（包含推理和可执行动作），环境返回奖励r_t和新观测o_{t+1}。
- 收集完整轨迹后，使用Bi-Level GAE计算每个令牌的优势值，再利用PPO目标更新策略和值函数。

## 3. 实验设计

### 使用的数据集/场景
- **五个不同的智能体任务**：
  1. Sokoban（经典推箱子）
  2. FrozenLake（冰湖导航）
  3. Navigation（3D室内导航，基于AI2-THOR）
  4. PrimitiveSkill（机器人操作：放置、堆叠、抽屉对齐等，基于ManiSkill3）
  5. SVG Reconstruction（根据目标图像生成SVG代码）

### Benchmark
- 对比了多种模型：
  - **开源模型**：Qwen2.5-VL-3B/7B/72B, VLM-R1-3B
  - **闭源模型**：GPT-5, o3, o4-mini, GPT-4o, Gemini 2.5 Pro, Gemini 2.0, Claude 4.5 Sonnet, Claude 3.7 Sonnet
- RL基线：Vanilla-PPO, GRPO w/ Mask, Turn-PPO w/ Mask

### 评估指标
- 任务成功率的均值 (Sokoban, FrozenLake, Navigation, PrimitiveSkill)
- DreamSim和DINO相似度 (SVG)
- 总体性能：五个任务的平均分数

## 4. 资源与算力

- 论文明确指出：使用8×H100 GPU，104 CPU，1.7TB内存。每个训练会话约需4-8小时。
- 具体各任务GPU小时数（附录表26）：
  - FrozenLake: ~40 H100 GPU小时
  - Sokoban: ~40 H100 GPU小时
  - Navigation: ~30 H100 GPU小时
  - PrimitiveSkill: ~30 H100 GPU小时
  - SVG: ~10 H100 GPU小时
- LLM-as-a-Judge令牌消耗：约2.3×10^7（FrozenLake/Sokoban）到4.6×10^6（ManiSkill）等。

## 5. 实验数量与充分性

- **实验数量**：非常充分。包括：
  - 五种推理策略对比（NoThink, FreeThink, StateEstimation, TransitionModeling, WorldModeling）
  - 三种视觉状态表示对比（自然语言、符号、结构化）
  - 奖励设计消融（WorldModeling Reward, Bi-Level GAE, 以及全组合）
  - 多个RL基线对比
  - 不同模型规模和家族（3B, 7B, InternVL3-2B）
  - 每个任务独立训练和测试
- **充分性/公平性**：
  - 控制变量（相同架构、大小）进行对比
  - 包含开源和闭源模型，设置合理系统提示和温度（0.7）
  - 进行了详细的消融研究，验证每个组件贡献
- 但未提供多次运行的标准差或置信区间（由于计算资源限制），是一个不足。

## 6. 主要结论与发现

1. **显式世界模型推理显著提升性能**：WorldModeling策略平均得分0.76，远超NoThink（0.28）和FreeThink（0.67）。
2. **最优状态表示依赖于任务**：自然语言适合通用任务（Sokoban/FrozenLake），结构化格式适合精准操作（PrimitiveSkill），符号表示最差。
3. **WorldModeling Reward + Bi-Level GAE进一步提升**：VAGEN-Full达到0.82，超过所有封闭模型和基线，验证了密集奖励和细粒度信用分配的有效性。
4. **现有RL方法不足**：Vanilla-PPO、GRPO、Turn-PPO均不如VAGEN方法。
5. **3B模型超越大模型**：Qwen2.5-VL-3B在VAGEN-Full下超过GPT-5（0.75）等模型。
6. **可迁移性**：Bi-Level GAE可作为通用插件提升FreeThink等其他方法。

## 7. 优点

- **方法创新**：首次将POMDP显式建模、世界模型推理与多轮RL系统结合，并引入Bi-Level GAE解决信用分配问题。
- **实验全面**：覆盖多种任务类型（2D、3D导航、机器人操作、图像生成），对比大量开源/闭源模型，消融实验清晰。
- **实用性**：仅用3B模型即可达到SOTA，对算力要求相对较低（几十个GPU小时），易于复现。
- **开源框架**：提供了VAGEN框架和代码（代码已开源于GitHub），便于社区扩展。
- **细致分析**：包含对奖励作弊（reward hacking）、响应收敛、熵下降等行为的观察。

## 8. 不足与局限

- **模型单一**：主要基于Qwen2.5-VL系列，未在其他架构（如LLaVA, InternVL）上充分验证（仅附录有一个InternVL3-2B小实验）。
- **环境有限**：仅包含5个特定环境，未在更多真实复杂场景（如具身AI、GUI操作）中评估。
- **无误差棒**：未报告多次运行的标准差，实验结果稳定性未知。
- **潜在奖励作弊**：LLM-as-a-Judge可能被对抗性生成绕过，需持续监控。
- **推理收敛问题**：训练后期响应趋于模板化，可能损失多样性。
- **仅采用Qwen2.5-VL-3B作为骨干**：未探索更大模型（如7B/72B）在相同训练下的表现（仅少量对比）。
- **应用限制**：当前方法依赖于可获取文本化ground truth状态的环境，实际应用可能受限。
- **计算开销**：LLM-as-a-Judge调用会增加额外推理成本（尤其token消耗大）。

（完）
