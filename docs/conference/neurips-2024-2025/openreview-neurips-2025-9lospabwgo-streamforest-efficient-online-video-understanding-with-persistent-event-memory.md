---
title: "StreamForest: Efficient Online Video Understanding with Persistent Event Memory"
title_zh: StreamForest：基于持久事件记忆的高效在线视频理解
authors: "Xiangyu Zeng, Kefan Qiu, Qingyu Zhang, Xinhao Li, Jing Wang, Jiaxin Li, Ziang Yan, Kun Tian, Meng Tian, Xinhai Zhao, Yi Wang, Limin Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9loSPaBwGO"
tags: ["query:long-video"]
score: 8.0
evidence: 在线视频理解中的持久事件记忆机制
tldr: 该论文针对实时流式视频理解中历史特征存储受限和实时时空推理不足的问题，提出StreamForest架构，核心是持久事件记忆森林，通过自适应组织视频帧为事件级树结构，实现高效长期记忆保留，在在线视频理解任务上性能优异。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 695, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 688, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1158, \"height\": 1880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 1055, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9lospabwgo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 393, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 749, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 669, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 585, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 839, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 585, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1306, \"height\": 992, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 919, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1167, \"height\": 871, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1096, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1457, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1448, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9lospabwgo/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 738, \"height\": 266, \"label\": \"Table\"}]"
motivation: 实时流式视频理解需要有效的长期记忆机制。
method: 设计持久事件记忆森林，根据时间距离、内容相似度等引导帧组织。
result: 在流式视频理解基准上达到先进的效率与准确性平衡。
conclusion: 事件级记忆结构是实现实时视频理解的关键组件。
---

## Abstract
Multimodal Large Language Models (MLLMs) have recently achieved remarkable progress in video understanding. However, their effectiveness in real-time streaming scenarios remains limited due to storage constraints of historical visual features and insufficient real-time spatiotemporal reasoning. To address these challenges, we propose StreamForest, a novel architecture specifically designed for streaming video understanding. Central to StreamForest is the Persistent Event Memory Forest, a memory mechanism that adaptively organizes video frames into multiple event-level tree structures. This process is guided by penalty functions based on temporal distance, content similarity, and merge frequency, enabling efficient long-term memory retention under limited computational resources. To enhance real-time perception, we introduce a Fine-grained Spatiotemporal Window, which captures detailed short-term visual cues to improve current scene perception. Additionally, we present OnlineIT, an instruction-tuning dataset tailored for streaming video tasks. OnlineIT significantly boosts MLLM performance in both real-time perception and future prediction. To evaluate generalization in practical applications, we introduce ODV-Bench, a new benchmark focused on real-time streaming video understanding in autonomous driving scenarios. Experimental results demonstrate that StreamForest achieves the state-of-the-art performance, with accuracies of 77.3% on StreamingBench, 60.5% on OVBench, and 55.6% on OVO-Bench. In particular, even under extreme visual token compression (limited to 1024 tokens), the model retains 96.8% of its average accuracy in eight benchmarks relative to the default setting. These results underscore the robustness, efficiency, and generalizability of StreamForest for streaming video understanding.

---

## 论文详细总结（自动生成）

# StreamForest 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多模态大语言模型（MLLMs）在离线视频理解中取得了显著进展，但在实时流式（streaming）视频场景中面临两大挑战：  
  1. **历史视觉特征存储受限**：持续到达的视频帧需要高效压缩和长期记忆管理，现有方法要么在采样阶段粗暴压缩丢失细节，要么在存储阶段基于帧间相似度合并但易漏掉关键事件或造成局部过度合并。  
  2. **实时时空推理不足**：流式场景要求模型能同时进行实时感知、过去记忆回溯和未来预测，现有方法主要针对密集视频描述，缺乏对细粒度实时理解的支持。

- **整体含义**：本文旨在设计一种更通用、高效的在线视频理解架构，实现长期事件记忆与即时感知的平衡，并推动 MLLMs 在自动驾驶、直播、机器人等实时场景中的应用。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心架构：StreamForest

由两大部分组成：**细粒度时空窗口（Fine-grained Spatiotemporal Window, FSTW）** 和 **持久事件记忆森林（Persistent Event Memory Forest, PEMF）**。

