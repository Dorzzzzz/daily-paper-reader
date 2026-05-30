---
title: "Eagle 2.5: Boosting Long-Context Post-Training for Frontier Vision-Language Models"
title_zh: Eagle 2.5：提升前沿视觉语言模型的长上下文后训练
authors: "Guo Chen, Zhiqi Li, Shihao Wang, Jindong Jiang, Yicheng Liu, Lidong Lu, De-An Huang, Wonmin Byeon, Matthieu Le, Max Ehrlich, Tong Lu, Limin Wang, Bryan Catanzaro, Jan Kautz, Andrew Tao, Zhiding Yu, Guilin Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X2xLfqX24x"
tags: ["query:long-video"]
score: 9.0
evidence: 长视频理解与高分辨率图像理解
tldr: 针对长上下文视觉语言模型训练中上下文完整性和视觉细节保持的挑战，本文提出Eagle2.5框架，包含自动降采样和图像区域保留技术，并构建了Eagle-Video-110K数据集。实验证明，该方法在长视频理解基准上取得了显著提升。该工作为长视频多模态学习提供了有效训练范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 619, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 662, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 756, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 690, \"height\": 495, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 703, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2xlfqx24x/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 706, \"height\": 217, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型在处理长视频和高分辨率图像时，上下文完整性和细节保持不足。
method: 提出自动降采样和图像区域保留技术，结合长上下文数据训练优化。
result: Eagle2.5在长视频理解基准上取得了显著改进。
conclusion: 所提出的后训练框架有效提升了视觉语言模型的长上下文能力。
---

## Abstract
We introduce Eagle2.5, a frontier vision-language model (VLM) for long-context multimodal learning. Our work addresses the challenges in long video comprehension and high-resolution image understanding, introducing a generalist framework for both tasks. The proposed training framework incorporates Automatic Degrade Sampling and Image Area Preservation, two techniques that preserve contextual integrity and visual details. The framework also includes numerous efficiency optimizations in the pipeline for long-context data training. Finally, we propose Eagle-Video-110K, a novel dataset that integrates both story-level and clip-level annotations, facilitating long-video understanding. Eagle2.5 demonstrates substantial improvements on long-context multimodal benchmarks, providing a robust solution to the limitations of existing VLMs. Notably, our best model Eagle2.5-8B achieves 72.4\% on Video-MME with 512 input frames, matching the results of top-tier commercial model such as GPT-4o and large-scale open-source models like Qwen2.5-VL-72B and InternVL2.5-78B.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：当前视觉语言模型（VLM）主要聚焦于短上下文任务，在长视频理解和高分辨率图像理解方面存在明显不足。长上下文场景（如多图、长视频、高分辨率媒体）的处理面临数据集构建、架构设计、训练策略以及计算/内存瓶颈等根本性挑战。
- **整体含义**：本文旨在开发一个通用的长上下文VLM训练框架，通过创新的训练策略和数据配方，使模型能够原生地处理长序列视觉输入，并在不引入额外压缩模块的前提下，实现随输入帧数增加而一致提升的性能。最终达到或超越闭源模型（GPT-4o）和大型开源模型（Qwen2.5-VL-72B、InternVL2.5-78B）的效果。

### 2. 论文提出的方法论

- **核心思想**：采用“信息优先采样”策略，优先保留文本完整性并动态优化视觉内容；配合“渐进式混合后训练”逐步提升上下文长度；同时构建包含故事级和片段级双重标注的长视频数据集，以增强长视频理解能力。
- **关键技术细节**：
  - **图像区域保留**：优化分块策略，通过最大化面积保留率和宽高比保真度的联合目标（公式1），避免传统刚性分块对图像几何信息的破坏。
  - **自动降采样**：一个两阶段动态优化过程。先固定图像分块数为1，优化时间采样数（视频帧或文档页数）以最大化时间覆盖，同时确保文本不被截断；再根据剩余视觉预算动态选择图像分块数（从12降至1），保留尽可能多的视觉细节。
  - **渐进式混合后训练**：逐步增大最大序列长度（如32K→64K→128K），相比一次性训练到最大长度，能更好保持短上下文能力并实现平滑过渡。
  - **Eagle-Video-110K数据集**：采用多样性驱动的视频收集策略（基于CLIP相似度阈值过滤），并通过自上而下的故事级标注（利用人类标注的章节生成密集描述和长问答）和自下而上的片段级标注（GPT-4o生成细粒度问答并加入时间锚和文本上下文锚）实现双重标注。

