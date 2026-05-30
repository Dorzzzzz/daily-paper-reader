---
title: "HoPE: Hybrid of Position Embedding for Long Context Vision-Language Models"
title_zh: HoPE：面向长上下文视觉语言模型的混合位置嵌入
authors: "Haoran Li, Yingjie Qin, Baoyuan Ou, Lai Xu, Ruiwen Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6TmLco2L2D"
tags: ["query:long-video"]
score: 8.0
evidence: 面向长上下文视觉语言模型（特别是长视频）的混合位置嵌入
tldr: 视觉语言模型在长视频等长上下文场景中性能下降。HoPE首次系统分析不同频率分配策略对长上下文能力的影响，并提出混合位置嵌入方法，有效编码时空依赖，提升长视频理解性能。理论分析与实验验证了方法的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1368, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1462, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 462, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 685, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 778, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1037, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6tmlco2l2d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 693, \"height\": 242, \"label\": \"Table\"}]"
motivation: 现有位置嵌入在长视频等长上下文场景中性能不佳，频率分配缺乏理论分析。
method: 分析不同频率分配策略的影响，提出混合位置嵌入以更好编码时空信息。
result: 在长视频理解任务上，HoPE显著优于基线。
conclusion: 合理的位置嵌入设计对于提升长视频理解至关重要。
---

## Abstract
Vision-Language Models (VLMs) have made significant progress in multimodal tasks. However, their performance often deteriorates in long-context scenarios, particularly long videos. While Rotary Position Embedding (RoPE) has been widely adopted for length generalization in Large Language Models (LLMs), extending vanilla RoPE to capture the intricate spatial-temporal dependencies in videos remains an unsolved challenge. Existing methods typically allocate different frequencies within RoPE to encode 3D positional information. However, these allocation strategies mainly rely on heuristics, lacking in-depth theoretical analysis. In this paper, we first study how different allocation strategies impact the long-context capabilities of VLMs. Our analysis reveals that current multimodal RoPEs fail to reliably capture semantic similarities over extended contexts. To address this issue, we propose HoPE, a Hybrid of Position Embedding designed to improve the long-context capabilities of VLMs. HoPE introduces a hybrid frequency allocation strategy for reliable semantic modeling over arbitrarily long contexts, and a dynamic temporal scaling mechanism to facilitate robust learning and flexible inference across diverse context lengths. Extensive experiments across four video benchmarks on long video understanding and retrieval tasks demonstrate that HoPE consistently outperforms existing methods, confirming its effectiveness.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

**研究动机**：视觉语言模型（VLM）在长视频等长上下文场景中性能严重下降，例如对象计数、时间定位等简单任务也难以完成。尽管旋转位置编码（RoPE）在文本大语言模型中广泛用于长度泛化，但将其扩展到多模态（尤其是视频）以捕获复杂的时空依赖仍是一个未解决的关键挑战。

**核心问题**：现有方法（如M-RoPE、VideoRoPE）通过为时间、空间维度分配不同频率来编码3D位置信息，但这些分配策略主要基于启发式，缺乏深入的理论分析。论文首次系统研究了不同频率分配策略对VLM长上下文能力的影响，并指出：现有多模态RoPE在超长上下文中无法可靠地维持“语义偏好”（即语义相似的token应获得更高注意力）。

**整体含义**：合理的频率分配和灵活的时间缩放对提升VLM在长视频任务中的性能至关重要，论文通过理论和实验证明其提出的混合位置嵌入（HoPE）能有效解决该问题。

## 2. 论文提出的方法论

**核心思想**：HoPE由两个关键组件组成：
- **混合频率分配（HFA）**：高频分配给空间维度（x, y）以捕捉局部细节，将时间维度的最低频率直接设为0（即采用NoPE方式），从而在理论上保证语义偏好性质在任意长上下文中成立。
- **动态时间缩放（DTS）**：定义一组缩放因子Γ={0.5,0.75,1,1.25,1.5}，训练时随机选择，允许对视觉token的时间索引进行压缩或扩展；推理时可灵活选择以适配不同视频时长。

