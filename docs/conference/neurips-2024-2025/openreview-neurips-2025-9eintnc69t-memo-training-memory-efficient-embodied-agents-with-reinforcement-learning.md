---
title: "Memo: Training Memory-Efficient Embodied Agents with Reinforcement Learning"
title_zh: Memo：通过强化学习训练记忆高效的具身智能体
authors: "Gunshi Gupta, Karmesh Yadav, Zsolt Kira, Yarin Gal, Rahaf Aljundi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9eIntNc69t"
tags: ["query:agent-memory"]
score: 8.0
evidence: 设计基于Transformer的记忆架构用于具身智能体
tldr: 具身智能体在长时间任务中面临上下文窗口限制，难以高效利用记忆。本文提出Memo架构，采用Transformer结合压缩记忆机制，将大量视觉输入抽象为紧凑表示，使智能体在强化学习训练下能够有效利用长期记忆。实验证明Memo在需要长期情境感知的任务上显著优于RNN和全上下文Transformer基线，为智能体记忆架构设计提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 830, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 626, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1452, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9eintnc69t/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 493, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9eintnc69t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1294, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9eintnc69t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 1612, \"label\": \"Table\"}]"
motivation: 具身智能体在长时间任务中视觉输入超出Transformer上下文限制，缺乏高效记忆压缩。
method: 提出Transformer架构结合记忆压缩机制，将视觉输入抽象为紧凑记忆。
result: 在多种长期任务上优于RNN和全上下文Transformer基线。
conclusion: Memo为具身智能体提供了高效的记忆架构。
---

## Abstract
To enable embodied agents to operate effectively over extended timeframes, it is crucial to develop models that form and access memories to stay contextualized in their environment. In the current paradigm of training transformer-based policies for embodied sequential decision-making tasks, visual inputs often overwhelm the context limits of transformers, while humans can maintain and utilize a lifetime of experience compressed as memories. Significant compression is possible in principle, as much of the input is irrelevant and can be abstracted. However, existing approaches predominantly focus on either recurrent models with fixed-size memory or transformers with full-context reliance. In this work, we propose Memo, a transformer-based architecture and training recipe for reinforcement learning (RL) on memory-intensive, long-horizon tasks. Memo incorporates the creation and retrieval of memory by interleaving periodic summarization tokens with the inputs of a model during training. We demonstrate Memo’s effectiveness on a grid-world meta-RL benchmark and a multi-object navigation task in photo-realistic indoor settings. Memo outperforms naive long-context transformer baselines while being more compute and storage efficient. Additionally, Memo generalizes better to longer contexts at inference time and remains robust in streaming settings, where historical context must be truncated to fit inference constraints.

---

## 论文详细总结（自动生成）

# Memo：通过强化学习训练记忆高效的具身智能体——论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：具身智能体在长时间跨度的决策任务中，需要持续记忆和利用环境信息以保持情境感知。然而，当前基于Transformer的策略网络在输入视觉序列时，其上下文窗口长度有限，而人类能够压缩并存储一生的经验，只保留任务相关细节。
- **核心问题**：现有的方法要么依赖固定大小的循环神经网络（RNN）记忆，要么依赖全上下文注意力的Transformer，前者容量受限且梯度传播困难，后者计算开销大（二次复杂度）、难以扩展至长序列，且在推理时需要存储巨大的KV缓存。
- **整体含义**：亟需一种能自我学习压缩经验、同时保持长时推理能力的高效记忆架构，以提升具身智能体在长期任务中的性能和可扩展性。

## 2. 论文提出的方法论

### 2.1 核心思想
- **Memo**：一种基于Transformer的架构与训练方案，通过插入可学习的**摘要Token (summarization tokens)**，让模型定期将过去经验压缩成紧凑的记忆表示，并在后续步骤中通过注意力机制访问这些摘要，从而替代对完整历史序列的依赖。

### 2.2 关键技术细节
- **上下文切分与摘要生成**：将长输入序列划分为固定长度 `l_seg` 的片段，在每个片段末尾生成 `l_sum` 个摘要Token。这些摘要Token存储于专用记忆缓冲区，后续片段通过注意力机制仅访问摘要和当前片段内的观测，形成信息瓶颈。
- **注意力掩码**：采用因果掩码，只允许当前片段中的观测和之前所有摘要Token被注意，禁止直接访问已过时的历史观测，迫使模型通过摘要传递历史信息。
- **位置编码**：摘要Token的位置索引按累计片段数量递增，观测Token的位置索引在片段内相对排列，确保位置信息正确性。
- **片段长度随机化**：训练时在每个片段长度上随机化（±20%固定值），避免模型过拟合固定边界。
- **KV缓存维护**：结合ReLIC的在线策略更新，每次策略更新后刷新KV缓存和摘要向量，保持一致性。

### 2.3 算法流程（文字说明）
- 训练时，将整个试次的观测序列按 `l_seg` 切分，每个片段先馈入带摘要Token的Transformer，生成新的摘要并将其追加到摘要序列中。最终损失（PPO或Actor-Critic）基于最后一个片段的隐藏状态计算，梯度通过所有摘要片段反向传播到最早的记忆。
- 推理时，维护摘要Token的KV缓存，不再存储完整历史观测，从而大幅降低内存和计算。

## 3. 实验设计

