---
title: "Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding"
title_zh: Time-R1：面向时间视频定位的大型视觉语言模型后训练
authors: "Ye Wang, Ziheng Wang, Boshen Xu, Yang Du, Kejun Lin, Zihan Xiao, Zihao Yue, Jianzhong Ju, Liang Zhang, Dingyi Yang, Xiangnan Fang, Zewen He, Zhenbo Luo, Wenxuan Wang, Junqi Lin, Jian Luan, Qin Jin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gJ05Gm5VxQ"
tags: ["query:long-video"]
score: 9.0
evidence: 对大型视觉语言模型进行后训练以实现长视频中的时间定位，支持问答
tldr: 时间视频定位是长视频理解的核心挑战，现有监督微调方法泛化性不足。本文提出Time-R1后训练框架，利用强化学习与可验证奖励增强大型视觉语言模型的定位能力；同时引入TimeRFT探究不同后训练策略。该方法在多个长视频基准上显著提升定位准确性，为长视频问答提供了可靠的细粒度定位能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1272, \"height\": 157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1305, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 568, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1335, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1332, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1386, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 555, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 650, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 648, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1240, \"height\": 173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1372, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1439, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1270, \"height\": 165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1435, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1341, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1442, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 130, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1442, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1439, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1418, \"height\": 332, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1391, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 681, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 706, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 604, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1285, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1123, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 605, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1358, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 658, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1452, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1445, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1454, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gj05gm5vxq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1453, \"height\": 327, \"label\": \"Table\"}]"
motivation: 现有监督微调方法对时间视频定位的泛化能力有限。
method: 提出基于强化学习的后训练框架，使用可验证奖励引导推理。
result: 在多个长视频定位基准上显著提升性能。
conclusion: Time-R1有效增强了LVLM在长视频中的细粒度定位能力。
---

## Abstract
Temporal Video Grounding (TVG), the task of locating specific video segments based on language queries, is a core challenge in long-form video understanding. While recent Large Vision-Language Models (LVLMs) have shown early promise in tackling TVG through supervised fine-tuning (SFT), their ability to generalize remains limited. To address this, we propose a novel post-training framework that enhances the generalization capabilities of LVLMs via reinforcement learning (RL).
Specifically,  our contributions span three key directions:
(1) Time-R1: we introduce a reasoning-guided post-training framework via RL with verifiable reward to enhance capabilities of LVLMs on the TVG task. 
(2) TimeRFT: we explore post-training strategies on our curated RL-friendly dataset, which trains the model to progressively comprehend more difficult samples, leading to better generalization.
(3) TVGBench: we carefully construct a small but comprehensive and balanced benchmark suitable for LVLM evaluation, which is sourced from available public benchmarks.
Extensive experiments demonstrate that Time-R1 achieves state-of-the-art performance across multiple downstream datasets using significantly less training data than prior LVLM approaches, while improving its general video understanding capabilities. 
Project Page: https://xuboshen.github.io/Time-R1/.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将严格遵循您的要求，对这篇论文进行结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

-   **研究动机与背景**：
    -   **核心问题**：时间视频定位（TVG）旨在根据自然语言查询，在长视频中定位对应的片段。尽管大视觉语言模型（LVLMs）通过监督微调（SFT）在此任务上展现出潜力，但其**泛化能力严重不足**。
    -   **问题根源**：论文指出，SFT 的逐 token 交叉熵损失函数会“过度惩罚”合理的预测。例如，当预测时间戳与真实值仅有微小偏差时，模型仍会收到高惩罚，这导致模型过拟合于训练数据，泛化能力差。
    -   **解决方案思路**：受强化学习（RL）在数学和代码推理中的成功启发，本文**首次将RL引入长视频理解领域**，提出直接优化任务相关指标（如IoU）来替代刚性惩罚，以鼓励模型做出更合理的预测，从而提升泛化能力。

### 2. 论文提出的方法论

