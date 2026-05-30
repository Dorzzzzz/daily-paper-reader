---
title: Modularized Self-Reflected Video Reasoner for Multimodal LLM with Application to Video Question Answering
title_zh: 面向多模态大语言模型的模块化自反思视频推理器及其在视频问答中的应用
authors: "Zihan Song, Xin Wang, Zi Qian, Hong Chen, Longtao Huang, Hui Xue, Wenwu Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dtmTQawQN2"
tags: ["query:long-video"]
score: 9.0
evidence: 可解释推理路径的视频问答
tldr: 现有视频问答方法缺乏可解释性，无法展示推理路径。本文提出MSR-ViR，首次将模块化网络集成到多模态大模型中，通过模块化时空定位和自我反思机制生成显式推理路径，在保持性能的同时大幅提升可解释性，为视频问答提供更透明的解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1596, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1546, \"height\": 942, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1595, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1482, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1498, \"height\": 2045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1592, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1590, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1599, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1645, \"height\": 653, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 690, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 714, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 792, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 752, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1354, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1510, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1265, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1326, \"height\": 236, \"label\": \"Table\"}]"
motivation: 视频问答方法缺乏可解释性，无法呈现推理过程。
method: 提出MSR-ViR，集成模块化网络和时空定位，实现可解释推理。
result: 在视频问答任务上兼顾性能与可解释性。
conclusion: 该工作为视频问答提供了首个显式推理路径方案。
---

## Abstract
Multimodal Large Language Models (Multimodal LLMs) have shown their strength in Video Question Answering (VideoQA). However, due to the black-box nature of end-to-end training strategies, existing approaches based on Multimodal LLMs suffer from the lack of interpretability for VideoQA: they can neither present reasoning paths nor indicate where the answers are derived from the video. To address this issue, we propose **MSR-ViR** (**M**odularized **S**elf-**R**eflected **Vi**deo **R**easoner), which for the first time integrates modular networks to Multimodal LLMs, capable of providing VideoQA with explicit reasoning paths for more interpretability. Specifically, a **MoST-Grounding** (Modularized Spatial-Temporal Grounding) network is proposed to decompose complex questions via tree-structured policies, localizing relevant temporal and spatial segments within videos through step-by-step reasoning. The proposed MoST-Grounding network provides explicit visually grounded information for Multimodal LLMs with clear reasoning paths, thus enhancing interpretability for the predicted answers. To further improve the reasoning quality, we design an **Alternate Self-reflection Training Strategy** to jointly optimize policy generation and Multimodal LLMs. Experiments on real-world datasets demonstrate the superiority of our proposed MSR-ViR framework in video understanding, reasoning transparency, and providing explicit localization evidence for answers.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有基于多模态大语言模型（Multimodal LLM）的视频问答（VideoQA）方法尽管性能优异，但采用端到端黑盒训练，缺乏可解释性——无法展示推理路径，也无法指明答案源自视频的哪个具体时空片段。
- **整体含义**：本文首次将模块化网络（Modular Network）引入多模态大语言模型，旨在为VideoQA提供显式的、可解释的推理路径和视觉证据，同时不牺牲问答性能。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过一个**问题解析器（Question Parser）**将复杂问题分解为树状结构策略，由**模块化时空定位网络（MoST-Grounding）**逐步执行，定位视频中相关的时空片段，再将这些定位结果与全局视频表示一同输入**多模态大语言模型回答器（Multimodal LLM Answerer）**生成答案。整个流程具备清晰的推理路径和视觉定位证据。
- **关键技术细节**：
    - **问题解析器**：基于大语言模型（Qwen2-7B），通过精心设计的提示（prompt）和上下文学习，生成统一JSON格式的策略，指导MoST-Grounding递归调用小模块。
    - **MoST-Grounding模块**：包含**时间定位器**和**空间定位器**，各由若干小模块组成（如DetectAct、LocateObj等），可动态组装。时间定位器采用UniVTG模型定位动作片段，空间定位器采用YOLO-World定位物体边界框。
    - **多模态大语言模型回答器**：接收原始问题、MoST-Grounding输出的时空定位帧、全局视频表示（通过平均池化压缩均匀采样帧）以及引导提示，经监督微调（SFT）产生答案。损失函数为交叉熵损失。
    - **交替自反思训练策略**：交替进行多模态LLM的监督微调和问题解析器的强化学习（利用直接偏好优化DPO）。每200步切换一次：先冻结问题解析器，训练多模态LLM；再冻结多模态LLM，利用训练损失作为反馈，通过DPO优化问题解析器，使其生成更合理的策略。
- **算法流程简述**：
    1. 问题解析器根据输入问题生成模块化策略。
    2. MoST-Grounding按策略递归调用时间/空间定位模块，提取相关时空帧。
    3. 多模态LLM结合时空帧、全局表示和引导提示，输出答案。
    4. 训练时：多模态LLM通过SFT优化（交叉熵损失）；问题解析器通过DPO优化（以多模态LLM的交叉熵损失作为偏好信号）。
    5. 两个模型交替训练，循环优化。

## 3. 实验设计

