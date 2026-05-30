---
title: Recurrent Attention-based Token Selection for Efficient Streaming Video-LLMs
title_zh: 基于循环注意力令牌选择的高效流式视频大语言模型
authors: "Vaggelis Dorovatas, Soroush Seifi, Gunshi Gupta, Rahaf Aljundi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1OuhWYrwgW"
tags: ["query:long-video"]
score: 9.0
evidence: 基于循环注意力令牌选择的高效流式视频语言模型
tldr: "针对流式场景下长视频在线处理的需求，本文提出一种免训练的视觉令牌选择方法，利用LLM的注意力机制识别并丢弃约95%的不重要令牌，同时结合层次化令牌选择与自然语言理解。该方法在不引入额外训练开销的情况下，使标准Video-LLM能够高效处理小时级长视频，并保持高问答准确率。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1ouhwyrwgw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1413, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1ouhwyrwgw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1404, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1176, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 678, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 723, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 448, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 695, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 829, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 935, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 753, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1219, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1ouhwyrwgw/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 977, \"height\": 178, \"label\": \"Table\"}]"
motivation: 流式长视频需要在线处理，现有视频LLM要求完整访问视频，无法实时响应。
method: 利用LLM注意力机制识别重要令牌，层次化选择并丢弃大部分令牌，实现流式处理。
result: "丢弃95%令牌后性能损失极小，可处理小时级视频流。"
conclusion: 注意力驱动的令牌选择是实现高效流式视频理解的关键技术。
---

## Abstract
Video Large Language Models (Video-LLMs) excel at understanding videos in-context, assuming full access to the video when answering queries. However, these models face challenges in streaming scenarios where hour-long videos must be processed online, and questions need timely responses. In this work, we propose a training-free approach compatible with standard Video-LLMs, leveraging three key concepts: 1) LLM-informed selection of visual tokens to identify those that the LLM has attended to and contributed to its understanding of each short clip. Our attention-based selection allows us to discard up to ~95\% of unimportant visual tokens with minimal performance loss; 2) Hierarchical selection of tokens combined with natural language understanding of each processed clip; 3) Caption-based question answering for lightweight and accurate responses. Our method achieves state-of-the-art performance on streaming video benchmarks, striking a balance between efficiency and effectiveness.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：现有视频大语言模型（Video-LLMs）需要完整访问视频才能回答问题，但在流式场景（如小时级视频在线处理、实时问答）中，计算成本随令牌数线性增长，且上下文长度限制导致稀疏采样，信息丢失严重。
- **意义**：为实现智能助手在自动驾驶、监控、医疗等领域的实时视觉理解，亟需一种高效、低内存、可流式处理的长视频理解方法。

## 2. 方法论
- **核心思想**：利用 LLM 在生成文本描述（caption）时的注意力分数，识别并保留少量关键视觉令牌，通过循环传递历史令牌保持时序连贯性，最后仅依靠 caption 进行问答。
- **关键技术细节**：
  - **注意力引导的视觉令牌选择**：对每个短片段，计算 LLM 最后生成 token 与输入视觉 token 的跨层/跨头平均注意力分数（公式 5），保留分数最高的 \(N_S\) 个令牌（约 6%），丢弃其余 94%。
  - **循环处理（Recurrency）**：将上一片段选出的令牌作为下一片段输入的一部分（FIFO 队列），使 LLM 能基于过去视觉信息理解当前片段，增强时序连贯性。
  - **基于 Caption 的检索与问答**：存储每个片段的 caption 文本（而非视觉令牌）。回答问题时，对用户查询和所有 caption 进行余弦相似度计算，并用最大边际相关性（MMR）检索 top-K 最相关且多样化的 caption，仅将 caption 文本送入 LLM 生成答案（算法 1）。
- **无需训练**：直接利用预训练 Video-LLM（如 LLaVA-OV、Qwen2.5-VL），无需微调或添加外部模块。

