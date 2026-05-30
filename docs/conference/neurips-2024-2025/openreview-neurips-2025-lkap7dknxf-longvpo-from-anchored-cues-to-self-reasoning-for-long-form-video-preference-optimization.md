---
title: "LongVPO: From Anchored Cues to Self-Reasoning for Long-Form Video Preference Optimization"
title_zh: LongVPO：从锚定线索到自推理的长视频偏好优化
authors: "Zhenpeng Huang, Jiaqi Li, Zihan Jia, Xinhao Li, Desen Meng, Lingxue Song, Xi Chen, Liang Li, Limin Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=LKAp7Dknxf"
tags: ["query:long-video"]
score: 9.0
evidence: 使短上下文视觉语言模型能够理解超长视频以回答提问
tldr: 长视频理解面临标注成本高和上下文窗口限制的问题。本文提出LongVPO两阶段框架，第一阶段通过锚定线索合成偏好三元组并过滤以消除位置偏差，第二阶段递归生成场景级元数据并利用大语言模型推理。该方法使短上下文视觉语言模型无需长视频标注即可理解超长视频，实验显示在多个长视频基准上显著优于基线，为高效长视频理解提供了可扩展的方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 588, \"height\": 161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 594, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1281, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 584, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 597, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1162, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1450, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1461, \"height\": 1033, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1440, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1437, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1441, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1435, \"height\": 139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lkap7dknxf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1440, \"height\": 408, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-lkap7dknxf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 1212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lkap7dknxf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1172, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lkap7dknxf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1321, \"height\": 438, \"label\": \"Table\"}]"
motivation: 短上下文视觉语言模型难以理解超长视频，且缺乏长视频标注数据。
method: 提出两阶段偏好优化框架，合成偏好三元组并递归生成场景字幕。
result: 无需长视频标注即实现超长视频理解，在多个基准上显著提升。
conclusion: LongVPO为长视频理解提供了一种无需标注的高效方案。
---

## Abstract
We present LongVPO, a novel two‑stage Direct Preference Optimization framework that enables short‑context vision‑language models to robustly understand ultra‑long videos without any long‑video annotations. In Stage 1, we synthesize preference triples by anchoring questions to individual short clips, interleaving them with distractors, and applying visual‑similarity and question‑specificity filtering to mitigate positional bias and ensure unambiguous supervision. We also approximate the reference model’s scoring over long contexts by evaluating only the anchor clip, reducing computational overhead. In Stage 2, we employ a recursive captioning pipeline on long videos to generate scene-level metadata, and then use a large language model to craft multi-segment reasoning queries and dispreferred responses, aligning the model's preferences through multi-segment reasoning tasks. With only 16K synthetic examples and no costly human labels, \model{} outperforms the state‑of‑the‑art open‑source models on multiple long‑video benchmarks, while maintaining strong short‑video performance (e.g., on MVBench), offering a scalable paradigm for efficient long‑form video understanding.

---

## 论文详细总结（自动生成）

# 论文总结：LongVPO: From Anchored Cues to Self-Reasoning for Long-Form Video Preference Optimization

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的短上下文视觉语言模型（VLM）在理解超长视频（如超过1小时）时性能严重下降，主要面临两大挑战：（1）长视频标注成本极高、难以获取；（2）短上下文VLM在扩展上下文长度时出现“lost-in-the-middle”位置偏差，导致对位于中间位置的视觉内容理解不足。
- **研究动机**：尽管短上下文VLM仅用有限帧训练，但在长视频基准上已展现出一定潜力。本文旨在探索如何在不依赖昂贵长视频标注的前提下，有效扩展短上下文VLM的能力，使其能够稳健理解超长视频。
- **整体贡献**：提出一个两阶段直接偏好优化（DPO）框架LongVPO，仅使用约1.6万合成样本，无需任何长视频人工标注，即可使短上下文VLM在多个长视频基准上达到最先进水平，同时保持短视频性能。

## 2. 论文提出的方法论

### 核心思想
采用两阶段渐进式训练：第一阶段通过锚定短片段合成伪长视频，训练模型在长上下文中定位关键信息；第二阶段利用真实长视频的场景级元数据和LLM生成的推理查询，训练模型进行跨片段推理与偏好对齐。

### 关键技术细节

