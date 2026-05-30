---
title: "VideoLucy: Deep Memory Backtracking for Long Video Understanding"
title_zh: VideoLucy：面向长视频理解的深度记忆回溯框架
authors: "Jialong Zuo, Yongtai Deng, Lingdong Kong, Jingkang Yang, Rui Jin, Yiwei Zhang, Nong Sang, Liang Pan, Ziwei Liu, Changxin Gao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=To7Rs2wsTd"
tags: ["query:long-video"]
score: 9.0
evidence: 层次化记忆用于长视频理解
tldr: 基于智能体的长视频理解系统常对单帧建模，忽略时序上下文，且稀疏采样可能丢失关键信息。本文提出VideoLucy，受人类从粗到细回忆过程启发，采用层次化记忆结构：先构建粗粒度全局记忆，再通过回溯机制定位关键片段进行细粒度分析。在多个长视频基准上，VideoLucy显著优于现有方法，实现了对长视频更全面的理解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 681, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 717, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 708, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 710, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 764, \"height\": 125, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 946, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1428, \"height\": 124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1442, \"height\": 128, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1375, \"height\": 105, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-to7rs2wstd/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1449, \"height\": 130, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 967, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 479, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 717, \"height\": 788, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 533, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1416, \"height\": 1148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 1035, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1420, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 824, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 637, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-to7rs2wstd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1423, \"height\": 645, \"label\": \"Table\"}]"
motivation: 现有长视频理解系统无法有效捕获连续帧的时序上下文且采样稀疏。
method: 提出层次化记忆结构与深度回溯机制，从粗到细处理长视频。
result: 在多个长视频基准上取得最优性能，实现全面理解。
conclusion: 为长视频理解提供了有效的记忆驱动框架。
---

## Abstract
Recent studies have shown that agent-based systems leveraging large language models (LLMs) for key information retrieval and integration have emerged as a promising approach for long video understanding. However, these systems face two major challenges. First, they typically perform modeling and reasoning on individual frames, struggling to capture the temporal context of consecutive frames. Second, to reduce the cost of dense frame-level captioning, they adopt sparse frame sampling, which risks discarding crucial information. To overcome these limitations, we propose VideoLucy, a deep memory backtracking framework for long video understanding. Inspired by the human recollection process from coarse to fine, VideoLucy employs a hierarchical memory structure with progressive granularity. This structure explicitly defines the detail level and temporal scope of memory at different hierarchical depths. Through an agent-based iterative backtracking mechanism, VideoLucy systematically mines video-wide, question-relevant deep memories until sufficient information is gathered to provide a confident answer. This design enables effective temporal understanding of consecutive frames while preserving critical details. In addition, we introduce EgoMem, a new benchmark for long video understanding. EgoMem is designed to comprehensively evaluate a model's ability to understand complex events that unfold over time and capture fine-grained details in extremely long videos. Extensive experiments demonstrate the superiority of VideoLucy. Built on open-source models, VideoLucy significantly outperforms state-of-the-art methods on multiple long video understanding benchmarks, achieving performance even surpassing the latest proprietary models such as GPT-4o. Our code and dataset will be made publicly available.

---

## 论文详细总结（自动生成）

# VideoLucy：深度记忆回溯框架用于长视频理解 —— 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

长视频理解要求系统具备对整个视频内容的全面记忆和把握，以准确回答用户问题。现有基于智能体（agent-based）的系统主要存在两大挑战：
- **时序上下文缺失**：这些系统通常对独立帧进行建模和推理，难以捕获连续帧之间的时序上下文。
- **稀疏采样导致信息丢失**：为降低密集帧级描述成本，采用稀疏帧采样，可能丢弃关键信息。

受人类回忆过程（从粗到细）启发，论文提出 VideoLucy，一种深度记忆回溯框架，模拟人类“先有模糊印象，再逐步回忆细节”的能力，实现长视频中信息的全覆盖与时序理解。同时引入新基准 EgoMem，评估极长视频中的时间理解与细粒度细节感知。

## 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：层次化记忆结构 + 智能体驱动的迭代回溯机制。记忆按颗粒度分为三个层次：长程粗粒度记忆、短程细粒度记忆、帧级超细粒度记忆。随着层级加深，时间跨度缩小，细节逐渐丰富。

**关键技术细节**：
- **层次化记忆结构**：将视频分为K个短片段，每个片段由视频 MLLM 生成文本描述。通过控制K值（从1到N）获得不同时间感知范围的记忆。定义了三种记忆：粗粒度（大面积时间块）、细粒度（更短片段）、超细粒度（帧级）。
- **多智能体角色**：
  - 描述代理（Captioning Agent）：视频 MLLM，将视频片段转换为文本。
  - 定位代理（Localization Agent）：LLM，基于当前记忆和问题，找出最相关的时间段。
  - 指令代理（Instruction Agent）：分析缺失的关键信息，生成指引描述的重点指令。
  - 回答代理（Answering Agent）：基于当前记忆判断是否能自信回答问题；若不能则输出不自信标志。
- **迭代回溯机制**（Algorithm 1）：
  1. **稀疏粗粒度记忆初始化**：对整个视频采用粗粒度时间跨度生成初始记忆列表，并通过定位代理筛选出最相关的几个时间段。
  2. **问题引导的深度与广度探索**：每次迭代中，定位代理找出单个最相关时间段；指令代理分析缺失信息；描述代理对该时间段重新生成文本描述（更新当前深度记忆），并将该片段进一步分割为更短片段生成更深层记忆。
  3. **循环停止条件**：回答代理认为当前记忆足够提供自信答案时终止迭代。设置最大迭代次数防止超时。

