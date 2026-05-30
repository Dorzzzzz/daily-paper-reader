---
title: "VideoPrism: A Foundational Visual Encoder for Video Understanding"
title_zh: VideoPrism：用于视频理解的基础视觉编码器
authors: "Long Zhao, Nitesh Bharadwaj Gundavarapu, Liangzhe Yuan, Hao Zhou, Shen Yan, Jennifer J. Sun, Luke Friedman, Rui Qian, Tobias Weyand, Yue Zhao, Rachel Hornung, Florian Schroff, Ming-Hsuan Yang, David A Ross, Huisheng Wang, Hartwig Adam, Mikhail Sirotenko, Ting Liu, Boqing Gong"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=oBP8vXFJNQ"
tags: ["query:long-video"]
score: 7.0
evidence: 用于多种视频理解任务的基础视频编码器
tldr: 本文提出VideoPrism，一个通用视频编码器，在包含3600万高质量视频-字幕对和5.82亿视频片段的大规模异构语料上预训练。通过全局-局部蒸馏和token打乱改进掩码自编码，在33个视频理解任务中的31个上达到最先进性能，涵盖网络视频问答到科学视频分析。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1610, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1497, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 729, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-obp8vxfjnq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 860, \"height\": 309, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1679, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1667, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1621, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1316, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1640, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 838, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 716, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 895, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 866, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1506, \"height\": 1091, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1449, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1446, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1446, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 920, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 820, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 830, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 833, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1179, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 845, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 764, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 719, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 864, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 761, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-obp8vxfjnq/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 729, \"height\": 149, \"label\": \"Table\"}]"
motivation: 需要一个通用视频编码器处理多样视频理解任务。
method: 在大规模异构视频-文本数据上预训练，采用改进的掩码自编码和全局-局部蒸馏。
result: 在31/33个视频理解任务上达到最先进水平。
conclusion: VideoPrism作为单一冻结模型可广泛适用于视频理解。
---

## Abstract
We introduce VideoPrism, a general-purpose video encoder that tackles diverse video understanding tasks with a single frozen model. We pretrain VideoPrism on a heterogeneous corpus containing 36M high-quality video-caption pairs and 582M video clips with noisy parallel text (e.g., ASR transcripts). The pretraining approach improves upon masked autoencoding by global-local distillation of semantic video embeddings and a token shuffling scheme, enabling VideoPrism to focus primarily on the video modality while leveraging the invaluable text associated with videos. We extensively test VideoPrism on four broad groups of video understanding tasks, from web video question answering to CV for science, achieving state-of-the-art performance on 31 out of 33 video understanding benchmarks.

---

## 论文详细总结（自动生成）

# VideoPrism 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：构建一个通用的视频基础模型（ViFM），能够使用**单一冻结编码器**处理广泛的视频理解任务（分类、定位、检索、描述、问答等），避免为每个任务单独微调带来的高昂计算和存储成本。
- **背景问题**：现有视频模型难以同时兼顾外观（appearance）和运动（motion）信息，往往在某一类任务上表现优异而在另一类上落后；且大多数视频-文本数据中文本描述噪声大、偏向外观。
- **核心目标**：训练一个既具备丰富语义、又能捕捉运动线索的通用视频编码器，在多个下游任务上达到或超越任务专用模型。

## 2. 论文提出的方法论

### 核心思想
采用**两阶段预训练策略**，结合视频-文本对比学习与改进的掩码视频建模：
- 第一阶段：利用所有视频-文本对进行对比学习，让视频编码器学习到语言引导的视觉语义。
- 第二阶段：在大量纯视频数据上使用掩码自编码（masked autoencoding），通过**全局-局部蒸馏**与**token shuffling**，让学生模型在保留第一阶段语义的同时，深入学习运动信息。

### 关键技术细节
1. **数据组成**：
   - 36M 高质量人工标注视频-字幕对（Anonymous-Corpus #1）。
   - 582M 带噪声平行文本的视频片段（ASR、元数据、大模型生成等），共约275M视频。
   - 所有评估数据与预训练数据严格去重。

2. **模型架构**：
   - 基于 ViT 的时空分解设计（ViViT），包含空间编码器和时间编码器。
   - 两种规模：VideoPrism-B（ViT-Base，约 0.3B 参数）和 VideoPrism-g（ViT-giant，约 1B 参数）。
   - 输入：8帧（预训练）/ 16帧（评估），空间分辨率 288×288，patch size 18×18。

3. **两阶段训练流程**：
   - **Stage 1（视频-文本对比学习）**：
     - 视频编码器＋文本编码器，对称交叉熵损失。
     - 使用多注意力池化层（MAP）提取视频全局特征。
     - 引入 AGD（交替梯度下降）混合不同数据集，提升可扩展性。
     - 初始化自 CoCa 图像模型，并加入 WebLI（约10亿图像-文本对）共同训练。
   - **Stage 2（改进的掩码视频建模）**：
     - 冻结 Stage 1 编码器作为教师，训练学生编码器（从 Stage 1 初始化）。
     - BEVT 掩码（masking ratio=0.65），仅保留可见 token。
     - **Token shuffling**：将可见 token 与 [MASK] token 拼接后随机打乱，再送入解码器，防止“复制粘贴”捷径。
     - **全局蒸馏损失**：让学生通过可见 token 预测教师的全局视频嵌入（经 MAP）。
     - **局部（token-wise）蒸馏损失**：让学生解码器重建教师的逐 token 嵌入。
     - 两个蒸馏损失权重相同。