#### 第一阶段：基于锚定线索的高效短到长学习（Efficient Short-to-Long Learning from Anchored Cues）
- **锚定QA生成**：从SFT数据中随机选择一段短片段作为锚定片段，由目标VLM生成仅依赖该片段可回答的问答对（锚定查询 \(q_i\) 和偏好响应 \(y_i^+\)）。
- **复合序列组装**：将多个不同短片段（包括锚定片段）拼接成伪长视频 \(x_i = [x_{i,1}, ..., x_{i,anchor}, ..., x_{i,k}]\)。
- **非偏好响应生成**：通过提示模型从非锚定片段（干扰片段）中获取信息，生成看似合理但错误的非偏好响应 \(y_i^-\)，模拟时间定位错误。
- **后过滤机制**：
  - **场景相似性过滤**：移除或替换与锚定片段DINOv2嵌入余弦相似度超过阈值（0.6）的非锚定片段，确保信息唯一性。
  - **问题特异性过滤**：使用外部LLM验证查询是否依赖锚定片段中的多个不同视觉元素，剔除可被其他片段回答的模糊问题。
- **锚定近似参考模型**：由于短上下文参考模型 \(\pi_{\text{ref}}\) 在长上下文中退化，作者提出仅使用锚定片段 \(x_{i,anchor}\) 来近似参考模型的似然：\(\pi_{\text{ref}}(y|x_i) \approx \pi_{\text{ref}}(y|x_{i,anchor})\)，从而规避上下文长度不匹配并降低计算开销。
- **目标函数**：结合DPO损失和SFT损失：
  \[
  \mathcal{L}_{\text{stage1}}(\theta) = -\sum_i \log \sigma\left( \beta \left[ \log \frac{\pi_\theta(y_i^+|x_i)}{\pi_{\text{ref}}(y_i^+|x_{i,anchor})} - \log \frac{\pi_\theta(y_i^-|x_i)}{\pi_{\text{ref}}(y_i^-|x_{i,anchor})} \right] \right)
  \]
  并加入SFT项：\(\mathcal{L}(\theta) = \mathcal{L}_{\text{stage}i}(\theta) + \alpha \cdot (-\log \pi_\theta(y^+|x) / |y^+|)\)。

#### 第二阶段：面向长视频偏好对齐的自训练（Self-Training for Long Video Preference Alignment）
- **数据准备**：对真实长视频进行场景分割，采用递归字幕生成策略——模型基于当前视频片段和先前场景字幕生成连贯的上下文感知字幕序列。
- **偏好数据构建**：
  - **长上下文知识迁移**：使用LLM（Qwen2.5-32B）根据场景ID和字幕生成查询 \(q_i\) 和推理链 \(r_i\)（明确引用场景ID作为相关性标签）。
  - **偏好响应 \(y_i^+\)**：目标MLLM基于完整长视频 \(x_i\) 和查询生成回答。
  - **非偏好响应 \(y_i^-\)**：通过两种退化策略生成——（1）仅提供部分相关场景（部分证据）；（2）仅提供不相关场景（无关幻觉）。
- **训练**：使用标准DPO目标，策略模型初始化为第一阶段检查点，参考模型冻结为第一阶段检查点。

## 3. 实验设计

### 使用的数据集/场景
- **训练数据**：
  - 第一阶段：LLaVA-Video-178K数据集中的字幕标注，从中选取短片段。
  - 第二阶段：Vript数据集中的场景分割但未标注的长视频。
  - 总计约1.6万训练样本（第一阶段1万，第二阶段6k）。
- **测试基准**：
  - **长视频基准**：LVBench（平均时长4101秒）、LongVideoBench（473秒）、MLVU（651秒）、Video-MME（1010秒，含with/without subtitle两种设置）。
  - **短视频基准**：MVBench（16秒）。

### 对比方法
- **闭源模型**：GPT4-V、GPT4-o、Gemini-1.5-Pro。
- **开源多图像VLM**：LLaVA-OneVision、InternVL2、Oryx-1.5、MiniCPM-v2.6、mPLUG-Owl3、Qwen2-VL、NVILA等。
- **开源视频语言模型**：VideoLLaMA2、LLaVA-Video、Video-XL、Video-CCAM、Kangaroo、LongVU、LongVA、LongVILA、VideoChat-Flash、InternVL2.5、InternVideo2.5等。

### 基准模型
- 主要基线：InternVL2.5-8B（短上下文模型，训练时最多32帧）。
- 扩展实验：InternVideo2.5-8B（专为长视频设计的模型，支持256帧训练）。

## 4. 资源与算力

- **硬件**：4×8 NVIDIA H100 GPU（每个80GB显存）。
- **训练策略**：使用DeepSpeed Ulysses序列并行实现内存高效训练；全模型端到端微调（包括视觉编码器、V-L连接器、LLM骨干）。
- **超参数**：模型共16k样本，每个变体训练1个epoch；学习率5e-7，批次大小8，余弦学习率调度，warm-up比例0.01；复合损失权重 \(\beta=0.01, \alpha=1.0\)。
- **训练时长**：启用序列并行时约10小时，否则约1小时（在4×8 H100配置下）。

