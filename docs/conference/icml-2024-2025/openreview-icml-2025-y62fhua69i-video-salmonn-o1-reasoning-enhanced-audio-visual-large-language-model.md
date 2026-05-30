---
title: "video-SALMONN-o1: Reasoning-enhanced Audio-visual Large Language Model"
title_zh: video-SALMONN-o1：推理增强的视听大语言模型
authors: "Guangzhi Sun, Yudong Yang, Jimin Zhuang, Changli Tang, Yixuan Li, Wei Li, Zejun MA, Chao Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=y62fhuA69I"
tags: ["query:long-video"]
score: 9.0
evidence: 提出了推理增强的视听大语言模型，用于通用视频理解与问答
tldr: 针对通用视频理解中推理能力不足的问题，提出了video-SALMONN-o1，首个开源推理增强的视听大语言模型。该模型利用推理密集型数据集和过程直接偏好优化方法，提升了复杂视频问答的推理能力。实验表明，在多个视频理解基准上，其推理能力显著优于现有模型，为视频问答任务提供了更强的推理基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1505, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 774, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1218, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1227, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1229, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 581, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1224, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1413, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1409, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1226, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1238, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1230, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1233, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1415, \"height\": 212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1414, \"height\": 211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1402, \"height\": 462, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 818, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1607, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1368, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1530, \"height\": 625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1335, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1351, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 193, \"label\": \"Table\"}]"
motivation: 现有推理优化方法局限于数学和图形输入，未充分覆盖通用视频理解。
method: 构建推理密集型视听数据集，并采用过程直接偏好优化进行步骤级奖励学习。
result: 在多个视频理解基准上显著提升了视频问答的推理性能。
conclusion: 推理增强的视听大语言模型为通用视频理解提供了一种有效的新范式。
---

## Abstract
While recent advancements in reasoning optimization have significantly enhanced the capabilities of large language models (LLMs), existing efforts to improve reasoning have been limited to solving mathematical problems and focusing on visual graphical inputs, neglecting broader applications in general video understanding. This paper proposes video-SALMONN-o1, the first open-source reasoning-enhanced audio-visual LLM designed for general video understanding tasks. To enhance its reasoning abilities, we develop a reasoning-intensive dataset featuring challenging audio-visual questions with step-by-step solutions. We also propose process direct preference optimization (pDPO), which leverages contrastive step selection to achieve efficient step-level reward modelling tailored for multimodal inputs. Additionally, we introduce RivaBench, the first reasoning-intensive video understanding benchmark, featuring over 4,000 high-quality, expert-curated question-answer pairs across scenarios such as standup comedy, academic presentations, and synthetic video detection. video-SALMONN-o1 achieves 3-8% accuracy improvements over the LLaVA-OneVision baseline across different video reasoning benchmarks. Besides, pDPO achieves 6-8% improvements compared to the supervised fine-tuning model on RivaBench. Enhanced reasoning enables video-SALMONN-o1 zero-shot synthetic video detection capabilities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的推理优化方法（如 Chain-of-Thought、过程奖励模型、结果奖励模型）主要聚焦于数学问题求解和图像输入，忽视了通用视频理解中复杂的推理需求（如学术演讲、喜剧、合成视频检测等需要跨模态推理的场景）。当前多模态大语言模型在视频问答任务中往往直接生成答案，缺乏分步推理能力，且对音频和视觉信息的联合推理不足。
- **整体含义**：本论文旨在填补这一空白，提出首个**开源推理增强的视听大语言模型**——video-SALMONN-o1，通过构建推理密集型数据集和提出新的步骤级偏好优化方法（pDPO），显著提升模型在通用视频理解场景中的逻辑推理能力，从而实现更透明、可解释的视频问答。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 在现有视频-语言模型的基础上，增加**推理能力强化**：先通过监督微调（SFT）让模型学会生成分步推理路径，再通过**过程直接偏好优化（pDPO）** 在步骤级进行偏好学习，纠正模型在中间推理步骤中的错误。
- 提出**对比步骤选择**机制，高效定位对视频内容敏感的易错步骤，从而节省计算资源并提升训练效率。

