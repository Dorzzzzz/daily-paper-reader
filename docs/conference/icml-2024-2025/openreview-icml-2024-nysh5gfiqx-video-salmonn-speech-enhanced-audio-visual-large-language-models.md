---
title: "video-SALMONN: Speech-Enhanced Audio-Visual Large Language Models"
title_zh: video-SALMONN：语音增强的音视频大语言模型
authors: "Guangzhi Sun, Wenyi Yu, Changli Tang, Xianzhao Chen, Tian Tan, Wei Li, Lu Lu, Zejun MA, Yuxuan Wang, Chao Zhang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=nYsh5GFIqX"
tags: ["query:long-video"]
score: 5.0
evidence: 语音增强的视频理解，多分辨率时序处理
tldr: 本文提出video-SALMONN，一个端到端音视频大语言模型，能同时理解视觉帧、音频事件和语音。为获取精细时序信息同时保持效率，提出多分辨率因果Q-Former结构，结合多样性损失和非配对音视频混合训练。实验表明其在多种视频理解任务上的有效性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1515, \"height\": 887, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 791, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1617, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1613, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1536, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1602, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1643, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1514, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1574, \"height\": 1051, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1557, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1498, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1487, \"height\": 911, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-nysh5gfiqx/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1452, \"height\": 762, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1459, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1524, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1756, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 732, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1596, \"height\": 1898, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1637, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1366, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 736, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1371, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1346, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-nysh5gfiqx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1417, \"height\": 241, \"label\": \"Table\"}]"
motivation: 视频理解中语音理解是重要但未被充分研究的方面。
method: 提出多分辨率因果Q-Former结构连接音视频编码器和LLM，设计多样性损失与非配对混合训练。
result: 在多种视频理解任务上取得优异性能，包括语音相关任务。
conclusion: video-SALMONN实现了一体化音视频理解，尤其增强了语音能力。
---

## Abstract
Speech understanding as an element of the more generic video understanding using audio-visual large language models (av-LLMs) is a crucial yet understudied aspect. This paper proposes video-SALMONN, a single end-to-end av-LLM for video processing, which can understand not only visual frame sequences, audio events and music, but speech as well. To obtain fine-grained temporal information required by speech understanding, while keeping efficient for other video elements, this paper proposes a novel multi-resolution causal Q-Former (MRC Q-Former) structure to connect pre-trained audio-visual encoders and the backbone large language model. Moreover, dedicated training approaches including the diversity loss and the unpaired audio-visual mixed training scheme are proposed to avoid frames or modality dominance. On the introduced audio-visual evaluation benchmark, video-SALMONN achieves more than 25% absolute accuracy improvements on the video-QA task and over 30% absolute accuracy improvements on audio-visual QA tasks with human speech. In addition, video-SALMONN demonstrates remarkable video comprehension and reasoning abilities on tasks that are unprecedented by other av-LLMs. Our training code and model checkpoints are available at https://github.com/bytedance/SALMONN/

---

## 论文详细总结（自动生成）

# video-SALMONN 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在音视频大语言模型（av-LLMs）的通用视频理解中，语音理解是一个关键但未被充分研究的方面。现有 av-LLMs（如 Video-LLaMA、Macaw-LLM）主要处理非语音音频事件（如环境声音）和视觉帧，但无法有效理解语音内容及其中包含的丰富副语言信息（语调、情绪、说话人属性等）。
- **整体含义**：语音是视频中人类语言的主要载体，对完整理解视频不可或缺。构建一个能够端到端、一体化地处理视觉帧、音频事件、音乐以及语音的模型，是实现通用视频理解的重要一步。为此，论文提出 **video-SALMONN**，一个语音增强的音视频大语言模型，旨在同时理解视频中的所有基本要素。

## 2. 方法论：核心思想、关键技术细节

