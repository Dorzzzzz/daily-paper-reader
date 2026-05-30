---
title: "Video-LaVIT: Unified Video-Language Pre-training with Decoupled Visual-Motional Tokenization"
title_zh: Video-LaVIT：通过解耦视觉-运动标记化的统一视频语言预训练
authors: "Yang Jin, Zhicheng Sun, Kun Xu, Kun Xu, Liwei Chen, Hao Jiang, Quzhe Huang, Chengru Song, Yuliang Liu, Di ZHANG, Yang Song, Kun Gai, Yadong MU"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=S9lk6dk4LL"
tags: ["query:long-video"]
score: 6.0
evidence: 通过解耦视觉-运动标记化实现统一视频语言预训练
tldr: 针对视频时空动态建模的挑战，本文提出Video-LaVIT，将视频分解为关键帧和时序运动，并通过专用标记器离散化为少量token，实现视频、图像和文本的统一生成式预训练。在多种下游任务上取得优异效果。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1674, \"height\": 698, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1722, \"height\": 923, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1710, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 781, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 783, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1601, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 781, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 782, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1690, \"height\": 1961, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1687, \"height\": 1696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1690, \"height\": 1814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-s9lk6dk4ll/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1690, \"height\": 993, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1702, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1694, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1684, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1701, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 820, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1234, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1068, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1763, \"height\": 1984, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1749, \"height\": 1217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-s9lk6dk4ll/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1733, \"height\": 1372, \"label\": \"Table\"}]"
motivation: 视频的时空动态性给大规模预训练带来挑战。
method: 将视频分解为关键帧和运动表示，设计tokenizer离散化为少量token，结合LLM进行统一预训练。
result: 在多项视频语言任务上表现出色。
conclusion: Video-LaVIT实现了高效的视频语言统一预训练框架。
---

## Abstract
In light of recent advances in multimodal Large Language Models (LLMs), there is increasing attention to scaling them from image-text data to more informative real-world videos. Compared to static images, video poses unique challenges for effective large-scale pre-training due to the modeling of its spatiotemporal dynamics. In this paper, we address such limitations in video-language pre-training with an efficient video decomposition that represents each video as keyframes and temporal motions. These are then adapted to an LLM using well-designed tokenizers that discretize visual and temporal information as a few tokens, thus enabling unified generative pre-training of videos, images, and text. At inference, the generated tokens from the LLM are carefully recovered to the original continuous pixel space to create various video content. Our proposed framework is both capable of comprehending and generating image and video content, as demonstrated by its competitive performance across 13 multimodal benchmarks in image and video understanding and generation. Our code and models are available at https://video-lavit.github.io.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：多模态大语言模型（LLMs）在图像-文本数据上取得了显著进展，但视频模态因具有复杂的时空动态性，在大规模预训练中面临挑战。直接使用2D编码器逐帧处理视频会丢失时间运动信息；3D编码器虽能建模时间信息，但会生成大量token（如2.2秒片段需1280个token），计算开销过高，难以扩展至长视频。
- **核心问题**：如何高效地对视频进行表征，使其既能保留时间动态信息，又能以紧凑的token形式与LLM统一预训练，实现视频的理解与生成。
- **整体含义**：通过将视频分解为关键帧和运动向量，分别进行离散化标记化，从而大幅减少冗余token，并利用已有的图像LLM知识，实现视频、图像、文本的统一生成式预训练，提升模型在多种多模态任务上的性能。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程（文字说明）

- **核心思想**：视频在同一镜头内的帧存在高度冗余，因此可分解为一个关键帧（I帧）和后续帧相对于关键帧的运动向量（MV）。关键帧用现有图像tokenizer（来自LaVIT）编码，运动向量用专门设计的VQ-VAE运动tokenizer编码为紧凑离散token序列。LLM将这些视觉-运动token与文本token统一视为1D离散序列，进行自回归预训练。生成时，利用条件扩散模型（3D U-Net）将LLM输出的token依次解码为关键帧和后续帧，并采用DDIM反转和噪声约束实现长视频的时序一致性。

- **关键技术细节**：
  - **视频分解**：利用MPEG-4压缩标准提取I帧（关键帧）和运动向量。每帧分成16×16宏块，计算相邻帧最佳宏块偏移得到运动向量M ∈ R^(T × H/16 × W/16 × 2)。
  - **运动tokenizer**：基于VQ-VAE架构，包含时空编码器f_E（L=12个Transformer块，含空间注意力和时间注意力层）、可学习码本C（大小1024）和对称解码器f_D。编码后的潜在嵌入经过L2归一化后量化到最近码本。采用低维投影和指数移动平均（EMA）更新防止码本崩溃。最终每个视频片段产生135个运动token（默认）。
  - **视频detokenizer**：使用3D U-Net（基于Stable Video Diffusion初始化），以关键帧潜在表示、运动向量以及运动特征作为条件进行去噪重建。训练时最小化EDM目标函数：E[λ_σ ||g_V(X_0+n, σ, Î, M) − X_0||]。
  - **长视频解码**：对连续片段的关键帧，利用前一clip的最后帧进行DDIM反转得到噪声状态，作为当前clip去噪的初始噪声，保证跨clip的视觉连贯性。
  - **统一生成建模**：所有模态（视频、图像、文本）通过特殊标记（如[IMG]、[/IMG]、[MOV]、[/MOV]）区分后拼接成多模态序列，以标准自回归next-token预测目标进行预训练。训练时混合图像-文本对、视频-文本对和纯文本数据，并交换顺序（视频→文本 和 文本→视频）。

### 3. 实验设计：使用的数据集/场景、benchmark、对比方法

