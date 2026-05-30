---
title: "Optimus-1: Hybrid Multimodal Memory Empowered Agents Excel in Long-Horizon Tasks"
title_zh: Optimus-1：混合多模态记忆赋能智能体在长视距任务中表现出色
authors: "Zaijing Li, Yuquan Xie, Rui Shao, Gongwei Chen, Dongmei Jiang, Liqiang Nie"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=XXOMCwZ6by"
tags: ["query:agent-memory"]
score: 9.0
evidence: 提出混合多模态记忆模块，用于智能体在长视距任务中的记忆系统设计
tldr: 该论文指出通用智能体在长视距开放世界任务中表现欠佳，归因于缺乏世界知识和多模态经验。为此提出了混合多模态记忆模块，包含分层有向知识图（显式世界知识）和抽象多模态经验池（隐式经验）。智能体借助该记忆模块在多个长视距任务中取得显著性能提升，证明了混合记忆对智能体长期规划的关键作用。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1411, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1386, \"height\": 964, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 967, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 1393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1263, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1414, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1416, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xxomcwz6by/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1430, \"height\": 558, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 1179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 722, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 723, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 622, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 920, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 946, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1446, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 742, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1446, \"height\": 1969, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xxomcwz6by/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1447, \"height\": 2291, \"label\": \"Table\"}]"
motivation: 现有智能体在长视距开放世界任务中缺乏必要的世界知识和多模态经验。
method: 设计混合多模态记忆模块，包括分层有向知识图和抽象多模态经验池。
result: 在多个长视距任务中，Optimus-1显著优于现有智能体方法。
conclusion: 混合多模态记忆是构建通用长视距智能体的关键组件。
---

## Abstract
Building a general-purpose agent is a long-standing vision in the field of artificial intelligence. Existing agents have made remarkable progress in many domains, yet they still struggle to complete long-horizon tasks in an open world. We attribute this to the lack of necessary world knowledge and multimodal experience that can guide agents through a variety of long-horizon tasks. In this paper, we propose a Hybrid Multimodal Memory module to address the above challenges. It 1) transforms knowledge into Hierarchical Directed Knowledge Graph that allows agents to explicitly represent and learn world knowledge, and 2) summarises historical information into Abstracted Multimodal Experience Pool that provide agents with rich references for in-context learning. On top of the Hybrid Multimodal Memory module, a multimodal agent, Optimus-1, is constructed with dedicated Knowledge-guided Planner and Experience-Driven Reflector, contributing to a better planning and reflection in the face of long-horizon tasks in Minecraft. Extensive experimental results show that Optimus-1 significantly outperforms all existing agents on challenging long-horizon task benchmarks, and exhibits near human-level performance on many tasks. In addition, we introduce various Multimodal Large Language Models (MLLMs) as the backbone of Optimus-1. Experimental results show that Optimus-1 exhibits strong generalization with the help of the Hybrid Multimodal Memory module, outperforming the GPT-4V baseline on many tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：通用智能体在开放世界长视距任务（如 Minecraft 中从砍树到合成钻石剑）中性能远低于人类水平。
- **归因**：现有智能体缺乏两类长期记忆存储：
  - **结构化世界知识**（如物品合成配方、工具等级限制）——现有 MLLM 如 GPT-4V 缺乏 Minecraft 专属知识，而传统方法仅从视频中学习碎片化知识。
  - **多模态经验**（成功的策略与失败的教训）——现有方法仅存储单模态信息（文本或代码），无法像人类一样利用包含视觉、环境、状态的多模态历史经验。
- **研究目标**：构建通用长视距智能体，使其具备类似人类的长期记忆（知识 + 经验）能力，从而在开放世界中高效规划与反思。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 提出 **混合多模态记忆（Hybrid Multimodal Memory）** 模块，模拟人类语义记忆（知识）与情景记忆（经验）的协同。
- 在该记忆模块之上构建 **Optimus-1** 智能体，由三个组件构成：
  - **Knowledge-Guided Planner**（知识引导规划器）
  - **Experience-Driven Reflector**（经验驱动反射器）
  - **Action Controller**（动作控制器）

