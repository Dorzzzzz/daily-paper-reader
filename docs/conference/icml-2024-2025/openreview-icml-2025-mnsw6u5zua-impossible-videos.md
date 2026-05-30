---
title: Impossible Videos
title_zh: 不可能视频
authors: "Zechen Bai, Hai Ci, Mike Zheng Shou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=MNSW6U5zUA"
tags: ["query:long-video"]
score: 7.0
evidence: 视频理解基准
tldr: 针对现有合成视频数据集只复制现实场景、忽视不可能视频概念的不足，本文提出IPV-Bench基准，涵盖4个领域14个类别的不可能视频，用于评估视频理解与生成模型。该基准包含违反物理、生物、地理或社会规律的场景，促进了视频理解模型对反现实内容的处理能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1112, \"height\": 1389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1702, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 772, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 749, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 784, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 773, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 769, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1604, \"height\": 1061, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1753, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1143, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1145, \"height\": 219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1372, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1368, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1369, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1367, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1373, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1367, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1369, \"height\": 192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1361, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1366, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1374, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1373, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1381, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1378, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1380, \"height\": 208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1380, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1376, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1382, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1657, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1651, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1643, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1654, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1654, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mnsw6u5zua/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1649, \"height\": 244, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1721, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1601, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1595, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 737, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1415, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mnsw6u5zua/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 814, \"height\": 239, \"label\": \"Table\"}]"
motivation: 现有视频理解模型在处理反现实或不可能视频内容时能力未知，需要专门的基准评估。
method: 构建包含4大领域14类不可能场景的IPV-Bench基准，并测试视频理解与生成模型。
result: 揭示了当前视频模型在理解不可能视频上的不足，为后续研究提供评估标准。
conclusion: 不可能视频基准能有效推动视频理解与生成模型向更鲁棒的方向发展。
---

## Abstract
Synthetic videos nowadays is widely used to complement data scarcity and diversity of real-world videos.
Current synthetic datasets primarily replicate real-world scenarios, leaving impossible, counterfactual and anti-reality video concepts underexplored. This work aims to answer two questions: 1) Can today's video generation models effectively follow prompts to create impossible video content? 2) Are today's video understanding models good enough for understanding impossible videos?
To this end, we introduce *IPV-Bench*, a novel benchmark designed to evaluate and foster progress in video understanding and generation. *IPV-Bench* is underpinned by a comprehensive taxonomy, encompassing 4 domains, 14 categories.
It features diverse scenes that defy physical, biological, geographical, or social laws. Based on the taxonomy, a prompt suite is constructed to evaluate video generation models, challenging their prompt following and creativity capabilities. In addition, a video benchmark is curated to assess Video-LLMs on their ability of understanding impossible videos, which particularly requires reasoning on temporal dynamics and world knowledge. Comprehensive evaluations reveal limitations and insights for future directions of video models, paving the way for next-generation video models.

---

## 论文详细总结（自动生成）

# 论文《Impossible Videos》详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前合成视频数据集主要用于复制真实世界场景，忽略了“不可能、反事实、反现实”的视频概念。作者认为，不可能视频可以作为评估视频模型的有效测试床，因为它们要求模型不仅记忆真实数据，还要真正推理和泛化。
- **核心问题**：
  - ① 现有视频生成模型能否有效遵循文本提示生成不可能的（即违反物理、生物、地理或社会规律的）视频内容？
  - ② 现有视频理解模型（特别是Video-LLMs）是否足够好地理解不可能视频？

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：构建一个系统性的基准IPV-Bench，用于同时评估视频生成和视频理解模型在“不可能”场景下的表现。
- **关键技术细节**：
  - **IPV Taxonomy**：涵盖4大领域、14个类别：
    - 物理定律（力学、热学、光学、流体、材料属性、守恒定律）
    - 生物定律（生物能力、形态、拟人化）
    - 地理定律（气候/天气、地形/环境）
    - 社会定律（常识、魔法效果、历史异常）
  - **IPV-Txt（提示套件）**：260个高质量文本提示，描述不可能场景。通过迭代方式（LLM生成 + 众包收集 + 人工质量控制 + 语言增强）构建。
  - **IPV-Vid（视频数据集）**：
    - 来源：10个T2V模型生成（Open-Sora、HunyuanVideo、CogVidX、Mochi 1、LTX、Pyramid-Flow、Sora、Kling、Luma、Hailuo）共2600个视频；网络社区收集155个；真实视频（从OpenVid用CLIP检索得到）650个。
    - 人工标注：筛选视觉质量+语义不合理性，并标注空间/时间异常、类别、解释。
  - **任务设计**：三个层次任务（难度递增）：
    - 判断任务（AI生成 vs. 真实视频）
    - 多选问答（MCQA，识别正确的不可能现象描述）
    - 开放问答（OpenQA，自由解释不可能现象，用LLM评估器打分）

## 3. 实验设计：数据集/场景、Benchmark、对比方法