### 关键技术细节
1. **模型结构**：沿袭 video-SALMONN 2 架构，包含视觉编码器（SigLIP）、音频编码器（Whisper-Large-v3），各自通过模态对齐器（视觉：两层线性+GELU；音频：窗口级 Q-Former）映射到 LLM 输入维度，再通过**交错同步模块**将视觉和音频 token 按时间顺序拼接后送入 LLM 骨干（Qwen 2 7B）。
2. **推理密集型 SFT 数据生成**：
   - 使用 Gemini-1.5-pro 基于视频+音频生成问题、答案及分步推理步骤。
   - 使用 GPT-4o 进行质量检查，丢弃不合格数据并重新生成。
   - 最终获得约 30k 推理密集型 QA 对，并保留所有原始 QA 对（共约 150k），防止模型失去直接回答能力。
3. **过程直接偏好优化（pDPO）**：
   - **对比步骤选择**：对每个推理步骤计算输入视频微小扰动后的 KL 散度（`d_s_k`），选择散度最大的 Top T 步骤（本文取 T=3）作为优化目标，因为这些步骤最可能因视频误读而出错。
   - **成对 rollout**：对被选步骤及其替代步骤分别进行 N 次 rollout（本文取 N=6），估算该步骤的期望正确率 `p_s_k`。
   - **偏好建模**：将步骤对视为偏好数据，使用 DPO 损失训练。损失函数中引入软标签 `α_k` 以平滑 rollout 噪声。
   - **联合优化**：pDPO 同时使用完整路径偏好对（PPRM）和步骤级偏好对，实现粗细粒度结合。
4. **训练流程**：
   - 第一阶段：音频模态对齐（LibriSpeech、AudioCaps）。
   - 第二阶段：视听 SFT（冻结视觉/音频编码器，训练对齐器和 LoRA）。
   - 第三阶段：pDPO 强化学习（基于 SFT 模型）。

### 公式（文字说明）
- `p_s_k ≈ (1/N) Σ (A_n == A_ref)`：通过 N 次 rollout 估算步骤 s_k 的期望正确率。
- pDPO 损失：基于 Bradley-Terry 模型，定义 `p(s_k > s'_k) = σ(r(s_k) - r(s'_k))`，其中 r(s_k) 通过策略模型和参考模型的 log 概率差计算，最终损失为交叉熵形式（含软标签 α_k）。
- `d_s_k = (1/|s_k|) Σ D_KL(P(y|HAV) || P(y|˜HAV))`：计算步骤 s_k 对输入扰动的敏感度。

## 3. 实验设计

### 使用的数据集 / 场景
- **现有基准**：
  - **VideoMME**（视听基准，需联合推理）
  - **NExT-QA**（视觉为主，因果推理）
- **自建基准 RivaBench**（论文贡献之一）：
  - **Academic**：基于 M3AV 测试集，由医学、工程等领域专家撰写问题，共 1,912 个 QA。
  - **StandUp**：基于喜剧视频，问题要求推理为什么某个笑点有趣，共 2,128 个 QA。
  - **SynthDec**：合成视频检测（Hunyuan-large 生成 + 真实视频），200 个 QA，Yes/No 格式，F1 评估。

### 对比方法
- **专有模型**：GPT-4o（2024-08-06 检查点）、Gemini-1.5-pro（均测试预定义模型和“+reasoning”版本）。
- **开源模型**：
  - LLaVA-OneVision（相同视觉编码器和骨干，仅视觉）
  - video-SALMONN（原版，视听）
  - Video-LLaMA 2.1（视听）
- **自身消融**：不同 SFT 数据配置、不同奖励建模方法（ORM、PRM、pDPO）、不同步骤选择策略。

### 评估指标
- 准确率（除 SynthDec 用 F1 外）；SynthDec 报告精确率/召回率。
- 推理过程质量以定性案例展示（附录）。

## 4. 资源与算力

- **SFT 阶段**：16×A100 GPU，训练 48 小时。
- **pDPO 阶段**：8×A100 GPU，训练 24 小时。
- **其他**：视觉编码器、音频编码器、LLM 骨干冻结；LoRA 参数 r=64, α=256；训练数据规模约 150k 常规 QA + 30k 推理密集型 QA，pDPO 数据从 5k 视频中生成约 100k 完整路径对 + 100k 步骤级对。