#### 2.1.1 细粒度时空窗口（FSTW）
- **目的**：增强模型对当前时刻的细粒度实时感知。
- **组成**：
  - **实时感知**：直接采样当前帧的高分辨率视觉特征，并编码时空位置信息。
  - **短期时空记忆**：保留最近 `ts` 秒的帧序列（每帧压缩为128个视觉 token），当容量超限时，旧帧被送入 PEMF。
- **事件分割**：在帧序列中识别局部最小帧间相似度位置，将连续帧分割成“元事件”（meta-event），每个元事件作为独立节点。

#### 2.1.2 持久事件记忆森林（PEMF）
- **目的**：高效存储和管理长期视觉信息，构建事件级树结构。
- **机制**：
  - 限制长期记忆 token 总数上限 `Lq`（默认8192）。
  - 当超限时，基于三个惩罚函数选择最优节点对进行合并（采用 ToMe 算法压缩 token 数为原两节点总和的一半）。
  - 三个惩罚函数：
    1. **相似度惩罚（Similarity Penalty）**：鼓励合并视觉内容高度相似的相邻事件节点。使用二分图匹配计算跨节点 token 对平均相似度，取 `1 - 平均相似度` 作为惩罚。
    2. **合并次数惩罚（Merge Count Penalty）**：避免节点因多次合并导致信息退化，根据历史合并次数进行正则化：`Pm = (ci + ci+1) / (2 * cmax)`。
    3. **时间距离惩罚（Temporal Distance Penalty）**：鼓励保留近期事件细节，对历史事件更激进压缩：`Pt = 1 - (di + di+1)/2`，其中 `di = (tq - ti)/tq`。
  - **总惩罚**：`P = ws * Ps + wm * Pm + wt * Pt`（默认权重 0.4, 0.4, 0.2）。
- **查询时**：将所有根节点（树中未合并的节点）的视觉特征与 FSTW 中的特征一起送入 LLM，支撑实时交互。

### 2.2 指令微调数据集：OnlineIT

- **OnlineIT-general**：约32K 高质量流式训练实例，融合现有数据集并新增，涵盖空间感知、时间感知、时空感知、事件感知四类任务。
- **OnlineIT-drive**：89K 自动驾驶场景训练实例，覆盖静态目标理解、动态目标理解、事件导向推理四类子任务。

### 2.3 新评测基准：ODV-Bench

- **目的**：评估自动驾驶场景下的在线视频理解能力，侧重实时感知和未来预测。
- **数据**：从6个自动驾驶数据集（如 Road-Waymo, BDD100K, MM-AU 等）中筛选视频，经四阶段构建（视频筛选→元标注生成→QA构建→质量审核）。
- **任务**：分三大类12个子任务：静态目标相关（RTP, PTM, DDM 等）、动态目标相关（AP, LP, DP）、事件相关（RP, RA, ARA）。

## 3. 实验设计

### 3.1 使用的数据集与 Benchmark

| 类型 | 具体基准/数据集 |
|------|----------------|
| 在线视频 QA 基准 | StreamingBench, OVBench, OVO-Bench, **ODV-Bench（新）** |
| 离线长视频 QA | VideoMME, MLVU |
| 离线短视频 QA | MVBench, PerceptionTest |
| 训练数据 | OnlineIT-general, OnlineIT-drive, 以及 VideoChat-Flash、LLaVA-Video、LLaVA-OneVision 等离线数据 |

### 3.2 对比方法

- **离线 MLLMs**：InternVL2, LongVA, LLaVA-OneVision, Qwen2-VL, LLaVA-Video, LongVU 等。
- **在线 MLLMs**：Flash-VStream, Dispider, VideoChat-Online, VideoLLM-online, MovieChat 等。
- **商业模型**：GPT-4o, Gemini 1.5 Pro, Claude 3.5 Sonnet。

### 3.3 评价指标

- 主要采用**准确率（Accuracy）**，部分任务包含平均分数（Avg.）或子项精度。

## 4. 资源与算力

- **训练设备**：32 张 A100 GPU。
- **训练策略**：五阶段训练：
  - 阶段 1-3：遵循 VideoChat-Flash 范式，使用图像和长短视频数据，逐步训练投影器→全模型，学习率从 2e-6 到 1e-5 不等。
  - 阶段 4：在线微调，总视觉 token 上限 8192（实时感知729 + 短期记忆18帧×128）。
  - 阶段 5（可选）：使用 OnlineIT-drive 进一步微调。
