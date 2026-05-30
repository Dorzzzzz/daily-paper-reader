---
title: Unleashing Hour-Scale Video Training for Long Video-Language Understanding
title_zh: 解锁小时级视频训练以实现长视频语言理解
authors: "Jingyang Lin, Jialian Wu, Ximeng Sun, Ze Wang, Jiang Liu, Yusheng Su, Xiaodong Yu, Hao Chen, Jiebo Luo, Zicheng Liu, Emad Barsoum"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2ptM76yNzZ"
tags: ["query:long-video"]
score: 9.0
evidence: 包含问答对的小时级视频指令跟随数据集
tldr: 针对长视频语言理解中高质量标注数据稀缺的问题，本文构建了VideoMarathon数据集，包含约9700小时的长视频和330万问答对，覆盖时空、物体、动作、场景和事件六大主题。实验表明，利用该数据集训练的视频大语言模型在长视频理解基准上表现优异。该数据集为小时级视频理解研究提供了重要资源。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1460, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1347, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1429, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ptm76ynzz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1162, \"height\": 1621, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 972, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 715, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 725, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 775, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 673, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1195, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1014, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 655, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2ptm76ynzz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1089, \"height\": 510, \"label\": \"Table\"}]"
motivation: 长视频训练数据匮乏，尤其是小时级视频的标注数据缺失。
method: 构建包含9700小时长视频和330万问答对的VideoMarathon数据集，覆盖多种主题。
result: 基于该数据集训练的视频模型在长视频理解基准上取得优异性能。
conclusion: 大规模长视频指令数据集的构建可有效推动长视频语言理解研究。
---

## Abstract
Recent long-form video-language understanding benchmarks have driven progress in video large multimodal models (Video-LMMs). However, the scarcity of well-annotated long videos has left the training of hour-long Video-LMMs underexplored. To close this gap, we present VideoMarathon, a large-scale hour-long video instruction-following dataset. This dataset includes around 9,700 hours of long videos sourced from diverse domains, ranging from 3 to 60 minutes per video. Specifically, it contains 3.3M high-quality QA pairs, spanning six fundamental topics: temporality, spatiality, object, action, scene, and event. Compared to existing video instruction datasets, VideoMarathon significantly extends training video durations up to 1 hour, and supports 22 diverse tasks requiring both short- and long-term video comprehension. Building on VideoMarathon, we propose Hour-LLaVA, a powerful and efficient Video-LMM for hour-scale video-language modeling. It enables hour-long video training and inference at 1-FPS sampling by leveraging a memory augmentation module, which adaptively integrates question-relevant and spatiotemporally informative semantics from the cached full video context. In our experiments, Hour-LLaVA achieves the best performance on multiple representative long video-language benchmarks, demonstrating the high quality of the VideoMarathon dataset and the superiority of the Hour-LLaVA model.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：当前视频大语言模型（Video-LMMs）在处理长视频（小时级）时表现不佳，主要原因是**缺乏高质量、长时长的视频指令跟随训练数据**。现有数据集（如LLaVA-Video-178K）视频平均时长不到1分钟，训练视频与测试视频（常超过1小时）之间存在严重长度不匹配，导致模型无法显式学习长程依赖。
- **背景**：长视频理解基准（如LVBench、Video-MME）已推动评测发展，但训练数据匮乏，尤其缺少小时级视频的指令标注。为此，论文提出构建大规模长视频指令跟随数据集**VideoMarathon**，并设计适配的模型**Hour-LLaVA**。