**算法流程**（文字说明）：
- 输入：视频、问题、各代理、各层级时间跨度参数。
- 输出：最终自信答案。
- 步骤：初始化稀疏粗记忆 -> 回答 -> 若不自信则循环：定位最相关不重复时间段 -> 分析缺失信息并生成指令 -> 获取该时间段的视频片段 -> 按当前深度对应时间跨度分成短片段 -> 更新当前深度记忆 -> 生成更深层记忆 -> 再次回答。直到回答自信或达到最大迭代。

## 3. 实验设计：数据集/场景、基准、对比方法

**基准数据集**：
- **MLVU**（综合，视频时长3分钟-2小时，9类任务）
- **Video-MME**（2700个问题，900视频，分短/中/长三档，报告无字幕结果）
- **LVBench**（超长视频，1492问题，99视频，平均4101秒，6类任务）
- **EgoMem**（新构建，基于EgoLife，42个视频平均6.33小时，504个QA，6种事件理解+细节感知问题）

**对比方法**：
- 专有模型：Gemini 1.5 pro/Flash、GPT-4o、GPT-4V、GLM-4V-plus
- 开源MLLM：TimeMarker-8B、VideoLLaMA3-7B、InternVL2.5-78B、Qwen2-VL-72B、ReTake-7B、VideoChat-Flash-7B、AdaReTaKe-72B 等
- 智能体系统：VideoAgent、VideoTree、MemVid、VCA、DrVideo、Video-RAG-7B 等

**评估指标**：准确率（accuracy）。

## 4. 资源与算力

论文中**未明确说明**训练算力（GPU型号、数量、训练时长）。因为VideoLucy是一个基于智能体的零样本框架，无需训练。推理时：
- MLLM（Qwen2.5-VL-7B）部署在8块A100 GPU上使用vLLM批量推理。
- LLM（DeepSeek-R1）使用官方API。

## 5. 实验数量与充分性

**实验组数**：
- 主对比实验：4个基准（MLVU、Video-MME、LVBench、EgoMem）均报告了与众多方法的对比结果。
- 消融实验：
  - “Needle-in-A-Video-Haystack”实验（10个长视频，共200个问题）
  - 记忆深度影响（粗/细/超细对比）
  - 迭代次数影响（1~6次）
  - 信息丰富度与相关性分析（Shannon熵与LLM评分）
  - 不同MLLM/LLM组合的适应性测试（8种组合）
- 定性比较：两个案例（事件理解、细节感知）
- 失败案例分析：两种代表性失败场景。

**充分性与公平性**：
- 实验覆盖了多个主流长视频基准，包括极长视频（LVBench、EgoMem），对比了专有模型和开源模型中状态最优的方法。
- 使用了官方排行榜结果或论文报告的最新数据，保证对比的时效性和公平性。
- 消融实验设计合理，验证了各组件贡献。
- 需要注意：部分对比方法的结果从论文或官方排行榜获取，环境可能不完全一致，但属于该领域通用做法。

## 6. 论文的主要结论与发现

- VideoLucy在MLVU、Video-MME、LVBench、EgoMem四个基准上均取得最优或领先性能，显著超越所有现有智能体系统，甚至在某些指标上超过GPT-4o等专有模型。
- 在LVBench上，VideoLucy准确率58.8%，比GPT-4o高9.9%；在KIR任务上达75.6%。
- 层次化记忆结构有效：从粗到细逐步深入能持续提升性能，超细粒度最优。
- 迭代次数5为默认最佳，继续增加提升有限。
- 在“针海捞针”实验中，VideoLucy几乎不受视频长度影响，细节感知能力远超其他模型。
- 不同MLLM/LLM组合的适应性实验表明框架鲁棒性好，更强的基座模型进一步提升性能。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 受人类记忆启发，提出层次化记忆结构，显式控制细节层次和时间范围，有效兼顾全局与局部。
  - 迭代回溯机制动态探索问题相关记忆，避免全记忆处理的高成本和干扰信息。
  - 多智能体协作设计清晰，各司其职（定位、描述、指令、回答），可解释性强。
- **实验设计亮点**：
  - 构建了专属超长视频基准EgoMem（平均6.33小时），专门评估跨时间事件理解和瞬时细节感知，填补了现有基准的空白。
  - “Needle-in-A-Video-Haystack”实验直观展示了细节检索能力。
  - 对信息丰富度和相关性进行了量化分析（Shannon熵和LLM评分）。
  - 探索了不同MLLM/LLM组合的泛化能力，证明框架无模型绑定。
- **开源友好**：全部使用开源模型（Qwen2.5-VL-7B、DeepSeek-R1），可复现、低成本。

## 8. 不足与局限

- **依赖基座模型能力**：系统的“眼睛”MLLM和“大脑”LLM的局限性会传导至整体性能，如MLLM产生幻觉导致错误描述（见失败案例2），LLM上下文限制可能影响超超长视频（数百小时）。
- **推理效率**：相比端到端视频MLLM，智能体系统需要多轮LLM调用，推理时间较长。不过论文指出，同一视频的多个问题可复用缓存记忆以加速。
- **实验覆盖**：虽然对比了多个基准，但缺少在更广泛场景（如不同语言、不同拍摄质量）下的评估。EgoMem基于第一视角日常视频，可能无法全面代表所有超长视频类型。
- **未提及训练**：框架是零样本的，未讨论如何通过训练进一步优化记忆结构或代理策略。
- **最大视频长度的局限性**：受LLM上下文长度限制，对于数百小时的视频可能仍有挑战（但已远超现有数据集）。

（完）
