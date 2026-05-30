---
title: Universal Video Temporal Grounding with Generative Multi-modal Large Language Models
title_zh: 基于生成式多模态大语言模型的通用视频时间定位
authors: "Zeqian Li, Shangzhe Di, Zhonghua Zhai, Weilin Huang, Yanfeng Wang, Weidi Xie"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FS3FzdrFZ7"
tags: ["query:long-video"]
score: 6.0
evidence: 通过多模态大语言模型实现通用视频时间定位，属于长视频分析方法
tldr: 该论文针对现有视频时间定位方法受限于特定领域或时长的问题，提出了UniTime模型，利用生成式多模态大语言模型实现通用视频时间定位。该模型能处理不同视角、类型和长度的视频，并理解复杂语言查询。通过将MLLM的能力扩展至时间边界预测，在多个基准上取得了先进结果，为长视频问答和分析提供了新的技术手段。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 895, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 489, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 492, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1312, \"height\": 1910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1119, \"height\": 422, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 692, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 725, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 693, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 699, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 694, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 702, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1302, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1294, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 472, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 443, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fs3fzdrfz7/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 440, \"height\": 183, \"label\": \"Table\"}]"
motivation: 现有视频时间定位方法受限于领域和时长，缺乏通用性。
method: 利用生成式MLLM进行视频时间定位，输出精确时间戳，处理多样视频和复杂查询。
result: 在多个视频定位基准上，UniTime实现跨领域、跨时长的最先进性能。
conclusion: 生成式MLLM可有效统一视频时间定位任务，具备良好泛化性。
---

## Abstract
This paper presents a computational model for universal video temporal grounding, which accurately localizes temporal moments in videos based on natural language queries (e.g., questions or descriptions). 
Unlike existing methods that are often limited to specific video domains or durations, we propose **UniTime**, a robust and universal video grounding model leveraging the strong vision-language understanding capabilities of generative Multi-modal Large Language Models (MLLMs).
Our model effectively handles videos of diverse views, genres, and lengths while comprehending complex language queries.
The key contributions include:
(i) We consider steering strong MLLMs for temporal grounding in videos. To enable precise timestamp outputs, we incorporate temporal information by interleaving timestamp tokens with video tokens.
(ii) By training the model to handle videos with different input granularities through adaptive frame scaling, our approach achieves robust temporal grounding for both short and long videos.
(iii) Comprehensive experiments show that UniTime outperforms state-of-the-art approaches in both zero-shot and dataset-specific finetuned settings across five public temporal grounding benchmarks.
(iv) When employed as a preliminary moment retriever for long-form video question-answering (VideoQA), UniTime significantly improves VideoQA accuracy, highlighting its value for complex video understanding tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有视频时间定位方法通常受限于特定视频领域或时长（如仅处理短片段或特定视角），难以泛化到真实世界中多样的视频数据（不同视角、主题、时长）。同时，现有方法在长视频理解中需要先定位相关片段再推理，但定位阶段往往表现不佳。
- **整体含义**：本文旨在开发一个**通用视频时间定位模型**，能够处理任意时长、视角、主题的视频，并理解复杂的自然语言查询（描述、问题、步骤等），为后续的细粒度视频理解和视频问答提供坚实基础。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用强大的生成式多模态大语言模型（MLLM）来实现通用时间定位，通过将时间戳标记显式插入视频标记序列中，让MLLM直接“读出”目标时间戳，而非传统的位置编码回归。
- **关键技术细节**：
  - **自适应帧缩放（Adaptive Frame Scaling）**：根据视频时长动态调整每帧分配的令牌预算（$N_{\text{res}}$）。短视频使用高空间分辨率（图像缩放），长视频使用令牌压缩（双线性插值压缩令牌数），在令牌预算固定下最大化信息保留。
  - **时间戳交错的序列构建（Timestamp-Interleaved Sequence）**：将时间戳作为文本标记插入视频帧或片段之前，构成交错序列输入LLM。支持两种粒度：细粒度（每一帧前插时间戳）和粗粒度（每个固定长度片段前插时间戳）。
  - **多阶段推理（Multi-stage Inference）**：对长视频，先粗粒度检索相关片段，再在片段内细粒度定位时间边界；短视频则单阶段完成。该过程可递归。
  - **视频中心训练（Video-centric Training）**：一次加载视频的所有查询-答案对，通过修改注意力掩码避免交叉干扰，大幅减少I/O和重复编码的计算开销。
- **损失函数**：自回归负对数似然，仅对目标令牌计算。
- **算法流程简述**：
  1. 根据视频帧数$N_f$和阈值$N_{\text{short}}^f$、$N_{\text{long}}^f$选择输入处理方式（缩放或压缩）。
  2. 构建交错序列 $S = [T_1; V_1; T_2; V_2; ...; T_{N_f}; V_{N_f}; Q]$。
  3. 送入冻结视觉编码器+LoRA微调的LLM，输出格式如“From $s_k$ seconds to $e_k$ seconds”。
  4. 若视频超长（$N_f > N_{\text{long}}^f$），分片处理并执行粗到细定位。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **预训练**：INaQ、DiDeMo、QuerYD、HiRest、COIN、Momentor、YouCook2等。
  - **时间定位基准**：Ego4D-NLQ（长视频）、TACoS（长视频）、Charades-STA（短视频）、ANet-Captions（短视频）、QVHighlights（短视频）。
  - **视频问答基准**：QaEgo4D、CG-Bench（带时间戳问答）、MLVU、LongVideoBench（通用问答）。
