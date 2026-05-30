---
title: "$\\infty$-Video: A Training-Free Approach to Long Video Understanding via Continuous-Time Memory Consolidation"
title_zh: ∞-Video：通过连续时间记忆整合实现无训练的长视频理解
authors: "Saul Santos, António Farinhas, Daniel C McNamee, Andre Martins"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=afDHwQ1ZDO"
tags: ["query:long-video"]
score: 9.0
evidence: 通过连续时间记忆整合实现长视频理解
tldr: 当前视频语言模型受限于上下文长度和稀疏帧采样，难以处理长视频。本文提出∞-Video，通过连续时间长期记忆整合机制，无需额外训练即可处理任意长度视频。动态注意机制为相关视频片段分配更高粒度，形成随时间演化的记忆。在Video-LLaMA和VideoChat2上的实验证明了其有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1537, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1732, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1065, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1595, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1747, \"height\": 1067, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1642, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1770, \"height\": 236, \"label\": \"Table\"}]"
motivation: 现有视频语言模型无法有效处理长视频，信息丢失严重。
method: 提出连续时间长期记忆整合机制，利用连续注意动态分配粒度。
result: 在Video-LLaMA等模型上实现高效长视频理解，无需额外训练。
conclusion: ∞-Video能有效扩展视频模型到任意长度视频，保持性能。
---

## Abstract
Current video-language models struggle with long-video understanding due to limited context lengths and reliance on sparse frame subsampling, which often leads to information loss. In this paper, we introduce $\infty$-Video, which is able to process arbitrarily long videos through a continuous-time long-term memory (LTM) consolidation mechanism. Our framework augments video Q-formers by making them able to process unbounded video contexts efficiently and without requiring additional training. Through continuous attention, our approach dynamically allocates higher granularity to the most relevant video segments, forming "sticky" memories which evolve over time. Experiments with Video-LLaMA and VideoChat2 demonstrate improved performance in video question-answering tasks, showcasing the potential of continuous-time LTM mechanisms to enable scalable and training-free comprehension of long videos.

---

## 论文详细总结（自动生成）

# 论文中文总结：∞-Video: 通过连续时间记忆整合实现无训练的长视频理解

## 1. 核心问题与整体含义（研究动机和背景）

当前视频-语言模型（Video-LLM）受限于以下瓶颈：
- **有限上下文长度**：Transformer 只能处理固定数量的帧（如 16～32 帧），对于长视频只能采用稀疏帧采样，导致关键信息丢失。
- **缺乏连续时间建模**：传统注意力将视频视为离散帧序列，难以高效整合跨长时段的依赖。
- **高昂训练成本**：大多数长视频模型需要大规模重新训练或微调，计算资源需求大。

受人类认知中记忆巩固（memory consolidation）机制启发——人类能够动态将重要事件整合进长期记忆——本文提出 **∞-Video**，一种无需额外训练的框架，通过**连续时间长期记忆（LTM）整合机制**，使现有的短视频模型（如 Video-LLaMA、VideoChat2）能够有效处理任意长度视频。

## 2. 方法论

### 2.1 核心思想
- 将视频分为若干 **帧块（chunks）**，每个块由原有视频 Q-former 的**短期记忆（Short-Term Memory, STM）**处理。
- 同时维护一个**连续时间长期记忆（Long-Term Memory, LTM）**，通过连续信号表示全局视频信息。
- 最终输出为 STM 与 LTM 的加权和：`Z = α * Z_STM + (1-α) * Z_LTM`，其中 α 是平衡因子。

### 2.2 关键技术细节
1. **连续时间信号构建**：将离散帧序列转换为连续信号 `x(t) = B^T ψ(t)`，其中 `ψ(t)` 为基函数（如矩形函数），`B` 通过多元岭回归（ridge regression）从帧嵌入求得，基函数数量 `N` 远小于帧数，实现压缩。
2. **连续注意力**：对每个查询 `q_i`，定义连续键-值函数 `k(t)`、`v(t)`，计算相似度 `s_i(t) = q_i^T k(t)`，用 **Gibbs 概率密度** 替换传统 softmax 离散分布：
   ```
   p_i(t) = exp(s_i(t)) / ∫ exp(s_i(t')) dt'
   ```
   通过梯形法数值积分近似。
3. **长期记忆整合（Memory Consolidation）**：
   - 将当前 LTM 信号 `x(t)` 收缩（contraction）到区间 `[0, τ]` 以模拟遗忘（τ 为遗忘因子）。
   - 在 `[0, τ]` 内均匀或按注意力密度采样 `T` 个点，与当前块的新帧 `X_new` 拼接成 `X = [X_past, X_new]`。
   - 重新计算基系数 `B`，实现 LTM 更新。
4. **粘性记忆（Sticky Memories）**：非均匀采样，根据先前注意力密度直方图采样，使高注意力区域获得更高分辨率，类似人类记忆的“资源分配”理论。
5. **单次遍历（One-Pass）**：边处理边累积嵌入（running average），无需存储所有块信息，内存开销恒定。

### 2.3 流程示意（文字说明）
- 输入视频 → 帧分块 → 每个块依次送入视频 Q-former（含 STM 和 LTM）。
- Q-former 的交叉注意力层同时计算当前块的 STM 和全局 LTM 输出，两者加权合并。
- 所有块的输出通过滑动平均得到固定数量的视频令牌嵌入。
- 最后将视频令牌与问题一起送入 LLM 生成答案。

