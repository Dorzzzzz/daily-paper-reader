---
title: "Temporal Chain of Thought: Long-Video Understanding by Thinking in Frames"
title_zh: 时间思维链：通过帧思考实现长视频理解
authors: "Anurag Arnab, Ahmet Iscen, Mathilde Caron, Alireza Fathi, Cordelia Schmid"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BDkNRlGmP9"
tags: ["query:long-video"]
score: 9.0
evidence: 通过迭代帧选择实现长视频问答
tldr: 针对长视频问答中模型容易受到无关帧干扰的问题，本文提出动态上下文聚合推理策略，利用VLM自身迭代地识别和提取最相关帧用于回答。该方法在推理时增加计算以选择关键上下文，在多个长视频问答基准上显著提升了准确率，表明精细的帧选择比全量输入更有效。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1425, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 830, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 857, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 980, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1002, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 996, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 937, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1432, \"height\": 207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1442, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1438, \"height\": 212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdknrlgmp9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 255, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 629, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 785, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 627, \"height\": 644, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 943, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 409, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdknrlgmp9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 481, \"height\": 282, \"label\": \"Table\"}]"
motivation: 长视频VLM难以有效利用长上下文，易受无关帧干扰。
method: 利用VLM自身迭代地选择最相关帧构建精简上下文进行问答。
result: 在多个长视频QA数据集上准确率大幅提升，验证了动态帧选择的优势。
conclusion: 推理时动态上下文聚合是提升长视频问答效能的关键。
---

## Abstract
Despite recent advances in Vision-Language Models (VLMs), long-video understanding remains a challenging problem. Although state-of-the-art long-context VLMs can process around 1000 input frames, they still struggle to effectively leverage this sequence length, and succumb to irrelevant distractors within the context window. We present Dynamic Context Aggregation, an inference strategy for video question-answering that curates the model's input context. We use the VLM itself to iteratively identify and extract the most relevant frames from the video, which are then used for answering. We demonstrate how leveraging more computation at inference-time to select the most relevant context leads to improvements in accuracy, in agreement with recent work on inference-time scaling of LLMs. Moreover, we achieve state-of-the-art results on 4 diverse video question-answering datasets, showing consistent improvements with 3 different VLMs. In particular, our method shines on longer videos which would not otherwise fit in the model's context window: On longer videos of more than 1 hour on LVBench, our approach using a context window of 32K outperforms the same VLM using standard inference with a 700K context window by 2.8 points.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：尽管视觉-语言模型（VLM）能处理约1000帧的长视频，但长上下文中大量无关帧会分散模型注意力，导致性能饱和甚至下降。
- **背景**：已有研究显示，LLM/VLM处理长上下文时中间位置的关键信息容易被忽略（“Lost in the Middle”）。长视频问答需要从数千帧中定位相关信息，现有方法多依赖多模型级联（如先逐帧描述再检索），增加了复杂性和信息丢失风险。
- **整体含义**：本文提出**推理时动态上下文聚合**策略，利用VLM自身迭代识别并提取最相关帧，再基于精简上下文进行回答，实现精准、高效的长视频理解。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：将视频问答分解为两步：① 上下文聚合（Context Aggregation）→ ② 答案生成。两步共用同一VLM，无需外部模型。
- **关键技术细节**：
  - **Single‑Step Temporal Chain of Thought (TCoT)**：给定一组帧，VLM根据问题输出相关帧ID列表（JSON格式），附加理由；同时保留少量均匀采样帧（u个）以提供全局线索。
  - **Dynamic‑Segment TCoT**：将长视频划分为l个等长段，每段均匀采样s帧，独立执行Single‑Step TCoT；合并所有选中的帧，若超出上下文限制k，则再均匀采样至k-u帧，并添加u帧均匀上下文。
  - **公式化**：选择函数`S(x, q)`返回选定帧集；聚合函数`G(x, q)`通过分段迭代获得`c`；答案函数`H(c, q)`输出最终答案`a`。
  - **特点**：上下文窗口固定为s（每段帧数），与视频总长度解耦，计算成本随段数l线性增长；自适应问题类型（如时间定位问题选少量帧，概括问题选较多帧）。

