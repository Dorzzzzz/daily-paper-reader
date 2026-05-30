---
title: "MoMa: Modulating Mamba for Adapting Image Foundation Models to Video Recognition"
title_zh: MoMa：调制Mamba以适配图像基础模型进行视频识别
authors: "Yuhuan Yang, Chaofan Ma, Zhenjie Mao, Jiangchao Yao, Ya Zhang, Yanfeng Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AgAn6xtwWO"
tags: ["query:long-video"]
score: 8.0
evidence: 通过Mamba适配器实现视频时空建模
tldr: 现有视频理解方法常分离处理时空信息，难以捕捉完整动态。本文提出MoMa适配器框架，将Mamba状态空间模型注入图像基础模型，通过SeqMod操作实现统一的时空建模，在保持预训练特征的同时高效提升视频识别性能。该方法为视频理解提供轻量级有效方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-agan6xtwwo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1783, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-agan6xtwwo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-agan6xtwwo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 824, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-agan6xtwwo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 420, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 883, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1762, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-agan6xtwwo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 695, \"height\": 243, \"label\": \"Table\"}]"
motivation: 现有视频理解方法时空分离，难以捕捉完整动态。
method: 提出MoMa适配器，利用Mamba选择性状态空间模型注入图像基础模型实现全时空建模。
result: 在视频识别任务上取得高效且有效的性能提升。
conclusion: MoMa为适配图像模型进行视频理解提供了新的轻量级框架。
---

## Abstract
Video understanding is a complex challenge that requires effective modeling of spatial-temporal dynamics. 
With the success of image foundation models (IFMs) in image understanding, recent approaches have explored parameter-efficient fine-tuning (PEFT)  to adapt IFMs for video. 
However, most of these methods tend to process
spatial and temporal information separately,
which may fail to capture the full intricacy of video dynamics. 
In this paper, we propose MoMa, an efficient adapter framework that achieves full spatial-temporal modeling by integrating Mamba's selective state space modeling into IFMs. 
We propose a novel SeqMod operation to inject spatial-temporal information into pre-trained IFMs, without disrupting their original features. 
By incorporating SeqMod into a Divide-and-Modulate architecture, MoMa enhances video understanding while maintaining computational efficiency. 
Extensive experiments on multiple video benchmarks demonstrate the effectiveness of MoMa, achieving superior performance with reduced computational cost. 
Codes will be released upon publication.

---

## 论文详细总结（自动生成）

# 论文《MoMa: Modulating Mamba for Adapting Image Foundation Models to Video Recognition》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视频理解的核心挑战是有效建模时空动态。图像基础模型（IFM，如CLIP）在图像任务上成功，但缺乏时序建模能力。现有参数高效微调（PEFT）方法通常将空间和时间信息分开处理（如AIM、DiST），导致时空交互间接、难以捕捉完整动态。直接对完整时空序列使用全注意力则计算复杂度过高（二次复杂度）。
- **整体含义**：本文提出MoMa框架，利用Mamba（选择性状态空间模型）的线性复杂度优势，将其作为轻量级适配器注入预训练Transformer-based IFM，在不破坏原有特征的前提下实现全时空建模，从而提升视频识别性能并保持计算效率。

## 2. 方法论

### 核心思想：Divide-and-Modulate架构

- 在每个Transformer层中，依次执行**Divide阶段**和**Modulate阶段**。

### 关键技术细节

#### （1）Divide阶段
- **目的**：降低注意力计算成本，通过限制注意力范围为局部窗口。
- **操作**：将每帧的特征图划分为非重叠的2D窗口（默认窗口大小 \(w \times w = 8 \times 8\)），在每个窗口内独立应用预训练CLIP的注意力层。
- **复杂度**：从 \(O((HW)^2 T)\)（逐帧全注意力）降至 \(O(w^2 \cdot HWT)\)（线性于窗口大小和序列长度）。

#### （2）Modulate阶段
- **核心组件**：**SeqMod（Sequence Modulation）操作**，灵感来自自适应归一化（AdaN），但将标量尺度和偏置扩展为与输入同形状的序列，实现细粒度的序列级调制。
- **SSM层**：使用Mamba的SSM模块，通过双向扫描（空间和时序维度）输出两个序列 \(y_1\)（尺度）和 \(y_2\)（偏置）。
- **公式**：
  - 输入：Divide阶段输出 \(x_i\)
  - SSM输出：\(y_1^i, y_2^i = \text{SSM}(x_i)\)
  - SeqMod：\(\text{SeqMod}(x_i, y_1^i, y_2^i) = y_1^i \odot x_i + y_2^i + x_i\)（⊙为元素乘）
  - 最终输出：\(V_{i+1} = \text{FFN}(\text{SeqMod}(x_i, y_1^i, y_2^i))\)
- **训练方式**：仅SSM层可训练，CLIP所有参数冻结；使用分类损失和CLIP蒸馏损失。

