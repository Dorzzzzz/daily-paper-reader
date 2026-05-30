---
title: "LongVU: Spatiotemporal Adaptive Compression for Long Video-Language Understanding"
title_zh: LongVU：面向长视频语言理解的时空自适应压缩
authors: "Xiaoqian Shen, Yunyang Xiong, Changsheng Zhao, Lemeng Wu, Jun Chen, Chenchen Zhu, Zechun Liu, Fanyi Xiao, Balakrishnan Varadarajan, Florian Bordes, Zhuang Liu, Hu Xu, Hyunwoo J. Kim, Bilge Soran, Raghuraman Krishnamoorthi, Mohamed Elhoseiny, Vikas Chandra"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=XzZC4gs1mf"
tags: ["query:long-video"]
score: 9.0
evidence: 面向长视频理解的时空自适应压缩
tldr: 长视频处理受限于LLM上下文大小，现有方法丢失细节。本文提出LongVU，利用DINOv2去除冗余帧并结合文本引导跨模态查询自适应减少时空冗余，有效压缩视频令牌，在保持视觉细节的同时使多模态大模型高效理解长视频。该方法显著扩展了视频理解长度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1730, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 1227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1726, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1667, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1702, \"height\": 946, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1601, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1567, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1044, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1462, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1605, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1300, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1685, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1080, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1258, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1260, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1259, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1258, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1260, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1256, \"height\": 208, \"label\": \"Table\"}]"
motivation: LLM上下文限制制约长视频理解，现有方法丢失细节。
method: 提出LongVU时空自适应压缩机制，利用DINOv2去冗余和文本引导查询。
result: 在长视频理解基准上取得优异性能，扩展了可处理视频长度。
conclusion: LongVU为长视频理解提供了有效的令牌压缩方案。
---

## Abstract
Multimodal Large Language Models (MLLMs) have shown promising progress in understanding and analyzing video content. However, processing long videos remains a significant challenge constrained by LLM's context size. To address this limitation, we propose \textbf{LongVU}, a spatiotemporal adaptive compression mechanism that reduces the number of video tokens while preserving visual details of long videos. Our idea is based on leveraging cross-modal query and inter-frame dependencies to adaptively reduce temporal and spatial redundancy in videos. Specifically, we leverage DINOv2 features to remove redundant frames that exhibit high similarity. Then we utilize text-guided cross-modal query for selective frame feature reduction. Further, we perform spatial token reduction across frames based on their temporal dependencies. Our adaptive compression strategy effectively processes a large number of frames with little visual information loss within given context length. Our LongVU consistently surpass existing methods across a variety of video understanding benchmarks, especially on hour-long video understanding tasks such as VideoMME and MLVU. Given a light-weight LLM, our LongVU also scales effectively into a smaller size with state-of-the-art video understanding performance.

---

## 论文详细总结（自动生成）

# LongVU: 时空自适应压缩用于长视频语言理解

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：多模态大语言模型（MLLM）在处理长视频时受限于LLM的上下文长度（如8k）。现有方法要么均匀采样固定帧数（丢失关键帧），要么采用密集采样导致超出上下文而截断，均无法高效保留长视频的视觉细节。
- **背景**：单张图像消耗数百至数千token，而一小时视频可能需超过200k token。亟需一种在有限上下文内保留尽可能多帧信息的压缩策略。
- **目标**：提出LongVU，通过自适应时空压缩，使模型能在给定上下文长度内处理密集采样的长视频（如1fps），并显著提升长视频理解性能。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 利用**跨模态查询**（文本引导）和**帧间依赖**，自适应减少视频中的时空冗余，保留关键视觉信息。

### 技术细节（三步压缩）

1. **时间缩减 (Temporal Reduction)**  
   - 使用DINOv2（自监督视觉模型）提取帧特征，计算滑动窗口内（大小J=8）每帧与其它帧的平均相似度，丢弃高相似度（冗余）帧。  
   - 剩余帧再用SigLIP提取特征，并通过Spatial Vision Aggregator (SVA)融合DINOv2和SigLIP特征。

2. **选择性特征缩减 via 跨模态查询 (Selective Feature Reduction via Cross-modal Query)**  
   - 若拼接后的帧特征仍超过上下文长度`L_max`，则利用文本查询的LLM嵌入，计算每帧与文本的注意力分数。  
   - 保留分数最高的`N_h`帧为高分辨率（`H_h×W_h` tokens），其余帧降采样为低分辨率（`H_l×W_l` tokens）。  
   - `N_h`由`L_max`、文本长度和低分辨率tokens总数动态计算。

3. **空间令牌压缩 (Spatial Token Compression, STC)**  
   - 若低分辨率tokens仍超限，则将帧序列分为非重叠滑动窗口（大小K=8）。  
   - 窗口内第一帧保留全部token，后续帧与第一帧对应空间位置计算余弦相似度，相似度高于阈值θ的token被剪枝。  
   - 通过帧间依赖减少空间冗余。

### 关键公式
- 查询引导选择公式：  
  `N_h = max(0, (L_max - L_q - T·H_l·W_l) / (H_h·W_h - H_l·W_l))`  
  L_q为文本长度，T为时间缩减后的帧数。
