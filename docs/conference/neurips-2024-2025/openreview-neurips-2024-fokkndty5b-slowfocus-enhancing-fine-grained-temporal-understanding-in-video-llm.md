---
title: "SlowFocus: Enhancing Fine-grained Temporal Understanding in Video LLM"
title_zh: SlowFocus：增强视频大语言模型的细粒度时间理解
authors: "Ming Nie, Dan Ding, Chunwei Wang, Yuanfan Guo, Jianhua Han, Hang Xu, Li Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=FOkKndty5B"
tags: ["query:long-video"]
score: 8.0
evidence: 视频LLM中的细粒度时间理解
tldr: 当前视频LLM难以同时保持高帧质量与足够帧数，限制了细粒度理解。本文提出SlowFocus机制，在不降低帧级视觉token质量的前提下提高等效采样频率，通过识别关键帧并分配更多token。在长视频理解任务上，SlowFocus显著提升了时序感知能力，使模型能够捕捉到更多细节。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1135, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1137, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1309, \"height\": 170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 1890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1316, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fokkndty5b/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 1728, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 898, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 542, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fokkndty5b/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 354, \"label\": \"Table\"}]"
motivation: 视频LLM无法同时保留高质量帧语义与充分的时间采样帧数。
method: 提出SlowFocus机制，通过识别关键帧提高等效采样频率而不降低帧质量。
result: 在长视频理解任务上显著提升时序细节捕捉能力。
conclusion: 为视频LLM高效处理长视频提供了新的采样策略。
---

## Abstract
Large language models (LLMs) have demonstrated exceptional capabilities in text understanding, which has paved the way for their expansion into video LLMs (Vid-LLMs) to analyze video data. However, current Vid-LLMs struggle to simultaneously retain high-quality frame-level semantic information (i.e., a sufficient number of tokens per frame) and comprehensive video-level temporal information (i.e., an adequate number of sampled frames per video). This limitation hinders the advancement of Vid-LLMs towards fine-grained video understanding. To address this issue, we introduce the SlowFocus mechanism, which significantly enhances the equivalent sampling frequency without compromising the quality of frame-level visual tokens. SlowFocus begins by identifying the query-related temporal segment based on the posed question, then performs dense sampling on this segment to extract local high-frequency features. A multi-frequency mixing attention module is further leveraged to aggregate these local high-frequency details with global low-frequency contexts for enhanced temporal comprehension. Additionally, to tailor Vid-LLMs to this innovative mechanism, we introduce a set of training strategies aimed at bolstering both temporal grounding and detailed temporal reasoning capabilities. Furthermore, we establish FineAction-CGR, a benchmark specifically devised to assess the ability of Vid-LLMs to process fine-grained temporal understanding tasks. Comprehensive experiments demonstrate the superiority of our mechanism across both existing public video understanding benchmarks and our proposed FineAction-CGR.

---

## 论文详细总结（自动生成）

# SlowFocus: 增强视频大语言模型的细粒度时间理解 — 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：当前视频大语言模型（Vid-LLMs）在分析视频数据时面临一个根本性矛盾：在有限的计算资源下，必须在**帧级语义信息**（每帧保留足够多的token）与**视频级时间信息**（每视频采样足够多的帧）之间进行取舍。低采样频率会丢失关键的时间细节，而过度的帧特征压缩则会损害每帧的语义和空间上下文。这种权衡严重限制了Vid-LLMs在细粒度视频理解任务上的性能。

- **研究动机**：人类在回答视频问题时，往往能聚焦于与问题相关的时间片段，获得该片段内的高频时间细节。本文受此启发，提出让模型能够**根据问题定位相关时间段，并在该时间段内进行密集采样**，从而在不牺牲全局信息的前提下提升等效采样频率，实现对视频细粒度时序细节的捕捉。

- **整体含义**：本文提出的SlowFocus机制为视频LLM提供了一种全新的混合频率采样范式，显著增强了模型在时序定位、时序推理等细粒度任务上的能力，同时保持了在粗粒度视频理解基准上的性能。