## 2. 方法论：核心思想、关键技术细节
### 2.1 VideoMarathon数据集
- **数据来源**：整合5个公开视频数据集（Panda-70M、Ego4D、ActivityNet、YouCook2、MovieChat-1K），总共约**9,700小时**视频，每条视频时长3~60分钟，共28K个视频。
- **任务分类**：定义22个子任务，覆盖6大主题（时间性、空间性、物体、动作、场景、事件），兼顾短时与长时理解。
- **构建流程**：采用**层次化视频描述**流水线：
  1. 使用**Qwen2VL-7B**生成每个30秒片段的六维度描述（时间、空间、物体、动作、场景、总结）。
  2. 通过**DeepSeek-V3**进行事件分割，生成事件级描述（含起止时间）。
  3. 再用**DeepSeek-V3**生成全局级描述。
  4. 基于这些描述，使用DeepSeek-V3和任务特定提示（含示例）生成**330万条QA对**（包含开放式和多项选择）。

### 2.2 Hour-LLaVA模型
- **核心思想**：通过**记忆增强（MemAug）模块**平衡计算效率与上下文保真度。全视频以1 FPS采样存入**记忆存储库**；仅将约6%的“衰减令牌”（经过时空遗忘机制压缩）送入语言模型，然后通过MemAug模块从存储库中动态检索并整合与问题相关且时空信息丰富的语义。
- **关键技术细节**：
  - **遗忘机制**：空间上随机丢弃3/4令牌，时间上均匀丢弃3/4帧，总压缩比1/16。对于极长/极短视频，设置最大512帧、最小32帧的衰减令牌阈值。
  - **MemAug模块**：由4个Transformer块组成，采用交叉注意力（衰减令牌和问题令牌作为查询，全视频令牌作为键值）和自注意力，并使用1D结构化RoPE保持时空对应。
  - **编码器**：SigLIP视觉编码器 + 两层MLP投影器，空间平均池化至8×8/帧。
  - **LLM解码器**：Qwen2.5-3B-Instruct（3B版）或 Qwen2-7B-Instruct（7B版）。
- **训练三阶段**：
  1. **图像-语言预训练**：3B图像-文本对（LLaVA-OV），仅训练MemAug的Transformer块。
  2. **视频-语言适应**：混合单图、多图、文本、短视频（0.3M来自LLaVA-Video-178K），全参数微调1 epoch。
  3. **视频指令微调**：加入0.7M长视频样本（来自VideoMarathon）以及其他样本，冻结视觉编码器，微调其余部分。

## 3. 实验设计
- **评测基准**：4个主流视频语言基准：
  - **TempCompass**（平均11s）：评估短时时间推理。
  - **LongVideoBench**（平均459s）：评估长视频检索与推理（含字幕）。
  - **Video-MME**（平均1021s）：综合长视频理解（分无/有字幕、短/中/长视频）。
  - **LVBench**（平均4037s）：极端长视频理解（最长超过2小时）。
- **对比方法**：
  - 闭源：GPT-4V、GPT-4o、Gemini 1.5 Flash/Pro。
  - 开源<7B：VILA1.5-3B、Phi-3.5、LongVU-3.2B、InternVL2.5-2B、Apollo-1.5B/3B、LLaVA-OV-SI-3B、LLaVA-Video-3B。
  - 开源7-8B：Video-LLaVA、VideoChat2、ShareGPT4Video、VideoLLaMA2、Video-XL、Kangaroo、LongVA、LongVILA、LongVU、Apollo-7B、LLaVA-OV-SI-7B、LLaVA-Video-7B。
- **评估指标**：多项选择平均准确率（M-Avg），部分报告无/有字幕结果。

## 4. 资源与算力
- **明确说明**：
  - Hour-LLaVA-3B：使用**64块AMD MI250 GPU**训练。
  - Hour-LLaVA-7B：使用**64块AMD MI300X GPU**训练。
  - 总训练Epoch：每阶段均为1 epoch。未报告具体训练时长。
- **备注**：论文未提供单次实验的具体GPU小时数，但给出了硬件配置。

