---
title: "TUMTraf VideoQA: Dataset and Benchmark for Unified Spatio-Temporal Video Understanding in Traffic Scenes"
title_zh: TUMTraf VideoQA：交通场景中统一时空视频理解的数据集与基准
authors: "Xingcheng Zhou, Konstantinos Larintzakis, Hao Guo, Walter Zimmer, Mingyu Liu, Hu Cao, Jiajie Zhang, Venkatnarayanan Lakshminarasimhan, Leah Strand, Alois Knoll"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Yfoi5O68rf"
tags: ["query:long-video"]
score: 9.0
evidence: 用于长交通视频问答的数据集和基准
tldr: 长视频问答面临复杂交通场景的挑战，论文构建TUMTraf VideoQA数据集，包含1000个视频和85000个多选QA对，统一视频问答、目标描述和时空定位三个任务，并引入TraffiX-Qwen基线模型，为长视频问答评估提供了标准化平台。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 423, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 413, \"height\": 195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1712, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 845, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 847, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 835, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1624, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1626, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 737, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 749, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 751, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1710, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1770, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1773, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1768, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 802, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 802, \"height\": 1001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 803, \"height\": 1005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1678, \"height\": 1978, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 873, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 893, \"height\": 677, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 892, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 369, \"label\": \"Table\"}]"
motivation: 现有视频QA数据集缺乏复杂交通场景的标注，且任务孤立。
method: 构建包含多选QA、目标描述和定位的多任务数据集，并设计基线模型。
result: 数据集覆盖恶劣天气等多样性条件，基线模型提供初步性能。
conclusion: TUMTraf VideoQA推动交通场景下的视频理解研究。
---

## Abstract
We present TUMTraf VideoQA, a novel dataset and benchmark designed for spatio-temporal video understanding in complex roadside traffic scenarios. The dataset comprises 1,000 videos, featuring 85,000 multiple-choice QA pairs, 2,300 object captioning, and 5,700 object grounding annotations, encompassing diverse real-world conditions such as adverse weather and traffic anomalies. By incorporating tuple-based spatio-temporal object expressions, TUMTraf VideoQA unifies three essential tasks—multiple-choice video question answering, referred object captioning, and spatio-temporal object grounding—within a cohesive evaluation framework. We further introduce the TraffiX-Qwen baseline model, enhanced with visual token sampling strategies, providing valuable insights into the challenges of fine-grained spatio-temporal reasoning. Extensive experiments demonstrate the dataset’s complexity, highlight the limitations of existing models, and position TUMTraf VideoQA as a robust foundation for advancing research in intelligent transportation systems. The dataset and benchmark are publicly available to facilitate further exploration.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：现有交通场景理解工作主要聚焦于驾驶视角（如nuScenes、BDD100k），且多为单一任务（如图像QA、目标跟踪或视频定位），缺乏面向路边监控视角的、统一的**时空视频理解数据集**和**多任务基准**。同时，复杂的交通事件（如事故、救援、恶劣天气）需要多帧视频分析，而图像级VLM无法捕捉时间动态。
- **整体含义**：本文构建了**TUMTraf VideoQA**——首个面向路边交通场景的、包含**视频QA、目标描述、时空定位**三个统一任务的视频语言数据集与基准，填补了该领域空白，推动智能交通系统中细粒度时空推理的研究。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：构建高质量、多样化、半自动标注的视频语言数据集，并提出一个**基于元组表示的统一对象引用框架**，将三个任务纳入同一评估体系；同时建立**TraffiX-Qwen基线模型**，探索不同视觉token采样策略对性能的影响。
- **关键技术细节**：
  - **元组表示**：对象在视频中的时空位置表示为 `(c, fn, x, y)`，其中`c`为唯一对象标识，`fn`为归一化帧时间戳，`(x, y)`为归一化图像中心坐标。同一对象在视频中保持`c`不变，位置随时间变化。
  - **半自动标注流水线**：包括视频选择（一年以上、多种场景与天气）、元数据管理（利用历史天气记录、检测/跟踪器、VLM生成外观描述、人工质检）、QA生成与过滤（模板+LLM混合，迭代过滤）。
  - **模型架构**：TraffiX-Qwen包含视觉编码器SigLIP（384×384，101帧/视频）、跨模态投影器（2层MLP）、**四种视觉token采样策略**（Spatial Pooling、MultiRes Spatial-Pooling、MultiRes Token-Pruning、MultiRes Temporal-Pooling）以及大语言模型Qwen-2（0.5B/7B）。
  - **训练流程**：两阶段——①视频语言对齐（冻结编码器与LLM，仅训练投影器1 epoch）；②视觉指令微调（冻结编码器与投影器，全参数微调LLM 1 epoch）。