### 关键技术细节

#### ① 混合多模态记忆模块
- **分层有向知识图（HDKG）**：
  - 将 Minecraft 中的物品合成关系建模为有向图 \( D(V, E) \)，节点为物品，有向边指向可由该物品合成的目标。
  - 给定任务目标，检索对应子图并进行拓扑排序，得到完整的材料链与步骤顺序。
  - 无需参数更新，可高效扩展（新增节点/边仅需局部线性操作）。
- **抽象多模态经验池（AMEP）**：
  - 动态采集智能体执行任务时的视频帧，经视频缓冲区（1 fps）和图像缓冲区（窗口大小16，自适应去重）过滤。
  - 使用 MineCLIP 计算视觉内容与文本子目标的相似度，超过阈值则存储为多模态经验（含环境信息、初始状态、规划、视频帧）。
  - 同时存储成功与失败案例，提供三种反射结果（COMPLETE / CONTINUE / REPLAN）的参考。

#### ② Optimus-1 框架
- **Knowledge-Guided Planner**：
  - 输入：任务描述 \( t \)、当前观察 \( o \)（原始图像）、从 HDKG 检索的子图 \( p_\eta(t) \)。
  - 一次性生成完整子目标序列 \( g_1, g_2, ..., g_n \)（公式 2）。
  - 利用视觉信息进行环境感知规划（如“离开洞穴”）。
- **Action Controller**：
  - 采用 STEVE-1，输入当前观察与子目标，生成底层鼠标/键盘动作（公式 3）。
- **Experience-Driven Reflector**：
  - 定期激活，从 AMEP 检索最相关的经验（成功/失败案例），结合当前观察输出三类判断：COMPLETE（切换下一子目标）、CONTINUE（继续执行）、REPLAN（要求规划器重新规划）（公式 4）。

#### ③ 非参数化学习（自演化）
- 采用“自由探索 – 教师指导”两阶段方法：
  - **自由探索**：随机初始化装备、任务、环境，智能体尝试执行，将成功/失败知识加入 HDKG，经验加入 AMEP。
  - **教师指导**：提供少量长视距任务的完整规划（通过脚本从 Minecraft Wiki 自动提取），智能体执行并进一步扩展记忆。
- 多个 Optimus-1 实例共享同一记忆池，无需微调参数即可逐步掌握从易到难的任务。

## 3. 实验设计

- **环境**：MineRL（Minecraft 1.16.5），智能体以 20 fps 运行，仅通过鼠标/键盘底层动作交互。
- **Benchmark**：构建包含 **67 个任务** 的基准，分为 7 个难度组（Wood, Stone, Iron, Gold, Diamond, Redstone, Armor）。每个任务初始库存为空，随机世界种子，最大步数按人类平均完成步数设置。
- **对比方法**：
  - GPT-3.5、GPT-4V（纯 MLLM 基线）
  - DEPS（基于 LLM 的交互式规划）
  - Jarvis-1（记忆增强多模态智能体）
  - **人类基线**：10 名有经验的志愿者（≥20 小时游戏时间）重复执行任务，取平均值。
- **评估指标**：
  - 成功率（SR）
  - 平均步数（AS）
  - 平均耗时（AT）
  - 每个任务至少评估 30 次（使用不同世界种子）。
- **额外对比**：还在 Voyager、MP5、DEPS 的原有 benchmark 上进行了测试（附录 F.2）。

## 4. 资源与算力

- **硬件**：4 块 NVIDIA A100（80 GB）GPU。
- **时间**：
  - 自由探索与教师指导阶段（非参数化学习）：约 16 小时。
  - 推理阶段（评估所有任务）：约 20 小时。