## 5. 实验数量与充分性
- **实验组数**：包括主结果（表2，对比10+方法）、数据集消融（图3，5种混合比例）、遗忘机制消融（表3、表4、图4左中）、MemAug消融（表5、表6）、记忆存储库规模（图4中）、1D RoPE消融（表9）、自由生成任务（表10）、最新模型对比（表11）等，共约**10+组实验**。
- **充分性**：
  - 覆盖短、中、长视频基准，验证泛化能力。
  - 消融实验系统，比较了不同遗忘策略、MemAug有无、压缩比、块数等。
  - 与多种开源方法和闭源方法公平对比，使用相同或类似LLM骨干。
  - 数据集质量有人工评估（330样本，MC准确率78.7%，OE平均分7.81）。
- **客观性**：实验设计合理，控制变量（如数据量匹配），结论有充分数据支撑。

## 6. 主要结论与发现
1. **VideoMarathon**显著优于现有短视频指令数据集，能有效提升长视频理解性能（尤其在LongVideoBench、Video-MME中/长视频子集、LVBench上）。
2. **Hour-LLaVA**在所有四个基准上均取得开源模型最佳结果（3B和7B规模），甚至3B版本超越多数7-8B模型。
3. **MemAug模块**是关键：无论使用何种遗忘策略，添加MemAug均能带来1.4~2.4个点的提升，说明它有效恢复了被压缩的有用信息。
4. **稀疏采样（如64帧）**无法从长视频训练中获益，而Hour-LLaVA的1 FPS全上下文+记忆增强则能有效学习长程依赖。
5. **混合长短视频数据**（3:1比例）达到最佳性能，完全去除短视频数据会导致下降，说明多样性有益。

## 7. 优点
- **数据规模与质量**：首个大规模小时级视频指令数据集（9700小时，3.3M QA），覆盖多种领域，任务分类全面，且有层次化描述和人工验证。
- **模型效率**：通过遗忘机制+MemAug，仅输入约6%令牌，实现与稀疏采样法相当甚至更优的计算效率，同时保留高保真上下文。
- **通用性**：Hour-LLaVA在短、中、长视频基准上均表现优异，且能泛化到超出训练分布（LVBench平均67分钟>训练最大60分钟）。
- **消融详尽**：对空间/时间遗忘策略、压缩比、MemAug块数、存储库规模等均进行了系统分析，结论可靠。
- **开源贡献**：计划公开数据和代码，促进研究可复现。

## 8. 不足与局限
- **评测局限**：长视频理解主要依赖多项选择QA，缺乏对生成式任务（如摘要、开放问答）的全面评估。MLVU-Dev上仅测试了字幕和摘要，但其他基准未覆盖自由生成。
- **数据噪声**：合成数据不可避免存在噪声（如MC准确率78.7%），目前训练未显式处理。
- **缺少音频模态**：忽略讲座、访谈等长视频中关键的音频信息，限制了多模态性能。
- **计算资源要求较高**：尽管模型本身高效，但训练仍需64块高端GPU，可能对小规模研究团队不友好。
- **实验未报告误差棒**：由于训练成本高，未重复多次实验计算方差，稳定性未知。
- **遗忘机制对极长视频的处理**：虽设置了最大512帧的阈值，但若视频超过24小时（如连续监控），仍可能丢失关键信息，且未验证。

由于上一次输出已被截断，以下从中断处“8. 不足与局限”之后继续补全，补充对论文技术细节的深入分析、潜在改进方向及综合评价。

---

## 9. 技术细节的深入分析

### 9.1 遗忘机制与记忆增强的权衡
- **遗忘机制的效率性**：通过空间随机丢弃3/4令牌（保留1/4）和时间均匀丢弃3/4帧（保留1/4），总压缩比1/16，使得仅约6%的原始像素令牌进入语言模型。这显著降低了计算开销，但同时也造成了信息损失。论文通过引入MemAug模块从全分辨率记忆存储库中动态检索缺失信息，形成一个“压缩-检索引擎”的闭环，实现了效率与保真度的平衡。
- **MemAug的设计动机**：作者发现直接对所有帧进行均匀采样（如64帧）会导致模型在训练中无法学习到长程依赖（因为稀疏帧之间的时间跨度太大，难以捕捉连续动作）；而保留全部帧则计算不可行。MemAug的本质是**将视频信息分为两部分**：一部分（衰减令牌）经过强烈压缩后送入LLM进行初步理解，另一部分（全视频令牌）存储在外部存储库中，仅在需要时通过交叉注意力检索。这类似于人类认知中的“工作记忆+长期记忆”协同机制。
- **1D结构化RoPE的作用**：为了避免全视频令牌在MemAug的交叉注意力中丢失时间顺序，论文使用了1D结构化RoPE，为每个令牌赋予全局时间戳，使得模型能够感知事件的时间位置，这对时间性任务（如“事件发生的先后顺序”）至关重要。