## 3. 实验设计：数据集/场景、Benchmark、对比方法
- **数据集**：TUMTraf VideoQA，包含1,000个视频（10秒至2分钟）、85,000多选QA、2,300目标描述、5,700时空定位标注。视频覆盖高速、城市交叉口、乡村道路等场景，包含雨雪雾、事故、救援等极端条件。7:3划分为训练/验证集。
- **Benchmark**：三项任务：
  1. **多选视频问答**（5个维度：Positioning/Counting/Motion/Class/Existence，各分Easy/Hard），评价指标为Top-1准确率。
  2. **视频推理对象描述**（基于元组查询对象外观），使用BLEU、CIDEr、ROUGE、METEOR、SPICE。
  3. **时空目标定位**（输出开始/结束帧的元组），使用Temporal Error、Spatial Error、Spatio-Temporal Error（L1/L2损失）。
- **对比方法**：LLaVA-OneVision（0.5B/7B）、Qwen2-VL（2B/7B）、VideoLLaMA2（7B-8F/16F），均在零样本设置下评估。
- **消融实验**：
  - 不同token采样策略（4种）对三项任务的影响。
  - 不同帧数（0/1/11/101帧）对性能的影响（表7）。
  - 统一101帧输入下与其他模型的对比（表8）。
  - 额外分析了光照、天气等条件下的分布（附录A/B）。

## 4. 资源与算力
- **训练硬件**：4块NVIDIA A100 GPU。
- **训练时长**：TraffiX-Qwen 0.5B模型约28小时（全流程），7B模型约36小时。
- **推理速度**：0.5B平均1.6秒/QA，7B平均3.8秒/QA（单A100，无量化/缓存加速）。
- 文中明确报告了参数数量和训练时间。

## 5. 实验数量与充分性
- **实验数量**：约**8组主要实验**（表3-8及附录多个补充表），包括：
  - 3项任务上的开源模型零样本对比（表3、5、6）。
  - 4种采样策略在2个模型规模下的全面对比（表3、5、6）。
  - 帧数消融实验（表7，包含0/1/11/101帧）。
  - 统一帧数下的公平对比（表8）。
  - 可视化分析（雷达图、token剪枝示例、定性结果等）。
- **充分性评价**：
  - **充分**：覆盖了所有主要任务、多种基线、采样策略、输入帧数的比较，并附有消融和定性分析。
  - **客观**：零样本设置公平（统一系统提示），消融实验控制变量，训练/验证集划分明确。
  - **潜在偏差**：开源模型由于未针对该任务微调，零样本性能普遍较差；基线模型训练仅1 epoch，可能未完全收敛。

## 6. 主要结论与发现
- **数据集挑战性**：TUMTraf VideoQA具有高难度，尤其Positioning类问题（需要3D空间推理）是所有模型的瓶颈。
- **开源模型局限**：零样本VLM在时空定位任务上几乎失效（误差接近1.0），在问答任务上表现远低于微调后的基线。
- **TraffiX-Qwen有效性**：微调后显著超越零样本模型，多分辨率策略在问答和描述任务上略有提升，但对时空定位反而有负效果。
- **帧数影响**：从0帧到1帧、1帧到11帧提升明显，但11帧到101帧收益递减，尤其0.5B模型几乎无增益。
- **幻觉问题**：无视觉输入时基线仍能实现较高准确率（表7），说明模型可能学习了文本模式或数据偏差。
- **小模型潜力**：0.5B模型在多数任务上接近7B性能，表明轻量模型在实际部署中具有价值。

## 7. 优点
- **新颖性**：首个面向路边监控视角的、统一多任务的视频语言数据集与基准。
- **数据多样性**：涵盖一年以上、多天气、多场景、多异常事件，具代表性。
- **统一表示**：基于元组的时空对象引用方法，简洁且可扩展，便于多任务集成。
- **基准贡献**：建立TraffiX-Qwen基线并开源，便于后续研究对比。
- **实验设计**：消融覆盖全面（采样策略、帧数、模型规模），定性案例丰富，分析深入（如幻觉、多分辨率负效果）。

## 8. 不足与局限
- **数据规模**：仅1,000个视频，相对较小，可能不足以支撑大规模模型训练；未来需扩展。
- **标注噪声**：半自动标注依赖LLM和检测器，可能存在错误（如外观描述偏差、跟踪丢失），文中虽有人工质检但未量化校验准确率。
- **模型幻觉**：无视觉输入时仍能回答，说明数据存在文本模式，可能使模型忽视视觉信息。
- **多分辨率负效果**：对时空定位任务有退化，显示策略设计仍需优化。
- **评估指标局限**：传统NLG指标（如ROUGE-L）对语义差异不敏感，未能区分生成质量（例：图19中“白车”与“绿顶公交”得分相同）。
- **应用验证**：仅停留在离线基准评估，未在真实交通监控系统中测试部署效率和鲁棒性。

（完）
