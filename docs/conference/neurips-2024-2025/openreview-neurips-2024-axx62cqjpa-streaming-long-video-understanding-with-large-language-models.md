---
title: Streaming Long Video Understanding with Large Language Models
title_zh: 基于大语言模型的流式长视频理解
authors: "Rui Qian, Xiaoyi Dong, Pan Zhang, Yuhang Zang, Shuangrui Ding, Dahua Lin, Jiaqi Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=axX62CQJpa"
tags: ["query:long-video"]
score: 10.0
evidence: 流式长视频理解，采用记忆传播编码
tldr: 针对长视频处理中令牌数量过多导致计算负担沉重的问题，本文提出VideoStreaming模型，核心设计包括记忆传播流式编码和自适应令牌选择，以常数令牌数处理任意长度视频。在多个长视频理解基准上，该方法以更低的计算量取得了领先的性能，证明了流式编码和动态选择机制在长视频理解中的有效性。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 802, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 540, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 491, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 699, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1365, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-axx62cqjpa/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 529, \"height\": 276, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 507, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 931, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 573, \"height\": 544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 838, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 731, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1277, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 837, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 604, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1215, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 939, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 914, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 675, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1266, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1226, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-axx62cqjpa/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 996, \"height\": 375, \"label\": \"Table\"}]"
motivation: 长视频处理中令牌数量过多导致计算负担，现有稀疏采样或帧压缩方法损失时空信息。
method: 提出记忆传播流式编码和自适应令牌选择两大核心设计，实现常数级令牌数视频表示。
result: 在多个长视频基准上以更低计算量达到领先性能，验证了方法有效性。
conclusion: 流式编码和动态令牌选择是高效长视频理解的关键方向。
---

## Abstract
This paper presents VideoStreaming, an advanced vision-language large model (VLLM) for video understanding, that capably understands arbitrary-length video with a constant number of video tokens streamingly encoded and adaptively selected.
The challenge of video understanding in the vision language area mainly lies in the significant computational burden caused by the great number of tokens extracted from long videos. Previous works rely on sparse sampling or frame compression to reduce tokens. However, such approaches either disregard temporal information in a long time span or sacrifice spatial details, resulting in flawed compression. 
To address these limitations, our VideoStreaming has two core designs: Memory-Propagated Streaming Encoding and Adaptive Memory Selection. The Memory-Propagated Streaming Encoding architecture segments long videos into short clips and sequentially encodes each clip with a propagated memory. In each iteration, we utilize the encoded results of the preceding clip as historical memory, which is integrated with the current clip to distill a condensed representation that encapsulates the video content up to the current timestamp. This method not only incorporates long-term temporal dynamics into the streaming encoding process but also yields a fixed-length memory as a global representation for arbitrarily long videos. After the encoding process, the Adaptive Memory Selection strategy selects a constant number of question-related memories from all the historical memories, and feeds them into the LLM to generate informative responses. The question-related selection reduces redundancy within the memories, enabling efficient and precise video understanding. Meanwhile, the disentangled video extraction and reasoning design allows the LLM to answer different questions about a video by directly selecting corresponding memories, without the need to encode the whole video for each question. Through extensive experiments, our model achieves superior performance and higher efficiency on long video benchmarks, showcasing precise temporal comprehension for detailed question answering.

---

## 论文详细总结（自动生成）

# 论文《Streaming Long Video Understanding with Large Language Models》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：长视频理解面临巨大的计算负担。将长视频中的大量视觉令牌（tokens）输入大语言模型（LLM）不仅会急剧增加计算需求，还可能导致早期上下文信息丢失。
*   **现有方法的不足**：先前的工作通常采用稀疏采样或帧压缩来减少令牌数量，但这些方法要么忽略长时间跨度内的时序信息，要么牺牲空间细节，导致压缩效果不佳。例如，LLaMA-VID 将每帧压缩为两个令牌，但忽略了帧间时序动态；记忆库方法依赖明确的时间戳来回忆历史细节，限制了无特定时间指示时的综合响应能力。
*   **研究动机**：旨在设计一种能够以常数数量的视频令牌流式编码并自适应选择的方式理解任意长度视频的视觉-语言大模型，从而在保持高效的同时实现精确的时序理解。

## 2. 论文提出的方法论：核心思想、关键技术细节

