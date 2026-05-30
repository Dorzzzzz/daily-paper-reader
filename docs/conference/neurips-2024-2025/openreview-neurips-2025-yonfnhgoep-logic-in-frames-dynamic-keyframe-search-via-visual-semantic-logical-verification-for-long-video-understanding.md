---
title: "Logic-in-Frames: Dynamic Keyframe Search via Visual Semantic-Logical Verification for Long Video Understanding"
title_zh: 逻辑帧：基于视觉语义逻辑验证的动态关键帧搜索用于长视频理解
authors: "Weiyu Guo, Ziyang Chen, Shaoguang Wang, Jianxiang He, Yijie Xu, Jinhui Ye, Ying Sun, Hui Xiong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yONFNHGoeP"
tags: ["query:long-video"]
score: 9.0
evidence: 基于语义逻辑验证的动态关键帧搜索用于长视频理解
tldr: 现有长视频理解方法常忽略查询与视觉元素间的逻辑关系，本文提出视觉语义逻辑搜索框架VSLS，明确定义空间共现、时间邻近、属性依赖和因果关系四种逻辑依赖，并据此动态搜索关键帧。该方法在长视频理解任务中有效提升关键帧定位准确率，从而改善整体理解性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 691, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1082, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1418, \"height\": 980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1139, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yonfnhgoep/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 700, \"height\": 353, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 767, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1090, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yonfnhgoep/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 990, \"height\": 260, \"label\": \"Table\"}]"
motivation: 长视频关键帧选择常忽略查询与视觉元素间的逻辑关系，导致次优。
method: 定义四种逻辑依赖并基于语义搜索动态提取关键帧。
result: 在长视频理解基准上关键帧定位和问答准确率均显著提升。
conclusion: 利用逻辑关系指导关键帧选择可有效提升长视频理解质量。
---

## Abstract
Understanding long video content is a complex endeavor that often relies on densely sampled frame captions or end-to-end feature selectors, yet these techniques commonly overlook the logical relationships between textual queries and visual elements. In practice, computational constraints necessitate coarse frame subsampling, a challenge analogous to “finding a needle in a haystack.” To address this issue, we introduce a semantics-driven search framework that reformulates keyframe selection under the paradigm of Visual Semantic-Logical Search (VSLS). Specifically, we systematically define four fundamental logical dependencies: 1) spatial co-occurrence, 2) temporal proximity, 3) attribute dependency, and 4) causal order. These relations dynamically update frame sampling distributions through an iterative refinement process, enabling context-aware identification of semantically critical frames tailored to specific query requirements. Our method establishes new state-of-the-art performance on the manually annotated benchmark in keyframe selection metrics. Furthermore, when applied to downstream video question-answering tasks, the proposed approach demonstrates the best performance gains over existing methods on LongVideoBench and Video-MME, validating its effectiveness in bridging the logical gap between textual queries and visual-temporal reasoning. The code will be publicly available.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：长视频理解面临“大海捞针”难题——视觉语言模型（VLM）由于token限制和时空数据的高维度，通常只能处理有限数量的帧。现有方法（密集采样、均匀采样）忽略了文本查询与视觉元素之间的**逻辑关系**（如空间、时间、属性、因果），导致关键帧选取次优，影响下游任务（如视频问答）的准确性。
- **背景与动机**：当前方法要么基于静态均匀采样（查询无关），要么依赖密集帧描述或聚类，效率低且缺乏语义对齐。作者假设：**通过从文本查询中分解出视觉语义和逻辑线索（目标对象、逻辑关系），结合启发式采样和搜索，能高效识别任务相关帧**。
- **整体含义**：提出一种**训练无关、即插即用**的视觉语义逻辑搜索框架（VSLS），首次将逻辑关系显式建模引入长视频关键帧搜索，极大提升搜索效率与下游任务性能。

## 2. 方法论：核心思想、关键技术细节、算法流程
### 核心思想
- **视觉语义逻辑搜索（VSLS）**：将关键帧选择重构为一种**基于语义逻辑的迭代搜索**过程，通过**目标对象置信度估计**和**视觉语义逻辑联合验证**，动态更新帧采样分布，最终选出置信度最高的关键帧。
- **四种基本逻辑依赖**（从语言学与逻辑学归纳）：  
  ① **空间共现（Spatial）**：两个对象必须在同一帧中出现。  
  ② **时间邻近（Temporal）**：两个对象在时间相近的帧中出现（间隔 < `Δt`）。  
  ③ **属性依赖（Attribute）**：对象的属性（如颜色、大小）与另一对象在相同帧中满足重叠阈值（IoU > τ）。  
  ④ **因果顺序（Causal）**：对象A必须在对象B之前出现（时间先后）。

