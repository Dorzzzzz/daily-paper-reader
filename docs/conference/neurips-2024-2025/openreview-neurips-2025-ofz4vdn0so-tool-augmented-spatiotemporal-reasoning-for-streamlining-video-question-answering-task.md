---
title: Tool-Augmented Spatiotemporal Reasoning for Streamlining Video Question Answering Task
title_zh: 工具增强的时空推理：简化视频问答任务
authors: "Sunqi Fan, Jiashuo Cui, Meng-Hao Guo, Shuojin Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OFz4VDn0SO"
tags: ["query:long-video"]
score: 8.0
evidence: 工具增强的视频问答推理
tldr: 多模态大模型在复杂视频问答中难以同时建模空间关系与时间因果动态。本文为MLLM配备可扩展视频工具包，增强时空推理能力，并控制工具调用顺序。在多个VideoQA基准上，该方法显著提升了推理准确率，实现了工具数量与多样性的平衡。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 676, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 671, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 1074, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 1013, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ofz4vdn0so/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1456, \"height\": 699, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1405, \"height\": 1213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1490, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1433, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1402, \"height\": 1179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ofz4vdn0so/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1124, \"height\": 257, \"label\": \"Table\"}]"
motivation: 现有MLLM在复杂视频问答中无法兼顾空间关系建模与时间因果理解。
method: 为MLLM配备综合视频工具包，增强时空推理并控制工具调用顺序。
result: 在多个VideoQA基准上获得显著性能提升。
conclusion: 工具增强是提升视频问答推理能力的有效途径。
---

## Abstract
Video Question Answering (VideoQA) task serves as a critical playground for evaluating whether foundation models can effectively perceive, understand, and reason about dynamic real-world scenarios. However, existing Multimodal Large Language Models (MLLMs) struggle with simultaneously ensuring the ability to model spatial relationships between video frames and to understand the causal dynamics of temporal evolution on complex and reasoning-intensive VideoQA. In this work, we equip MLLM with a comprehensive and extensible Video Toolkit, to enhance MLLM’s spatiotemporal reasoning capabilities as well as guarantee the harmony between the quantity and diversity of tools. To better control the tool invocation sequence and avoid toolchain shortcut issues, we propose a Spatiotemporal Reasoning Framework (STAR) that strategically schedules temporal and spatial tools, thereby progressively localizing the key area in the video. Our STAR framework enhances GPT-4o using lightweight tools, achieving an 8.2% gain on VideoMME and 4.6% on LongVideoBench. We believe that our proposed Video Toolkit and STAR framework make an important step towards building autonomous and intelligent video analysis assistants. The code is publicly available at https://github.com/fansunqi/VideoTool.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：视频问答（VideoQA）要求模型同时理解视频帧间的空间关系和时间动态因果，但现有多模态大语言模型（MLLM）在复杂推理场景下表现不佳，难以兼顾这两方面。
- **背景**：现有方法分为视频专用LLM（Video-LLMs）和工具增强LLM（Tool-augmented LLMs），但工具增强方法存在三个关键缺陷：①工具利用单一维度（仅空间或仅时间）；②工具数量与多样性失衡；③工具调度策略不足，导致调用混乱（如“工具链捷径”问题）。
- **动机**：为MLLM配备综合视频工具包，并通过合理的调度框架提升时空推理能力，从而简化视频问答任务。

## 2. 方法论：核心思想、关键技术细节、算法流程
### 核心思想
- 构建一个包含22种工具的视频工具包（Video Toolkit），分为三类：**时间工具**（如帧选择器、时间定位）、**空间工具**（如目标检测、图像字幕）、以及**通用工具**（如文本摘要、视频问答）。
- 提出**时空推理框架（STAR）**，强制交替调用时间工具和空间工具，逐步缩小视频中的**3D感兴趣区域（3D RoI）**，避免工具链捷径。

### 关键技术细节
- **工具设计**：所有工具均为即插即用（plug-and-play），通过标准化工具卡封装功能。代表性工具包括：
  - 空间工具：基于YOLO/Grounding DINO的目标检测，结合补丁缩放（Patch Zoomer）和视觉标记（Set-of-Mark Prompting）。
  - 时间工具：帧选择器（基于LLM），可输出单帧或片段，并支持AKeyS、T*等高效关键帧搜索。
- **STAR算法**：
  - 初始化：对视频均匀稀疏采样，构建可见帧字典（Visible Frame Dictionary）。
  - 迭代过程：
    1. 首轮由LLM规划器从时间或空间工具中选择一个执行。
    2. 后续轮次交替选择另一类工具（时间→空间或空间→时间），更新可见帧字典。
    3. 当时间与空间工具均不足以回答时，允许调用通用工具输出最终答案。
- **优势**：时空交替保证了信息在时间与空间维度之间的互补，逐步聚焦关键区域，类似于链式思维（Chain-of-Thought）的视觉推理。