*   **核心思想**：通过记忆传播流式编码（Memory-Propagated Streaming Encoding）和自适应记忆选择（Adaptive Memory Selection）两大设计，将长视频分割为短片段并顺序编码，利用传播的记忆保留长时间动态，并根据问题自适应选择相关记忆输入LLM生成响应。
*   **关键技术细节**：
    *   **单片段编码（Single Clip Encoding）**：使用一个小型语言模型（Phi-2 2.7B）作为编码器。输入一个T帧的视频片段，首先用预训练的CLIP ViT-L提取帧级特征，并通过相邻令牌合并减少令牌数（每帧得到64个令牌）。同时初始化一组汇总令牌（summarization tokens），其数量远少于视觉令牌。将视觉特征与汇总令牌拼接后输入编码器（含MLP投影器和Phi-2），利用自回归性质使信息积累到最后的汇总令牌上，输出该片段的压缩表示（condensed representation）。
    *   **前缀任务（Prefix Task）**：训练编码器时，通过修改注意力掩码，使得语言模型在生成文本响应时只能从汇总令牌中获取视频信息，从而迫使汇总令牌提取更全面的视频内容。
    *   **记忆传播流式编码**：将长视频划分为K个片段（每片段T帧），顺序编码。在每个迭代中，将前一片段的编码结果作为历史记忆（H_{k-1}），与当前片段特征、汇总令牌以及一个全局令牌（clip indicator）一起输入流式编码器，生成当前片段的压缩表示H_k和片段指示符Ĥ_k。这样，H_k不仅包含当前片段信息，还封装了截至当前时间戳的整个视频内容，从而以固定长度记忆表示任意长度视频。
    *   **时间提示（Time Prompt）**：在流式编码过程中加入显式的时间戳文本提示（如“此片段采样于xx到xx秒”），增强时序感知能力。
    *   **自适应记忆选择**：存储所有历史片段的记忆{H_1,...,H_K}。给定一个问题，将最终迭代的全局记忆H_K与问题文本拼接后通过同一小语言模型，取最后一个令牌作为问题指示符Ĥ_Q。计算Ĥ_Q与所有片段指示符{Ĥ_1,...,Ĥ_K}的余弦相似度，并使用Gumbel-Topk技术选择V个最相关的片段（V为常数，文中默认V=4）。将选中的记忆按时序拼接后输入LLM（Vicuna-7B）生成最终响应。这样，不同问题只需一次视频编码即可通过选择相应记忆来回答，避免为每个问题重新编码整个视频。
*   **训练策略**：采用两阶段渐进式训练。第一阶段：使用图像和短视频数据训练单片段编码能力（包括MLP投影器和Phi-2）。第二阶段：使用长视频QA数据联合训练ViT、流式编码器和LLM（Vicuna-7B）。其中，长视频QA数据来源于已有电影QA、从Panda-70M构造的多轮长视频QA对以及将短视频拼接合成得到的长视频QA数据。

## 3. 实验设计：数据集、基准、对比方法

*   **数据集**：
    *   **Next-QA**：42.23秒平均时长，5K个选择题。
    *   **Next-GQA**：39.60秒，带时序定位标注。
    *   **VideoChatGPT**：1.81分钟，评估五个维度（CI、DO、CU、TU、CO）。
    *   **EgoSchema**：3分钟，5K个选择题。
    *   **MovieChat-1K**：7.66分钟，包括全局模式和断点模式。
    *   **MovieNet-QA**：108.26分钟（小时级），评估概述、情节、时序理解。
    *   **IntentQA**：长视频理解，包括Why、How、Before/After三类问题。
*   **基准与对比方法**：
    *   **VideoChatGPT**：对比Video-LLaMA、VideoChat、VideoChatGPT、MovieChat、LongVLM、LLaMA-VID、PLLaVA等。
    *   **EgoSchema**：对比MC-ViT、InternVideo、FrozenBiLM、SeViLA、LLoVi、Vamos、LangRepo等。
    *   **Next-QA**：对比BLIP-2、LLaMA-VQA、Vamos、InternVideo、SeViLA、Mistral、LLoVi、LangRepo等。
    *   **Next-GQA**：对比TempCLIP、SeViLA、LLoVi、LangRepo等。
    *   **MovieChat-1K**：对比VideoChat、Video-LLaMA、VideoChatGPT、MovieChat、MovieChat+。
    *   **MovieNet-QA**：对比LLaMA-VID、MovieLLM（包括使用文本和纯视觉两种设置）。
    *   **IntentQA**：对比LLaMA-VID、LLoVi、LangRepo。

## 4. 资源与算力

