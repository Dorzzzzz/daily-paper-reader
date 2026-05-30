---
title: "ROVER: Recursive Reasoning Over Videos with Vision-Language Models for Embodied Tasks"
title_zh: ROVER：用于具身任务的基于视觉语言模型的递归视频推理
authors: "Philip Schroeder, Ondrej Biza, Thomas Weng, Hongyin Luo, James R. Glass"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NNiwGUY50Y"
tags: ["query:long-video"]
score: 9.0
evidence: 对长视频轨迹进行递归推理
tldr: 针对视觉语言模型在长视频序列推理中的局限，本文提出ROVER框架，通过递归地将长视频轨迹分解为较短子任务片段，使得模型能够聚焦于局部帧序列进行推理。实验表明，该方法在具身任务中提升了长视频推理的准确性和效率。该工作为长视频理解在具身场景中的应用提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1162, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1086, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 835, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1175, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1177, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1295, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1295, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1296, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1369, \"height\": 1566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1450, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1163, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1447, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1289, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1290, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 689, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 682, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 669, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 666, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 668, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 667, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 669, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 667, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1422, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1427, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1428, \"height\": 404, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 735, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 968, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1140, \"height\": 1310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 1922, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 1956, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 918, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1379, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1380, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 491, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 489, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1458, \"height\": 2200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1462, \"height\": 2135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 818, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1409, \"height\": 342, \"label\": \"Table\"}]"
motivation: 视觉语言模型在处理长视频帧序列时表现不佳，限制了其在具身任务中的应用。
method: 提出递归推理框架ROVER，将长视频递归分解为子任务段，使模型聚焦于局部帧序列进行推理。
result: 在具身任务基准上，ROVER提升了长视频推理的准确性和效率。
conclusion: 递归分解策略有效提升了VLM对长视频的推理能力，促进在具身场景的应用。
---

## Abstract
Vision-language models (VLMs) have exhibited impressive capabilities across diverse image understanding tasks, but still struggle in settings that require reasoning over extended sequences of camera frames from a video. This limits their utility in embodied settings, which require reasoning over long frame sequences from a continuous stream of visual input at each moment of a task attempt. To address this limitation, we propose ROVER (Reasoning Over VidEo Recursively), a framework that enables the model to recursively decompose long-horizon video trajectories into segments corresponding to shorter subtasks within the trajectory. In doing so, ROVER facilitates more focused and accurate reasoning over temporally localized frame sequences without losing global context. We evaluate ROVER, implemented using an in-context learning approach, on diverse OpenX Embodiment videos and on a new dataset derived from RoboCasa that consists of 543 videos showing both expert and perturbed non-expert trajectories across 27 manipulation tasks. ROVER outperforms strong baselines across three video reasoning tasks: task progress estimation, frame-level natural language reasoning, and video question answering. We observe that, by reducing the number of frames the model reasons over at each timestep, ROVER mitigates model hallucinations, especially during unexpected or non-optimal moments of a trajectory. In addition, by enabling the implementation of a subtask-specific sliding context window, ROVER's time complexity scales linearly with video length, an asymptotic improvement over baselines.

---

## 论文详细总结（自动生成）

# 论文总结：ROVER: Recursive Reasoning Over Videos with Vision-Language Models for Embodied Tasks

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：视觉-语言模型（VLM）在单图像理解任务中表现优异，但在需要推理长视频帧序列（例如具身机器人连续摄像头输入）的条件下存在困难。现有方法要么只关注少量局部帧（丢失全局上下文），要么将所有帧拼接进一个上下文（计算昂贵且容易导致模型幻觉）。
- **动机**：具身任务要求在每个时刻对连续视觉流进行精确推理，例如估计任务进度、生成自然语言描述、回答视频相关问题。需要一种能平衡局部精确性与全局上下文的机制。
- **整体含义**：ROVER提出一种递归推理框架，通过将长视频轨迹递归分解为子任务片段，使模型专注于短时间局部帧序列，同时不丢失任务整体脉络，从而提升推理准确性和效率。

## 2. 方法论

### 核心思想
- **递归分解**：将任务描述和视频帧序列作为输入，递归地生成子任务推理链。每个子任务对应一个较短的时间段，模型只在该子任务对应的帧范围内进行推理。
- **滑动上下文窗口**：在每个子任务推理过程中，只保留最近的三帧（子任务首帧、前一帧、当前帧）作为上下文，进一步减少模型负担。
- **算法流程**（Algorithm 1）：
  - 函数 `ROVER(c, Y)` 接收初始上下文 `c`（任务描述+首帧）和初始 token 序列 `Y`（空）。
  - 循环：模型生成下一个 token `Θ(c + Y)`。
  - 若生成 `[next-frame]` 标记，则追加下一帧的图像 token。
  - 若生成新子任务描述（如“机器人需要：{新子任务}”），则递归调用 `ROVER(ϕ(Y), [])` 创建子过程，子过程返回后将其输出追加回父序列。
  - 若生成任务完成标记或视频结束，则返回 `Y`。
- **ϕ 和 ψ 函数**：`ϕ` 提取父序列的新子任务描述和最后一帧作为子任务上下文；`ψ` 返回子过程最后一帧及其文本描述。
- **实现方式**：采用 in-context learning（ICL），无需微调，所有 backbone VLM 使用相同提示模板。

### 关键公式
- 任务建模为目标条件有限视界 POMDP（公式 (1)）。
- 价值函数基于几何距离：`y_t = (1-β)y^{r,e}_t + β y^{e,f}_t`，其中 `y^{r,e}_t` 是机械臂接触点与物体接触点距离之和，`y^{e,f}_t` 是物体当前位置与目标位置距离。
- 通过关键点辅助信号 `u_t` 和对距离取反缩放得到最终进度值 `v_t`。

