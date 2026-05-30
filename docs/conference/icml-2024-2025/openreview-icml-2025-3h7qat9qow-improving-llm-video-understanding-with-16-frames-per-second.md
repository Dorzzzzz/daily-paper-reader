---
title: Improving LLM Video Understanding with 16 Frames Per Second
title_zh: 以每秒16帧改善LLM视频理解
authors: "Yixuan Li, Changli Tang, Jimin Zhuang, Yudong Yang, Guangzhi Sun, Wei Li, Zejun MA, Chao Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3H7qAT9Qow"
tags: ["query:long-video"]
score: 9.0
evidence: 高帧率（16FPS）视频理解方法
tldr: 现有视频理解方法多采用低帧率采样，丢失动态信息。本文提出F-16多模态大模型，首次实现16FPS高帧率视频理解，通过每秒片段的视觉令牌压缩高效捕获动态特征，在多个基准上显著提升视频理解性能，为视频理解提供新视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1735, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 647, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1371, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1369, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1369, \"height\": 2283, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 739, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 772, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1677, \"height\": 1141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1241, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1272, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1243, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1642, \"height\": 1116, \"label\": \"Table\"}]"
motivation: 低帧率采样导致动态视觉信息丢失，限制视频理解。
method: 提出F-16多模态大模型，以16FPS处理视频并通过视觉令牌压缩保留语义。
result: 高帧率显著提升多个视频理解基准性能。
conclusion: 该工作表明提高帧率是改善视频理解的有效新途径。
---