### 关键技术细节
1. **查询语义解析**：用LLM（如GPT-4o）从查询Q中提取**关键对象**（主要参与者）和**线索对象**（上下文实体），并识别逻辑关系三元组 `(obj1, δ, obj2)`。
2. **自适应网格采样**：初始为均匀分布，每轮根据当前得分分布采样 `⌊√B⌋²` 帧，堆叠成 `k×k` 网格以提高YOLO检测效率。
3. **目标检测与评分**：使用轻量级YOLO-World（110M参数）检测对象，定义帧基础得分 `Ct = max_{o∈Ωt} (c_o · w_o)`。
4. **语义逻辑关系检测**：对每个检测到的关系，按类型附加奖励得分 `C(r)_t = Ct + α·γ_rtype`，其中 `α` 为全局缩放因子，`γ` 为关系特定权重（实验设置 α=0.3, γ=0.5）。
5. **分布更新与扩散**：将每轮得分合并到全局注册表，通过 `S_{f±δ} = max(S_{f±δ}, S_f/(1+|δ|))` 扩散到邻近帧，保证时间连续性；更新概率分布并归一化。
6. **终止条件**：达到预算B或所有关键对象已被识别。输出Top-K帧。

### 算法流程（文字说明）
```
输入：视频V，查询Q，参数K, Δt, τ, α, γ
1. 解析Q得到对象集O和关系集R
2. 初始化均匀分布P，预算B = |V|，空得分数组S
3. 循环直到B≤0或O为空：
   - 计算采样数量k²，从P中采样k²帧形成网格G
   - 对G进行YOLO检测，得到每个帧的检测结果Ω
   - 对每个帧g：计算基础得分C_g，遍历每个关系r，根据类型增加奖励得分
   - 更新全局得分S，对S进行时间扩散（窗口w）
   - 归一化P，B减少k²
4. 根据S取Top-K帧，若这些帧包含所有关键对象则移除已识别对象
5. 返回Top-K帧
```

## 3. 实验设计：数据集、场景、对比方法
### 使用的数据集
| 数据集 | 用途 | 规模/特点 |
|--------|------|----------|
| **LongVideoBench** | 长视频语言理解评估 | 3,763个视频，时长8s~60min，6,678个QA对 |
| **Video-MME** | 视频问答（多模态） | 900个视频，2,700个QA对，时长11s~60min |
| **Haystack-LVBench** | 关键帧选取精准评估（人工标注） | 从LongVideoBench扩展，含关键帧索引 |
| **Haystack-Ego4D** | 同上（第一人称视频） | 源于Ego4D（101小时视频） |

### 评估指标
- **搜索有效性**：视觉相似性（SSIM Precision/Recall）、时间覆盖度（Temporal Coverage）
- **搜索效率**：FLOPs、延迟（Latency）
- **下游任务**：视频问答准确率（Accuracy）

### 对比方法
- **静态采样**：Uniform（8帧/32帧）
- **密集检索**：VideoAgent（CLIP-1B）、T*-Retrieval、T*-Attention、T*-Detector
- **时序搜索**：T*（同类搜索基线，无逻辑关系）
- 所有基线与VSLS均集成相同VLM（GPT-4o、InternVL 2.5-78B、LLaVA-Video-7B等）进行公平对比。

### 实验场景
- 按视频长度分为短（15-60s）、中（180-600s）、长（900-3600s）
- 使用不同帧数（8/32帧）进行QA推理
- 进行消融实验：单独分析每种逻辑关系对性能的影响
- 覆盖分析：统计四种逻辑关系在数据集中的出现频率

## 4. 资源与算力
- **硬件环境**：单台或集群配置如下：
  - CPU：Intel(R) Xeon(R) Platinum 8378A @ 3.00GHz 或 8358P @ 2.60GHz
  - 内存：1TB RAM
  - GPU：4或6块 NVIDIA A800 (80GB)（SXM4或PCIe版本）