## 2. 方法论

### 核心思想
SlowFocus的核心是通过两阶段处理实现“慢聚焦”：
1. **相关段落的定位**：利用低频率采样的全局帧，根据用户问题预测出与问题高度相关的时间区间。
2. **混合频率采样与融合**：在该区间内进行高密度采样获取高频局部特征，然后将高频局部细节与低频全局上下文通过多频混合注意力模块进行聚合，最终输入LLM进行精细推理。

### 关键技术细节
- **相关段落定位**：将原始问题转化为时序定位问题，例如“请提供有助于回答如下问题的时间段：<问题>”，利用低频率帧获得的全局token，让LLM输出形如“from <start> to <end>”的离散时间区间。

- **混合频率采样**：在定位出的区间内进行密集采样，动态调整采样间隔以保证从该区间提取固定数量N_H的高频帧（实验中N_H=20）。这些高帧率帧经过视觉编码器和适配器后成为高频视觉token。

- **多频混合注意力（Multiple-frequency Mixing Attention, MMA）**：通过交叉注意力机制，将高频视觉token作为query，低频视觉token作为key/value，让高频特征吸收低频全局上下文信息，实现局部细节与全局背景的融合。公式为：π(h_L, h_H) = softmax(h_H h_L^T / √d) h_L。

- **时间关系建模**：引入一个离散化的时间编码器，将帧的相对位置编码为时间token（大小为N=1000），直接加到对应帧的视觉特征上，以显式建模时序关系。

### 训练策略（三阶段）
- **阶段一：模态对齐**：优化视觉适配器和时间编码器，冻结视觉编码器和LLM。使用图像-文本数据（LCS-558K）和视频-字幕数据（WebVid 2.5M中的232K样本）。
- **阶段二：边界增强**：训练模型理解视频帧序列并提升时序定位能力。使用InternVid-10M-FLT数据集，任务包括密集视频描述和时序定位。训练视觉适配器、时间编码器，并采用LoRA微调LLM。
- **阶段三：SlowFocus适配**：在细粒度字幕和推理任务上训练模型适应SlowFocus机制。使用ActivityNet Captions和FineAction数据集转化成的100K+高质量QA对话。训练时提供真实时间段τ_GT，进行混合频率采样，训练LLM和MMA模块，冻结视觉适配器和编码器。

## 3. 实验设计

### 使用的数据集/场景
- **主要基准**：**FineAction-CGR**（本文构建），基于FineAction数据集，划分为训练集75%、测试集25%。包含四类任务：分段字幕（captioning）、时序定位（temporal grounding）、时序推理（temporal reasoning）、多轮QA。评估指标包括mIoU、R@0.3/0.5/0.7、BLEU、METEOR、ROUGE、CIDEr、GPT-4评估的准确率和分数。
- **粗粒度视频理解基准**：MSVD-QA、MSRVTT-QA、ActivityNet-QA（零样本）；视频生成性能基准（VideoChatGPT提出）。
- **长视频基准**：MovieChat-1K（全局模式和断点模式）、EgoSchema。

### 对比方法
- 对比了FrozenBiLM、VideoLLaMA、LLaMA-Adapter、VideoChat、Video-ChatGPT、LLaMA-VID、VTimeLLM、MovieChat、LLoVi、Vamos、LangRepo等。大部分方法基于Vicuna-7B，部分使用LoRA微调。

## 4. 资源与算力

- 论文中明确说明：**所有实验在8张V100 GPU上进行**。训练分为三个阶段，第一阶段学习率1×10⁻³，第二、三阶段为2×10⁻⁴。LoRA参数r=64, alpha=128。具体训练时长未给出。

## 5. 实验数量与充分性