**关键技术细节**：
- 对于128维RoPE，前96维交错编码x和y（各48维），后32维设置频率为0（对应恒等矩阵）。
- DTS公式：对文本token位置直接索引；对视觉token（位置l在[L_t, L_t+L_v)）的时间索引为 `L_t + γ*(l - L_t)`，空间索引相应调整；对后续文本token也按缩放因子偏移。
- 理论证明：设时间维度频率为0时，语义偏好条件（Lemma 4.1）中时间项恒为正，优于任何非零频率分配。

## 3. 实验设计

**数据集与场景**：
- 长视频理解：LongVideoBench（8秒至1小时）、Video-MME（11秒至1小时）、MLVU（3分钟至2小时）
- 长视频检索：V-NIAH（1小时视频，约3000帧，插入“needle”图像进行检索）

**对比方法**：
- Vanilla RoPE（标准1D RoPE）
- M-RoPE（Qwen2-VL中高频率给时间）
- VideoRoPE（低频率给时间）
- 本文HoPE

**骨干网络**：Qwen2-1.5B和Qwen2-7B，结合Qwen2-VL视觉编码器得到2B/7B模型。

**训练数据**：LLaVA-Video-178k子集，约30k短视频（<2分钟）和3k长视频（2-3分钟），共计约300k指令样本。

**评估设置**：训练上下文长度8k，评估扩展到8k/16k/32k/64k。

## 4. 资源与算力

论文明确提到：**约304 GPU小时**，在**H800-80GB** GPU上完成。训练过程中使用了128的batch size、1e-5/2e-5学习率。

## 5. 实验数量与充分性

**实验数量**：
- 主实验：3个理解基准 × 2种骨干 × 4种长度 = 24组对比，见表1。
- 检索任务：V-NIAH，图3和表4。
- 消融实验：表2（逐步添加3D结构、HFA、DTS）。
- 缩放因子分析：表3（5个γ值在理解与检索任务上的性能）。
- 附加实验：表5对比不同维度分配（HoPE-X vs HoPE）。

**充分性**：实验设计较为全面，覆盖了多种基准、多种骨干、多种上下文长度，并进行了消融和参数分析。对比了三个有代表性的基线（包括无多模态的Vanilla RoPE、两种主流多模态RoPE）。结果客观，差距显著。

## 6. 论文的主要结论与发现

- HoPE在所有基准上一致优于现有方法：长视频检索提升22.23%，长视频理解提升8.35%（平均）。
- 理论部分证明：所有现有频率分配策略在超长上下文中均无法维持语义偏好；而HFA通过将时间频率置零，提供了更强的语义偏好保证。
- DTS中的缩放因子选择存在权衡：长视频检索偏好小缩放因子（如0.75）以保护语义偏好；长视频理解偏好大缩放因子（如1.5）以保留空间细节。
- 随着骨干模型增大（2B→7B），HoPE的性能增益更加显著。
- 所有方法在64k长度下性能大幅下降，但HoPE相对最稳健。

## 7. 优点

- **理论创新**：首次对多模态RoPE的频率分配策略进行严格理论分析，并提出零频率策略的合理性。
- **方法简单有效**：HFA仅需将最低维度频率置零，DTS仅需训练时随机选择缩放因子，不增加额外参数量。
- **动态灵活性**：DTS允许压缩和扩张双向缩放，适应真实世界视频速度变化。
- **实验扎实**：在多种长上下文基准上验证，消融实验清晰展示了各组件贡献。
- **代码开源**：论文承诺提供代码，有利于复现。

## 8. 不足与局限

- **模型规模限制**：实验仅使用9B以下的骨干（2B/7B），未测试更大模型（如13B/34B或更大数据集训练的效果）。
- **极端长度泛化有限**：在64k（8倍外推）时，所有方法性能显著下降，HoPE虽然最好但仍不理想。论文指出可能需更多长上下文训练数据。
- **数据规模较小**：仅使用约300k训练样本，可能未充分释放方法潜力。
- **未评估其他模态**：仅针对视频，未验证在图像-文本、视频-音频等更复杂多模态场景下的有效性。
- **缩放因子选择依赖任务**：理解与检索任务偏好不同缩放因子，需要手动调整，缺乏自适应机制。

（完）
