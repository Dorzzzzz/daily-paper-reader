---
title: "MECD: Unlocking Multi-Event Causal Discovery in Video Reasoning"
title_zh: MECD：解锁视频推理中的多事件因果发现
authors: "Tieyuan Chen, Huabin Liu, Tianyao He, Yihang Chen, Chaofan Gan, Xiao Ma, Cheng Zhong, Yang Zhang, Yingxue Wang, Hui Lin, Weiyao Lin"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=F8aSOovlEP"
tags: ["query:long-video"]
score: 8.0
evidence: 长视频中跨事件的因果发现
tldr: 当前视频因果推理局限于短时单事件，缺乏对多事件的系统分析。本文提出多事件因果发现任务MECD，要求从长视频的事件描述中识别事件间的因果关联，并构建相应数据集。该方法推动了视频理解从感知向因果推理的深入发展。实验证明了任务的有挑战性和基线方法的有效性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1029, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 656, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 675, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 619, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1260, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1454, \"height\": 1693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-f8asoovlep/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 785, \"height\": 326, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 567, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 571, \"height\": 135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 566, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 560, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 673, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-f8asoovlep/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 672, \"height\": 346, \"label\": \"Table\"}]"
motivation: 现有视频推理任务局限于短时单事件，缺乏多事件因果分析。
method: 定义多事件因果发现任务，要求从长视频事件描述中识别因果关联。
result: 构建数据集并评估基线方法，展示了任务的有效性和挑战性。
conclusion: 多事件因果发现任务促进了视频因果推理的深度研究。
---

## Abstract
Video causal reasoning aims to achieve a high-level understanding of video content from a causal perspective. However, current video reasoning tasks are limited in scope, primarily executed in a question-answering paradigm and focusing on short videos containing only a single event and simple causal relationships, lacking comprehensive and structured causality analysis for videos with multiple events. To fill this gap, we introduce a new task and dataset, Multi-Event Causal Discovery (MECD). It aims to uncover the causal relationships between events distributed chronologically across long videos. Given visual segments and textual descriptions of events, MECD requires identifying the causal associations between these events to derive a comprehensive, structured event-level video causal diagram explaining why and how the final result event occurred. To address MECD, we devise a novel framework inspired by the Granger Causality method, using an efficient mask-based event prediction model to perform an Event Granger Test, which estimates causality by comparing the predicted result event when premise events are masked versus unmasked. Furthermore, we integrate causal inference techniques such as front-door adjustment and counterfactual inference to address challenges in MECD like causality confounding and illusory causality. Experiments validate the effectiveness of our framework in providing causal relationships in multi-event videos, outperforming GPT-4o and VideoLLaVA by 5.7% and 4.1%, respectively.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：现有视频因果推理任务主要局限在短时单事件的问答范式，缺乏对长视频中多个事件之间复杂因果关系的系统分析与结构化表示。
- **动机**：现实场景（如交通监控）需要跨时间分析多个事件如何共同导致最终结果，现有方法无法提供事件级别的因果图。
- **贡献**：提出 **多事件因果发现（MECD）** 任务，要求从包含视觉片段和文本描述的长视频事件序列中，识别出各前置事件与最终结果事件的因果关联，输出完整的因果图；同时构建了相应数据集（基于ActivityNet Captions）和基线框架 **VGCM**。

## 2. 方法论
### 核心思想
- 借鉴 **Granger因果性** 思想：若某个前置事件被掩码后，对结果事件的预测能力显著下降，则认为该事件是原因。
- 但直接应用会面临 **因果混淆**（中间桥梁事件导致因果关系被干扰）和 **虚假因果**（时间临近或对象存在导致的伪因果）两大挑战。

### 关键技术细节
1. **Video Granger Causality Model (VGCM)**  
   - 双分支结构：橙色分支（原始所有前置事件）和绿色分支（掩码掉待测事件 \( e_k \)）。
   - 使用预训练视频编码器（ResNet200 + Action Recognition）和文本编码器（VideoBERT-like），经共享的多模态解码器融合，输出特征。
   - 通过 **关系头（relation head）** 比较掩码/未掩码分支的输出，结合语义相似度损失，判断因果性。