- **主要实验**：在FineAction-CGR上对比了6种方法，报告了时序定位、时序字幕、时序推理的全部指标。
- **粗粒度基准**：在MSVD-QA等三个QA基准上对比了6-8种方法，并报告了视频生成性能的四个维度（正确性、细节、上下文、时序一致性）。
- **长视频基准**：在MovieChat-1K上对比了4种方法，在EgoSchema上对比了7种方法。
- **消融实验**：
  - 组件分析（低频率、混合频率、时间编码器、MMA、高频率帧数N_H）。
  - 训练阶段消融（单独阶段1、1+2、1+3、1+2+3）。
  - 动态调整采样频率与帧token数的对比（固定总token数下改变频率和每帧token数）。
  - 时间token空间大小N的消融（0.1K, 1K, 10K）。
- 总实验组数：至少包含10组以上对比实验和消融实验。

**充分性评价**：实验设计较为全面，涵盖了细粒度、粗粒度、长视频多种场景，对比方法多样，消融实验覆盖了主要组件和训练策略。但仍存在一些不足（见第8节）。

## 6. 主要结论与发现

1. SlowFocus在FineAction-CGR基准上显著优于所有现有方法：时序定位mIoU达到66.68（第二名LLaMA-VID*仅22.38），时序推理准确率53.10%（第二名仅为24.81）。
2. 在粗粒度QA基准上，SlowFocus与最先进模型性能相当（如MSVD-QA准确率70.1%，MSRVTT-QA 58.3%，ActivityNet-QA 48.4%），证明细粒度增强并未损害粗粒度能力。
3. 在长视频基准MovieChat-1K（全局模式58.6%）、EgoSchema（39.7%）上表现有竞争力，虽未针对长视频专门训练。
4. 消融实验证明：混合频率采样、时间编码器、MMA均带来显著提升。高帧率帧数N_H从10增至20有明显增益，但40时饱和。时间token空间N=1K最优。
5. 三阶段训练缺一不可：单独阶段2虽能提升时序定位（mIoU 51.67），但推理准确率仅20.34；单独阶段3提升推理但定位弱；三者结合达最优。

## 7. 优点

- **方法简洁有效**：SlowFocus直接解决了Vid-LLM中采样频率与帧质量的trade-off问题，思路直观且工程实现友好。
- **新颖的混合频率采样框架**：首次将“先定位、再密集采样”的类人视觉注意机制引入视频LLM，并设计了对应的多频混合注意力模块和离散时间编码器。
- **完备的三阶段训练策略**：逐步从模态对齐到边界增强再到SlowFocus适配，保证了模型的稳定学习和性能提升。
- **贡献了新的基准**：FineAction-CGR专门针对细粒度时序理解任务，弥补了现有基准的不足，推动该方向研究。
- **实验覆盖全面**：在细粒度、粗粒度、长视频三大类基准上均进行了评估，且与多种基线公平对比。
- **消融实验充分**：验证了每个组件、每个阶段、不同超参数的影响。

## 8. 不足与局限

- **空间细节丢失**：论文承认由于视频分辨率低（224×224）且每帧仅压缩到64 token，可能导致空间细节不准确，尤其在需要高空间分辨率的任务上。
- **长视频性能有限**：虽然在EgoSchema上取得39.7%准确率，但距离当时最优LangRepo（41.2%）仍有差距，且弱于专门为长视频设计的MovieChat在部分模式下的表现。
- **训练成本**：三阶段训练需要较多数据和算力，且依赖预先标注的时序信息（如InternVid-10M-FLT），数据获取成本较高。
- **时序定位依赖LLM生成**：在第一阶段定位相关时间段时，依靠LLM输出离散bin，可能引入定位误差，影响后续高频率采样质量。
- **未在更高分辨率/更大模型上验证**：实验仅基于Vicuna-7B，未探索LLaMA-13B等更大模型或更高输入分辨率下的性能。
- **未报告误差范围（error bars）**：论文提到多次运行取平均，但未给出标准差或置信区间，统计显著性未知。
- **对实时性应用的潜在限制**：两阶段推理（先定位再密集采样）增加了推理延迟，不适用于对实时性要求高的场景。

（完）