## 3. 实验设计

### 3.1 数据集与场景
| 数据集 | 时长 | 任务类型 | 评估指标 |
|--------|------|----------|----------|
| NExT-QA (Xiao et al., 2021) | 平均 44 秒 | 多选题（5 选 1） | 准确率 |
| Egoschema (Mangalam et al., 2023) | 平均 3 分钟 | 多选题（5 选 1） | 准确率 |
| Video-MME (Fu et al., 2024) | 长达 1 小时 | 多选题（分类） | 准确率 |
| MovieChat-1K (Song et al., 2023) | 平均 8 分钟 | 开放式问答 | GPT-3.5 评分（正确性、细节、上下文等） |

### 3.2 对比方法
- **基于专有 LLM 的训练免费方法**：LLoVi (GPT-4), VideoAgent (GPT-4), VideoTree (GPT-4)
- **同类基础模型**：Video-LLaMA, MovieChat, MovieChat+, VideoChat2
- **本文变体**：∞-Video LLaMA (无 LTM、均匀采样、粘性记忆)，∞-VideoChat2 (同上)
- **其他基线**：ST-LLM, Video-LLaVA, ShareGPT4Video, Chat-UniVi, Qwen-VL-Chat 等

### 3.3 实验设置
- 基础模型：Video-LLaMA2-7B（EVA-CLIP ViT-G/14 + Vicuna-7B），VideoChat2（UMT-L + Mistral-7B）
- 块大小：Video-LLaMA 每块 256 帧，VideoChat2 每块 16 帧；均用 8 个块（或全部帧）。
- 超参数：基函数数 `N`（256 或 1024），遗忘因子 `τ=0.5~0.75`，采样点数 `T`（实验未明确数值但通过积分采样点 1000）。

## 4. 资源与算力

论文 **未明确说明** 所用 GPU 型号、数量或训练时长。由于方法完全无需训练，仅需推理阶段使用现有预训练模型，计算资源主要来自特征提取和连续注意力计算（梯形积分约 1000 采样点）。文中未报告具体推理时间或能耗。

## 5. 实验数量与充分性

- **实验数量**：在 4 个数据集（NExT-QA、Egoschema、Video-MME、MovieChat-1K）上进行了评估，覆盖短、中、长视频和多选题/开放问答任务。针对两个基础模型（Video-LLaMA, VideoChat2）分别测试了无 LTM、均匀采样、粘性记忆三种变体。
- **消融实验**：在 MovieChat 上对 α（LTM权重）和 N（基函数数）进行了系统性消融（附录 B.1），并比较均匀与粘性采样。
- **充分性与公平性**：对比了多个同类训练免费方法和自家基线，实验设计较全面。但在某些数据集（如 NExT-QA 上的 VideoChat2 变体）提升不显著，说明当原始模型已高度优化时，本方法增益有限。总体而言，实验客观且可复现（代码已开源）。

## 6. 主要结论与发现

1. **∞-Video 能显著提升长视频理解**：特别是在 Video-LLaMA 上，粘性记忆在 Egoschema 上提升 +6 百分点（46.8% vs 40.8%），在 MovieChat 上准确率 72.2% 超过其他方法。
2. **粘性记忆优于均匀采样**：通过动态分配更高粒度到关键区域，粘性记忆在几乎所有指标上表现更好。
3. **训练免费且可扩展**：无需额外训练，即可将短视频模型推广到任意长度视频，实现单次遍历。
4. **对强基模型提升有限**：在 VideoChat2 上改善较小，可能是因为其本身已经过大量指令微调，接近性能上限。
5. **注意力可视化证实有效性**：连续注意力密度图显示粘性记忆聚焦于剧情关键帧，而均匀采样会分散到无关部分（如片尾字幕）。

## 7. 优点

- **无需训练**：直接利用预训练模型，节省大量计算资源。
- **连续时间建模**：比离散帧采样更自然，可灵活压缩和分配注意力。
- **认知启发性**：模仿人类记忆巩固与资源分配机制，具有理论深度。
- **可解释性**：通过注意力密度热力图可观察模型关注的视频区间，提升透明度。
- **内存高效**：仅需存储有限个基函数系数，而非全部帧嵌入，适合任意长视频。
- **即插即用**：可适配不同视频 Q-former 架构（如 Video-LLaMA 和 VideoChat2）。

## 8. 不足与局限

- **实验覆盖有限**：仅测试了两个基础模型（Video-LLaMA 和 VideoChat2），且其中 VideoChat2 提升微弱，未在更多模型（如 LLaVA-Video、mPLUG-Owl）上验证。
- **超参数敏感**：性能对 α、N、τ 等超参数敏感，需要针对不同视频长度手动调整（但提供了经验值）。
- **未报告推理成本**：连续注意力积分计算（1000 采样点）可能带来额外延迟，但未与基线对比时间开销。
- **仅支持单轮问答**：当前设计是在视频处理完后一次性回答，未涉及多轮对话或实时流式处理。
- **依赖视频 Q-former**：若原始模型不具备视频 Q-former（如 CLIP 直投），本方法无法直接应用。
- **可能存在偏差风险**：问题仅在 LLM 端输入，视频 Q-former 无法感知问题内容（与 MovieChat+ 不同），可能导致信息提取方向偏差。
- **无多模态融合创新**：LTM 仅在视觉特征上操作，未结合音频或文本记忆。

（完）
