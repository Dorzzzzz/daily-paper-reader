---
title: "VideoLLM-MoD: Efficient Video-Language Streaming with Mixture-of-Depths Vision Computation"
title_zh: VideoLLM-MoD：基于混合深度视觉计算的高效视频语言流处理
authors: "Shiwei Wu, Joya Chen, Kevin Qinghong Lin, Qimeng Wang, Yan Gao, Qianli Xu, Tong Xu, Yao Hu, Enhong Chen, Mike Zheng Shou"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=NKPXHzYusG"
tags: ["query:long-video"]
score: 8.0
evidence: 面向长期密集视频帧的高效视频语言流处理
tldr: 长视频多帧输入导致视觉标记过多，增加计算负担且可能丢失上下文。VideoLLM-MoD提出混合深度视觉计算，通过跳过冗余层而非减少标记数，在保持视觉理解的同时显著降低内存和计算成本。实验表明在多个视频理解基准上达到高效与准确的平衡。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1340, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 549, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1424, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 665, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 656, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1431, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nkpxhzyusg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 803, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1473, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 654, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 981, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 927, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1541, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1357, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nkpxhzyusg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1377, \"height\": 689, \"label\": \"Table\"}]"
motivation: 长视频流场景中视觉标记过多导致内存和计算开销巨大，现有方法忽略LLM的因果上下文。
method: 提出混合深度视觉计算，通过跳过冗余视觉令牌层来减少计算，而非减少令牌数量。
result: 在多个视频理解任务上，该方法在保持性能的同时大幅降低计算成本。
conclusion: 层跳选择是一种有效的视觉令牌压缩方式，适用于长视频理解。
---

## Abstract
A well-known dilemma in large vision-language models (e.g., GPT-4, LLaVA) is that while increasing the number of vision tokens generally enhances visual understanding, it also significantly raises memory and computational costs, especially in long-term, dense video frame streaming scenarios. Although learnable approaches like Q-Former and Perceiver Resampler have been developed to reduce the vision token burden, they overlook the context causally modeled by LLMs (i.e., key-value cache), potentially leading to missed visual cues when addressing user queries. In this paper, we introduce a novel approach to reduce vision compute by leveraging redundant vision tokens ``skipping layers'' rather than decreasing the number of vision tokens. Our method, VideoLLM-MoD, is inspired by mixture-of-depths LLMs and addresses the challenge of numerous vision tokens in long-term or streaming video. Specifically, for certain transformer layer, we learn to skip the computation for a high proportion (e.g., 80\%) of vision tokens, passing them directly to the next layer. This approach significantly enhances model efficiency, achieving approximately 42% time and 30% memory savings for the entire training. Moreover, our method reduces the computation in the context and avoid decreasing the vision tokens, thus preserving or even improving performance compared to the vanilla model. We conduct extensive experiments to demonstrate the effectiveness of VideoLLM-MoD, showing its state-of-the-art results on multiple benchmarks, including narration, forecasting, and summarization tasks in COIN, Ego4D, and Ego-Exo4D datasets. The code and checkpoints will be made available at github.com/showlab/VideoLLM-online.

---

## 论文详细总结（自动生成）

# 论文中英文总结：VideoLLM-MoD —— 基于混合深度视觉计算的高效视频语言流处理

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在大型视觉语言模型（如 GPT-4、LLaVA）中，增加视觉 token 数量能提升视觉理解能力，但在长视频流场景下（例如以 2FPS 处理的 300 秒视频），视觉 token 数量急剧增加（可达 6k 个），导致计算和内存开销呈二次方增长。现有方法（如 Q-Former、Perceiver Resampler）通过减少 token 数量来降低负担，但破坏了 LLM 的因果建模上下文（key-value 缓存），可能遗漏关键视觉线索。
- **研究背景**：现有在线视频模型（如 VideoLLM-online）仅使用 CLS token 表示每帧，空间理解能力有限；直接增加空间 token 虽提升性能，但训练成本过高。视频内容存在时空冗余（相邻帧大量重叠），因此有潜力通过稀疏计算实现高效处理。
- **整体含义**：提出 VideoLLM-MoD，利用“跳过冗余视觉 token 层”而非减少 token 数量，在保持或提升性能的同时，大幅降低计算和内存消耗，使长视频在线助手成为可能。

## 2. 论文提出的方法论

### 核心思想
受 Mixture-of-Experts (MoE) 和 Mixture-of-Depths (MoD) [67] 启发，对视觉 token 在特定 Transformer 层进行选择性计算：通过可学习的 **LayerExpert** 模块为每个视觉 token 评分，仅让 top-k 的视觉 token 进入本层的 self-attention 和 FFN 计算，其余 token 通过残差连接直接跳过，保留上下文完整性。

### 关键技术细节
- **模型架构**：采用 LLaVA-like 架构（图像编码器 SigLIP-L/16 + 2层 MLP 投影器 + LLM Meta-Llama-3-8B-Instruct），每帧使用 (1 + 3×3) = 10 个 token（CLS token + 平均池化空间 token）。
- **LayerExpert 模块**：对每个视觉 token 计算重要性分数 μ = w^T x，仅保留分数高于帧内 (1-r) 百分位数的 token（r 为视觉保留率，默认 0.2）。语言 token 始终参与计算。
- **训练损失**：结合语言建模损失（LM Loss）和流式损失（Streaming Loss，让模型在无必要回答时输出 EOS）。
- **效率分析**：仅考虑 MHA 和 FFN 的 FLOPs。在在线视频场景下，视觉 token 远多于语言 token，总 FLOPs 与保留率 r 和插有 LayerExpert 的层数成正比。默认设置（每隔一层插入 LayerExpert，r=0.2）下，视频 LLM-MoD 的 FLOPs 仅为全计算基线的 0.6 倍，推理时 KV 缓存减少，支持 1.7 倍更长的上下文。

