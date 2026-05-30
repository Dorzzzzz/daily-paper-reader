---
title: Enhancing Temporal Understanding in Video-LLMs through Stacked Temporal Attention in Vision Encoders
title_zh: 通过在视觉编码器中堆叠时间注意力增强视频大语言模型的时间理解
authors: "Ali Rasekh, Erfan Bagheri Soula, Omid Daliran, Simon Gottschalk, Mohsen Fayyaz"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2EJrs3gUO6"
tags: ["query:long-video"]
score: 7.0
evidence: 堆叠时间注意力增强视频LLM的时间理解
tldr: 该论文发现现有视频LLM在理解动作序列和时间进展方面存在局限，因此在视觉编码器中引入堆叠的时间注意力模块，使得模型在将视觉标记传递给语言模型之前就能更好地捕捉帧间关系，实验证明该方法显著提升了时序理解能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1379, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1310, \"height\": 475, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1205, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 806, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 672, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 729, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1051, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 964, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 999, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 789, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 695, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1373, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ejrs3guo6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 924, \"label\": \"Table\"}]"
motivation: 视频LLM对复杂时序动态理解不足。
method: 在视觉编码器中插入堆叠的时间注意力模块。
result: 在时序理解任务上超过现有模型。
conclusion: 在编码阶段即进行时间建模能有效提升视频LLM的时间感知能力。
---

## Abstract
Despite significant advances in Multimodal Large Language Models (MLLMs), understanding complex temporal dynamics in videos remains a major challenge. Our experiments show that current Video Large Language Model (Video-LLM) architectures have critical limitations in temporal understanding, struggling with tasks that require detailed comprehension of action sequences and temporal progression. In this work, we propose a Video-LLM architecture that introduces stacked temporal attention modules directly within the vision encoder. This design incorporates a temporal attention in vision encoder, enabling the model to better capture the progression of actions and the relationships between frames before passing visual tokens to the LLM. Our results show that this approach significantly improves temporal reasoning and outperforms existing models in video question answering tasks, specifically in action recognition. We improve on benchmarks including VITATECS, MVBench, and Video-MME by up to +5.5%. By enhancing the vision encoder with temporal structure, we address a critical gap in video understanding for Video-LLMs. Project page and code are available at: https://alirasekh.github.io/STAVEQ2/

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

当前视频大语言模型（Video-LLM）在多模态理解方面取得了显著进展，但在理解复杂时间动态（如动作序列的方向、顺序和进展）方面仍然存在严重不足。现有模型在空间性问题上表现良好，但在需要精确理解时间进展的任务（如区分“从左到右拉”和“从右到左拉”）中常常失败。论文通过实验证明，即使提供上下文示例（in-context learning）或微调，现有模型仍无法可靠地捕捉时间模式，表明这是一个架构层面的根本缺陷，而不仅仅是数据或训练问题。

## 2. 方法论

### 核心思想
在视觉编码器中直接引入堆叠的时间注意力模块（Stacked Temporal Attention, STA），让模型在将视觉token传递给LLM之前，就能显式地建模帧之间的时间关系和动作进展。

### 关键技术细节
- **基础架构**：采用Qwen2-VL的视觉编码器，每个transformer块包含空间自注意力（对帧内patch）、注入的时间自注意力（对帧间同一patch）、MLP和残差连接。
- **时间注意力设计**：
  - 对每个patch，将空间注意力输出按帧排列成序列，然后应用时间自注意力。
  - 使用比空间注意力更少的注意力头（最多减少4倍），保持头维度，从而参数高效。
  - 在时间注意力中引入1D旋转位置编码（RoPE），而空间部分使用2D RoPE。
- **训练策略**（两阶段）：
  1. **第一阶段**：冻结所有参数（除时间注意力块及层归一化），将时间注意力输出投影层初始化为零，保持原有空间能力，逐步引入时间建模。
  2. **第二阶段**：在视觉编码器和LLM的线性层中加入LoRA适配器，联合训练时间注意力块和LoRA，使增强的时空特征与LLM对齐。

### 算法流程简述
视频帧 → patch嵌入 → 每个transformer块：空间注意力（帧内）→ 时间注意力（帧间同一patch）→ MLP → 输出特征 → 投影至LLM嵌入空间 → 与问题文本拼接 → LLM生成答案。