*   **算力使用**：在32张A100 (80G) GPU上训练约2.5天。具体训练配置：第一阶段在1个epoch内使用256 batchsize训练MLP，随后使用128 batchsize训练Phi-2和MLP；第二阶段使用128 batchsize微调整个架构（ViT、流式编码器、LLM）。

## 5. 实验数量与充分性

*   **实验数量**：论文在**7个长视频基准**（VideoChatGPT, EgoSchema, Next-QA, Next-GQA, MovieChat-1K, MovieNet-QA, IntentQA）上进行了评估，并提供了大量消融实验（约12组以上），包括：
    *   记忆传播和记忆选择的效果（表8）
    *   采样策略（clip vs frame，表9）
    *   编码器架构（不同层数、与MC-ViT对比，表10）
    *   时间提示的影响（表14）
    *   相似度测量方法（表15）
    *   汇总令牌数量和选择时间戳数量（表13）
    *   时序监督信号的使用（表12）
    *   在小时级MovieNet-QA上的更多消融（表16）
*   **充分性**：消融实验覆盖了核心设计（记忆传播、自适应选择、时间提示、编码器层数、令牌数量等），并使用了多个不同长度和任务类型的数据集，对比了多种强基线方法。实验设计较为全面，结果客观，且展示了统计上的优势（如选中的时间戳与真实标签接近，图4）。但未提供误差棒（由于计算成本），这一点在论文中已注明。

## 6. 论文的主要结论与发现

*   **主要结论**：提出的VideoStreaming在多个长视频理解基准上以显著更少的令牌输入（例如仅256个令牌）和更低的推理延迟（MovieNet-QA上5.32秒/问题，而LLaMA-VID需10.47秒）达到了领先性能，尤其在时序理解方面表现突出。
*   **关键发现**：
    *   记忆传播流式编码显著提升了全局理解能力，因为历史记忆允许每个片段的编码包含之前内容，形成完整的视频摘要。
    *   自适应记忆选择对于断点模式（特定时刻的详细问题）至关重要，选中的时间戳与真实标签高度吻合。
    *   使用语言模型作为流式编码器优于传统的ViT-based记忆方法（如MC-ViT），因为可端到端训练且与后续LLM更易对齐。
    *   使用较浅层（前16层）的Phi-2作为编码器比使用全部层更优，因为深层特征空间可能更针对语言生成而非视觉压缩。

## 7. 优点：方法或实验设计上的亮点

*   **方法亮点**：
    *   **流式编码机制**：通过顺序处理片段并传播历史记忆，以固定长度表示任意长视频，避免了冗余重编码。
    *   **自适应记忆选择**：基于问题动态选择相关片段，实现“解耦的视频提取与推理”，不同问题只需一次编码。
    *   **利用语言模型进行视觉浓缩**：将文本生成任务的自回归特性迁移到视觉信息聚合，并通过修改注意力掩码的前缀任务强化压缩能力。
    *   **时间提示融合**：显式加入时间戳提示，增强模型的时序感知。
*   **实验设计亮点**：
    *   在多个不同长度（秒级到小时级）和不同任务类型（全局描述、时刻定位、选择题）的数据集上全面评估。
    *   消融实验系统性地验证了每个组件的贡献，包括记忆传播、选择策略、编码器层数等。
    *   在Next-GQA上同时评估了响应正确性和时序定位精度（IoP、IoU、Acc@GQA），展示了综合能力。
    *   将推理效率和令牌数量纳入对比（表7），突出了实际应用优势。

## 8. 不足与局限

*   **采样策略局限**：论文提到统一均匀采样形成片段，但视频不同片段信息量差异大，可能导致冗余或信息不足。计划探索自适应分割。
*   **对文本辅助的依赖**：在MovieNet-QA上，纯视觉设置下性能虽好但仍有提升空间；依赖文本（字幕）的方法（如LLaMA-VID）在加入文本后表现更优。
*   **时序监督依赖**：自适应记忆选择需要一定数量的伪时序标签进行预热训练，若无这些标签，定位精度会下降，但整体QA准确率仍稳定（表12）。
*   **计算资源要求**：模型总参数量为8.3B（7B Vicuna + 1.3B Phi-2部分层），训练需32×A100 GPU约2.5天，对大范围部署仍有门槛。
*   **潜在偏差与风险**：论文在“Impact Statements”中提及，该技术可能被用于未经授权的监控或生成误导性内容，需考虑伦理和社会影响。此外，实验未提供误差棒，统计显著性未明确。
*   **局限性总结**：主要局限在于均匀采样导致的信息不匹配，以及时序监督的获取成本。未来工作可探索自适应分段或更灵活的采样策略。

（完）