- **推理效率**：单张 A100 GPU 上，在 600 秒视频（1fps 输入）下达到约 9.9 FPS 处理速度（限制单 token 输出），与 VideoLLM-Online (12.3 FPS) 相近，远优于 Qwen2.5-VL (OOM)。

## 5. 实验数量与充分性

- **主要实验**：在 4 个在线基准、2 个长视频基准、2 个短视频基准上进行全面评估，共 8 个标准基准。
- **消融实验**：
  - 对比 PEMF 与四种记忆策略（Uniform Sampling, FIFO, Similarity Merge, Pyramid Memory Bank）。
  - 逐模块消融（去掉 FSTW、去掉 PEMF、去掉事件级构建）。
  - 惩罚权重消融（变化 ws, wm, wt 观察性能）。
  - 训练数据贡献消融（base vs. base+OnlineIT-general vs. base+OnlineIT-general+drive）。
  - 不同视觉 token 预算下的鲁棒性分析（1K~10K）。
- **公平性**：在对比中保持视觉 token 预算一致，且模型均在相同条件下微调。训练数据组合公开合理，对比方法多来自开源或商业模型，设置公平。

**结论**：实验设计充分、客观，涵盖了核心组件有效性、泛化能力、资源效率、行业场景等多个维度。

## 6. 主要结论与发现

1. **性能领先**：StreamForest 在 StreamingBench (77.3%)、OVBench (60.5%)、OVO-Bench (55.6%) 上均达到 SOTA，显著优于所有开源的在线视频 MLLMs，并超越多数离线 MLLMs。
2. **极端压缩下的鲁棒性**：当视觉 token 预算降至 1024 时，平均准确率仅下降 3.2%（保留 96.8%），证明 PEMF 有效保留关键事件信息。
3. **事件级记忆优于帧级合并**：PEMF 的树结构记忆相比相似度合并、金字塔记忆库等方法在长视频推理上提升 2~3 个百分点。
4. **FSTW + PEMF 互补**：联合使用两者带来最大增益（MLVU 提升 +18.2%）。
5. **OnlineIT 数据集有效**：加入 OnlineIT-general 和 drive 显著提升在线理解及驾驶场景能力。
6. **在离线场景同样优秀**：在 VideoMME (61.4%)、MLVU (70.0%)、MVBench (70.2%)、PerceptionTest (73.1%) 上达到或超过部分离线 SOTA。

## 7. 优点

- **创新性**：
  - 提出事件级持久记忆森林，结合三种自适应惩罚函数，实现了对长视频的高效压缩与关键事件保留。
  - 引入细粒度时空窗口，保留秒级短期细节，弥补长期记忆的不足。
- **实用性**：
  - 在极端 token 压缩下仍保持高精度，适合实际部署中的资源限制场景。
  - 在自动驾驶场景（ODV-Bench）上表现突出，验证了在真实高风险应用中的潜力。
- **数据贡献**：
  - 发布 OnlineIT 数据集（含 general 和 drive 两部分），覆盖多种流式任务，促进社区研究。
  - 构建 ODV-Bench 基准，填补自动驾驶流式视频理解的空白。
- **实验全面性**：
  - 覆盖在线/离线、长/短、通用/专业场景；进行多维度消融和鲁棒性分析。
- **开源**：代码、模型、数据均已公开（GitHub），可复现。

## 8. 不足与局限

- **事件边界检测粗糙**：仅依赖帧间相似度局部最小值来确定事件分割，主要捕捉粗粒度场景变化，对语义事件边界不敏感。论文承认此局限并建议未来引入轻量 MLLM 辅助。
- **离线场景性能仍存差距**：虽然在部分离线基准上已接近 SOTA，但并非在所有长视频任务上完全超越（如 MLVU 上 70.0% vs. LLaVA-Video 的 70.8%）。
- **计算资源需求高**：虽然推理效率尚可，但训练需 32 张 A100，对普通研究者门槛较高。
- **数据偏差风险**：OnlineIT-drive 仅覆盖有限自动驾驶场景，可能存在地域或环境偏差（如天气、光照、交通规则等）。论文在 Broader Impacts 中提到了此风险。
- **未涉及音频/多模态融合**：当前仅处理视觉流，未利用音频或其它模态信息，可能限制在某些场景下的表现。
- **多轮交互效率未深入评估**：虽给出了单 token 输出的处理速度，但实际多轮对话中文本生成延迟可能影响用户体验。

（完）