## 5. 实验数量与充分性

- **主要结果表（Table 1）**：在5个长/短视频基准上比较了多种模型，并展示了LongVPO在128f、256f、512f不同帧数设置下的性能，以及基于InternVL2.5和InternVideo2.5的实验。
- **消融实验（Table 2）**：
  - 第一阶段：场景过滤 vs 无过滤（添加相似片段或TopK选择）。
  - 第二阶段：偏好响应生成方式（自生成 vs LLM生成 vs 场景交错字幕）；知识迁移骨干（InternLM2.5-7B vs Qwen2.5-32B）。
- **其他分析**：
  - 图4：V-NIAH测试（长视频上下文“针”检索任务），对比基线模型与LongVPO。
  - 图5：第一阶段SFT vs DPO训练策略对比。
  - 图6：输入帧数扩展性分析（32K、64K、128K上下文窗口）。
  - 图7：定性案例分析（南瓜雕刻动作计数）。
  - 附录Table 3：额外在Qwen2.5-VL、Video-LLaMA3等模型上验证泛化性。
- **充分性评价**：实验覆盖了多个主流长视频基准和短视频基准，消融实验覆盖了核心设计选择（过滤、响应生成方式、骨干模型），并提供了扩展性分析和泛化性验证。实验设计较为全面和客观。但未报告多次运行的标准差或统计显著性检验，且实验数量相对有限（仅1 epoch），可能受计算资源限制。

## 6. 论文的主要结论与发现

- **核心发现**：LongVPO仅用约1.6万合成样本，无需任何长视频标注，即可显著提升短上下文VLM在长视频理解任务上的性能，同时在短视频基准上保持甚至略微提升（MVBench +1.1%）。
- **阶段有效性**：
  - 第一阶段有效缓解了位置偏差，激活了模型在长上下文中定位关键片段的能力。
  - 第二阶段通过真实长视频的跨场景推理训练进一步提升了性能。
- **扩展性**：随着输入帧数增加（128→256→512），LongVPO性能持续提升，而基线模型趋于饱和，表明LongVPO能更有效利用长时序信息。
- **泛化性**：方法同样适用于已有长视频预训练的模型（如InternVideo2.5），并能继续提升其性能。
- **效率优势**：相比依赖人工标注或闭源模型的数据构建方法，LongVPO的数据合成策略更高效且可扩展。

## 7. 优点

- **创新性**：首次提出两阶段DPO框架，从合成伪长视频逐步过渡到真实长视频，有效解决短上下文VLM向长视频扩展时的分布偏移问题。
- **数据高效**：仅需16k合成样本，无需人工标注，大幅降低数据成本。
- **性能优异**：在多个长视频基准上超越所有同等规模开源模型，甚至优于部分训练数据更大的模型。
- **保持短视频能力**：在提升长视频理解的同时未损害甚至提升了短视频性能，体现通用性。
- **技术细节稳健**：锚定近似参考模型解决了上下文长度不匹配问题；场景相似性过滤和问题特异性过滤保证了偏好信号的质量。
- **可扩展性**：方法可应用于不同基础模型（InternVL2.5、InternVideo2.5、Qwen2.5-VL、Video-LLaMA3），且随训练帧数增加性能持续提升。

## 8. 不足与局限

- **计算效率**：论文明确提到“优先考虑性能提升而非推理计算效率”，未采用上下文压缩技术，推理时需处理大量视频帧，计算成本较高。
- **实验局限**：未报告多次运行的标准差或统计显著性检验，结果可能受随机性影响；训练仅1个epoch，可能未充分收敛；消融实验仅针对部分关键设计，未涵盖所有超参数选择。
- **数据依赖**：虽然无需长视频标注，但依赖已有的短视频SFT数据和场景分割数据集（Vript），后者可能限制泛化到无场景分割的视频。
- **合成数据偏差**：第一阶段使用伪长视频（随机拼接短片段），缺乏真实长视频的叙事连贯性和因果结构，可能造成分布偏差；第二阶段的偏好数据依赖于LLM生成的推理链和退化策略，可能引入LLM自身的偏差。
- **评估覆盖**：主要评估面向英文视频问答基准，未涉及多语言、开放域对话或视频生成等任务；定性案例有限（仅个别示例）。
- **应用限制**：当前方法未考虑视频中的音频信息，仅处理视觉模态；对于极端长时间（数小时）视频的扩展性未充分验证。
- **可重复性**：代码和数据集声称在接收后开放，但当前未提供，可能影响结果复现。

（完）
