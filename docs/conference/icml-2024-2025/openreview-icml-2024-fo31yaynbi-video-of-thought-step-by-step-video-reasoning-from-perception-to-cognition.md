---
title: "Video-of-Thought: Step-by-Step Video Reasoning from Perception to Cognition"
title_zh: 视频思维链：从感知到认知的逐步视频推理
authors: "Hao Fei, Shengqiong Wu, Wei Ji, Hanwang Zhang, Meishan Zhang, Mong-Li Lee, Wynne Hsu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=fO31YAyNbI"
tags: ["query:long-video"]
score: 9.0
evidence: 针对复杂长视频的逐步推理框架
tldr: 现有视频理解在精细时空感知和认知级场景理解上存在瓶颈。本文提出MotionEpic多模态大模型，结合视频时空场景图实现像素级定位，并构建Video-of-Thought推理框架，将复杂任务分解为逐步推理，显著提升长视频深度理解和推理能力。该方法为视频理解提供新的范式。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 842, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 841, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 855, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 864, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1787, \"height\": 163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 835, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 85, \"height\": 66, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 86, \"height\": 68, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 87, \"height\": 67, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1762, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1770, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fo31yaynbi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1782, \"height\": 132, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-fo31yaynbi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 905, \"height\": 644, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fo31yaynbi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fo31yaynbi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 703, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fo31yaynbi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 664, \"label\": \"Table\"}]"
motivation: 针对长视频理解中精细时空感知与认知推理不足的问题。
method: 提出MotionEpic MLLM整合时空场景图，并构建Video-of-Thought逐步推理框架。
result: 在复杂视频推理任务上取得显著改进，验证了框架的有效性。
conclusion: 该工作为长视频深度理解提供了新范式，弥合了感知与认知的鸿沟。
---

## Abstract
Existing research of video understanding still struggles to achieve in-depth comprehension and reasoning in complex videos, primarily due to the under-exploration of two key bottlenecks: fine-grained spatial-temporal perceptive understanding and cognitive-level video scene comprehension. This paper bridges the gap by presenting a novel solution. We first introduce a novel video Multimodal Large Language Model (MLLM), MotionEpic, which achieves fine-grained pixel-level spatial-temporal video grounding by integrating video spatial-temporal scene graph (STSG) representation. Building upon MotionEpic, we then develop a Video-of-Thought (VoT) reasoning framework. VoT inherits the Chain-of-Thought (CoT) core, breaking down a complex task into simpler and manageable sub-problems, and addressing them step-by-step from a low-level pixel perception to high-level cognitive interpretation. Extensive experiments across various complex video QA benchmarks demonstrate that our overall framework strikingly boosts existing state-of-the-art. To our knowledge, this is the first attempt at successfully implementing the CoT technique for achieving human-level video reasoning, where we show great potential in extending it to a wider range of video understanding scenarios. Systems and codes will be open later.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有视频理解方法在复杂视频的深度推理上存在两大瓶颈：一是缺乏**精细的时空感知理解**（像素级对象追踪与定位），二是缺乏**认知级的场景理解**（利用常识知识解释因果、预测未来等）。简单视频的感知任务尚可，但对于需要多步推理的复杂视频（例如“红色油罐车被撞后会发生什么？”），现有模型难以胜任。
- **研究动机**：受人类认知模式启发——人类推理视频时，通常先锁定目标对象（如“红色油罐车”），然后追踪其轨迹，理解动作与场景语义，最后结合常识形成认知结论。论文旨在构建**类人逐步推理的视频理解框架**，从低层像素感知逐步上升到高层认知解释。
- **整体含义**：本文首次成功将 **Chain-of-Thought (CoT) 技术**应用于视频推理，提出了 **Video-of-Thought (VoT)** 框架，并配套设计了能进行细粒度时空定位的视频多模态大模型 **MotionEpic**，显著提升了复杂视频QA任务的性能，为视频理解提供了新范式。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：借鉴CoT，将复杂的视频推理问题分解为**五步链式子问题**，从低层逐步到高层：
  1. **任务定义与目标识别**：确定问题涉及的主要目标对象。
  2. **对象追踪**：利用时空场景图（STSG）对目标进行像素级轨迹定位。
  3. **动作分析**：结合常识知识，分析目标的运动行为及场景语义。
  4. **问答排名**：对每个候选答案（或自生成选项）进行合理性评分并排序。
  5. **答案验证**：分别从像素感知（视觉事实）和常识认知两个角度验证答案一致性，必要时回溯重选。
- **关键技术细节**：
  - **MotionEpic MLLM**：基于 Vicuna-7B (v1.5) 作为LLM，ViT-L/14 作为视频编码器，Q-Former 作为投影器，并设计了**循环图变换器**（Recurrent Graph Transformer）对多帧时空场景图（STSG）进行编码。STSG 包含每帧的对象、属性、谓词关系以及跨帧的时间共指边。
  - **视频-场景图定位调优**：通过粗粒度（视频-STSG匹配、STSG生成）和细粒度（给定动作输出轨迹、给定对象输出轨迹、给定边界框输出标签/轨迹）共5种训练目标，使MotionEpic能够自主从视频解析STSG，实现像素级时空定位。
  - **VoT推理流程**：具体prompt设计见附录，每一步均输入前一步的输出和原问题，利用LLM的常识知识进行逐步推理。对于开放端问答，先让模型生成多个候选答案，转化为多项选择形式再排名。
