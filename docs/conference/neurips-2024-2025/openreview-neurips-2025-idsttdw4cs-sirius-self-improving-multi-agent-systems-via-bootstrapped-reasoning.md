---
title: "SiriuS: Self-improving Multi-agent Systems via Bootstrapped Reasoning"
title_zh: SiriuS：通过自增强推理实现多智能体系统的自改进
authors: "Wanjia Zhao, Mert Yuksekgonul, Shirley Wu, James Zou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IDSTtDw4Cs"
tags: ["query:agent-memory"]
score: 6.0
evidence: 构建经验库作为多智能体系统的记忆系统
tldr: 多智能体系统依赖手工提示和启发式难以优化。SiriuS通过自改进推理框架构建经验库，存储成功推理轨迹作为训练数据，实现智能体的自动优化。经验库可视为一种记忆模块，支持智能体从历史中学习。实验显示在复杂任务上性能提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 514, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 681, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 418, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1009, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 534, \"label\": \"Table\"}]"
motivation: 多智能体系统的优化缺乏自动方法，且难以获取高质量训练数据。
method: 构建经验库存储成功推理轨迹，以此作为训练数据优化智能体。
result: 在多种任务上，SiriuS显著提升了多智能体系统的性能。
conclusion: 经验库作为记忆形式，能够有效驱动智能体的自改进和协作。
---

## Abstract
Multi-agent AI systems powered by large language models (LLMs) are increasingly applied to solve complex tasks. However, these systems often rely on fragile, manually designed prompts and heuristics, making optimization difficult. A key challenge in optimizing multi-agent systems is acquiring suitable training data for specialized agents. We introduce SiriuS, a self-improving, reasoning-driven optimization framework for multi-agent systems. Central to our approach is the construction of an experience library: a repository of high-quality reasoning trajectories. The library is built by retaining reasoning steps that lead to successful outcomes, providing a robust training set for optimizing multi-agent system. Additionally, we introduce a library augmentation procedure that refines unsuccessful trajectories, further enriching the library. SiriuS boosts performance by 2.86% to 21.88% on reasoning and biomedical QA and enhances agent negotiation in competitive settings. Our results show that SiriuS enhances multi-agent performance while generating reusable data for self-correction and self-play enhancement in the future.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机与背景）

多智能体系统（Multi-agent AI systems）在大语言模型驱动下被广泛应用于复杂推理、编程、药物发现等任务，但存在两个根本痛点：
- **缺乏训练数据**：每个智能体（Agent）的中间推理步骤难以获得监督信号，无法直接获得高质量的专用训练数据。
- **多智能体优化困难**：传统方法依赖人工设计的 prompt 和启发式规则，系统脆弱且难以自动优化；任务级别的奖励反馈存在**多智能体信用分配**（multi-agent credit assignment）问题，难以将成功或失败归因到具体智能体的决策。

现有工作如 STaR、TextGrad、DSPy、CoMM 等或在单智能体自增强，或在 prompt 层面优化，但缺乏针对多智能体协同行为从结果奖励中学习的高效框架。

本文提出 **SiriuS**（Self-improving Multi-agent Systems via Bootstrapped Reasoning），核心思想是通过构建 **经验库（Experience Library）** ——存储导致成功结果的高质量推理轨迹——作为训练数据，并通过对**失败轨迹的增强**（augmentation）来丰富经验库，驱动多智能体系统的自改进。

## 2. 方法论

### 核心思想
- 利用多智能体系统协作解决任务时产生的完整交互轨迹，系统性地**保留成功轨迹**、**改造失败轨迹**，形成经验库，然后使用**监督微调（SFT）** 更新每个智能体的策略。
- 成功轨迹的收集避免了直接对中间步骤的监督；失败轨迹通过引入一个额外智能体的**反馈**（基于正确答案）进行重新生成、重述，再重新评估，从而转换为有效的训练样本。

### 关键技术细节
1. **多智能体系统形式化**：定义为元组 ⟨S, A, T, R, N, G⟩，其中 N 个 Agent 各有策略 π_i，通过有向图 G 定义交互顺序。每个 Agent 的动作为 a_i ~ π_i(·| state, predecessors’ outputs)。
2. **SiriuS 训练流程**（Algorithm 1）：
   - **Action Sampling**：每个 Agent 基于问题和前序 Agent 输出采样动作。
   - **Trajectory Evaluation & Augmentation**：使用奖励函数评估，高奖励轨迹加入好轨迹集合 C_t；对低奖励轨迹执行**增强管道**：①外部 Agent 提供基于正确答案的反馈；②该 Agent 根据反馈重新生成答案；③重述（rephrase）使其看起来像直接推理结果；④再次参与协作获得最终答案并评估。若成功则归入 C_t。
   - **Fine-Tuning**：对每个 Agent 使用标准 SFT 在 C_t 上更新参数。
3. **增强模块细节**（Algorithm 2 附录 C）：对每个错误答案的 Agent，尝试最多 max_f 次生成反馈、max_re 次重新生成；成功后将轨迹加入对应 Agent 的好轨迹集；同时更新后继 Agent 的轨迹。