- **数据集与场景**：
  - **图像理解**：VQA v2、GQA、VizWiz、ScienceQA-IMG、MME、MMBench、SEED、MM-Vet（8个benchmark）。
  - **视频理解**：MSVD-QA、MSRVTT-QA、ActivityNet-QA（zero-shot视频问答）；Perception Test、EgoSchema（长视频理解）。
  - **零样本文本到视频生成**：MSR-VTT、UCF-101（评估指标包括CLIPSIM、FVD、FID、IS）。
  - **零样本长视频生成**：EvalCrafter（2048个64帧视频，评估FVD、KVD、CLIPSIM）。
  - **文本到图像生成**：MS-COCO验证集（30K样本，FID评估）。
  - *注：图像生成结果在附录中呈现。*

- **对比方法**：对比了多个最新模型，包括：
  - **图像理解**：Flamingo、BLIP-2、InstructBLIP、CM3Leon、Emu、DreamLLM、Video-LLaVA、LLaMA-VID、LLaVA-1.5。
  - **视频问答**：FrozenBiLM、Video-LLaMA、VideoChat、Video-ChatGPT、LLaMA-VID、Video-LLaVA。
  - **长视频理解**：Flamingo、BLIP-2、VideoChat2、FrozenBiLM、mPLUG-Owl、InternVideo。
  - **文本到视频生成**：CogVideo、Video LDM、VideoComposer、InternVid、Make-A-Video、VideoPoet、PYoCo、SVD。
  - **长视频生成**：Direct、Sliding、Gen-L-Video、FreeNoise。

### 4. 资源与算力

- **训练硬件**：
  - 语言模型预训练：128块NVIDIA A100 GPU。
  - Tokenizer和Detokenizer训练：各64块NVIDIA A100 GPU。
- **训练时间**：
  - 语言模型预训练（Stage 2）：30K步，约60小时。
  - Tokenizer训练（Stage 1）：100K步，约10小时。
  - Detokenizer训练（Stage 1）：60K步（先50K步384×384，再10K步768×768或1024×576），约48小时。
- **数值精度**：bfloat16。

### 5. 实验数量与充分性

- **实验数量**：
  - 图像理解：8个benchmark，均进行了对比，报告了详细数值（表1）。
  - 视频理解：3个benchmark（表2）和2个长视频benchmark（表3）。
  - 视频生成：2个标准benchmark（表4）和1个长视频生成benchmark（表5）。
  - 消融实验：运动tokenization效果（表6）、运动token数量（表7）、增强运动调节（附录图10）、运动token对图像理解的影响（表9）、权重初始化影响（表10）。
  - 定性结果：多组图文、文生视频、图生视频、长视频对比图（图4-10）。
- **充分性与公平性**：
  - 对比了多个SOTA模型，涵盖开源和闭源（如Gen-2、SVD），评估指标多样。
  - 消融实验设计合理，验证了核心组件的必要性。
  - 控制变量：与LLaVA-1.5使用相同的指令数据和基础模型，保证公平对比。
  - 在视频生成中，数据来源多为公开数据集（WebVid-10M等），但部分对比模型使用了更大规模或非公开数据（如VideoPoet使用270M私有数据），作者已注明。
  - 总体实验设计较为系统，覆盖理解与生成两大能力，实验充分性较高。

### 6. 论文的主要结论与发现

- Video-LaVIT通过解耦关键帧和运动向量的方式，将视频表示为紧凑的离散token序列，显著降低了token数量（相比3D编码器节省>90% tokens），同时保留了时间运动信息。
- 在13个多模态benchmark中取得了具有竞争力的结果：图像理解上超越LLaVA-1.5等模型；视频问答中在MSVD-QA、ActivityNet-QA上达到最佳；长视频理解（Perception Test、EgoSchema）优于专门模型；文本到视频生成在多指标上接近或超越基于更大私有数据训练的模型。
- 长视频解码时采用DDIM反转和噪声约束，有效提升了跨clip的时序一致性。
- 统一的ID序列建模使模型能同时处理理解与生成任务，无需额外微调。

### 7. 优点

- **高效性**：利用运动向量代替逐帧编码，大幅减少token数量，使长视频处理成为可能，且能复用图像预训练知识。
- **统一性**：一个模型同时支持图像、视频的理解与生成，无需任务特定模块。
- **创新性**：提出解耦的视觉-运动标记化方法，结合运动向量和自回归LLM预训练，设计新颖。
- **可扩展性**：自然支持长视频的渐进解码和跨clip一致性。
- **实验严谨**：多维度消融实验验证了关键设计效果，对比公平（控制语言模型、指令数据等变量）。
- **公开性**：代码和模型开源，训练数据全部为公开数据集。

### 8. 不足与局限

- **长视频生成限制**：受限于LLM上下文窗口（4096）和训练数据（WebVid-10M平均时长约15秒，场景变化少），模型生成的关键帧容易在不同clip间相似，难以处理剧烈的场景切换。
- **训练成本仍高**：虽然token数量减少，但整体训练仍需大量GPU资源（128 A100×60小时），对规模化扩展仍需优化。
- **数据依赖**：视频训练仅使用WebVid-10M，可能存在水印、领域偏差；模型在非公开数据上的表现未知。
- **生成质量**：与专用扩散模型（如SVD）相比，在部分样本上运动幅度仍不够大或存在物理不合理（如图8中SVD的摩托车方向错误），定性比较中仍有改进空间。
- **潜在风险**：多模态LLM的通病如幻觉、偏见、滥用生成技术等问题未被重点讨论，但作者在Impact Statement中承认了这些风险。

（完）
