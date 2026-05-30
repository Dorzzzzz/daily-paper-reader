---
title: "Video-RAG: Visually-aligned Retrieval-Augmented Long Video Comprehension"
title_zh: Video-RAG：视觉对齐的检索增强长视频理解
authors: "Yongdong Luo, Xiawu Zheng, Guilin Li, Shukang Yin, Haojia Lin, Chaoyou Fu, Jinfa Huang, Jiayi Ji, Fei Chao, Jiebo Luo, Rongrong Ji"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QaZxGWlbgO"
tags: ["query:long-video"]
score: 9.0
evidence: 基于检索增强的长视频理解，利用视觉对齐辅助文本
tldr: 针对现有大视频语言模型因上下文限制难以正确理解长视频的问题，本文提出Video-RAG，一种免训练低成本的检索增强生成流程，通过开源工具提取视觉对齐的辅助文本来跨越模态对齐并提供额外信息。该方法无需微调或专有模型，在长视频问答任务上显著提升准确率，为高效长视频理解提供了实用方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1365, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1386, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 881, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 885, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qazxgwlbgo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 1333, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 692, \"height\": 528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 695, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 681, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 634, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 890, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 892, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1276, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 823, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qazxgwlbgo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 884, \"height\": 248, \"label\": \"Table\"}]"
motivation: 现有长视频模型上下文受限，微调成本高，基于GPT的代理依赖专有模型。
method: 利用开源工具提取视觉对齐的辅助文本，结合检索增强流程丰富视频上下文。
result: 在多个长视频QA基准上以零微调方式超越现有方法。
conclusion: 检索增强生成是提升长视频理解性价比的有效手段。
---

## Abstract
Existing large video-language models (LVLMs) struggle to comprehend long videos correctly due to limited context. To address this problem, fine-tuning long-context LVLMs and employing GPT-based agents have emerged as promising solutions. However, fine-tuning LVLMs would require extensive high-quality data and substantial GPU resources, while GPT-based agents would rely on proprietary models (e.g., GPT-4o). In this paper, we propose Video Retrieval-Augmented Generation (Video-RAG), a training-free and cost-effective pipeline that employs visually-aligned auxiliary texts to help facilitate cross-modality alignment while providing additional information beyond the visual content. Specifically, we leverage open-source external tools to extract visually-aligned information from pure video data (e.g., audio, optical character, and object detection), and incorporate the extracted information into an existing LVLM as auxiliary texts, alongside video frames and queries, in a plug-and-play manner. Our Video-RAG offers several key advantages: (i) lightweight with low computing overhead due to single-turn retrieval; (ii) easy implementation and compatibility with any LVLM; and (iii) significant, consistent performance gains across long video understanding benchmarks, including Video-MME, MLVU, and LongVideoBench. Notably, our model demonstrates superior performance over proprietary models like Gemini-1.5-Pro and GPT-4o when utilized with a 72B model.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有大型视频语言模型（LVLMs）在处理长视频时受到上下文窗口的限制，难以准确理解长视频内容。
- **背景困境**：目前两类解决方案各有缺陷：
  - 微调长上下文 LVLMs 需要大量高质量数据和高昂 GPU 资源，且增加帧数反而可能因信息冗余导致性能下降（如 LongVA 在 128→384 帧时准确率从 52.6% 降至 51.8%）。
  - GPT-based Agent 方法（如 VideoAgent）依赖专有模型（如 GPT-4o），处理成本极高（完整评估 Video-MME 需约 2000 美元 API 费用），且多轮交互资源消耗大。
- **论文目标**：提出一种**免训练、低成本、即插即用**的检索增强生成（RAG）管道——Video-RAG，通过提取**视觉对齐的辅助文本**（OCR、ASR、目标检测）来增强 LVLM 的长视频理解能力，最终在开放源码 72B 模型上达到甚至超越 GPT-4o/Gemini-1.5-Pro 的水平。

## 2. 方法论：核心思想、关键技术细节、流程