### 算法流程（文字说明）
1. 输入：视频帧按 2FPS 采样，每帧提取 10 个视觉 token，与语言 token 交错组成序列。
2. 对每个 Transformer 层（除浅层外每隔一层），LayerExpert 计算每个视觉 token 的得分。
3. 每个帧内选择得分最高的 top-k（k = r × 每帧 token 数）视觉 token，与所有语言 token 一起输入 self-attention 和 FFN；其余视觉 token 跳过本层计算，通过残差连接直接传递。
4. 输出层：语言建模头生成下一个 token 的概率；流式损失在需静默的帧最后一个 token 处监督 EOS 输出。

## 3. 实验设计

### 数据集与场景
- **在线实验**：Ego4D Narration Stream Benchmark（生成逐帧叙述）。
- **离线实验**：Ego4D 长期动作预测（LTA）、EgoExo4D 细粒度关键步识别、COIN 基准（步骤识别、预测、任务摘要等）。
- **通用基准**：Video-MME、MSVD-QA、MSRVTT-QA、ActivityNet-QA、GQA、MME、POPE、SQA 等图像/视频理解任务。

### 对比方法
- 基线：VideoLLM-online（仅 CLS token）、Full-computation（所有 token 全计算）、EarlyExit（浅层后丢弃所有视觉 token）、LayerSkip（每隔一层丢弃所有视觉 token）。
- 消融：不同 LayerExpert 插入策略（All、All-Deep、Interleaved、Interleaved-Deep）、不同保留率 r（0.1、0.2、0.3）、不同选择策略（Random、Uniform vs Learnable）。

### 评估指标
- 在线：LM-PPL（语言建模困惑度）、TimeDiff（时间对齐）、Fluency（流畅度）、LM-Correctness（正确率）。
- 离线：Top-1 准确率、编辑距离（ED@Z=20）、准确率等标准指标。

## 4. 资源与算力

- **硬件**：8 × NVIDIA A100 GPU（每张显存未提及，推断为 80GB）。
- **训练时间**：Ego4D 叙述基准 2 epoch（约 14 小时）；其他基准 5-10 epoch。全文无统一 GPU 小时总数，但估算单个实验约 10-20 小时。
- **注意**：论文未给出精确的 GPU 小时数或能耗数据，仅提供相对加速比（训练时间节省 42%，内存节省 30%）。

## 5. 实验数量与充分性

- **实验数量**：覆盖 4 个主要基准（Ego4D、EgoExo4D、COIN、通用基准），共计约 10 组表格结果；消融实验包括插入策略、保留率、选择策略、EarlyExit 对比等。
- **充分性**：实验较为充分，涵盖了在线和离线多种任务，并进行了多项消融。但存在不足：
  - 仅使用单一视觉编码器和语言模型，未比较不同规模 LLM 或视觉编码器。
  - 仅评估了 egocentric 和 instructional 视频，未涉及 exo-centric 视频（论文已承认）。
  - 通用基准实验（Video-MME 等）仅对比了 LLaMA-VID，未与更多最新模型对比。
- **客观性**：与复现的基线公平比较，在相同设置下训练；但未报告随机种子或多次重复实验的方差。

## 6. 论文的主要结论与发现

1. **效率显著提升**：VideoLLM-MoD 相比全计算基线，训练时间减少约 42%，GPU 内存节省约 30%，且支持更长视频。
2. **性能不降反升**：在多数任务上，VideoLLM-MoD 性能与全计算持平或更优；消融显示随机/均匀选择视觉 token 会降低性能，证明学到的选择策略有效。
3. **层选择策略最佳**：Interleaved（每隔一层插入 LayerExpert）在性能和成本间取得最佳平衡；早期退出（EarlyExit）性能最差，关键信息丢失。
4. **通用性**：方法可推广到离线视频理解任务，并在 COIN 等基准上达到 SOTA（端到端模型中最好）。
5. **减少幻觉**：可视化案例显示，VideoLLM-MoD 比全计算基线更鲁棒，能减少错误识别（如将“花椰菜”误认为是“甜椒”）。

## 7. 优点

- **创新性强**：将 Mixture-of-Depths 思想从 LLM 扩展到视频 LMM，通过“跳过层”而非减少 token 数量来保持上下文完整性。
- **效果显著**：在降低计算成本的同时，在多个基准上达到或超越全计算基线，实现了“免费午餐”。
- **架构简洁**：仅添加轻量 LayerExpert（线性投影），无需改变 LLM 结构，易于集成。
- **通用性好**：可同时应用于在线和离线场景，并提升空间理解能力。

## 8. 不足与局限

- **实验覆盖有限**：仅测试了 egocentric 和 instructional 视频，未涉猎广泛 exo-centric 视频（如一般视频问答）；通用基准对比方法较少。
- **泛化性验证不足**：仅使用单一视觉编码器（SigLIP-L/16）和单一 LLM（Llama-3-8B），未验证在其他架构上的表现。
- **可复现性细节缺失**：未公开代码和模型权重（承诺开放），未报告多次运行的标准差。
- **潜在偏差风险**：由于流式损失和在线数据增强，模型可能对静默帧过度抑制，从而在某些需要立即回应的场景下表现不佳。
- **训练和推理时延**：虽然 FLOPs 降低了，但 LayerExpert 的额外开销和 token 选择过程可能引入少量延迟，论文未详细测量端到端延迟。

（完）