- **关键模型**：
  - YOLO-World（110M参数，用于目标检测）
  - LLM/VLM：GPT-4o（API调用）、Qwen2.5-VL-7B、InternVL 2.5-78B、LLaVA系列等
- **无需额外训练**：VSLS整个框架为训练无关（training-free），仅使用预训练检测器和LLM推理。
- **搜索开销**：平均采样1.4%帧，搜索延迟约7.8s（Haystack-LVBench），总延迟（搜索+推理）约11.6s。

## 5. 实验数量与充分性
- **实验组数丰富**：
  - 主要实验：在2个大型QA基准（LongVideoBench, Video-MME）上对比了5+种基线，覆盖8/32帧、多种VLM。
  - 搜索效率分析：1张表（Table 1）展示TFLOPs、延迟、准确率。
  - 搜索效用分析：2张表（Table 2, Table 3）分别展示关键帧检索指标和下游QA准确率。
  - 消融实验：Table 4对比四种逻辑关系下的VSLS vs T*。
  - 覆盖分析：Figure 4展示各关系出现频率。
  - 额外分析：迭代次数对比（Figure 7）、置信度阈值/网格大小影响（Appendix C）。
  - 可视化案例：Figure 6展示关键帧搜索效果。
- **充分性评估**：
  - 实验覆盖多场景（短/中/长视频）、多模型、多指标，对比基线包括最先进的T*及其变体。
  - 消融实验证明了每种逻辑关系的贡献。
  - 但**未报告误差棒/统计显著性**（论文说明为确定性方法），且仅在公开数据集上评估，未在真实工业场景验证。

## 6. 主要结论与发现
- **性能提升显著**：
  - 在Haystack-LVBench上，VSLS以仅1.4%帧采样实现关键帧选择SOTA：SSIM Precision 74.5%、SSIM Recall 92.5%、Temporal Coverage 41.4%（超越次优T* 13.4%）。
  - 在LongVideoBench长视频段（900-3600s），VSLS+GPT-4o准确率51.2%（8帧）和54.2%（32帧），比T*高约2-5个百分点。
  - 在Video-MME上，VSLS同样在长视频段表现最佳。
- **效率优势**：搜索TFLOPs仅33.3（远低于密集检索的840），延迟与T*接近，但准确率更高。
- **逻辑关系有效性**：四种关系均有增益，其中空间关系提升最大（时间覆盖度+21.3%）；所有查询至少匹配一种关系，证明关系集合理性。
- **即插即用**：VSLS可无缝集成到现有VLM流水线中，无需修改原模型。

## 7. 优点（方法或实验设计亮点）
- **创新性**：首次将文本-视觉逻辑关系（空间、时间、属性、因果）显式建模并用于关键帧搜索，超越传统仅依赖对象检测的方法。
- **训练无关**：完全无需微调或训练，依赖预训练检测器和LLM，实用性强。
- **高效搜索**：通过概率分布扩散和自适应网格采样，仅需极少量帧（1.4%）即达到SOTA。
- **强可解释性**：四种逻辑关系有语言学/逻辑学理论支撑；搜索过程可通过得分分布可视化（Figure 3, 6）。
- **公平对比**：在统一设置下（相同VLM、相同帧数）与多个基线对比，并进行了消融分析。
- **附录丰富**：提供了详细算法伪代码、提示模板、超参数敏感性分析、额外案例，确保可重复性。

## 8. 不足与局限
- **依赖检测器性能**：YOLO-World在光线差、遮挡、特殊角度下可能失效，影响时序覆盖（论文已承认）。
- **属性关联启发式局限**：仅用边界框重叠（IoU阈值0.5）判断属性关系，逻辑上可能不精确，但论文解释为主过滤机制，后续由VLM精化。
- **搜索开销仍有优化空间**：平均7.8s搜索延迟对极端实时应用可能仍偏高（如毫秒级需求）。
- **实验统计缺乏误差分析**：未报告多次运行的标准差或置信区间，降低结果稳健性。
- **数据集局限**：仅评估3个公开基准（LongVideoBench, Video-MME, Haystack），未在新闻、医疗、监控等长视频场景验证。
- **关系定义不完备**：虽覆盖主要逻辑，但可能遗漏更细粒度关系（如动作序列、情绪变化等）。
- **适用范围**：假设查询和视频内容中存在可检测对象，对纯抽象或语义模糊的查询效果不明。

（完）
