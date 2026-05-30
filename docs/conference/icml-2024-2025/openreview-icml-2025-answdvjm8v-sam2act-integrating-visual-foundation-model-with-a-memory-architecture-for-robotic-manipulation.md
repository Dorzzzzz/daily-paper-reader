---
title: "SAM2Act: Integrating Visual Foundation Model with A Memory Architecture for Robotic Manipulation"
title_zh: SAM2Act：融合视觉基础模型与记忆架构的机器人操作
authors: "Haoquan Fang, Markus Grotz, Wilbert Pumacay, Yi Ru Wang, Dieter Fox, Ranjay Krishna, Jiafei Duan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=anSWDvJm8v"
tags: ["query:agent-memory"]
score: 8.0
evidence: 用于机器人操作的记忆架构
tldr: "针对现有机器人操作方法在处理记忆相关任务时泛化能力不足的问题，本文提出SAM2Act，将大规模视觉基础模型与记忆架构相结合，通过多视图变换器策略实现多任务交互与空间记忆。在RLBench基准的18个任务上达到86.8%的平均成功率，展现了强大的泛化能力。该方法为机器人操作中的记忆系统设计提供了有效方案。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1326, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1396, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1249, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 912, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1647, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 785, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 719, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1778, \"height\": 794, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1787, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1780, \"height\": 247, \"label\": \"Table\"}]"
motivation: 现有机器人操作方法在处理依赖空间记忆的任务时泛化能力不足，亟需引入记忆架构。
method: 提出多视图机器人变换器策略，结合大规模视觉基础模型的多分辨率上采样与记忆架构。
result: "在RLBench的18个任务上达到86.8%的平均成功率，实现最先进性能。"
conclusion: 视觉基础模型与记忆架构的融合能有效提升机器人操作的泛化与记忆依赖任务能力。
---