- **评估设置**：包括零样本（Zero-shot）、数据集特定微调（SP）、通用预训练（Full）三种设置。
- **对比方法**：
  - 传统方法：2D-TAN、VSLNet、RGNet、SnAG、UniVTG等。
  - MLLM方法：Qwen2-VL-7B、Qwen2.5-VL-7B、Mr.BLIP、VTimeLLM、TimeSuite、TimeChat、Momentor等。
  - 闭源模型：Gemini-2.5-flash/pro、GPT-4.1-mini、GPT-4o、Seed1.5-VL。

## 4. 资源与算力

- **硬件与训练配置**：基于PyTorch，使用8卡GPU（具体型号未明确，推测为A100或类似），batch size为8，优化器AdamW，学习率2e-4，训练1个epoch，线性预热3%步数。
- **训练时间**：视视频处理策略而定。使用令牌压缩处理长视频时，训练时间增加约5天（文中提到UniTime-Full使用混合策略，短视频用图像缩放、长视频用令牌压缩）。整体未给出精确总耗时。
- **模型规模**：基座MLLM为Qwen2-VL-7B，视觉编码器冻结，LLM通过LoRA（rank=8, alpha=8）微调。
- **注意**：论文未报告具体GPU型号、总训练时数（如GPU小时），仅提供了相对时间对比。

## 5. 实验数量与充分性

- **实验组数**：非常充分。
  - **主实验**：在5个时间定位基准（零样本/SP/Full三种设置）+ 4个VideoQA基准上评估。
  - **消融实验**：模块消融（自适应缩放、多阶段推理、片段检索）、超参数消融（片段长度、复制因子、令牌预算、阈值$N_{\text{short}}^f$、$N_{\text{long}}^f$）、视频处理策略对比、时间信息编码对比。
  - **鲁棒性测试**：时间偏移（扰动事件位置）、查询分解（分解为对象级问题）。
  - **灵活性验证**：在Qwen2-VL（2B/7B）、Qwen2.5-VL-7B、InternVL2.5（2B/8B）等多种MLLM上验证方法兼容性。
  - **闭源模型对比**：在Ego4D-NLQ和Charades-STA子集上与Gemini、GPT-4o、Seed1.5-VL对比。
  - **一致性评估**：在Charades-CON、ActivityNet-CON上评估重述/移位定位一致性。
- **公平性与客观性**：
  - 对比方法采用其公开代码/检查点，在相同设置下评估。
  - 零样本设置严格剔除目标领域训练数据，避免信息泄漏。
  - 鲁棒性测试揭示了时间分布偏差对方法的影响，并显示UniTime更稳健。
- **总体评价**：实验覆盖全面，控制变量合理，结论可信度高。

## 6. 主要结论与发现

- UniTime在所有时间定位基准（长/短视频）上均取得最先进性能，在零样本、数据集特定微调、通用预训练三种设置下均显著超过以往方法。
- 在VideoQA下游任务中，使用UniTime作为片段检索器可大幅提升长视频问答准确率（如QaEgo4D上mIoU提升约15%）。
- 自适应帧缩放和粗到细多阶段推理是处理长视频的关键设计，缺一不可。
- 显式时间戳交错优于隐式位置编码（如MRoPE），且与多种MLLM架构兼容，具备即插即用特性。
- 模型对时间分布偏移和复杂查询具有较好的鲁棒性，超过其他MLLM方法。
- 视频中心训练范式显著提高训练效率，减少I/O和计算冗余。

## 7. 优点：方法或实验设计上的亮点

- **通用性极强**：统一处理短视频和长视频（几分钟到几小时），覆盖多种视角、主题和查询类型。
- **创新性**：将时间戳作为文本标记显式插入，配合自适应帧缩放，巧妙地利用了MLLM的检索能力，避免了复杂的位置编码设计。
- **效率高**：视频中心训练、LoRA微调、自适应令牌分配，使大规模预训练成为可能。
- **鲁棒性验证充分**：额外测试了时间偏移、查询分解、一致性等维度，证明模型不仅指标高且可靠性好。
- **兼容性**：方法可轻松迁移到不同MLLM上（Qwen系列、InternVL系列），证实其范式通用性。
- **实验设计全面**：设置了多种评估场景（零样本、微调、通用），对比了传统方法和最新MLLM，并公开代码促进复现。

## 8. 不足与局限

- **任务局限**：当前模型仅限时间定位任务，若要扩展到密集视频描述等更复杂的时序任务，需要更多密集时间标注数据。
- **推理能力欠缺**：仅使用时间定位数据集训练，限制了模型的推理和问答能力；作者指出最终目标是将定位、推理、问答统一在单个MLLM中。
- **长视频处理固化**：使用固定片段长度（32帧）分割长视频，缺乏根据视频信息密度动态调整的灵活性。
- **部分基准提升有限**：在ANet-Captions短视频基准上，通用预训练模型性能略低于数据集特定微调（但差距极小），且分析发现该基准存在标注不完整和标签错误问题。
- **资源与算力报告不足**：未详细说明GPU型号和总训练小时数，影响复现和资源评估。
- **未见部署讨论**：未涉及实际应用中的延迟、内存占用等系统级评估。
- **潜在偏差风险**：虽然模型对时间分布偏移鲁棒，但训练数据仍存在分布不均衡（如事件集中在前/后），可能影响极端情况下的泛化。

（完）