### 3. 实验设计
- **数据集**：Egoschema（180秒，5000样本）、LVBench（平均68分钟，1043问题）、OpenEQA（450帧，开放问答）、NExT‑QA（39.5秒）。
- **Benchmark**：各数据集标准测试集，评估指标为准确率（多选）或LLM评分（OpenEQA）。
- **对比方法**：
  - 基线推理（直接输入所有帧）。
  - 均匀采样、特征相似度（CLIP/SigLIP嵌入）、VLM基于描述的选择。
  - 现有系统：VideoAgent、LLoVi、VideoTree、BOLT等。
  - 推理‑时间扩展基线：自‑一致性CoT（多次采样投票）、零样本CoT。
  - Oracle（使用人工标注的时间参考帧）。
- **使用的VLM**：Gemini 1.5 Flash（主要）、Qwen‑2.5‑VL 7B、GPT‑4o‑mini（验证泛化性）。

### 4. 资源与算力
- 实验主要通过API调用Gemini 1.5 Flash和GPT‑4o‑mini；Qwen‑2.5‑VL在8×NVIDIA A100 GPU上运行。
- 论文未报告具体的训练时长（方法无需训练，仅推理），但指出总计算成本随分段数l线性增加。

### 5. 实验数量与充分性
- **实验组数**：共7张表格（表1‑7）和多个图表（图4‑10），涵盖：
  - 聚合策略对比（表1、2）。
  - 准确率‑计算量权衡（图4）。
  - 超参数影响（表6a、6b）。
  - 问题类型分析（图6、8）。
  - 失败模式分析（图10、11）。
  - SOTA对比（表3）包含4个数据集、3个VLM。
- **充分性**：实验设计全面，消融系统，对比公平（使用相同VLM和上下文预算），且包含多模型、多数据集验证。平均结果基于3次运行，误差可接受。

### 6. 主要结论与发现
- **核心发现**：推理时动态帧选择能显著提升长视频问答准确率，且计算量增加时收益持续，而基线推理在约1000帧后饱和。
- **主要结果**：
  - LVBench上，32K上下文窗口的TCoT（61.7%）超越700K窗口的基线（58.9%），提升2.8个点；相比32K基线提升11.4个点。
  - 在所有4个数据集上均达到SOTA，且三个VLM均有提升，表明方法模型无关。
  - 自适应帧选择：时间定位任务仅选<10%帧，概括任务选>30%，与人类标注高度吻合。
- **方法对比**：VLM直接选择帧优于基于描述或特征相似度的选择；自‑一致性CoT在长视频上几乎无效。

### 7. 优点
- **简洁性**：仅使用单一VLM，无需额外模型或训练，易于部署。
- **可扩展性**：通过分段独立处理，可处理超长视频（即使模型上下文窗口有限）。
- **自适应性与可解释性**：模型输出选帧理由，可根据问题动态决定帧数；失败时可分析原因。
- **跨模型泛化**：在Gemini、Qwen、GPT‑4o‑mini上均有效，证明其通用性。
- **计算‑准确率帕累托曲线**：增加分段数l可平滑提升性能，便于根据预算调整。

### 8. 不足与局限
- **依赖模型指令遵循能力**：选择函数要求VLM能正确解析JSON格式并生成合法帧索引，对较弱模型可能失败。
- **潜在信息遗漏**：低召回问题（失败模式分析）显示，当关键帧未包含在任何分段采样中时，答案会错误。例如，未选中“水珠镜子”帧导致错误推断。
- **概括性问题有限**：图8显示TCoT在“概括”类问题上的提升不如其他类型，可能是因为需要较广范围的帧，而方法偏向于聚焦局部。
- **训练缺失**：当前为纯推理方法，未对选择模块进行强化学习训练，性能上限可能受限于VLM的固有能力（如对齐训练）。未来可通过RL优化提升。
- **计算成本**：分段越多，VLM调用次数线性增长，在大规模部署时需权衡。

（完）
