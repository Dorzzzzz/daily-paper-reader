---
title: Blending Complementary Memory Systems in Hybrid Quadratic-Linear Transformers
title_zh: 混合二次-线性变换器中互补记忆系统的融合
authors: "Kazuki Irie, Morris Yau, Samuel J. Gershman"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Q8m0TkIpJZ"
tags: ["query:agent-memory"]
score: 8.0
evidence: 提出混合KV内存与快速权重内存的架构，与智能体记忆系统设计相关
tldr: 该论文针对通用序列处理网络提出混合记忆架构，融合了基于softmax注意力的键值记忆（KV-memory）和通过动态突触调节的快速权重记忆（FW-memory）。两种记忆系统具有互补但各自有限的特性：KV-memory提供精确检索但受限于序列长度的二次复杂度，FW-memory支持任意长序列和更富表达力的计算但牺牲精确回忆。作者提出并比较了三种融合方法，为内存系统设计提供了新思路，可迁移至智能体记忆系统。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8m0tkipjz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8m0tkipjz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q8m0tkipjz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 944, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 989, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 661, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 767, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 738, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 793, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1184, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q8m0tkipjz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 697, \"height\": 553, \"label\": \"Table\"}]"
motivation: KV-Memory与FW-Memory各有局限性，需要融合以兼顾精确检索与长序列处理能力。
method: 提出三种将KV-memory和FW-memory混合成单一记忆系统的方法，在输入信息传递方式上有所区别。
result: 通过实验比较了三种混合方法的性能，展示了融合记忆在序列处理上的优势。
conclusion: 混合记忆系统能够有效结合两种记忆的优点，为后续智能体记忆设计提供基准。
---

## Abstract
We develop hybrid memory architectures for general-purpose sequence processing neural networks, that combine key-value memory using softmax attention (KV-memory) with fast weight memory through dynamic synaptic modulation (FW-memory)---the core principles of quadratic and linear transformers, respectively. These two memory systems have complementary but individually limited properties: KV-memory offers precise retrieval but is constrained by quadratic complexity in sequence length, while FW-memory supports arbitrarily long sequences and enables more expressive computation but sacrifices precise recall. We propose and compare three methods to blend these two systems into a single memory system, differing in how and when input information is delivered to each system, to leverage the strengths of both. We conduct experiments on general language modeling and retrieval tasks by training 340M- and 1.3B-parameter models from scratch, as well as on synthetic algorithmic tasks designed to precisely illustrate the benefits of certain hybrid methods over others. We also evaluate our hybrid memory systems on reinforcement learning in partially observable environments. Overall, we demonstrate how a well-designed hybrid can overcome the limitations of its individual components, offering new insights into the design principle of neural memory systems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：标准的二次复杂度变换器（使用 softmax 注意力的 KV-memory）能实现精确记忆检索，但受限于序列长度的二次复杂度；线性变换器（使用快速权重记忆 FW-memory）支持任意长序列并具有更强表达力（如状态跟踪），但牺牲了精确召回。如何融合两种记忆系统的互补优势，构建一个通用的序列处理神经网络记忆系统？
- **研究动机**：借鉴大脑中互补学习系统（海马体与新皮层分工）的思路，提出一种将 KV-memory 与 FW-memory 混合的架构，以同时获得精确检索、长上下文处理和强表达性。
- **背景**：已有的混合工作（如 Arora 等使用 vanilla LA，Munkhdalai 等使用延迟分块方案）未充分考虑最新 DeltaNet 等 FW-memory 的进展，在表达性和设计选择上存在缺陷。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将 KV-memory（二次注意力的显式键值存储）与 FW-memory（DeltaNet 的快速权重矩阵）在同一层内融合，通过不同的信息传递时序实现分工与协同。
- **三种混合方法（HQLT）**：
  - **Delayed-Streaming HQLT**：KV-memory 维护一个固定大小的滑动窗口（S 个最近 token），当旧的键值对被移出窗口时，将其送入 FW-memory 更新。输出为两者加权和。
  - **Delayed-Chunk HQLT**：基于分块并行训练思路，每个块内使用 softmax 注意力的 KV-memory，块间使用 FW-memory 传递历史信息，FW-memory 仅在块边界更新。
  - **Synchronous HQLT**：每个时间步的输入同时送入 KV-memory 和 FW-memory，两者并行处理并输出加权混合。论文最终推荐此方案。
- **关键技术细节**：
  - FW-memory 采用 DeltaNet（delta 学习规则），包含可动态生成的学习率 β 和 SiLU 归一化激活函数。
  - 记忆混合策略：简单求和、动态标量混合、动态向量混合（生成门控向量 γ）。
  - 兼容 flash-attention 和 flash-linear-attention，支持高效训练与推理。