- 空间令牌压缩公式（式2）：  
  若`sim(v1(h,w), vi(h,w)) ≤ θ`则保留，否则删除。

## 3. 实验设计

### 数据集
- **预训练**：LLaVA-OneVision单图像数据（3.2M样本）。
- **视频微调**：VideoChat2-IT子集，包括TextVR, Youcook2, Kinetics-710, NExTQA, CLEVRER, EgoQA, TGIF, WebVidQA, ShareGPT4Video, MovieChat等（约553K样本，详见正文Table 6）。

### Benchmark
- **EgoSchema**（约3分钟视频，179.8秒）
- **MVBench**（16秒视频）
- **MLVU**（3分钟~2小时视频）
- **VideoMME**（1分钟~1小时视频，含Short/Medium/Long子集）

### 对比方法
- **开源模型**：Video-LLaVA, LLaMA-VID, Chat-UniVi, ShareGPT4Video, LLaVA-NeXT-Video, VideoLLaMA2, LongVA, VideoChat2, LLaVA-OneVision, Phi-3.5-vision-instruct, InternVL2等。
- **闭源模型**：GPT4-V, GPT4-o。

### 评价指标
- 准确率（Accuracy），Greedy解码（num_beams=1），1fps采样输入（我们的方法）。

## 4. 资源与算力

- **GPU**：64块 NVIDIA H100 GPU（训练时使用）。
- **训练配置**：图像预训练阶段global batch size=128，视频微调阶段global batch size=64。均训练1个epoch，学习率1e-5，warmup rate 0.03，优化器AdamW。
- **额外需要**：DINOv2特征提取可离线预处理；单次推理在A100 (80GB)上20分钟视频约33秒（见Appendix E Table 11）。

## 5. 实验数量与充分性

### 主要实验组
- **主实验**：在4个基准（EgoSchema, MVBench, MLVU, VideoMME）上与10+开源模型及2个闭源模型对比。
- **小模型实验**：用Llama3.2-3B与Phi-3.5等对比。
- **消融实验**：详细分析各组件（时间缩减、查询引导、STC）、token数量、上下文长度、DINO/SigLIP选择、窗口大小、阈值等（Table 3-5, 13-18）。
- **Needle-in-a-Video-Haystack**：验证长视频中关键帧定位能力。
- **压缩率分析**：显示时间缩减保留约45.9%帧，STC保留约59.6% token（综合压缩至约14.2%）。
- **图像能力退化实验**：视频SFT后图像性能下降，再加图像SFT可恢复（Table 10）。

### 充分性与公平性
- 实验设计全面，覆盖短、中、长视频，且对比方法多为近期最强开源模型。
- 消融实验系统，证明每个组件的有效性。
- 公平性：所有模型在相同benchmark下评估（官方划分）。但训练数据量不同（如LLaVA-OneVision使用更多数据，但未公开），我们的模型用更少数据取得更好结果。
- 略缺乏与大型闭源模型的公平比较（算力、数据不可控），但在开源范畴内非常充分。

## 6. 主要结论与发现

- **LongVU显著提升长视频理解性能**：在VideoMME Long子集上比LLaVA-OneVision高12.8%，在MVBench上高10.2%（与VideoChat2相比）。
- **自适应压缩优于均匀采样和密集采样**：能保留更多关键帧信息，尤其适合长视频。
- **DINOv2+SigLIP组合优于单编码器**：DINOv2捕获低层视觉差异，SigLIP提供语义对齐。
- **跨模态查询有效引导选择性保留**：在计数、检索类任务（如MLVU的needle、order）上提升显著。
- **空间令牌压缩减少空间冗余**：在不损失性能前提下大幅减少token数。
- **可扩展至轻量模型**：3B参数版本仍达到SOTA。

## 7. 优点

- **创新性**：首次结合DINOv2自监督特征进行帧级时间缩减，并利用文本查询动态选择关键帧分辨率。
- **有效性**：在多个长视频基准上取得SOTA，尤其长视频（>30分钟）优势明显。
- **效率**：压缩后平均每帧仅2 token，使1fps采样的一小时视频可在8k上下文内处理。
- **可解释性**：每一步压缩都有明确动机（时间冗余、空间冗余、查询引导）。
- **工程实用**：DINOv2特征可离线提取，在线推理开销小；支持不同LLM（7B和3B）。

## 8. 不足与局限

- **图像能力退化**：仅用视频数据微调后，图像理解性能显著下降（如GQA从62.26→60.83），需额外图像SFT恢复（Table 10）。
- **缺乏帧级时序编码**：仅拼接压缩后token，未显式编码时间位置，导致时序定位（如事件起止）能力弱（Appendix G提及）。
- **训练数据局限**：视频训练数据平均时长较短（≤3分钟），可能限制对超长视频（>1小时）的泛化（Appendix F.2提及缺乏长视频标注）。
- **超参数敏感**：DINO阈值（0.83）、STC阈值（0.75）等需调参，不同视频分布可能需重新调整（如Table 15-16显示波动）。
- **未与最新长上下文方法比较**：如LongVILA（扩展至2M上下文），但论文未进行对比。
- **可复现性**：训练数据部分（VideoChat2-IT）可能不完全公开，LLaVA-OneVision图像数据可获取但需申请。

（完）