## 3. 实验设计
### 数据集与基准
- 使用四个广泛使用的VideoQA基准：
  - **VideoMME**（2700题，涵盖短/中/长视频）
  - **NExT-QA**（约5.4万题，侧重因果与时间推理）
  - **LongVideoBench**（1337题，长视频“针在大海”式问题）
  - **EgoSchema**（5000+题，长视频自拍视角）

### 对比方法
- 四类基线：
  - **图像级MLLM**：GPT-4o、Gemini 1.5 Pro、Claude 3.5 Sonnet等。
  - **视频专用LLM**：Qwen2-VL、InternVL3、VideoLLaMA3等（7B~72B规模）。
  - **基于LLM的帧选择方法**：VideoAgent、VideoTree、AKeyS、T*等。
  - **工具学习驱动的方法**：DoraemonGPT、ViperGPT等。
- 评估指标：多选题准确率、处理帧数、推理时间（运行效率）。

### 实验设置
- 两种变体：
  - **STAR（完整版）**：使用≤3B参数的开源模型工具 + GPT-4o作为规划器。
  - **STAR-MINI（轻量版）**：排除>500M参数的工具，使用GPT-3.5-turbo作为规划器。
- 视频长度>16秒时初始均匀采样16帧，否则按1 fps采样。

## 4. 资源与算力
- 论文明确说明：
  - **STAR**框架可运行于一张NVIDIA RTX 4090 GPU。
  - **STAR-MINI**可在个人电脑（如Mac）上运行。
- 未给出具体的训练时长（论文方法为训练-免费（training-free）），仅依赖预训练工具和API调用。
- 使用的工具模型中最大为3B参数（如Qwen2.5-VL-3B），部分工具依赖GPT-4o API（需付费）。

## 5. 实验数量与充分性
- **实验数量**：论文在4个数据集上进行了主实验（表1-4），并设计了详尽的消融实验（表5-10），包括：
  - 工具链策略对比（无约束、提示、上下文学习、时空分离、STAR）
  - 每个单一工具移除的影响（表6）
  - 不同帧采样率的性能（表7）
  - 不同基座LLM（GPT-4o、Gemini-2.5-pro、Qwen2.5-VL-72B、DeepSeek-R1）的泛化性（表8）
  - 工具使用平衡性分析（表9-10）
- **充分性**：实验覆盖了多种视频长度、问题类型和模型规模，消融全面（10张表+多个附录分析），结果客观（报告了准确率、帧数、运行时等）。但未提供统计误差棒（论文注明随机性影响小）。

## 6. 主要结论与发现
- **STAR显著提升GPT-4o**：在VideoMME上提升8.2%（70.0% vs 61.8%），在LongVideoBench上提升4.6%（57.2% vs 52.6%），且使用更少的帧（30.2帧 vs 32帧）。
- **优于7B级视频LLM**：在VideoMME上超越InternVL3-8B（66.3%）、Qwen2.5-VL-7B（65.1%）等。
- **优于现有工具学习方法**：在NExT-QA上，STAR-MINI超越DoraemonGPT达6.3%（62.0% vs 55.7%），且帧数更少（22.6帧 vs 1144.4帧）。
- **工具链交替策略最佳**：时空交替（STAR）比时空分离（Spatiotemporal Disentanglement）准确率提升1.4%，帧数减少10.4%。
- **每个工具都贡献正向性能**：移除任何单一工具均导致准确率下降（表6）。
- **可扩展性**：增加帧数（如1fps）可进一步提升准确率（+5.2%），且框架对不同基座LLM均有效（提升约7-8%）。

## 7. 优点
- **方法新颖**：首次提出时空交替调用的工具链策略，有效解决了工具链捷径问题。
- **实用性强**：轻量工具（≤3B参数）即可显著增强GPT-4o，且开源代码易于复现与扩展。
- **实验全面**：在多数据集、多基线、多角度消融下验证了有效性，结果可靠。
- **资源友好**：可在单张4090 GPU上运行，STAR-MINI甚至无需GPU。

## 8. 不足与局限
- **依赖闭源API**：完整STAR仍需调用GPT-4o，带来API成本与延迟，未能完全实现自主化。
- **未集成音频/字幕**：当前仅利用视频视觉信息，在多模态场景下（如字幕依赖型问题）可能受限（论文指出此点作为未来工作）。
- **失败案例揭示局限**：包括视觉信息模糊、主题理解不完整、难以推断人类动作动机，表明框架在深层因果推理上仍有不足。
- **实验偏差风险**：所有实验基于公开基准，可能存在领域分布偏差（如大多是互联网视频场景）。未在真实部署环境中测试。
- **可扩展性验证有限**：虽展示了帧数扩展，但未系统探索极长视频（如数小时）下性能与资源消耗的权衡。

（完）