- **API 花费**：使用 GPT-4V 作为规划器和反射器，总共花费约 **$5,000**。
- **备注**：开源 MLLM（如 Deepseek-VL、InternLM-XComposer2-VL）可作为低成本替代，性能相当。

## 5. 实验数量与充分性

- **主实验**：表 1 报告了 7 个任务组、5 种基线（含人类）的成功率、步数、耗时，每个任务至少 30 次独立评估。
- **消融实验**：
  - 表 2：去除规划 + 反射、去除 HDKG、去除 AMEP 等组合，在 5 组任务上验证。
  - 表 3：对 AMEP 的不同检索策略（零次、仅成功、仅失败、成功+失败）进行对比。
- **泛化实验**：图 5(a)：使用 Deepseek-VL、InternLM-XComposer2-VL 作为规划/反射器，有/无记忆模块的对比。
- **自演化实验**：图 5(b)：4 个 epoch 的迭代学习过程，每个 epoch 含 150 个自由探索任务 + 10 个教师指导任务。
- **充足性**：实验覆盖多个任务难度、多种模型、多个消融维度，且与多种 SOTA 方法及人类基线对比，统计上较充分。
- **公平性**：
  - Optimus-1 初始库存为空，而 DEPS、Jarvis-1 初始有工具，设置更困难。
  - 使用不同世界种子，减少随机性影响。
  - 人类基线由经验玩家提供，确保可比性。

## 6. 主要结论与发现

1. **性能领先**：Optimus-1 在所有任务组上成功率显著高于所有基线，尤其在 Iron 组（46.69% vs. 36.15%）、Diamond 组（11.61% vs. 8.98%）、Redstone 组（25.02% vs. 16.31%）提升明显。
2. **接近人类水平**：在 Wood 组接近 100%，在简单任务上表现与人类相当，在困难任务上差距缩小至平均 5.37%。
3. **混合记忆的有效性**：
   - 去除 HDKG 导致平均成功率下降约 20%；去除 AMEP 下降约 12%。
   - 同时使用成功与失败案例的检索比仅用成功案例或零次检索效果更好。
4. **泛化性**：不同的 MLLM（Deepseek-VL、InternLM-XComposer2-VL）在添加混合记忆后性能提升 2~6 倍，超过 GPT-4V 基线。
5. **自演化能力**：通过“自由探索-教师指导”迭代，智能体可以逐步掌握更复杂的任务，无需参数更新。

## 7. 优点（方法与实验亮点）

1. **记忆模块即插即用**：混合多模态记忆不依赖模型微调，可快速适配不同 MLLM，具有强通用性。
2. **显式知识 + 隐式经验协同**：HDKG 提供结构化、可溯源的规划知识；AMEP 提供丰富多模态上下文用于反思。
3. **一次性完整规划**：利用 HDKG 拓扑排序，避免逐步迭代规划带来的延迟与危险。
4. **失败案例纳入经验池**：创新性地将失败经验用于上下文学习，显著提升反射效果。
5. **实验设计完整**：涵盖多种基线、人类对比、消融、泛化、自演化，统计严谨，设置公平。

## 8. 不足与局限

1. **动作控制器能力受限**：采用 STEVE-1 作为底层控制器，其指令遵循与复杂动作生成能力有限，导致在“击败末影龙”“建造房屋”等挑战性任务上表现弱。
2. **未实现端到端**：当前模型依赖 MLLM 规划 + 反射 + 独立动作控制器，未来需构建统一的视觉-语言-动作模型。
3. **Minecraft 环境局限**：实验仅在 Minecraft 中进行，虽然在开放世界任务中具有代表性，但仍需在其他领域（如机器人、网页任务）验证泛化性。
4. **MLLM 随机性风险**：生成式 MLLM 存在随机性与幻觉，若用于高风险场景需要额外安全评估。
5. **计算成本**：虽然提出低成本的 MLLM 替代，但顶级性能仍需依赖 GPT-4V API 付费。

（完）