### 2.1 模型架构
- **编码器**：采用预训练编码器（冻结参数）提取各模态特征：
  - 视觉编码器：InstructBLIP 的 ViT + Q-Former（输出每帧 32 个特征向量，帧率 2Hz）。
  - 语音编码器：Whisper large-v2（输出 50Hz 频谱帧率）。
  - 非语音音频编码器：BEATs（输出 50Hz）。
- **时间精细同步模块**：将音频特征与视觉帧在时间上对齐（每 0.5 秒同步一次），通过零填充使序列长度一致，然后沿特征维度拼接得到联合表示 \( h^{SAV}_t \)。

### 2.2 多分辨率因果 Q-Former（MRC Q-Former）
- **核心思想**：针对语音需要精细时序信息而视觉需要宏观语义的矛盾，设计多分辨率窗口处理。
- **结构**：
  - 将同步后的输入序列划分为固定长度的滑动窗口，支持多个分辨率级别（默认使用 0.5 秒和 5 秒两种分辨率）。
  - 在每个分辨率级别 \( r \) 下，使用 \( N^{(r)} \) 个可学习查询向量对窗口内的特征进行 Q-Former 处理，输出 \( N^{(r)} \) 个查询向量。
  - 保持不同分辨率的总输出查询数 \( C = W^{(r)} \times N^{(r)} \) 一致（默认 \( C=160 \)）。
  - 所有分辨率级共享 Q-Former 参数（查询向量不同），最终通过投影层加权组合送入 LLM。
- **因果自注意力**：在 Q-Former 内部加入因果掩码，使编码当前帧时能自动回归地包含前帧信息，有利于时序因果推理。

### 2.3 训练策略
- **多样性损失（Diversity Loss）**：鼓励低分辨率窗口内输出查询向量之间的余弦相似度尽可能小，防止信息冗余。损失公式：
  \[
  L_{\text{diverse}} = \sum_{r}\sum_{w}\sum_{i}\sum_{j\neq i} \text{sim}(h^{(r)}_{w,i}, h^{(r)}_{w,j})
  \]
- **非配对音视频混合训练（Unpaired Audio-Visual Mixed Training）**：在训练数据中混入非配对的音频和视频，提示词同时要求完成原本配对任务，迫使模型从两个模态提取信息，避免模态主导。
- **总损失**：交叉熵损失 + \(\lambda L_{\text{diverse}}\)（默认 \(\lambda=0.1\)）。
- **LLM 微调**：使用 LoRA（秩 32）适配 Vicuna-v1.5（7B/13B），仅更新约 0.4% 的 LLM 参数。

## 3. 实验设计

### 3.1 评测基准（SAVE Benchmark）
- **单模态任务（6个）**：
  - ASR（LibriSpeech test-clean，WER）
  - 音频字幕（AudioCaps test，SPIDEr）
  - 图像字幕（Flickr30k test，CIDEr）
  - OCR（TextVQA test，准确率）
  - 视觉问答（GQA test-dev，准确率）
  - 视频问答（NExT-QA test，准确率）
- **音视频任务（4个，涵盖6个数据集）**：
  - 音视频语音识别（How2 dev5，WER）
  - 音视频问答（Ego4D-QA + Presentation-QA，准确率）
  - 音视频声音源检测（VGGSS，准确率）
  - 音视频匹配（SpokenCOCO + VGGSS，准确率）

### 3.2 对比方法
- 单模态基线：Whisper large-v2、InstructBLIP 13B（原始及在 video-SALMONN 训练集上微调后的版本）
- 多模态基线：Video-LLaMA 7B（唯一公开可用的音视频 LLM）

### 3.3 训练数据
- 总共约 100 万样本，包括：
  - 语音：LibriSpeech train-clean-100/360
  - 音频：AudioCaps
  - 视觉：LLAVA-150k、OCRVQA、TextCaps、COCO（带口语描述）、VideoChat、MSVD-QA
  - 音视频：Ego4D（600 小时）、How2（300 小时）、AVSD
- 所有数据均为公开数据集。