2. **因果推断增强**  
   - **前门调整（Front-door Adjustment）**：针对因果混淆中缺失的 \( e_{k-1} \to e_N \) 效应，引入链式思维（CoT）并利用 do 操作切断直接路径（公式5）。
   - **反事实干预（Counterfactual Intervention）**：去除冗余的 \( e_{k+1} \to e_N \) 效应，使用仅包含对象存在的描述 \( e'_k \) 替换实际事件（公式6）。
   - 最终融合得到修正后的掩码特征 \( O'_{mk} \)（公式7）。
3. **损失函数**：包含 caption 损失、视觉重建损失、因果关系损失、语义相似度损失，按权重组合（公式3）。

## 3. 实验设计
### 数据集与场景
- **MECD 数据集**：基于 ActivityNet Captions（1.3版本）筛选出1105个长视频（806训练，299测试），每个视频含4-11个事件，至少2个前置事件与结果有因果关系。人工标注因果标签，并引入GPT-4初始标注再经五名标注者交叉校验。
- **场景多样**：涵盖体育、制作、日常、表演、社交五大类。

### Benchmark 与对比方法
- **Baselines**：  
  - 随机猜测  
  - 少样本 LLM：Gemini-1.5-Pro、GPT-4-0613  
  - VLLM：MiniGPT4-video、MiniGPT-4、Video-llama、VideoChat2、VideoLLaVA、GPT-4o  
  - 微调模型：VAR、Videobert、CLIP (ViT-L/14)、VideoChat2 (fine-tuned)、VideoLLaVA (fine-tuned)
- **Metrics**：  
  - **Top-1 准确率**（输出因果链与标签一致）  
  - **结构汉明距离（SHD）**：评估完整因果图的匹配程度（平均12.31条因果边）。

## 4. 资源与算力
- **训练配置**：1块 NVIDIA A40 GPU，训练20个epoch，约6小时；优化器为BertAdam，学习率16e-5，预热3个epoch。
- **推理速度**：VGCM 0.76秒/样本，比所有 Video LLM 快3-6倍（如VideoLLaVA 2.12秒，MiniGPT4-video 3.98秒）。

## 5. 实验数量与充分性
- **主实验**（表1）：对比了11+个基线方法，包含少样本、微调等多种范式。
- **消融实验**（表2）：逐步验证各损失项（\( L_C, L_V, L_S \)）及因果推断组件（前门调整、反事实干预）的效果。
- **专项分析**：  
  - 虚假时间因果（表4）：比较首/末关系的准确率下降幅度。  
  - 虚假存在因果（表3）：测量特征相似度比值。  
  - 模态依赖分析（附录C.1）：分别掩码文本或视觉输入，评估稳健性。  
  - 鲁棒性实验（图5）：随机翻转标签、数据量变化。  
  - 开放集跨类别验证（表5）：5折交叉验证准确率64.4%。  
  - 下游任务验证（表7）：将VGCM输出的因果关系作为提示输入VLLM，提升VQA性能。
- **公平性**：所有VLLM/LLM均采用相同few-shot设置，微调模型使用相同训练数据，报告三次随机种子均值。

## 6. 主要结论与发现
- **VGCM 显著优于所有基线**：完整VGCM准确率71.2%，比GPT-4o高5.7%，比VideoLLaVA高4.1%。
- **因果推断组件有效**：前门调整和反事实干预分别缓解了时间混淆和存在错觉。
- **鲁棒性强**：对标签噪声和数据量变化不敏感；对输入模态依赖较低（即使80%掩码仍优于多数基线）。
- **可迁移性**：输出因果图能提升下游VQA任务准确率（从43.17%升至62.21%）。

## 7. 优点
- **任务创新**：首次系统定义多事件视频因果发现，填补了因果推理从单事件到多事件的空白。
- **方法论严谨**：结合Granger因果性与因果推断工具，针对性解决具体挑战（混淆与虚假因果），而非简单端到端分类。
- **数据质量**：通过GPT-4初始+人工交叉标注，降低主观偏差；数据集多样且包含丰富的辅助信息（CoT、存在描述）。
- **实验充分**：涵盖多种基线、消融、鲁棒性、跨任务验证，展示了方法的优越性和泛化性。
- **效率高**：推理速度远快于视频LLM，适合实际应用。

## 8. 不足与局限
- **输入依赖**：需要预先提供事件的时间戳（弱监督扩展待探索）。
- **高层语义理解不足**：对于情感、心理等抽象因果可能无法准确建模（如附录B.1中未发现“创造期待”这类非显式因果）。
- **监督范式限制**：当前为全监督，未来可探索无监督或自监督版本。
- **数据集规模**：仅约1100视频，可能不足以覆盖所有复杂的因果模式。
- **因果图仅限于事件级**：未涉及更细粒度的对象或动作级因果关系。

（完）