### 9.2 层次化描述管线的有效性
- **多粒度描述**：从30秒片段级描述 → 事件级描述（含起止时间） → 全局级描述，构建了一个分层知识库。这种结构使得生成的QA对能够覆盖从细粒度动作（如“在第几秒发生了什么”）到粗粒度情节（如“整个视频的主题是什么”）的多种信息粒度。
- **任务驱动提示**：为22个子任务设计特定的提示模板，包含示例，确保生成的QA多样化且符合任务要求。这比直接让模型自由生成QA更可控，减少了幻觉和重复。

### 9.3 数据混合策略的合理性
- 在训练第三阶段，视频指令微调数据中长视频（来自VideoMarathon）与短视频（来自LLaVA-Video-178K等）的比例为3:1（0.7M长视频样本 vs 约0.3M短视频/图文样本）。实验表明完全去除短视频会导致性能下降（尤其在短时任务上），而过度倾斜长视频也会损害短时能力。最佳比例3:1表明**异构任务间的协同训练**有助于学习通用视频理解能力。

## 10. 与其他工作的潜在关系

- **与LLaVA-OV、LLaVA-Video的关系**：Hour-LLaVA是在LLaVA系列基础上的扩展，继承了其图像-视频联合训练范式，但专门针对长视频问题提出了数据与记忆增强方案。
- **与LongVU、LongVA等长视频模型的关系**：这些模型也关注长视频理解，但通常采用稀疏采样或自适应帧选择方法，而Hour-LLaVA通过全帧记忆存储+动态检索提供了一种不同的思路，在视频长度极端时可能更稳定。
- **与Milvus、FAISS等向量检索的关系**：MemAug模块本质上是一种轻量级的密集检索器，但它不需要外部索引，直接利用Transformer的交叉注意力实现软检索，避免了额外的检索系统开销。

## 11. 对未来研究的启示

1. **多模态扩展**：引入音频模态（如Whisper特征）以及字幕文本，可以进一步提升长视频理解能力，尤其在对话、旁白密集的视频中。
2. **动态遗忘策略**：当前遗忘是固定均匀的，未来可以根据视频内容复杂度（如运动量、场景切换频率）自适应调整压缩比，以在高效与保真之间达到最优。
3. **记忆增强的在线化**：当前MemAug是离线检索所有帧（存储库规模固定），对于流式长视频（如直播），需要设计增量式记忆更新和检索机制。
4. **生成式评测**：建立长视频的自由生成基准（如摘要、问答解释、翻译等），以更全面评估模型能力，避免多项选择造成的评价偏差。
5. **数据自净化**：针对合成数据中的噪声，可以采用自训练或置信度过滤策略，提高训练数据的可靠性。

## 12. 整体评价

本文是长视频理解领域的一项重要贡献，其核心价值在于**首次提供了大规模小时级视频指令数据（VideoMarathon）**，并设计了与之匹配的**高效模型Hour-LLaVA**。论文实验设计严谨、消融充分，结果具有说服力。尽管存在一些局限（如评测侧重于多项选择、缺少音频等），但瑕不掩瑜，该工作为长视频大模型的研究提供了坚实的数据基线与方法范本，对推动视频理解向更复杂、更真实的应用场景迈进具有重要参考意义。

（完）