- **数据集/场景**：使用IPV-Bench自身，包含260个文本提示（用于生成评估）和902个高质量不可能视频（用于理解评估）。视频覆盖4大领域14类，同时包含真实世界视频作为对照。
- **Benchmark**：IPV-Bench（首次针对不可能视频的基准）。
- **对比方法**：
  - **视频生成模型**：
    - 开源：LTX、Open-Sora、Pyramid-Flow、CogVidX-1.5、Mochi 1、HunyuanVideo
    - 闭源：Luma、Sora、Kling 1.5、Hailuo
  - **视频理解模型（Video-LLMs）**：
    - 开源：Video-LLaVA、Oryx、Intern-VL-2.5、NVILA、LongVU、Qwen2-VL、LLaVA-Next
    - 闭源：Gemini-1.5-Flash、GPT-4o
  - 人类标注作为黄金参考。

## 4. 资源与算力

- **论文未明确说明**：未提及使用的GPU型号、数量、训练时长等算力信息。仅提到使用多个商业模型（如Sora、Kling等）生成视频，但未公开其内部资源消耗。实践中可能需要大量GPU用于生成和评估（如10个模型×260个提示），但论文未详细量化。

## 5. 实验数量与充分性

- **实验数量**：
  - 生成评估：10个生成模型，每个用260个提示生成视频，每个视频由人工标注视觉质量和提示遵循度，共约2600个生成视频。
  - 理解评估：9个Video-LLMs，在3个任务（判断、MCQA、OpenQA）上评估，涉及902个视频。
  - 消融/额外：对时空属性进行子集分析（表4），自动评估与人工对齐相关系数（Spearman's ρ > 0.8，图9）。
- **充分性与客观性**：
  - 覆盖主流的开源/闭源模型，任务设计全面（判别、选择、开放生成）。
  - 使用人类标注作为黄金标准，并报告了与自动评估的相关系数，确保评价客观。
  - 存在多个评估者（GPT-4o和Claude-3.5）以减少自评偏差。
  - 但未进行大规模消融实验（如不同数据比例、不同提示策略等），部分分析基于定性案例。

## 6. 论文的主要结论与发现

- **视频生成**：当前最好的模型（Mochi 1）也只能在37.3%的情况下生成高质量且符合提示的“不可能”视频，其他模型更差。生成失败类型：① 不可能的提示导致视觉质量低下；② 过度遵循物理规律而无法实现提示中的反现实事件。
- **视频理解**：
  - 判断任务：Qwen2-VL最优（Accuracy 76.2%），但部分模型存在偏向（如Intern-VL-2.5偏向回答“是”）。
  - MCQA：LLaVA-Next最优（86.4%），但开源模型普遍较差（最低Video-LLaVA仅26.8%）。
  - OpenQA：GPT-4o最好（得分49.1%），但与人类（82.7%）差距很大，说明模型难以独立识别不可能现象。
  - “物理”领域最难，时间推理比空间推理更难（表4）。
  - 目前没有模型能很好地结合时间动态推理与世界知识。

## 7. 优点：方法或实验设计上的亮点

- **首次聚焦“不可能视频”**：提出了一个新颖且有价值的概念，填补了现有基准的空白。
- **系统性的分类法**：覆盖4大领域14类，全面且可扩展。
- **双任务设计**：同时评估生成和理解，且理解任务从简单判别到开放生成，难度递进。
- **数据构建严谨**：采用迭代细化、LLM+众包、人工质量控制和语言增强，确保提示多样和质量；视频收集结合生成和真实，并人工过滤和标注。
- **自动评估与人工对齐**：提出IPV-Score（视觉质量×提示遵循度）和自动评估策略，与人类高度相关（ρ>0.8）。
- **详细的案例分析和失败分析**：揭示了模型在不可能视频上的具体局限性（如视觉质量下降、过度遵循物理规律等）。

## 8. 不足与局限

- **实验覆盖有限**：只测试了10个生成模型和9个理解模型，未包含更多最新模型（如Sora的更新版本、其他开源模型）。
- **资源算力未公开**：无法复现生成部分的计算成本，影响可重复性。
- **评估偏见风险**：OpenQA使用GPT-4o和Claude-3.5作为评判者，虽然做了交叉验证，但LLM评判本身可能有不稳定性。
- **时空子集划分依赖人工标注**：空间/时间异常的标注可能带有主观性，影响表4的结论严谨性。
- **领域平衡性**：虽然提示分布展示了（图3），但“社会定律”类别可能更容易通过常识识别，而“物理定律”更难，这可能导致模型在不同领域得分差异不是纯粹的能力差异。
- **实际应用限制**：不可能视频在现实中很少见，基准可能过度偏重反现实场景，不能完全代表真实世界模型能力。
- **未深入探讨模型内部机制**：仅报告了性能分数，没有分析模型为何失败（如注意机制、时间编码方式等）。

（完）