### 2.1 核心思想
利用开源工具从视频中提取三种类型的**视觉对齐辅助文本**（光学字符 OCR、自动语音识别 ASR、目标检测 DET），通过 RAG 检索与用户查询最相关的部分，与原始视频帧和查询一起输入任意 LVLM，辅助跨模态对齐，减少视觉幻觉，提升回答准确率。

### 2.2 关键技术细节

- **辅助文本提取工具**（全部开源）：
  - OCR：EasyOCR（逐帧识别文本） → T_ocr
  - ASR：Whisper（提取音频并转录） → T_asr
  - DET：APE（开放词汇目标检测，基于关键帧和查询中的物体名称）→ T_det（包含类别和位置坐标）
- **检索和数据库构建**：
  - 使用 Contriever 将 OCR/ASR 文本块编码为稠密向量，存入 FAISS 索引（IndexFlatIP）。
  - 目标检测关键帧选择：用 CLIP 计算查询中的物体名称与视频帧的相似度，筛选高于阈值 t 的帧。
- **场景图预处理**：对 DET 原始坐标信息进行结构化处理，生成三种类型文本：
  - 物体位置（Aloc）
  - 物体计数（Acnt）
  - 物体相对关系（Arel）
- **阈值**：CLIP 相似度和 FAISS 相似度阈值均设为 0.3。

### 2.3 算法流程（文字描述）

1. **查询解耦**：将用户文本查询（无视频）输入 LVLM，通过解耦提示生成 JSON 格式的检索请求 R = {R_asr, R_det, R_type}。
2. **辅助文本生成与检索**：
   - 并行构建 OCR、ASR、DET 三个数据库。
   - 根据请求 R 检索相关文本块（OCR/ASR 通过 FAISS 相似度；DET 基于 CLIP 选择关键帧，再用场景图生成结构化文本）。
   - 按时间顺序合并检索到的辅助文本 A_m = Concat(A_ocr, A_asr, A_det)。
3. **集成与生成**：将视频帧特征 F_v、辅助文本 A_m 和用户查询 Q 一起输入 LVLM，生成最终输出 O = LVLM(F_v, Concat(A_m, Q))。

## 3. 实验设计

### 3.1 数据集与基准

- **Video-MME**：长视频理解基准，按视频时长分 Short/Medium/Long，覆盖多种任务（12 个子任务）。不含字幕版（w/o S）和含字幕版（w/ S）均有评估。
- **MLVU**：长视频理解基准，平均时长 12 分钟，9 类任务。
- **LongVideoBench**：长视频多模态信息检索与推理基准，6678 个多项选择题。
- **补充实验**：VNBench（合成基准，评估检索、排序、计数能力）。

### 3.2 对比方法

- **专有模型**：GPT-4o、Gemini-1.5-Pro。
- **开源 LVLMs（7B 和 72B）**：Video-LLaVA、LLaVA-NeXT-Video、VITA-1.5、LongVA、Long-LLaVA、Qwen2-VL、LLaVA-Video。
- **GPT-based Agent 方法**：VideoAgent（仅在子集对比中涉及）。

### 3.3 实验设置

- 所有实验在 NVIDIA A100 80G GPU 上执行。
- 对于每个 LVLM，使用其官方帧率设置（7B 模型通常 16-128 帧，72B 模型 32-64 帧），但 72B Qwen2-VL 因资源限制未使用其 768 帧设置。
- Video-RAG 添加的辅助文本平均约 2.0K tokens（相当于约 14 帧的视觉 tokens）。

## 4. 资源与算力

- **硬件平台**：NVIDIA A100 80G GPU（未说明具体数量，通常单卡或多卡并行）。
- **额外开销**：
  - 对于 7B LVLM，Video-RAG 仅需额外 **8GB 推理 GPU 内存**，每 case 推理时间增加约 **5 秒**（数据库构建时间另计，但可并行一次完成）。
  - 72B 模型资源需求更高，论文未给出精确数字。
- **数据库构建时间**（补充材料）：以 LongVA-16 帧为例，ASR 约 21 分钟、OCR 2 分钟、DET 3 分钟，可并行，瓶颈为 ASR。
- **对比 GPT-based Agent**：VideoAgent 完成 Video-MME 子集需 14 分钟/查询，且需大量 API 费用；Video-RAG 仅需约 5 秒额外推理时间。