## 3. 实验设计

### 数据集 / 场景
- **模拟数据集**：基于 RoboCasa 仿真环境，从 27 个机器人操作任务生成 543 个视频（包括专家轨迹和通过随机扰动生成的非专家轨迹），每个视频带有细粒度地面真值进度标签。任务涵盖 pick-and-place、开关门、开关电器、拨动旋钮、微波解冻等 9 大类。
- **真实世界数据集**：OpenX Embodiment (OXE) 中 50 个数据集的 1000 个视频（共 20 种机器人、300+ 任务规格）。

### Benchmark
- **任务 1**：帧级任务进度估计（预测每帧的完成百分比），评估 Pearson 相关系数和 L2 距离。
- **任务 2**：帧级自然语言推理（生成帧描述并判定正误），评估错误率和成功率。
- **任务 3**：视频问答（事件是否发生及发生时间），评估准确率、精确率、召回率、时间差。

### 对比方法
- **GVL**（Generative Value Learning）：随机打乱帧顺序以打破时间偏见的 ICL 基线。
- **TemporalConcat**：按时间顺序拼接所有帧。
- **LocalConcat**：只保留最近三帧的局部推理基线。
- **LIV**（Language-Image Value model）：多模态对比学习微调的价值模型。
- 附加基线：VideoGemini、VideoLlama3、VideoLLaVA（附录 G）。
- 主 backbone 使用 Gemini-1.5-Pro，也测试了 Gemini-2.5-Pro、GPT-4o、Qwen-2.5-VL-32B。

## 4. 资源与算力

- **文中未明确说明训练资源**（ROVER 采用 in-context learning，无需训练）。
- **测试环境**：使用 Google Gemini API（Gemini-1.5-Pro、Gemini-2.5-Pro）、OpenAI API（GPT-4o）。Qwen-2.5-VL-32B-Instruct 在 A6000 GPU 上运行（附录 J）。
- **未报告具体 GPU 数量、总时长或费用**。仅在附录 F 报告了推理 token 数和 VLM 调用次数以体现效率。

## 5. 实验数量与充分性

- **实验数量多**：包含 3 个主要基准任务、27 个任务、9 个任务组、多个轨迹水平（专家到完全随机）。在真实世界 50 个数据集上重复了进度预测实验。
- **消融实验充分**：分别消融了“仅滑动窗口”“仅递归分解”，并对比了不同窗口大小（3/6/9/12）、不同 backbone、不同帧率（30~240 帧）、不同相机视角（腕部/左/右）。
- **错误分析**：手工审查了 100 个真实视频和 100 个模拟视频，分类统计错误类型。
- **公平性与客观性**：所有方法使用相同提示模板（GVL 与 ROVER 共享系统提示核心），报告误差棒（标准误），实验设置透明。代码和数据已开源。

- **总体充分性高**：实验覆盖了多种任务、数据类型、模型架构和控制变量，结论具有统计显著性。

## 6. 主要结论与发现

1. **ROVER 在所有三个基准任务上全面超越基线**，特别是在非专家（非最优）轨迹上改善显著。
2. **幻觉显著减少**：ROVER 通过减少每步推理的帧数（最多 3 帧），避免了 VLM 在长上下文中的感知错误。GVL 在非专家状态下严重幻觉（往往未发生事件却声称发生）。
3. **时间复杂度线性**：滑动窗口技术使推理时间与视频长度成线性关系，而基线（全帧拼接）需二次时间。
4. **分解与滑动窗口互补**：仅窗口即可在短任务上匹敌 GVL，添加递归分解在多子任务长任务上进一步获益。
5. **错误分析**：ROVER 主要错误为“指定错误子任务”（约 7-9%），但总错误率（约 23-26%）远低于 GVL（约 57-76%）。GVL 的“感知错误”（47% 真实视频）绝大多数发生在 >10 帧的上下文中。

## 7. 优点

- **创新性**：首次提出递归分解 + 滑动窗口的 VLM 视频推理框架，有效解决长视频推理的精度与效率矛盾。
- **数据集贡献**：开源了包含专家和非专家轨迹的大规模视频数据集，并附带细粒度进度标签，有利于后续研究。
- **实验全面严谨**：覆盖多种任务类型、多种退化程度、多种模型和多种设置，消融实验清晰验证各组件贡献。
- **实用性好**：采用 ICL 实现，无需额外训练，直接适配现有 VLM，且推理成本随视频长度线性增长。
- **开源**：代码、数据、演示均已公开，可复现。

## 8. 不足与局限

1. **子任务分解失败风险**：当 VLM 生成无效或错误的子任务时，后续推理可能碎片化甚至偏离任务，文中指出该问题但未提供鲁棒性改进。
2. **仅基于 ICL**：未探索通过微调提升分解准确性和价值估计精度，可能限制性能上限。
3. **依赖预定义子任务结构**：非专家轨迹生成假设任务可分解为对象级别的子任务序列，对于更开放或更复杂的任务适用性可能不足。
4. **真实世界数据集评估的代理真值**：OXE 数据集缺乏真实进度，只能使用帧序号作为代理，可能不能准确反映推理质量（尤其对于非单调轨迹）。
5. **实验场景有限**：仅在 RoboCasa 模拟厨房环境和有限真实数据集上验证，未见在更广泛具身场景（如移动机器人、交互式导航）中的评估。
6. **计算资源报告不足**：未提供完整训练/推理的 GPU 时数、API 调用费用等，不利于成本评估和复现。
7. **未讨论鲁棒性**：例如对高噪声视频、极端遮挡、光照变化等情况的适应能力未测试。

（完）