## 4. 资源与算力
- **论文未明确说明使用的 GPU 型号、数量及训练时长**。仅提及使用 Vicuna-v1.5（7B/13B）作为骨干 LLM，并采用 LoRA 微调。计算开销主要来自 MRC Q-Former 和前向传播。由于未提供具体算力信息，无法量化。

## 5. 实验数量与充分性

### 5.1 实验组数
- **主要结果**：表2（单模态任务，7个系统对比）、表3（音视频任务，7个系统对比）。
- **消融实验**：表4 展示了 7 种消融配置（移除不同分辨率、混合训练、多样性损失、MRC Q-Former 等）。
- **分辨率分析**：图4 展示了不同窗口大小对 ASR 和 Video QA 的影响。
- **多样性损失分析**：图5 展示了不同 \(\lambda\) 对 AVSR 和 Video QA 的影响。
- **额外实验**：附录中包含 LRS2 唇读、MUSIC-AVQA、Llama-2 vs Vicuna 对比、静态图像 spotlight 实验等。

### 5.2 充分性与公平性
- **充分性**：实验覆盖了多种模态组合和任务类型，消融实验验证了各核心组件的贡献，分辨率分析和多样性损失分析提供了深入理解。
- **公平性**：对比基线（InstructBLIP、Video-LLaMA）均在同一训练数据上微调或采用标准配置；零样本设置（如 NExT-QA、Presentation-QA）避免了数据泄露。但 Video-LLaMA 仅提供 7B 版本，而 video-SALMONN 主要使用 13B，规模不完全对等。

## 6. 主要结论与发现
- video-SALMONN 是首个能够同时理解语音、非语音音频和视觉的端到端单模型 av-LLM。
- 在 SAVE 基准上，video-SALMONN 在视频 QA 任务上相比微调后的 InstructBLIP 提升超过 25% 绝对准确率；在音视频 QA 任务上相比 Video-LLaMA 提升超过 30% 绝对准确率。
- MRC Q-Former 能够有效平衡语音（需高分辨率）和视觉（需低分辨率）的需求；多样性损失和非配对混合训练显著提升音视频联合推理能力。
- 模型展现出令人瞩目的涌现能力：如基于语音内容回答图像问题、为不配对音视频编故事、结合对话与背景音乐解释电影片段的情感等。

## 7. 优点
- **创新性**：MRC Q-Former 结构首次将多分辨率时序处理引入 Q-Former，兼顾语音的精细信息和视觉的粗粒度语义。
- **完整性**：统一处理语音、音频事件、音乐和视觉帧，涵盖视频所有基本要素，避免复杂级联系统。
- **训练技巧**：多样性损失和非配对混合训练有效缓解了帧/模态主导问题，增强了跨模态协同推理能力。
- **开源**：提供训练代码和模型权重，有利于复现和后续研究。
- **评测基准**：构建了包含多种任务类型的 SAVE 基准，便于系统评估。

## 8. 不足与局限
- **资源消耗**：高帧率视觉编码和 MRC Q-Former 的多窗口计算可能导致较高的存储和计算成本，论文未提供效率分析。
- **图像空间分辨率**：静态图像任务（如 OCR、VQA）性能受限于 ViT 的分辨率；虽然引入 spotlight 方法改进 OCR，但对视频任务有轻微负面影响。
- **偏差风险**：继承自预训练模型（Whisper、InstructBLIP、Vicuna）的偏差（如人口统计特征、文化偏见）未做缓解。
- **应用限制**：主要针对短视频（默认 25 秒），对更长视频需要更多计算资源；零样本泛化能力仅在部分任务上验证，实际表现可能受训练数据分布影响。
- **伦理风险**：论文提及语音理解可能导致监控和窃听等滥用，尽管声明了使用指南，但未提供具体缓解技术。
- **公开细节不足**：训练算力、超参数敏感性、推理速度等未充分披露，影响可复现性和公平比较。

（完）