## 3. 实验设计：使用的数据集 / 场景、benchmark、对比方法
- **通用语言建模**：使用 FineWeb-Edu 数据集训练 340M 和 1.3B 参数模型，评估 WikiText-2（困惑度）、LAMBADA（困惑度+准确率）以及六个零样本常识推理任务（PIQA、HellaSwag、WinoGrande、ARC-easy、ARC-challenge）。
- **检索密集型任务**：SWDE（网页信息抽取）、SQuAD（阅读理解）、FDA（PDF 信息检索）。
- **合成算法任务**：Parity（奇偶识别）、Modular Arithmetic（模 5 加减乘），测试模型的状态跟踪表达能力。
- **强化学习**：部分可观测环境——“被动视觉匹配”任务，要求智能体在导航检索苹果后记住初始颜色并到达正确目标。
- **对比方法**：标准二次变换器（Transformer++）、DeltaNet（FW-memory 基线）、三种 HQLT 变体（Delayed-Stream、Delayed-Chunk、Synchronous），以及消融实验中的 vanilla LA 版本。

## 4. 资源与算力
- **训练硬件**：4 块 H100-80GB GPU。
- **训练时间**：
  - 340M 模型：Transformer 基线约 8 小时，DeltaNet 和 HQLT 约 10 小时。
  - 1.3B 模型：基线约 26 小时，HQLT 约 30 小时。
- **训练数据量**：约 15B tokens（340M 模型）和 16.4B tokens（1.3B 模型）。
- 文中未详细说明推理的算力需求，但指出短窗口注意力在推理时通常为内存受限，增加窗口大小影响不大。

## 5. 实验数量与充分性
- **实验组数**：
  - 通用语言建模：2 种规模 × 6 种模型/变体，包含多种评估指标，并附有消融实验（记忆混合策略、窗口大小、位置编码、是否使用 DeltaNet 等）。
  - 检索任务：3 个数据集，不同窗口大小和混合策略的对比。
  - 合成算法：2 个任务，每种模型跑 3 次随机种子，报告最佳结果和中间统计。
  - 强化学习：3 种模型，3 个种子，含 95% 置信区间。
- **充分性评估**：实验覆盖语言建模、检索、算法能力、RL 四个不同领域，模型规模从 340M 到 1.3B，消融研究全面（窗口大小、混合方式、位置编码、FW-memory 选择）。对比基线包括当时最先进的二次变换器和 DeltaNet，以及 vanilla LA。实验设置详细，结果可复现。因此实验较充分、客观且公平。

## 6. 论文的主要结论与发现
- **核心发现**：Synchronous HQLT（同步混合）在所有任务中表现最佳，能成功利用 FW-memory 的表达性（如处理 Parity 和 Modular Arithmetic），同时借助 KV-memory 进行精确检索。Delayed-Stream 和 Delayed-Chunk 在合成算法任务上失败，因为它们推迟了 FW-memory 接收输入的时间，无法实时进行状态跟踪。
- **通用语言建模**：HQLT 在 LAMBADA 困惑度上相对纯 Transformer 和 DeltaNet 提升约 15%；在平均零样本指标上略优于基线。
- **检索任务**：增大 KV-memory 窗口大小能显著提升 HQLT 的检索性能，但即使窗口很小（64），也能大幅超越纯 DeltaNet。
- **强化学习**：Synchronous HQLT（窗口 64）几乎弥合了 Transformer 与 DeltaNet 之间的性能差距，证明了短窗口注意力可借助 FW-memory 减轻干扰。
- **设计选择**：使用 DeltaNet 作为 FW-memory 是关键；vanilla LA 无法提供表达性优势。动态向量混合略优于其他混合策略。

## 7. 优点
- **系统性比较**：首次全面比较了三种基于时序分工的混合策略，并揭示了同步方案在表达性上的优势。
- **紧跟最新进展**：采用最新的 DeltaNet 及其高效并行训练算法，避免了前人工作中因使用落后 FW-memory 而得到的误导性结论。
- **跨领域验证**：从语言建模、检索、算法逻辑到强化学习，实验覆盖范围广，增强了结论的普适性。
- **代码开源**：提供了基于 fla 和 flame 框架的可复现代码。

## 8. 不足与局限
- **检索任务仍依赖大窗口**：即使混合了 FW-memory，精确检索仍需较大的 KV-memory 窗口（例如 1024），完全消除窗口限制仍有挑战。
- **延迟变体的局限性**：Delayed-Stream 和 Delayed-Chunk 在需要实时状态跟踪的任务上完全失败，说明它们不适合需要 FW-memory 随时介入的场景。
- **未探索更复杂的通信机制**：当前混合只是简单的加权求和，未能实现如 FW-memory 主动将旧记忆重新注入 KV-memory 等更智能的交互。
- **硬件效率未详细分析**：虽然提及兼容 flash-attention 等，但未给出详细的训练/推理速度对比数据。
- **规模**：最大只到 1.3B 参数，在更大规模（如 7B+）上的表现未知。
- **部分任务结果存在波动**：如检索任务（SWDE、FDA）对窗口大小变化敏感，可能受限于数据特性或评估协议。

（完）