## 5. 实验数量与充分性

- **主要实验**：表2（主结果，5组开源模型+2组专有模型，4个基准），覆盖多种模态配置。
- **消融实验**：
  - 表3：SFT 数据成分影响（推理数据 vs. 直接回答、推理密集型部分是否移除）。
  - 表4：奖励建模方法对比（ORM、PRM、pDPO）。
  - 图5：对比步骤选择中不同 T 值的影响（Full paths、+Top3 steps、+All steps）。
- **额外评估**：附录 I 中在 VideoHallucer 基准上对比 Gemini-1.5-pro。
- **定性分析**：附录 F/G/H 提供多个案例展示 SFT 与 pDPO 输出差异、合成视频检测推理过程。
- **充分性评价**：实验设计较为全面，覆盖了数据、训练方法、奖励建模、步骤选择等多个维度，并给出了统计显著性（3-8% 提升）。但仍有不足：SynthDec 只有 200 例，规模较小；未评测长视频（>5分钟）或实时推理；对比基线中未包含近期模型（如 InternVideo、MovieChat）。总体客观公平，使用自建基准时也保证了人工专家注释质量。

## 6. 论文的主要结论与发现

- **性能提升**：video-SALMONN-o1 在 VideoMME、NExT-QA、RivaBench 上比 LLaVA-OneVision 基线高出 3-8% 绝对准确率。
- **pDPO 有效性**：pDPO 训练在 RivaBench 上比 SFT 模型提升 6-8%，显著优于 ORM/PRM 的绝对分数建模。
- **步骤选择重要性**：使用对比步骤选择（Top 3 敏感步骤）比使用所有步骤或仅用完整路径更优，尤其在需要频繁引用视频内容的场景。
- **零样本合成视频检测**：video-SALMONN-o1 首次在开源模型中展示出零样本合成视频检测能力，而其他开源模型在测试中均输出“Real”（失败）。
- **推理可解释性**：通过分步推理，可以定位错误原因，提高模型透明度和可靠性。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将推理优化（RL-based reasoning optimization）应用于通用视频理解，提出 pDPO 这一无需外部奖励模型、高效步骤级偏好学习方法。
- **高效性**：对比步骤选择基于 KL 散度计算，无需人工标注错误步骤，显著降低计算开销（仅对 Top T 步骤进行 rollout）。
- **数据贡献**：构建 RivaBench，填补了推理密集型视听基准的空白，涵盖学术、喜剧、合成视频检测三个新颖场景，且由学科专家人工注释。
- **零样本能力**：增强的推理能力自然迁移到合成视频检测任务，展示了推理的一般化潜力。
- **可解释性**：分步推理有助于理解模型决策过程，便于错误定位和模型审计。

## 8. 不足与局限

- **数据依赖与偏差**：SFT 数据和 rollout 答案正确性判断依赖 GPT-4o 与 Gemini-1.5-pro 等专有模型，可能引入偏见或错误传播。
- **实验覆盖不足**：
  - SynthDec 仅 200 例，规模较小，结果可能不够稳定。
  - 未评测极端长视频（>10分钟）或实时交互场景。
  - 未与更多新型视频理解模型（如 InternVideo2、MovieChat）直接对比。
- **计算资源需求高**：训练需 16-32 块 A100，对普通实验室不友好。
- **pDPO 噪声处理**：仅使用 6 次 rollout 估算步骤正确率，可能存在较大方差；软标签 α_k 的校准参数 μ 需手动设置。
- **模型局限性**：音频编码器（Whisper-Large-v3）有限的最大处理时长（`t_max`），长音频需分段；视觉帧率 2fps 可能漏掉快速动作。
- **潜在社会风险**：模型具备音频理解能力，需防范监控和窃听滥用；论文已讨论并计划发布使用指南。
- **偏差风险**：继承自预训练模型的性别、种族等偏见，视觉/音频编码器在特定人群上可能表现更差。

（完）
