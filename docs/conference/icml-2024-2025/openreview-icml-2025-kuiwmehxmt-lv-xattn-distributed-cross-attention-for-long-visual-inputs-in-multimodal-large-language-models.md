---
title: "LV-XAttn: Distributed Cross-Attention for Long Visual Inputs in Multimodal Large Language Models"
title_zh: LV-XAttn：多模态大语言模型中长视觉输入的分布式交叉注意力
authors: "Tzu-Tao Chang, Shivaram Venkataraman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kuIwMEHXMT"
tags: ["query:long-video"]
score: 8.0
evidence: 提出了针对长视觉输入的多模态大语言模型分布式交叉注意力机制，用于视频理解
tldr: 针对多模态大语言模型在处理长视频时交叉注意力层内存需求高、分布式通信开销大的问题，提出了LV-XAttn分布式精确交叉注意力机制。该方法通过最小化通信开销实现高效并行计算，在不牺牲精度的情况下显著加速训练和推理。实验证明，LV-XAttn有效支持了长视频输入的处理，为大视频模型提供了可行的分布式解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 688, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 833, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 968, \"height\": 785, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 872, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 739, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1649, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 502, \"label\": \"Table\"}]"
motivation: 多模态大模型处理长视频时交叉注意力的内存和通信开销成为瓶颈。
method: 提出LV-XAttn分布式交叉注意力机制，最小化通信开销，支持长视觉输入的高效处理。
result: 在保持精度的同时显著降低了分布式训练和推理的通信开销。
conclusion: LV-XAttn为长视频理解中的交叉注意力分布式计算提供了高效方案。
---

## Abstract
Cross-attention is commonly adopted in multimodal large language models (MLLMs) for integrating visual information into the language backbone. However, in applications with large visual inputs, such as video understanding, processing a large number of visual tokens in cross-attention layers leads to high memory demands and often necessitates distributed computation across multiple GPUs. Existing distributed attention mechanisms face significant communication overheads, making cross-attention layers a critical bottleneck for efficient training and inference of MLLMs. To address this, we propose LV-XAttn, a distributed, exact cross-attention mechanism with minimal communication overhead. We observe that in applications involving large visual inputs, the size of the query block is typically much smaller than that of the key-value blocks.  Thus, in LV-XAttn we keep the large key-value blocks locally on each GPU and exchange smaller query blocks across GPUs. We also introduce an efficient activation recomputation technique to support longer visual context. We theoretically analyze the communication benefits of LV-XAttn and show that it can achieve speedups for a wide range of models. Our evaluations with Llama 3-V, mPLUG-Owl3 and OpenFlamingo models find that LV-XAttn achieves up to 10.62$\times$ end-to-end speedup compared to existing approaches.

---

## 论文详细总结（自动生成）

# 论文总结：LV-XAttn：多模态大语言模型中长视觉输入的分布式交叉注意力

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：多模态大语言模型（MLLMs）广泛采用交叉注意力（cross-attention）层来融合视觉信息与语言主干。然而，在长视频理解等需要处理大量视觉令牌（visual tokens）的场景中，交叉注意力层的计算和内存需求极高（例如，Llama 3-V处理20分钟视频、2048个文本令牌时，即使使用FlashAttention也需要超过234 GB内存），必须采用分布式计算。现有分布式注意力方法（如Ring Attention）在长KV序列时会面临巨大的通信开销，使得交叉注意力成为训练和推理的效率瓶颈。
- **核心观察**：在长视频场景中，查询序列长度（SQ，来自文本）通常远小于键值序列长度（SKV，来自视觉）。例如，在Video-MME基准中，平均SQ≈5514，而SKV≈1528万。基于此，LV-XAttn设计为仅传输小尺寸的查询块，而将大尺寸的KV块保留在本地，从而大幅降低通信量。

## 2. 方法论

### 核心思想
- **保留大KV块本地，交换小Q块**：每个GPU（worker）存储其分配到的KV块（Ki, Vi），并将查询块（Qj）、输出块（Oj）和softmax统计量（Lj）在环状拓扑中轮转传输，计算完整的注意力输出。
- **通信与计算重叠**：利用异步通信，在计算当前注意力时，同时接收下一轮需要的查询块和前一跳的统计量，发送上一轮的结果，几乎完全隐藏通信延迟。
- **激活重计算（Activation Recomputation）**：由于所有交叉注意力层共享相同的视觉特征（y），在反向传播时只需保存一份视觉特征，重计算每层的KV激活，避免每层存储大KV块，从而将可处理的视觉输入长度提升1.6倍，且额外开销<8%。

### 技术细节（文字说明流程）
1. **正向传播**：每个worker i拥有Qi, Ki, Vi。初始化Oi和Li为零。进行n轮循环（n为worker数）：
   - 并行发送当前worker的Qj、Oj、Lj给下一个worker，并从前一个worker接收Qj_next、Oj、Lj。
   - 使用FlashAttention计算局部注意力：ΔO, ΔL = FlashAttention(Qj, Ki, Vi)。
   - 根据ΔO和ΔL对接收到的Oj和Lj进行缩放更新。
   - 最终经过n轮后，每个worker得到完整的注意力输出。
2. **反向传播**：类似地采用环状通信，但通信量约为正向的2.5倍（表1给出理论分析）。
3. **通信量对比**：Ring Attention每轮传输2×SKV/n×d个元素；LV-XAttn仅传输2×SQ/n×d + SQ/n个元素。由于SKV≫SQ，LV-XAttn通信量极小。