-   **核心思想**：**Time-R1** 是一个基于强化学习（RL）的后训练框架。关键思想是让 LVLM 先生成链式思维（CoT）描述进行推理，然后预测时间戳，最后使用可验证的奖励信号来优化整个过程，而不是像 SFT 那样强制匹配固定的 token。

-   **关键技术细节**：
    1.  **Time-R1 框架**：
        -   **基础**：采用**广义强化策略优化（GRPO）** 算法来训练策略模型 \( \pi_\theta \)。
        -   **奖励建模**：设计了复合奖励函数，包含两个部分：
            -   **时间戳感知的 IoU 奖励 \( r_{tIoU} \)**：在标准 IoU 基础上，增加了对时间戳起始点和终点偏差的惩罚，提供了更精细、更严格的定位信号，避免了标准 IoU 在某些场景下的评估偏差。
            -   **推理模板奖励 \( r_{form} \)**：强制模型以 `<think>...</think><answer>...</answer>` 的格式生成推理过程和最终答案，鼓励模型在定位前进行上下文感知的推理。
        -   总奖励：\( r(o) = r_{tIoU}(o) + r_{form}(o) \)。GRPO 训练的最终目标是最大化此带 KL 散度惩罚项的奖励。
    2.  **TimeRFT 训练策略**：
        -   **数据筛选（RFT Data Filtering）**：提出了一种基于难度的数据选择策略。先让基座模型预测所有样本，根据IoU计算难度分数，然后从中筛选出中等难度的样本（IoU值分布在0.3附近的高斯分布），最终仅用 **2.5K** 个样本进行RL训练，极大地提高了数据效率。
        -   **动态硬采样（Dynamic Hard Sampling）**：采用多轮训练策略，每轮训练后，移除那些已经变得“简单”（IoU > 0.7）的样本，让模型聚焦于更难、信息量更大的样本，增强泛化能力。
        -   **冷启动微调（Cold Start Fine-tuning）**：为了防止小模型直接RL训练产生难以理解的CoT，先用少量（150个）带有结构化CoT的样本进行SFT微调，引导模型学习有效的推理格式，稳定训练过程。

### 3. 实验设计

-   **使用的数据集与基准**：
    -   **训练数据**：从 YT-Temporal, DiDeMo, HowTo100M 等多个互联网视频数据集中收集共 **339K** 个视频片段，然后从中筛选出 **2.5K** 个样本用于 RL 训练。
    -   **TVG 评估基准**：
        -   **本文构建的 TVGBench**：从 Charades-STA, ActivityNet-Captions, HiREST 等5个公开数据集中精心选取了 **800** 个样本，平衡了视频时长、查询中心、查询语义等多个维度，专为评估LVLM设计。
        -   **标准公开基准**：Charades-STA, ActivityNet。
    -   **视频问答（QA）评估基准**：MVBench, TempCompass (短视频), EgoSchema, VideoMME (长视频)，用于评估泛化能力。

-   **对比方法**：
    -   **基于VLPs的传统方法**：2D-TAN, SnAG, EaTR 等。
    -   **基于SFT的LVLM方法**：TimeChat, TRACE, TimeSuite, VideoChat-Flash, Gemini-2.5-Pro 等。
    -   **与SFT对比消融**：Self：**SFT-2.5K** (全参数微调)，**SFT-LoRA-2.5K** (LoRA微调)，**SFT-LoRA-339K** (用全部数据LoRA微调)。

### 4. 资源与算力

-   **文中明确说明**：
    -   **GPU型号**：NVIDIA A100 (80GB)。
    -   **GPU数量**：8块。
    -   **训练时长**：
        -   后训练（RL）阶段：约 3 天。
        -   下游任务微调阶段：约 0.5 天。
    -   评估时，为了加速，使用了 **vLLM** 库。在8块GPU上，对整个TVGBench（800样本）进行CoT推理仅需 8.3 分钟。

### 5. 实验数量与充分性