## Abstract
Robotic manipulation systems operating in diverse, dynamic environments must exhibit three critical abilities: multitask interaction, generalization to unseen scenarios, and spatial memory. While significant progress has been made in robotic manipulation, existing approaches often fall short in generalization to complex environmental variations and addressing memory-dependent tasks. To bridge this gap, we introduce **SAM2Act**, a multi-view robotic transformer-based policy that leverages multi-resolution upsampling with visual representations from large-scale foundation model. SAM2Act achieves a state-of-the-art average success rate of **86.8% across 18 tasks** in the RLBench benchmark, and demonstrates robust generalization on *The Colosseum* benchmark, with only a **4.3% performance gap** under diverse environmental perturbations. Building on this foundation, we propose **SAM2Act+**, a memory-based architecture inspired by SAM2, which incorporates a memory bank, an encoder, and an attention mechanism to enhance spatial memory. To address the need for evaluating memory-dependent tasks, we introduce ***MemoryBench***, a novel benchmark designed to assess spatial memory and action recall in robotic manipulation. SAM2Act+ achieves an average success rate of **94.3% on memory-based tasks** in *MemoryBench*, significantly outperforming existing approaches and pushing the boundaries of memory-based robotic systems.
Project page: [sam2act.github.io](https://sam2act.github.io/).

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义

- **研究动机**：机器人操作需要在多样、动态环境中同时具备**多任务交互、对未见场景的泛化能力、以及空间记忆**。现有方法（如PerAct、RVT、RVT-2）在多任务和泛化上取得了进展，但在处理需要记忆的复杂环境变化和记忆依赖型任务时仍显不足。
- **核心问题**：如何将**大规模视觉基础模型（SAM2）**与**记忆架构**有效结合，使机器人策略能实现高精度操作、鲁棒泛化，并具备空间记忆推理能力。
- **整体含义**：本文提出的SAM2Act和SAM2Act+代表了将通用视觉表示与显式记忆机制引入机器人操作的重要一步，推动了通用机器人操作系统的能力边界。

## 2. 论文提出的方法论

### 核心思想
- 基于**RVT-2**的多视图变换器框架，引入**SAM2图像编码器**生成多分辨率视觉嵌入，并通过**多分辨率上采样**技术增强特征表示。
- 为处理空间记忆任务，提出**SAM2Act+**，在粗分支中集成**记忆银行、记忆编码器、记忆注意力**三个模块（源自SAM2的目标追踪架构），使策略能利用历史动作和观察进行序贯决策。

### 关键技术细节
- **SAM2Act架构**：
  - 输入：多视角RGB-D图像 → 重建点云 → 从三个虚拟相机渲染虚拟图像。
  - 将虚拟图像的RGB通道复制后送入SAM2图像编码器，产生多分辨率嵌入。
  - 使用**LoRA（rank=16）**微调SAM2编码器以适应操作域。
  - **多分辨率上采样**：级联三个凸上采样器，每个阶段将特征图尺寸加倍，并与SAM2对应分辨率的嵌入进行元素相加和层归一化，逐步生成精确的平移热图。
  - 粗分支预测平移粗热图，细分支进一步细化并预测旋转等动作。
- **SAM2Act+架构**：
  - 冻结SAM2编码器、多视图变换器及细分支，仅微调粗分支。
  - 将记忆机制集成到粗分支中：记忆注意力对当前观察嵌入和历史记忆进行交叉注意力；记忆编码器将预测热图与未加记忆的嵌入融合生成新记忆；记忆银行以FIFO队列存储每视图独立的历史记忆。
  - 训练时采用**连续关键帧采样**（从同一episode中采样N个连续观测），依次前向传播。

## 3. 实验设计

### 数据集 / 场景
- **RLBench**：选择18个标准任务（如Close Jar、Insert Peg、Sort Shape等），共249种变体（物体位置、颜色、大小、类别等）。
- **The Colosseum**：含20个任务，13种环境/物体扰动（如光照、颜色、纹理、大小、遮挡、相机姿态等），用于评估泛化能力。
- **MemoryBench**：新提出的空间记忆基准，包含3个任务：
  - **reopen drawer**：记忆初始打开的抽屉（3个抽屉），关门并按键后重新打开。
  - **put block back**：记忆方块初始位置（4个色块），移走后放回。
  - **rearrange block**：记忆哪个方块未被移动，反向推理移动正确方块。
- **真实世界实验**：使用Franka Panda机器人，4个真实任务（开灯、按钮序列、堆叠方块、记忆按钮位置）。

### 对比方法
- **3D关键帧行为克隆基线**：PerAct、RVT、RVT-2、SAM-E。
- 额外对比非3D方法（如Image-BC、C2F-ARM-BC、HiveFormer、PolarNet、Act3D、3D Diffuser Actor、3D-LOTUS、ARP+等）——见附录C。

### 实验设置
- 所有仿真实验在CoppeliaSim/PyRep中运行，5个RGB-D摄像头（128×128），7自由度Franka Panda机器人。
- 每个任务收集100个演示用于训练，25个未见演示用于测试。每个策略评估4次取均值和标准差。
- 真实实验：每任务10个分布内和10个分布外试验。

## 4. 资源与算力

- **训练资源**：使用**32块 NVIDIA H100/A100 GPU**，有时也使用16或8块，但保持总batch size一致以保证公平。
- **训练步数**：RLBench上SAM2Act训练**56.25K步**（90 epochs），MemoryBench上SAM2Act训练**6.25K步**（10 epochs），SAM2Act+微调**12.5K步**（20 epochs）。
- **batch size**：RLBench上总batch size为256，MemoryBench上根据任务窗口大小调整（如reopen drawer为256，其余为320）。
- **优化器**：LAMB，学习率与batch size成比例（1.25e⁻⁵ × bs），余弦衰减，warmup 2000步。
- 文中明确给出了算力信息。

## 5. 实验数量与充分性

- **实验数量**：
  - RLBench 18任务 × 4次评估 = 72组测试。
  - The Colosseum 20任务 × 3次评估 × 13种扰动 = 大量对比。
  - MemoryBench 3任务 × 4次评估 = 12组测试。
  - 真实世界4任务 × 各10次（分布内+分布外）≈ 80次试验。
  - 消融实验：替换图像编码器（SAM/DINOv2/Depth Anything V2）、移除多分辨率输入、替换上采样方式等，均在RLBench和The Colosseum上进行了对比。
- **充分性**：实验覆盖多任务性能、泛化能力、记忆能力、真实世界迁移，且与多个SOTA基线对比，统计了均值和标准差。消融实验系统验证了各组件贡献。因此实验设计充分、客观、公平。

## 6. 论文的主要结论与发现

- SAM2Act在RLBench 18个任务上平均成功率**86.8%**，超越RVT-2（81.4%）和ARP+（84.9%），尤其在需要高精度的任务（如Insert Peg提升44%）上优势显著。
- 在The Colosseum泛化测试中，SAM2Act平均性能下降仅**-4.3%**，远优于基线（RVT-2下降-19.5%），对环境扰动（光照、颜色、纹理等）鲁棒。
- SAM2Act+在MemoryBench上平均成功率**94.3%**，远超无记忆机制的SAM2Act（55.0%）和RVT-2（54.0%），证明显式记忆建模的必要性。
- 真实世界实验中，SAM2Act在分布内/外性能均优于RVT-2，记忆任务中SAM2Act+成功率达70%。

## 7. 优点

- **创新性**：首次将SAM2的多分辨率特征与多视图变换器深度结合，并引入源自SAM2的记忆机制解决操作中的空间记忆问题，设计巧妙。
- **实验全面**：覆盖仿真多任务、泛化、记忆新基准、真实场景，消融实验详实，对比基线包括最新方法。
- **性能突出**：多个标准上达到SOTA，尤其在高精度和记忆任务上表现亮眼。
- **泛化能力强**：对多种环境扰动稳健，证明视觉基础模型带来的特征鲁棒性。
- **开放贡献**：开源MemoryBench基准，有助于推动记忆型机器人操作的研究。

## 8. 不足与局限

- **内存机制局限性**：SAM2Act+依赖固定窗口长度的FIFO记忆银行，不同任务需要调整窗口大小，限制了跨任务的自适应能力和长序列应用。
- **未扩展到灵巧控制**：目前仅适用于6-DoF末端执行器操作，未涉及灵巧手连续控制。
- **训练复杂度**：SAM2Act+需要两阶段训练（先预训练SAM2Act，再微调记忆模块），且连续关键帧采样降低了数据多样性，收敛较慢。
- **真实场景规模有限**：仅4个真实任务，且场景相对简单，未在更复杂动态环境（如多物体遮挡、动态干扰）中验证。
- **记忆推理类型**：MemoryBench任务主要测试空间位置记忆，未涉及语义/长期任务规划记忆，评价维度稍窄。
- **偏差风险**：所有演示通过脚本生成，可能存在与真实人类演示的分布偏移。

（完）