## 3. 实验设计

- **模型**：6个主流MLLMs（表2）
  - Llama 3-V-11b（8个交叉注意力层）
  - mPLUG-Owl3（-7b, -2b, -1b，4个交叉注意力层）
  - OpenFlamingo（-9b, -3b，8/24个交叉注意力层）
- **场景与输入**：模拟长视频输入，使用随机生成的文本和视觉令牌，序列长度涵盖不同帧数和文本长度（表3/4中列出）。参考了Video-MME基准的平均值（视频时长2386秒，文本3128词）。
- **基准方法**：
  - **Ring Attention**（主基线，用于所有LM块和交叉注意力层）
  - **DeepSpeed-Ulysses**（头部并行+序列并行，仅用于部分对比）
  - 所有方法均使用FlashAttention加速。
- **集群配置**（三种）：
  1. 16×A100 80GB（4节点，节点内NVLink，跨节点25 GB/s）
  2. 8×A30 24GB（8节点，跨节点1.25 GB/s，资源受限环境）
  3. 12×A100 40GB（用于小规模消融，节点间PCIe 64 GB/s，跨节点25 GB/s）
- **评估指标**：单次迭代的总时间和交叉注意力时间（秒），测量5次取平均。

## 4. 资源与算力

- 论文明确描述了使用的GPU型号和数量：A100 80GB（16卡、12卡）、A30 24GB（8卡）。集群跨节点网络带宽也给出（25 GB/s、1.25 GB/s、64 GB/s PCIe）。
- **未提供总训练时长**：实验仅测量推理/训练的单次迭代时间，未提及完整模型训练或预训练所需时长。因此无法评估整体算力消耗。

## 5. 实验数量与充分性

- **多模型覆盖**：6个不同规模、不同架构（层数、视觉令牌数差异大）的模型，增强了泛化性。
- **多输入尺寸**：每个模型测试了3种SQ/SKV组合（如Llama 3-V: SQ=1K/2K, SKV=1200K/2401K），包含6种场景对比。
- **多集群环境**：三种集群配置（A100大带宽、A30小带宽、A100中等带宽）验证了在不同硬件条件下的普适性。
- **消融实验**：
  - 通信-计算重叠效果（图5）：显示LV-XAttn可完全消除通信开销（<0.42% overhead）。
  - 激活重计算效果（图6a/6b）：显示内存节省与迭代时间微增（<8%），支持帧数增加1.6倍。
- **与DeepSpeed-Ulysses对比**（表5/6）：在跨多种worker数下比较，验证LV-XAttn内存效率更高（避免OOM）。
- **公平性**：所有方法使用相同FlashAttention实现，仅通信方式不同；均使用全分片数据并行（FSDP）以公平分配内存。理论分析（图4、表1）给出了预期的加速比，与实验结果一致。

**总体感觉实验充分**，但缺乏真实视频数据集（如Video-MME）上的端到端精度测量（仅测速度，未测模型输出正确性或任务性能）。因此对实际应用效果的证明稍显不足。

## 6. 主要结论与发现

- **速度提升**：LV-XAttn相比Ring Attention可加速交叉注意力计算最高45.85倍，端到端迭代时间最高加速10.62倍（表3/4）。
- **通信开销极低**：由于通信量极小并可完全重叠，实际开销低于理论无通信基线的0.42%（图5）。
- **内存节省**：激活重计算技术使可用视觉输入长度增加1.6倍，同时迭代时间仅增<8%。
- **适用范围**：在SKV≫SQ的典型MLLM场景（长视频理解）中效果显著，且理论上适用于任何交叉注意力架构的MLLM（如Flamingo、Llama 3-V、mPLUG-Owl3等）。

## 7. 优点

- **简单且精确**：不修改注意力计算公式，与FlashAttention兼容，输出结果与标准注意力完全一致。
- **理论完备**：提供了清晰的通信-计算权衡分析（表1、图4），指导参数选择。
- **高效且可扩展**：通过通信-计算重叠实现实际零通信开销；激活重计算充分利用MLLM视觉输入跨层共享的特性，而非通用Transformer激活重计算。
- **公平实验**：与主流基线（Ring Attention、DeepSpeed-Ulysses）在多种硬件配置下对比，并控制其他因素（如FSDP、FlashAttention）一致。

## 8. 不足与局限

- **架构依赖**：仅适用于交叉注意力型MLLM（如Flamingo系列），不适用于拼接型MLLM（如LLaVA、InternVL），后者可能需要序列并行但通信模式不同。
- **缺乏真实任务验证**：实验仅使用随机输入测量速度，未在实际长视频数据集（如Video-MME、Ego4D）上评估准确率或推理质量，可能忽略精度影响。
- **单batch假设**：实验中batch size为1，未考虑批量训练场景下的通信模式变化。若batch size较大，Q的尺寸增加，LV-XAttn的优势可能减弱。
- **假设SQ远小于SKV**：若文本很长（如包含大量前文或指令），SQ变大，通信量上升，加速比会降低。论文在附录A中讨论了边界情况（图7），表明仍优于Ring Attention，但优势缩小。
- **通信库实现细节**：当前实现基于PyTorch分布式和Triton，可能未针对NCCL等底层库做极致优化；且跨节点带宽配置较理想（25 GB/s），实际云环境可能更低，加速效果可能变化。
- **软件生态适用性**：需要对现有MLLM源码修改交叉注意力计算部分，引入自定义Triton内核，部署难度略高于纯PyTorch实现。

（完）