-   **实验数量**：论文进行了大量详尽的实验，包括：
    -   **主实验**：在 Charades-STA, ActivityNet 和 TVGBench 三个数据集上与 **20+** 种基线方法进行对比。
    -   **消融实验**：**8大组**，细致分析了数据集过滤（GF）、多轮训练（ME）、样本过滤（SF）、冷启动、奖励函数设计（7种变体）、损失函数（GRPO vs. DAPO）、基座模型规模（3B vs. 7B）和架构（Qwen, MiMo, InternVL）等关键组件的影响。
    -   **SFT vs. RL 对比实验**：通过 Fig-4 直观展示了不同后训练范式在TVG、短/长视频QA任务上的性能趋势差异。
    -   **数据效率对比**：用表5对比了 RL-2.5K 和 SFT-LoRA-339K 的性能。
    -   **迁移学习与泛化实验**：在多个视频QA基准上验证了方法的泛化能力。

-   **充分性与公平性**：
    -   **覆盖全面**：实验覆盖了TVG任务的多个标准数据集，以及视频理解的其他下流任务，验证了方法的有效性和通用性。
    -   **设计公平**：在相同基座模型（Qwen2.5-VL-7B）上比较了RL与SFT的各种变体，控制变量严谨。为保持对比公平，基线模型的设置均参考了其原始论文的最佳配置。

### 6. 论文的主要结论与发现

-   **Time-R1 在 TVG 任务上达到 SOTA 水平**：在零样本和微调两种设定下，均超越所有基于 SFT 的 LVLM 方法，甚至超越了许多传统的 VLP 方法。例如，在 Charades-STA 上，微调后的 R1@0.7 达到 50.1%，远超前代最佳方法的 43.0%。
-   **RL 相比于 SFT 具有显著优势**：
    -   **泛化性强**：RL 后训练不仅提升了 TVG 任务性能，还同时提升了短/长视频问答的准确性，而 SFT 则导致性能下降。
    -   **数据效率极高**：仅用 2.5K 样本的 RL 训练，性能就超越了 100 倍数据量的 SFT-LoRA 训练（339K 样本）。
-   **设计的有效性**：论文提出的所有组件（数据过滤、动态硬采样、冷启动、复合奖励函数）都对最终性能有正向贡献，证明了整体框架设计的合理性。

### 7. 优点

-   **方法新颖且有效**：首次成功将 RLVR 范式应用于长视频的 TVG 任务，并展示了其在数据效率和泛化性上的巨大优势，是一个创新性很强的突破。
-   **问题诊断深刻**：清晰地分析了 SFT 在 TVG 任务上的根本缺陷（过度惩罚），为后续研究提供了有价值的参考。
-   **实验设计严谨**：消融实验非常全面，因果性分析到位，对比了多种 SFT 配置，有力地证明了 RL 范式的优越性。
-   **基准构建合理**：TVGBench 的构建考虑周全，平衡了多种分布，为 LVLM 的 TVG 评估提供了一个更公平、更全面的平台。
-   **数据效率突出**：在 RL 训练中使用仅 2.5K 样本，极大降低了计算成本，具有很高的实用价值。

### 8. 不足与局限

-   **超长视频处理限制**：当前框架在处理超长视频（如电影）时仍存在困难。低帧率采样和 GPU 内存是主要瓶颈。
-   **训练与推理速度**：由于模型规模大和 CoT 推理，其训练和推理速度慢于传统的特征方法，虽然在工作中已尝试用 vLLM 加速，但这仍是 LVLM 的通病。
-   **低帧率采样**：为节省内存使用较低的帧率，可能丢失了帧间的精细运动信息。
-   **特定场景下的局限**：在涉及复杂指令（如HAP，OC）和物体定位（如OA）的任务上，与最强基线（如 Gemini-2.5-Pro）的性能差距仍然存在，表明模型在理解和执行高度复杂或细微的查询方面还有提升空间。
-   **实验潜在的偏差**：尽管 TVGBench 经过平衡设计，但基座模型（如 Qwen2.5-VL-7B）自身的偏见或局限可能会影响最终结果。不同基座模型的真实“容量上限”也可能影响 RL 后训练能达到的性能天花板。

（完）