### 3. 实验设计

- **数据集/场景**：
  - 视频基准：MVBench、Perception_test、EgoSchema、MLVU、LongVideoBench、Video-MME、CG-Bench、HourVideo、Charade-STA等。
  - 图像基准：DocVQA、ChartQA、InfoVQA、TextVQA、OCRBench、MMstar、RWQA、AI2D、MMMU、MMB 1.1、MMVet、HallB、MathVista等。
  - 训练数据：大量开源数据（人类标注+合成数据）以及自创的Eagle-Video-110K。
- **对比方法**：
  - 闭源模型：GPT-4o、Claude-3.5-Sonnet、Gemini-1.5-Pro、Gemini-2.5-Pro、Seed1.5-VL。
  - 开源模型：MiniCPM-V2.6-8B、LongVILA-8B、InternVL2.5-8B/78B、LLaVA-Video-8B/72B、Qwen2.5-VL-8B/72B、VideoChat-Flash-8B、LLaVA-One-Vision-8B/72B等。

### 4. 资源与算力

- 论文在“Limitations”部分明确提到：训练Eagle2.5需要大量的计算资源，具体为128块H100 GPU集群。未说明训练总时长或其他细节。

### 5. 实验数量与充分性

- **实验数量**：论文在视频和图像两个大类共约20个基准上进行了主实验对比，并做了4组消融实验：
  - Q1：长上下文数据对图像基准的影响（表4，含Lmax=32K/64K/128K）。
  - Q2：图像数据和预训练对视频基准的影响（表5）。
  - Q3：信息优先采样的效果（表6，包含w/o IAP和w/o ADS）。
  - Q4：Eagle-Video-110K数据集和不同后训练调度的效果（表7，图6）。
- **充分性与公平性**：实验覆盖了主流视频和图像基准，对比了多个同级和更大规模模型，消融实验直接验证了核心组件的贡献。但未报告误差棒或统计显著性，也未说明随机种子与多次运行结果。总体来说实验设计较为充分且公平。

### 6. 论文的主要结论与发现

- Eagle2.5-8B在多个长视频基准上达到领先水平：Video-MME（w/o subtitle）72.4%，MLVU 77.6%，LongVideoBench 66.4%，均超过同尺寸模型，并匹配GPT-4o和更大规模开源模型。
- 信息优先采样（IAP+ADS）对高分辨率图像和细粒度视频任务至关重要，能有效保留视觉信息并避免文本截断。
- 渐进式混合训练优于直接长上下文混合训练，能更平稳地提升模型处理长序列的能力。
- Eagle-Video-110K数据集填补了开源数据中长视频缺失的问题，显著提升了模型处理128帧以上帧数的能力。

### 7. 优点

- **方法亮点**：
  - 提出“信息优先采样”，以文本完整性为先，动态优化视觉内容分配，避免传统固定采样导致的信息丢失。
  - 图像区域保留策略兼顾面积和宽高比，避免了传统分块的几何失真。
  - 双重标注的数据集（故事级+片段级）有效提升了长视频的叙事理解和时空细节捕捉。
- **实验亮点**：
  - 在8B参数规模下达到或超越72B级模型，展示了高效率。
  - 消融实验直接验证了各组件贡献，结论清晰。

### 8. 不足与局限

- **资源需求高**：训练需要128块H100 GPU，限制了可复现性和普及性。
- **缺乏统计可靠性**：未报告误差棒或统计检验，可能存在单次运行的不确定性。
- **数据与代码未开源**：虽描述了方法细节，但未提供模型权重、数据集访问方式或代码，影响可复现性。
- **未讨论社会影响**：缺少对模型潜在滥用（如生成误导信息）的讨论和安全措施描述。
- **领域覆盖有限**：主要针对视频和图像理解，未见对多模态文档、3D或音频等其他长上下文场景的评估。

（完）