## 3. 实验设计

### 数据集与 Benchmark
论文将评估分为四大任务群，涵盖 33 个基准数据集：

| 任务类别 | 数据集 |
|---------|--------|
| 通用视频理解（VideoGLUE） | K400, MiT, SSv2, D48, Charades, ActivityNet, AVA, AVA-K |
| 零样本视频-文本检索 | MSRVTT (1K-A & full split), VATEX, ActivityNet |
| 零样本视频分类 | K400, K600, SSv2 (Temporal/Events), NExT-QA (ATP-Hard), Charades, Charades-STA |
| 零样本视频描述与问答 | MSRVTT-Cap, VATEX-Cap, YouCook2, MSRVTT-QA, MSVD-QA, NExT-QA |
| 科学视频理解 | Fly vs. Fly, CalMS21, CRIM13 (侧/顶), KABR, ChimpACT |

### 对比方法
- 图像基础模型：CLIP, CoCa, FLAVA, ImageBind
- 视频基础模型：VATT, VideoMAE, InternVideo, UMT, VideoCoCa, LanguageBind, IMP, Flamingo, mPLUG-2 等
- 科学领域专家模型（如 SlowFast、Task Programming 等）

### 评估设置
- **主实验**：冻结视频编码器，仅训练任务头（MAP probe / G-TAD / 分类器 / 低秩适配器）。
- **适应方法**：四种（frozen、MLAP、adapter、end-to-end fine-tuning）在 VideoGLUE 上分别报告。
- **零样本**：利用 LiT 学习文本编码器进行检索和分类；将视频编码器与 PaLM-2 通过 Resampler 连接进行描述/QA。

## 4. 资源与算力

- 论文**未明确说明** GPU 型号、数量或总训练时长。
- 训练配置：
  - Batch size: 4096（两阶段均相同）
  - Stage 1: 200K 步，学习率 linear decay，Adafactor 优化器
  - Stage 2: 300K 步，学习率 cosine decay，Adafactor 优化器
  - 预训练数据总量约 618M（36M+582M）视频片段
- 模型规模最大达 **1B 参数**（ViT-giant），但未给出具体硬件信息。可以认为需要大规模分布式训练（如 TPU 集群）。

## 5. 实验数量与充分性

- **实验数量充足**：在 33 个基准上全面评估，覆盖分类、定位、检索、生成、科学视频。
- **公平性**：
  - 所有评估数据严格从预训练数据中去重，避免泄漏。
  - 对比方法均采用相同评估协议（冻结编码器、相同任务头结构等）。
  - 消融实验系统化：数据规模、两阶段策略、蒸馏方式、掩码策略、模型缩放等。
- **客观性**：论文报告了均值、多次消融、不同适应方法下的分数，并提供了 VideoGLUE 的聚合指标 VGS（考虑了性能和计算成本）。
- **不足之处**：
  - 未与最新的一些开源大模型（如 Video-LLaVA、VideoChat）在长视频任务上比较。
  - 部分基准（如 youcook2、VATEX）上的零样本描述表现未全面超越 Flamingo（但 Flamingo 使用更大 LLM 和非冻结视频编码器）。

## 6. 论文的主要结论与发现

- VideoPrism **在 31/33 个基准上取得最佳成绩**，且没有其他方法能稳定获得第二，证明其**通用泛化能力**。
- 两阶段训练显著提升运动密集型任务（如 SSv2 提升 8%）与外观任务（如 K400 提升 2-4%）。
- Token shuffling 和全局蒸馏在消融实验中分别带来约 1-2% 和 1-1.6% 的提升。
- 模型和数据均具有良好可扩展性：增大模型或增加第二阶段无标注数据均持续改进结果。
- 冻结预训练编码器结合轻量任务头即可达到或超越任务专用模型，实际部署成本低。

## 7. 优点

1. **数据大规模且多样化**：首次将 36M 人工标注视频-字幕与 582M 噪声文本片段结合，覆盖广泛场景。
2. **两阶段设计巧妙**：先通过对比学习建立语义基础，再用改进掩码建模强化运动学习，兼顾外观和运动。
3. **Token shuffling + 全局-局部蒸馏**：创新性地解决了掩码模型中的解码捷径和知识遗忘问题。
4. **严格去重与零泄漏**：避免对评估集过拟合，提高结果可信度。
5. **实用性强**：单一冻结编码器即可覆盖多数任务，降低下游部署开销。
6. **科学视频领域首次全面评估**：展示了视频基础模型在生态、神经科学等领域的潜力。

## 8. 不足与局限

1. **噪声文本可能引入偏差**：ASR/元数据等质量较低，可能局限模型对真实动作的理解。
2. **仅处理短片段（16帧）**：难以直接应用于长视频理解，需要额外系统集成。
3. **冻结设置并非最优**：部分任务（如深度定位）可能需要端到端微调才能达到最佳，当论文未详尽展示。
4. **模型巨大**：1B 参数模型训练和推理资源需求高，可能限制社区复现。
5. **未公开全部预训练数据**：标注数据和部分 YouTube 数据为内部数据，提升复现门槛。
6. **计算成本未量化**：缺少 GPU 小时等细节，无法直接比较效率。
7. **科学视频任务**：部分数据集（如 KABR）上 VideoPrism-B 略低于领域专家模型（~0.4%），且科学任务数量较少，结论外推需谨慎。

（完）