## Abstract
Human vision is dynamic and continuous. However, in video understanding with multimodal large language models (LLMs), existing methods primarily rely on static features extracted from images sampled at a fixed low frame rate of frame-per-second (FPS) $\leqslant$2, leading to critical visual information loss. In this paper, we introduce F-16, the first multimodal LLM designed for high-frame-rate video understanding. By increasing the frame rate to 16 FPS and compressing visual tokens within each 1-second clip, F-16 efficiently captures dynamic visual features while preserving key semantic information.
Experimental results demonstrate that higher frame rates considerably enhance video understanding across multiple benchmarks, providing a new approach to improving video LLMs beyond scaling model size or training data. F-16 achieves state-of-the-art performance among 7-billion-parameter video LLMs on both general and fine-grained video understanding benchmarks, such as Video-MME and TemporalBench. Furthermore, F-16 excels in complex spatiotemporal tasks, including high-speed sports analysis (*e.g.*, basketball, football, gymnastics, and diving), outperforming SOTA proprietary visual models like GPT-4o and Gemini-1.5-pro.
Additionally, we introduce a novel decoding method for F-16 that enables highly efficient low-frame-rate inference without requiring model retraining. We will release the source code, model checkpoints, and data at [https://github.com/bytedance/F-16](https://github.com/bytedance/F-16).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **现状问题**：现有视频多模态大语言模型（Video LLMs）普遍采用低帧率采样（≤2 FPS）或固定帧数（如8-64帧），导致快速变化的视觉信息（如身体运动、微表情）丢失，限制了模型对动态场景的理解能力。
- **研究动机**：人类视觉是动态连续的，而低帧率采样相当于把每1秒视频片段当作几张静态图片处理，无法捕捉高速运动中的细节。作者旨在通过提高帧率至16 FPS，同时压缩冗余信息，使模型能像人类一样感知连续动态。
- **整体含义**：提出F-16，首个支持16 FPS高帧率视频理解的多模态LLM，证明提升帧率是超越单纯扩大模型或数据规模的新途径，在通用和细粒度视频理解任务上达到7B参数量的SOTA，并在高速运动任务上超越GPT-4o等商业模型。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：以16 FPS密集采样视频帧，通过设计**高帧率对齐器（High-Frame-Rate Aligner）** 将每1秒窗口内的多帧视觉特征压缩为少量视觉令牌，既保留语义信息又捕获动态特征，同时控制令牌总数。
- **架构**：基于LLaVA-OneVision-7B架构（SigLIP视觉编码器 + Qwen2-7B LLM），扩展为16 FPS处理。
- **高帧率对齐器设计**：
  - 输入：每1秒窗口包含16帧（窗口宽度w=16），每帧经图像编码器得到特征$Z_i \in \mathbb{R}^{p \times d}$（p个patch，d维度）。
  - 步骤：将窗口内16帧特征沿特征维度拼接 → $Z^{\text{cat}}_j \in \mathbb{R}^{p \times (16d)}$。
  - 两层线性层（含GELU）：第一层$P$将维度从$16d$映射到$16h$，第二层$Q$映射到$h$（LLM输入维度）。输出$\tilde{H}_j \in \mathbb{R}^{p \times h}$。
  - 空间压缩：对$\tilde{H}_j$进行$2 \times 2$最大池化，将p个patch减至约p/4，最终每个窗口输出令牌$H_j \in \mathbb{R}^{\lfloor \sqrt{p}/2 \rfloor^2 \times h}$。
- **预训练图像LLM初始化**：采用**块矩阵分解**，将单帧对齐器的权重$W_A$, $W_B$复制并组合成高维对齐器参数，使初始状态等价于窗口内各帧特征的平均，保证训练稳定性。主对角线外加入Kaiming均匀噪声。
- **变帧率解码**：测试时可通过帧重复（frame repetition）将训练好的16 FPS模型降帧率运行，无需重训练。方法：对于目标帧率低于16，将每帧特征重复k次以满足对齐器输入维度。

## 3. 实验设计
- **通用视频理解**：
  - 数据集：Video-MME（短/中/长）、NeXT-QA、TemporalBench、MotionBench、MLVU、LongVideoBench、VideoVista。
  - 对比方法：GPT-4o、Gemini-1.5-Pro、Qwen2-VL-7B、VideoLLaMA2、LLaVA-OV-7B、LLaVA-Video-7B、NVILA-7B等。
  - 评价指标：Accuracy（TemporalBench用Multiple Binary Accuracy）。
- **高速运动理解**（微调后评估）：
  - 数据集：FineGym（体操）、Diving48（跳水）、SoccerNet（足球传球计数）、NBA（投篮是否命中）。
  - 对比方法：GPT-4o、Gemini-1.5-Pro、GPU=1和GPU=16版本的F-16自对比。
  - 评价指标：Accuracy、F1。
- **变帧率解码分析**：对比不同测试FPS（1/2/4/8/16）下的表现和推理时间。
- **消融实验**：池化位置（pre vs post）、对齐器结构（线性 vs CNN vs 注意力 vs 双线性）、参数初始化策略、变量解码方法（重复 vs 裁剪）。
- **特征分析**：计算帧间余弦相似度，验证高帧率特征差异。

## 4. 资源与算力
- **通用视频训练**：128块H100 GPU，学习率2e-5，1个epoch。
- **运动任务微调**：64块H100 GPU，LoRA（rank=128，scale=2.0），5个epoch，学习率2e-5。
- 未明确说明总训练时间，但算力投入较大。

## 5. 实验数量与充分性
- **实验数量**：
  - 通用理解：7个基准数据集，对比8+种方法。
  - 运动理解：4个任务（含自对比和商业模型）。
  - 变帧率测试：不同FPS下性能与时间对比。
  - 消融实验：池化位置、对齐器结构（线性/CNN/注意力/双线性）、解码策略（重复/裁剪）、初始化噪声影响。
  - 特征余弦相似度分析。
- **充分性与客观性**：
  - 基准选择覆盖通用、细粒度、高速运动，较全面。
  - 对比方法包括SOTA开源及商业模型，基线公平。
  - 消融实验充分验证设计选择，包括对CNN/注意力等替代结构的探讨（虽未完全成功，但诚实报告）。
  - 变帧率解码验证了实际部署效率。
  - 不足：仅使用7B规模，未与更大模型（如13B/34B）对比；运动数据集较小且仅在一个域（运动）微调；未在长视频（>110秒）上提供有效方案（均匀采样1760帧，可能丢失时间结构）。

## 6. 主要结论与发现
- **高帧率显著提升性能**：在通用视频理解上，F-16在Video-MME、NeXT-QA、TemporalBench、MotionBench上达到7B SOTA；在TemporalBench上比前SOTA提高13.5%。
- **高速运动理解超越商业模型**：F-16在体操、跳水、篮球、足球任务上均优于GPT-4o和Gemini-1.5-Pro，高帧率比低帧率版本提升10-15%以上。
- **变帧率解码有效**：训练于16 FPS的模型可降帧率测试，性能基本保持，计算成本大幅下降。
- **对齐器结构**：线性MLP优于CNN或注意力，池化放在对齐器之后（post-pooling）更有效，帧重复解码优于参数裁剪。

## 7. 优点
- **创新性**：首次系统研究高帧率（16 FPS）在视频LLM中的应用，提供新思路。
- **架构简洁高效**：通过简单拼接+线性层+池化实现帧间压缩，避免复杂空间-时间建模，且可利用预训练图像LLM的知识。
- **实用性**：变帧率解码允许实际场景中权衡速度与质量，无需额外训练。
- **实验全面**：覆盖通用及高速运动场景，消融实验详细解释设计选择。
- **开源承诺**：代码、模型、数据将公开。

## 8. 不足与局限
- **模型规模单一**：仅探索7B参数，未验证在更大LLM上的适用性。
- **长视频处理局限**：超过110秒的视频仅均匀采样1760帧，可能丢失关键事件的时间连续性（非流式处理）。
- **运动任务泛化性**：仅微调了4个运动类，未验证其他高速场景（如动物行为、粒子运动等）。
- **推理速度**：高帧率下图像编码器成为瓶颈，尽管变帧率解码可缓解，但原模型实时性仍不足。
- **数据偏差**：训练数据主要来自公开集（ActivityNet等），运动数据规模有限，可能导致域内过拟合。
- **未考虑音频模态**：模型仅处理视觉，而运动场景常伴随声音线索（如哨声、碰撞声）。
- **实验缺陷**：未与同参数量的其他专门运动理解模型（如基于3D CNN的方法）对比；变帧率解码仅测试在通用基准上的表现，未在运动任务上验证。

（完）