## 3. 实验设计
- **数据集与场景**：
  - 流式基准：**Realtime VStream-QA**（RVS-Ego 和 RVS-Movie，各 40 分钟视频，开放性问题）。
  - 离线基准：**MovieChat**（170 视频，平均 576 秒）、**VS-Ego/VS-Movie**、**CG-Bench**（1219 视频，平均 27 分钟）。
  - 短视频消融：**NextQA-valset**（570 视频，平均 44 秒）。
- **对比方法**：
  - 有训练方法：VideoChatGPT、Chat-UniVi、LLaMA-VID、VideoScan、Flash-VStream-7B。
  - 免训练方法：MovieChat、Goldfish、ReKV。
- **评估指标**：准确率（Acc）与 GPT-3.5 评分（Score）；流式还报告延迟、GPU 内存、KV-Cache 量。

## 4. 资源与算力
- **硬件**：单张/两张 NVIDIA A100 40GB GPU；延迟和 VRAM 测量在单卡上进行。
- **训练时长**：**无需训练**（免训练方法），仅进行推理。
- **模型规模**：主实验使用 LLaVA-OV 7B，也测试 0.5B 和 Qwen2.5-VL 7B。

## 5. 实验数量与充分性
- **实验组数**：
  - 离线长视频：4 个基准（Table 1）。
  - 流式：2 个基准（Table 3），含不同 backbone 和模型规模。
  - 短视频选择策略消融：NextQA 上 4 种选择方法 × 2 种压缩率（Table 2）。
  - 核心设计消融：有无循环（Table 4）、问答模态对比（Table 5）、选择方法对比（Table 6）、压缩率影响（Table 7）。
  - 附加消融：层选择（附录 B）、注意力聚合（附录 C）、上下文长度（附录 D）、检索策略（附录 F）、与其他 uniform 基线对比（附录 G）。
- **充分性与公平性**：实验覆盖主流流式和离线基准，与多种 SOTA 方法公平比较（使用同一 backbone 或同一评估协议）；消融实验系统验证各组件贡献。结论可靠客观。

## 6. 主要结论与发现
- 所提方法 rLiVS 在流式基准 RVS-Ego/Movie 上达到 **SOTA**（LLaVA-OV 7B：65.3%/57.7%），超越之前最好方法 ReKV（63.7%/54.4%），且延迟更低（1.9s vs 2.7s）、VRAM 减少 11GB（25GB vs 36GB）。
- 即使在 0.5B 小模型上仍优于许多 7B 方法，体现高效性。
- 注意力选择比均匀采样、均值池化、K-Means 更优，仅保留 6% 令牌即可保持接近完整性能。
- 循环处理（recurrency）带来 3-4% 的持续提升；基于 caption 的问答优于基于视觉令牌或混合模态。
- 极端压缩（6%）在复杂运动场景（如体育）中仍能生成语义准确描述。

## 7. 优点
- **免训练、模型无关**：即插即用，无需修改 backbone，降低部署门槛。
- **极高压缩率**：保留 6% 视觉令牌，大幅降低内存和计算开销，适合流式实时处理。
- **循环增强时序连贯性**：通过传递历史令牌，使短片段理解更连续，避免“独立片段”方法中的实体跟踪困难。
- **Caption 问答有效**：将长视频问答转化为纯文本检索+推理，利用 LLM 擅长长文本的优势。
- **任务可自适应**：注意力选择对输入指令敏感，可灵活适配不同任务（如跟踪、动作识别）。

## 8. 不足与局限
- **效率优先可能忽略细节**：极端压缩下可能丢失细微视觉信息，尤其在关键物体被错误过滤时。
- **FIFO 记忆机制简单**：仅基于时序丢弃旧令牌，无法保证保留语义上最重要的历史信息。
- **依赖预训练 backbone**：继承视觉/时序理解局限性，无法解决 backbone 本身的不足。
- **Caption 冗余**：循环 captioning 可能产生相似描述，影响检索多样性；虽用 MMR 缓解，但非完美。
- **场景覆盖有限**：未在更多超长视频或复杂推理基准（如 EgoSchema）上验证；仅一种 backbone（LLaVA-OV）作为主要实验，Qwen2.5-VL 仅测流式。
- **可扩展性未充分探讨**：当视频长度远超训练时体验极值，性能可能退化。

（完）