- **公式/算法流程**（文字说明）：无显式公式，整体为链式prompt调用。训练过程分为两阶段：① 基于Action Genome和WebVid-10M构建视频-STSG对，进行视频-场景图定位调优；② 在任务数据集上进行指令微调。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **微调设置**（6个复杂视频QA数据集）：VLEP, STAR（含Interaction, Sequence, Prediction, Feasibility四个子集）, IntentQA（2-Way和4-Way）, Social-IQ, Causal-VidQA（含Description, Explanation, Prediction, Counterfactual四个子集）, NExT-QA（含Causal, Temporal, Descriptive子集）。
  - **零样本设置**（2个数据集）：MSR-VTT, ActivityNet。
  - **视频-STSG对训练语料**：Action Genome（10K高质量人工标注）+ WebVid-10M中筛选的350K视频（利用SoTA解析器自动解析）。
- **基准**：采用各数据集的标准划分和评估指标（Accuracy）。
- **对比方法**：
  - **SoTA基线**：InternVideo, LLaMA-VQA, VLAP, SeViLA, TranSTR, HiTeA, VideoChat2, Video-LLaMA, Video-ChatGPT, VideoChat, Video-LLaVA等。
  - **消融/对比变体**：Video-LLaVA + CoT, Video-LLaVA + STSG（显式集成STSG特征）, MotionEpic + 普通CoT, MotionEpic + VoT。
  - **人类评估**：从Causal-VidQA和Social-IQ各选200个困难样本进行人工打分。

## 4. 资源与算力

- **训练硬件**：明确提到 “All trainings are conducted on 16 NVIDIA A100 GPUs”。
- **训练时长**：论文未明确给出具体训练时长或总计算量。
- **模型规模**：LLM为Vicuna-7B，视频编码器ViT-L/14，Q-Former和STSG编码器（6层图变换器，768维）。参数冻结策略：视频编码器和LLM冻结，仅通过LoRA更新少量参数。

## 5. 实验数量与充分性

- **实验分组**：
  - **主表**：Table 1（4个数据集，含STAR四个子集）、Table 2（Causal-VidQA四个子集）、Table 3（NExT-QA三个子集）、Table 4（零样本4个数据集）。共覆盖8个数据集，含多种子任务。
  - **消融实验**：
    - 图6：在NExT-QA和ActivityNet上分析5种定位调优目标（L1~L5）的贡献，每次去除一个目标观察性能下降。
    - 图7（下）：错误类别分析（6类常见错误：对象识别、动作时序、长视频、动作数量、动作语义、常识），对比Video-LLaVA+CoT与MotionEpic+VoT。
    - 表4下半：零样本下取消像素验证（w/o Verify-G）和常识验证（w/o Verify-C）的消融。
  - **定性分析**：图5展示MotionEpic在物体定位、场景图三元组分类、动作定位上与SoTA解析器及人类对比；图7（上）展示人类评估；图8、9、10为可视化案例。
- **充分性与公平性**：实验设计较为全面，对比了多类基线（包括最新SoTA），且在同一训练设置下比较（相同数据分割、评价方法）。消融实验覆盖了框架核心组件（STSG集成、定位调优目标、验证机制、CoT vs VoT）。零样本和微调两种场景均有评估。但未报告方差或多次运行的结果，可能影响统计显著性判断。

## 6. 论文的主要结论与发现

- VoT框架在所有复杂视频QA基准上**大幅超越现有SoTA**，微调和零样本设置下均取得最佳结果，尤其在需要认知推理的任务（如因果、预测、反事实）上提升显著。
- 普通CoT对视频推理提升有限（“Let's think step by step”），而VoT通过精细的多步分解带来巨大增益。
- STSG结构特征的显式集成（Video-LLaVA+STSG）优于不集成，但MotionEpic的隐式（内生）STSG解析相比显式集成更优。
- 像素级验证和常识验证均重要：复杂视频任务中两者缺一不可；简单任务中像素验证更关键。
- 零样本下VoT相比CoT的提升比微调下更大，说明VoT能更好地激发MLLM的泛化推理能力。
- 人类评估表明VoT输出接近人类水平（Causal-VidQA 74.3% vs 人类80.6%；Social-IQ 61.4% vs 72.7%），显著优于Video-LLaVA+CoT。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将CoT技术成功应用于视频推理，提出VoT框架，填补了领域空白。
- **技术完整性**：设计了从模型（MotionEpic）到推理框架（VoT）的完整方案，包括细粒度时空定位调优、多步骤推理、答案验证等环节。
- **实验充分**：覆盖8个数据集、多种任务类型（描述、因果、预测、反事实等），对比最新SoTA，进行消融、人类评估、错误分析，定性定量结合。
- **可解释性**：VoT每一步输出中间推理结果（如STSG轨迹、动作分析、合理性评分），使推理过程透明、可追溯。
- **通用性**：框架可推广到其他视频理解任务（论文举例可转换为QA格式），且支持零样本推理。

## 8. 不足与局限

- **计算成本高**：16块A100 GPU训练，且视频帧采样率8fps，对长视频可能有较大开销。
- **数据依赖**：STSG定位调优依赖于Action Genome（10K标注）和WebVid解析（自动解析可能有误差），数据质量和规模受限可能影响泛化。
- **任务覆盖有限**：仅验证视频QA任务，其他视频推理任务（如视频摘要、事件预测、交互检测等）未实验，通用性待证明。
- **评估指标单一**：仅使用Accuracy，未报告F1、BLEU、CIDEr等指标（尤其对于开放端问答），且未给出多次运行的标准差，结果稳定性未知。
- **模型瓶颈**：基于Vicuna-7B，LLM能力相对较小（与GPT-4V等相比），可能限制常识推理上限。未对比更大型的LLM（如13B/70B）或GPT-4V。
- **社会影响**：论文提到能耗与恶意利用风险，但未提出具体缓解措施。框架强大但可能被滥用生成虚假视频解释。

（完）