## 5. 实验数量与充分性

### 5.1 实验组数

- **主实验结果**：三个基准测试（表1、2、3），覆盖 7 种 LVLM（含 2 个 72B），共 10 余个模型-基准组合。
- **消融实验**：
  - 不同辅助文本组件（DET、OCR、ASR）组合（表4、表9、表10）。
  - 不同帧采样率（8~256帧，图3）。
  - 不同 RAG 阈值（0~1.0，表5）。
  - RAG vs. 随机检索（表5底行）。
  - 子任务级分析（图7）。
- **定性分析**：Grad-CAM 和 t-SNE 可视化（图5），多个视频案例展示（图4、图9）。
- **子集对比**：与 VideoAgent 在 90 视频子集上对比资源与性能（图6、表8）。

### 5.2 充分性评估

- **正面**：实验覆盖主流基准、多尺度模型、关键组件和参数，消融设计完整，可视化支撑直觉。
- **不足**：
  - 未报告多次重复的误差线（统计显著性问题）。
  - 与 GPT-based Agent 的对比仅限子集（因资源限制），且未提供 GPT-4o 的完整推理成本。
  - 未在更多多样性视频（如体育、纪录片）上验证泛化性。
  - 未分析失败案例或工具引入的错误累积。

## 6. 主要结论与发现

1. **性能提升显著**：在 7 种 LVLM 上，Video-RAG 使 Video-MME 平均提升 **2.8%**（相对于字幕版），长视频提升尤为明显（最高达 6.0%）。
2. **达到专有模型水平**：LLaVA-Video-72B + Video-RAG 在 Video-MME 上达到 **77.4%**，超越 GPT-4o（77.2%）和 Gemini-1.5-Pro（81.3%，但仅考虑无字幕时 Video-RAG 版本胜出）。
3. **各组件均有贡献**：ASR 对一般性推理提升最大；DET 增强空间感知和计数；OCR 提升文字相关任务。RAG 检索比直接使用全部辅助文本提高 2.3%。
4. **鲁棒性**：在不同帧率和阈值下均稳定提升；在资源受限场景（如少帧率）下增益更加突出。
5. **轻量高效**：仅需少量额外 tokens 和 GPU 内存，推理时间增加可接受。

## 7. 优点

- **免训练**：无需微调任何模型，直接插拔使用，极大降低计算成本。
- **即插即用**：兼容任意 LVLM，无需修改模型结构。
- **全开源**：所有工具（EasyOCR、Whisper、APE、Contriever、FAISS）均可免费获取，无商业依赖。
- **成本效益高**：相比 GPT-based Agent 方法节省大量 API 费用和推理时间。
- **设计巧妙**：通过 RAG 筛选与查询对齐的辅助文本，避免信息冗余，同时利用场景图预处理提升文本可理解性。
- **实验全面**：在多个基准上验证，消融深入，可视化有力。

## 8. 不足与局限

- **工具依赖**：性能受限于所选工具（EasyOCR 文本识别能力、Whisper 对不同口音的鲁棒性、APE 的检测质量），若工具较弱可能引入噪声。
- **阈值调参**：RAG 相似度阈值需要手动调整（0.3 为经验值），可能在不同场景下非最优。
- **跨场景泛化有限**：仅在三个基准上评估，未涵盖人机交互、自动驾驶等长视频场景。
- **未考虑工具错误累积**：OCR/ASR/DET 错误会传播至最终答案，论文未分析错误案例。
- **实验统计不充分**：未提供多次运行的标准差，无法判断改进是否具有统计显著性。
- **GPT-based Agent 对比不全面**：仅在子集上对比 VideoAgent，且未报告 GPT-4o API 的具体消耗。
- **可扩展性限制**：72B 模型仍需较大 GPU 资源（约 3K 显存），可能仍对普通用户不友好。
- **适应性不足**：目前辅助文本提取策略固定，未根据视频内容动态调整（如无音频视频仍运行 ASR 会浪费资源）。

（完）