## 3. 实验设计

### 数据集与场景
- **SSv2（Something-Something v2）**：动作识别，全数据集及子集SSv2-T10（10类方向性动作）。
- **SSv2-VSM**：视觉相似性匹配任务。
- **VITATECS**：诊断时间概念理解（6个方面：组合性、方向、强度、定位、序列、类型）。
- **MVBench**：20个视频任务。
- **Video-MME**：多模态视频理解，含字幕/无字幕。

### Benchmark与对比方法
- 对比模型：Qwen2-VL（2B/7B/72B）、Qwen2.5-VL（7B/72B）、InternVideo2-Chat、LLaVA-NeXT-Video、ST-LLM、TG-Vid、LLaVA-OneVision、VideoLLaMA2、LLaVA-Video、GPT-4o、VideoRoPE等。
- 评估指标：准确率（Acc）。

### 实验组数
- 零样本/上下文学习实验（表1、2）。
- SSv2全数据集动作识别（表2）。
- SSv2-VSM相似性匹配（表3）。
- 多个基准测试（表4）。
- 消融实验：
  - 注意力顺序与头数（表6）。
  - 时间注意力块数量与位置（表7）。
  - STA对InternVideo2-Chat的增强（表8）。
  - 更多扩展模型（表12，包含STAVEQ2.5、VideoRoPE+STA、InternVideo2.5-Chat+STA）。
- 提示工程实验（附录F，表10、11）。
- 注意力可视化（附录G）。

## 4. 资源与算力

论文明确说明：**实验使用64块NVIDIA A100 GPU**，但未详细说明具体训练时长或总GPU小时数。训练过程采用两阶段策略，第一阶段只训练新增的时间注意力块，第二阶段加入LoRA。

## 5. 实验数量与充分性

论文进行了**大量实验**，覆盖多种设置：
- 零样本、少样本对比。
- 在多个标准benchmark上对比多个SOTA模型。
- 针对性的消融研究（注意力结构和位置）。
- 跨模型家族验证通用性（Qwen2-VL、Qwen2.5-VL、VideoRoPE、InternVideo2.5-Chat）。
- 可视化分析（注意力图）。

实验设计较为充分，对比方法选择合理，消融实验覆盖了关键设计维度。但部分实验（如消融）仅在SSv2-T10上进行，未在所有benchmark上重复；且缺少误差棒或统计显著性报告。总体而言，实验**客观、公平**，但统计严谨性可进一步提升。

## 6. 主要结论与发现

1. 现有Video-LLM在时间上存在根本缺陷，即使在提供上下文示例或微调后，仍难以区分方向性动作。
2. 在视觉编码器中引入堆叠时间注意力（STA）显著提升了时间推理能力。
3. STA在多个benchmark上超越现有SOTA：
   - SSv2全数据集：InternVideo2 1B+STA达到78.0%，超过InternVideo2 6B（77.5%）。
   - VITATECS、MVBench、Video-MME上，STAVEQ2各尺寸均优于Qwen2-VL和Qwen2.5-VL。
4. STA能有效增强其他架构（InternVideo2-Chat、VideoRoPE、InternVideo2.5-Chat），证明其通用性。
5. 时间建模放在编码阶段比依赖LLM更为有效。

## 7. 优点

- **方法创新**：首次在Video-LLM的视觉编码器中高效集成专用时间注意力模块，而非依赖LLM处理时间信息。
- **参数高效**：使用较少注意力头和LoRA，在保持较低计算开销的同时提升性能。
- **广泛验证**：在多个基准、多种模型家族、不同规模上均验证了有效性。
- **诊断性工作**：通过精细化子集（SSv2-T10）和可视化，深入揭示了现有模型的缺陷。
- **开源开放**：提供了项目页面和代码。

## 8. 不足与局限

- **资源限制**：未进行大规模预训练或从头训练，仅基于现有模型微调。
- **模型规模局限**：仅实验到72B参数规模，更大模型（如100B+）的效果未知。
- **统计显著性缺失**：未报告误差棒或重复实验，结果可能受随机因素影响。
- **实验覆盖**：部分消融实验仅在一个数据集上进行，泛化性有待进一步验证。
- **应用场景**：主要针对短时动作识别和时间方向判断，对于长视频、多事件复杂推理的适用性仍需探索。

（完）