## 3. 实验设计

### 数据集与场景

- **标准视频识别**：Kinetics-400（240K训练视频，400类）、Something-Something V2（SSv2，168.9K训练视频，174类，需强时序建模）
- **长视频理解**：Breakfast（1,712视频，10种烹饪活动，平均77小时）、COIN（11,827视频，180种程序性任务，平均2.36分钟）
- **零样本迁移**：HMDB51（51类）、UCF101（101类）

### 对比方法

- **全参数微调**：MViT、TimeSformer、VideoSwin、UniFormer、VideoMamba等
- **PEFT方法**：EVL、AIM、DiST、ActionCLIP、X-CLIP等
- 所有方法均基于CLIP预训练（ViT-B/16或ViT-L/14）

### 评估指标

- Top-1 / Top-5准确率
- 计算量（GFLOPs）、参数量、可训练参数量

## 4. 资源与算力

- **硬件**：8块NVIDIA Tesla V100 GPU，使用fp16混合精度训练
- **训练时长**：在K400数据集上训练30个epoch约需12小时
- **优化器**：AdamW，学习率3e-4，权重衰减0.05
- **其他**：使用与ActionCLIP相同的提示词（prompt）

## 5. 实验数量与充分性

- **实验类别**：
  - 标准识别：K400（表1）、SSv2（表2），对比多种PEFT和全微调方法。
  - 长视频：Breakfast和COIN（表3），与VideoMamba、Turbo等对比。
  - 零样本：HMDB51和UCF101（表4），与ActionCLIP、X-CLIP、DiST对比。
  - 消融实验（表5-7）：
    - 不同融合操作（Skip, Add, Max, Concat, Raw-AdaN vs. SeqMod）
    - 窗口大小（全图、16×16、8×8、4×4、3D窗口）
    - 层设计模式（[TM]12, [T]12[M]12, [T]6[TMM]6, [TTMM]6）
  - 速度对比（图4）：与UMT（全注意力）和AIM（空时分离）比较GPU内存和FPS。
- **充分性**：覆盖了主流视频理解benchmark，消融实验系统分析了核心设计（融合策略、窗口尺寸、层结构），对比了多种SOTA方法，实验设计较为全面和公平。

## 6. 主要结论与发现

- MoMa在K400和SSv2上均达到或超越现有PEFT方法，且计算量（GFLOPs）更低（例如ViT-L/14在K400上仅需4152 GFLOPs，比AIM的5604低25.6%）。
- 在长视频数据集（Breakfast, COIN）上，MoMa大幅超越非端到端方法，并优于VideoMamba。
- 零样本迁移方面，MoMa在HMDB51和UCF101上均优于DiST（如ViT-L/14: 59.1% vs 57.5% on HMDB51）。
- 消融实验证明：
  - SeqMod远优于简单融合（Add、Max、Concat）和原始AdaN。
  - 窗口分割（8×8）比全图注意力更快且性能更好（全图注意力可能不符合CLIP训练时的序列长度）。
  - 交替的[TM]12模式优于先用全部Transformer再全部Mamba或间隔插入。
- 速度对比显示MoMa在GPU内存和推理FPS上优于全注意力UMT，与空时分离AIM相当或更优，且内存增长更平缓。

## 7. 优点

- **创新性**：首次将Mamba作为适配器集成到预训练图像基础模型中，利用线性复杂度实现全时空建模。
- **方法设计巧妙**：SeqMod借鉴自适应归一化（AdaN）思想，但扩展为序列级调制，避免干扰预训练特征分布，同时保持信息注入能力。
- **高效性**：仅增加少量可训练参数（ViT-B/16仅11M可训练参数），显著降低FLOPs，同时保持或提升性能。
- **全面验证**：在多个标准/长视频/零样本场景下验证，消融实验覆盖核心设计选择。
- **速度与记忆优势**：随帧数增长，GPU内存和推理时间增长平稳，适合实际部署。

## 8. 不足与局限

- **实验覆盖**：未在更大规模视频基础模型（如VideoMAE、InternVideo）上验证，仅基于CLIP，不同IFM的泛化性未知。
- **窗口大小敏感**：窗口大小需手动设定（默认8×8），对不同输入分辨率或任务可能需调整，但论文未讨论自动选择策略。
- **对比方法时效性**：对比的PEFT方法（如AIM、DiST）发表于2023年，未包括2024-2025年的最新方法（如VideoMamba2或其他基于Mamba的融合策略），但已对比VideoMamba本身。
- **零样本评估范围**：仅测试HMDB51和UCF101，未在更多零样本视频基准（如Kinetics-600零样本）上评估。
- **长视频评估**：在Breakfast和COIN上，MoMa基于K400微调，未从头训练，可能受益于预训练的大规模数据。
- **无错误分析**：未讨论失败案例或模型在特定类别上的偏差风险。

（完）