### 三个主要设置
- **Problem Solving**：顺序协作（如物理学家→数学家→总结者；或上下文分析者→问题解决者）。
- **Actor-Critic**：解决复杂任务（如 PubMedQA），包含 Actor（生成解答）、Judgment（判断正误）、Critic（反馈修正）三层。
- **Competitive**：资源交换、最后通牒、买卖谈判等场景，两个玩家轮流动作，目标是最大化自身收益。

## 3. 实验设计

### 数据集与场景
- **College Physics / College Chemistry**：由 MMLU、GPQA、TheoremQA 混合构建，训练/测试 2:1 划分。
- **PubMedQA**：生物医学问答，500 训练/500 测试。
- **Competitive Settings**：Resource Exchange、Ultimatum、Sell&Buy（基于 NegotiationArena）。

### Baseline 方法
- Single-Agent、STaR、CoMM（Prompt Multi-Agent）、TextGrad、DSPy（MIPROv2）。
- 在 Actor-Critic 设置中对比 Self-Correct 和 Prompt 两种基线。

### 实验充分性
- 使用 GPT-3.5-turbo、GPT-4o-mini、Llama-3.2-3B-instruct 作为 backbone。
- 进行了**主实验**（表3）、**消融实验**（表4、表5）、**竞争场景实验**（图2-4）及**泛化测试**（图5-7）。
- 报告了带标准差的多次运行结果，每个实验均有可重复的随机种子（temperature=0）。
- 消融实验覆盖了：替换单一 Agent、共享 LLM vs. 专用 LLM、是否使用增强模块、额外迭代次数。

## 4. 资源与算力

论文中**未明确说明**具体使用的 GPU 型号、数量、训练时长。仅提到使用 OpenAI 的 Fine-tuning API（通过 API 调用进行 SFT），未披露 API 调用成本或计算资源。原始推理使用的 LLM 为 OpenAI 或 Llama 的 API/本地模型。对于 Llama-3.2-3B-instruct 可能是本地运行，但未提供硬件细节。

## 5. 实验数量与充分性

- 主实验：三个数据集 × 三种 backbone（GPT-3.5-turbo、GPT-4o-mini、Llama-3.2-3B-instruct）× 多种基线，共约 20+ 组实验，每组报告均值和标准差（至少3次运行）。
- 消融实验：PubMedQA 上 5 种消融 × 2 个 backbone。
- Actor-Critic 实验：两个 backbone × 三种方法，并附消融（4种）。
- Competitive 实验：3 个博弈任务 × 多个对手组合 × 泛化测试。
- 总计至少 60+ 组实验配置，覆盖多种维度。
- **充分性评价**：实验设计合理，消融条款清晰，泛化测试验证了跨设置迁移能力。但竞争场景仅测试了固定初始资源设置和对手，未见更复杂的博弈树搜索；缺乏对更大规模 Agent 数（N>3）的验证。整体上实验相当充分、客观。

## 6. 主要结论与发现

1. **SiriuS 在所有任务上一致优于所有基线**：在 College Physics/Chemistry 和 PubMedQA 上，准确率提升 2.86%~21.88%。
2. **经验库构建是关键**：消融实验显示去掉增强模块性能下降，说明失败轨迹的转化对提升覆盖度重要。
3. **多智能体联合优化优于单一优化**：替换任一个 SiriuS-trained Agent 为 Base Agent 都会导致性能下降。
4. **角色专用微调优于共享模型**：为不同角色分别微调比用一个模型微调所有角色更好。
5. **竞争场景中 SiriuS 提升 win rate 和 payoff**，且能泛化到新的初始资源配置。
6. **Actor-Critic 设置**显著提升了 True Positive 准确率（即正确判断正确答案并避免误改），解决了自纠正（Self-Correct）中常见的过度纠正问题。

## 7. 优点

- **新颖性**：将自增强（bootstrapping）思想从单智能体扩展到多智能体，提出“经验库”作为多智能体系统的记忆模块，避免了复杂的信用分配。
- **无需人工标注**：完全基于任务级结果奖励自动生成训练数据，可扩展。
- **失败轨迹增强算法**：结合反馈、重新生成、重述三步，高效地将失败转化为成功数据。
- **多场景适用**：验证了问题求解、Actor-Critic、竞争博弈三类不同场景，具有泛化性。
- **充分的消融实验**：有力地验证了每个组件（联合优化、角色分离、增强模块、多次迭代）的必要性。
- **代码开源**：补充材料中提供了代码仓库。

## 8. 不足与局限

- **依赖基础 LLM 能力**：性能受限于 backbone 模型（GPT-3.5、GPT-4o-mini、LLaMA-3.2-3B）的推理和指令跟随能力，未在最强模型（如 GPT-4、Claude 3.5）上验证。
- **信用分配问题仍未被完全解决**：虽然通过整体轨迹收集绕开了直接监督，但在极端复杂的多轮交互中，仍然可能存在误导性信号。
- **交互协议设计依赖人工**：当前每种场景的 Agent 角色和顺序由人工指定，未自动搜索最优拓扑。
- **计算资源未披露**：无法评估训练成本（Fine-tuning API 调用次数、token 消耗）和可重复性。
- **竞争场景泛化测试有限**：仅测试了少量资源变化，未涉及策略对抗或动态对手模型。
- **仅三个 backbone**：缺乏在开源大模型或更大规模模型上的结果。
- **缺乏错误类型分析**：未详细分析哪些类型的任务或问题提升最多，可能掩盖失效模式。

（完）