### 3.1 数据集与场景
- **Dark-Key-To-Door**：9×9网格世界元强化学习基准，智能体需记住隐形钥匙和门的位置，每试次500步，最多50步/回合。
- **EXT OBJ NAV**：在HSSD-200照片级真实室内场景中，智能体（Fetch机器人）需重复导航至不同物体目标，单次试次32,000步，使用RGB相机和里程计传感器。训练集包含11100个场景实例，验证集108个实例。

### 3.2 对比方法
- **Full-Context Transformer (FCT)**：标准Transformer，可访问全部历史上下文（基于ReLIC或AMAGO训练）。
- **无跨注意力变体 (no-IEA)**：禁止跨回合注意力，作为下限。
- **循环记忆Transformer (RMT)**：固定大小的循环记忆，仅保留最新生成的摘要。
- **自动压缩器 (AC)**：模仿语言模型中的AutoCompressors，使用预训练初始化+截断反向传播（TBTT）或全梯度传播。
- **其他基线**：RL^2、Tr-XL等（因性能差被排除）。

### 3.3 评估指标
- **EXT OBJ NAV**：成功率（SR）和成功加权路径长度（SPL），每500步计算一次。
- **Dark-Key-To-Door**：平均总回报。

## 4. 资源与算力

- **硬件**：16块 NVIDIA A40 GPU（表2）。
- **训练规模**：总环境步数约7亿步（700M），训练时长约2.5天。
- **计算效率**：Memo在推理时KV缓存大小仅为FCT的1/10，FLOPs降低4.2倍，推理速度提升约2倍（表1）。

## 5. 实验数量与充分性

- **主要对比实验**：在EXT OBJ NAV上对比Memo、FCT、no-IEA、RMT、AC变体，报告SR和SPL曲线（图2b）；在Dark-Key-To-Door上对比Memo、RMT、FCT（图3a）。
- **消融实验**：摘要长度（16/32/64）、片段随机化（有/无）、直接KV缓存构造替代摘要重编码、梯度传播范围（全片段 vs 截断）、微调（4k→16k上下文）、流式设置等（图4a、4b、5a、5b、9、10）。
- **额外验证**：Memory Maze任务（图7）、T-Maze任务（图8），证明摘要积累优势。
- **统计可靠性**：所有实验均使用多个随机种子（EXT OBJ NAV用10个种子，Dark-Key-To-Door用3个种子），并绘制误差区间。
- **公平性**：所有方法使用相同的基础Transformer架构和训练超参数（除上下文处理方式外），比较在同等计算资源下进行。

**结论**：实验数量充实，覆盖多任务、多算法、多消融，对比客观公平，充分支持论文结论。

## 6. 论文的主要结论与发现

1. **性能与效率兼得**：Memo在EXT OBJ NAV上平均成功率比FCT高7.5%，SPL高2.5%，同时上下文token数减少8倍，计算和存储成本显著降低。
2. **积累式摘要优于固定循环记忆**：Memo（积累所有摘要）在收敛速度和最终性能上均优于RMT（固定大小循环记忆），在T-Maze上训练速度快10倍以上。
3. **全梯度传播至关重要**：对比AC（截断反向传播）和AC（全梯度传播），全梯度版本在早期表现更好，但随后退化，表明预训练初始化反而有害；Memo从头训练并传播所有梯度，持续优于两者。
4. **流式推理鲁棒性**：在推理时仅保留最近6k步的KV缓存，Memo性能几乎不受影响，而FCT性能急剧下降。
5. **微调可扩展**：将训练上下文从4k扩展到16k，Memo和FCT的ICL能力均提升，但Memo在SR和SPL上仍优于FCT。
6. **消融结论**：摘要长度32最优；片段随机化显著提升数据效率；直接提取内部状态作为KV缓存（省略重编码）导致性能退化，说明重编码步骤的必要性。

## 7. 优点

- **方法简洁有效**：仅通过插入可学习的摘要Token和简单的训练修改，即实现了高效记忆压缩，与on-policy和off-policy RL均可无缝集成。
- **计算与存储效率突出**：推理时KV缓存降低一个数量级，同时性能不降反升，对资源受限的具身系统极具价值。
- **泛化能力强**：在训练上下文之外（如32k步评估）表现稳健，流式设置下无需额外修改即可保持性能。
- **消融设计全面**：从摘要长度、片段随机化、梯度传播方式、记忆积累机制等多个角度验证设计决策，结论可靠。
- **开源代码**：作者提供代码便于复现。

## 8. 不足与局限

- **语义泛化未评估**：实验仅关注导航到见过类别的目标，未测试对全新物体类别的泛化，限制了在开放世界场景的推论。
- **记忆机制单一**：仅使用单层摘要积累，未探索渐进式压缩或记忆巩固等更灵活的策略。
- **长度外推仍有挑战**：虽然Memo比FCT外推更好，但在训练上下文1.5倍后仍出现性能退化，需进一步研究位置编码或动态压缩策略。
- **训练依赖RL目标**：记忆形成完全由奖励驱动，未利用自监督信号（如未来预测）提升数据效率，可能限制样本效率。
- **仅在仿真环境验证**：实验在Habitat仿真器中完成，未在真实机器人上验证，可能存在Sim-to-Real gap。
- **偏差风险**：EXT OBJ NAV任务中物体分布经过特意调整（减少密集放置），可能未能充分反映真实室内杂乱场景的难度。

（完）