- **使用的数据集**：
    - VideoQA：**NExT-QA**、**STAR**（创建子集STAR-sub，仅含Interaction和Sequence类型，排除不适合时空定位的Prediction和Feasibility）。
    - 长视频VideoQA（零样本）：**EgoSchema**（子集和全集）、**VideoMME**（按视频长度分为Short/Medium/Long三个子集）。
    - 定位VideoQA（提供标注时间跨度）：**NExT-GQA**。
- **Benchmark**：各数据集的标准测试集/验证集。
- **对比的方法**：
    - 小视觉语言模型：ATP、MIST、CoVGT、HiTeA、InternVideo等。
    - 多模态大语言模型：BLIP-2、InstructBLIP、Qwen-VL、LLaVA-NeXT、Qwen2-VL、LLaVA-Video等。
    - 基于定位的多模态LLM：TGB、SeViLa、GCG等。
    - 模块化方法：LLoVi、MoReVQA、LangRepo等。
    - 此外还对比了使用更大LLM（如GPT-4、Palm-2）的方法，但公平比较时主要关注大小相当的模型。

## 4. 资源与算力

- **论文未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。仅在附录G.2中提及推理速度测试在**单张NVIDIA A100 GPU**上进行，但训练资源未提及。

## 5. 实验数量与充分性

- **实验数量**：覆盖5个数据集，包含多种设置（微调与零样本）；在NExT-QA和STAR-sub进行全量微调，在EgoSchema和VideoMME进行零样本评估，在NExT-GQA进行有监督定位评估。
- **消融实验**：在NExT-QA和NExT-GQA上针对自反思训练、空间定位模块、引导提示、全局表示等组件进行了消融，并探究了不同时间定位模型（UniVTG vs R2-Tuning vs Moment-DETR）和帧采样策略的影响。
- **充分性与公平性**：
    - 对比了多种类型的方法，包括小模型、多模态LLM、基于定位的方法和模块化方法，且对基于Qwen-VL和LLaVA-NeXT的直接基线进行了相同设置下的对比。
    - 在NExT-GQA上，将使用显著更大LLM（GPT-4、Palm-2）的方法淡化处理，保证公平。
    - 消融实验覆盖了核心设计选择，验证了各模块的必要性。
    - 不足：未在更多样化的场景（如开放域、多语言）评估；仅针对视频问答任务，未扩展到其他视频理解任务（如视频描述、时序定位本身）。

## 6. 主要结论与发现

- MSR-ViR在多个数据集上**显著优于**其直接基线（如Qwen-VL、LLaVA-NeXT）以及现有基于定位和模块化的方法，尤其在需要时序推理的任务（NExT-QA的Temporal问题、长视频）上提升明显。
- 在NExT-GQA上，MSR-ViR不仅能提高问答准确率，还能更**精确地定位**答案来源的时间段（更高的mIoU、IoU@0.5、Acc@GQA），验证了其可解释性和定位证据能力。
- 自反思训练策略、空间定位模块、全局表示和引导提示等设计均被消融实验证明对性能有正面贡献。
- 推理路径（例如树状策略）能清晰地展示多步推理过程，并提供视觉定位证据，增强了可解释性。
- 计算复杂度在理论上可严格界定，实际推理速度约为直接基线的2~3倍（使用7B问题解析器），属于可接受范围。

## 7. 优点

- **首创性**：首次将模块化网络与多模态大语言模型结合，实现了**显式推理路径**和**可视化时空定位证据**，显著提升了可解释性。
- **方法鲁棒**：通过自反思训练联合优化问题解析器和多模态LLM，使策略生成和答案质量相互促进，避免仅靠上下文学习导致的低质量策略。
- **实验全面**：在多个标准数据集上进行了包括微调、零样本、定位评估在内的全面实验，消融实验覆盖了主要设计点。
- **计算效率可控**：提供了计算复杂度的理论上界，并通过实验验证了额外的计算开销是合理的（推理速度约2-3倍于基线）。
- **代码与框架开源**：基于SWIFT框架实现，便于复现和扩展。

## 8. 不足与局限

- **实验覆盖不足**：未在更多样的场景（如开放域、多语言、多人对话视频）进行测试；仅针对VideoQA任务，未验证在视频描述、时序定位等其他视频理解任务上的泛化能力。
- **偏见与公平性风险**：未讨论模型在不同文化、性别、种族等维度上的潜在偏见；模块化方法依赖于预定义模块（如UniVTG、YOLO-World），这些模块本身可能携带偏见。
- **可解释性的局限性**：虽然提供了推理路径，但路径的合理性依赖于问题解析器的生成质量；对于极其复杂或模糊的问题，策略可能仍不完美。
- **计算开销**：尽管可控，但推理速度仍比端到端模型慢2-3倍，对实时应用可能构成挑战。
- **依赖外部模块**：MoST-Grounding中的小模块（UniVTG、YOLO-World）是固定且未经联合优化的，其性能上限可能成为瓶颈。
- **训练资源未披露**：论文未提供训练所需的GPU型号/时长、内存需求等关键资源信息，影响可复现性评估。

（完）
