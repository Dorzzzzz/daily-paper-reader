---
title: "InfiniPot-V: Memory-Constrained KV Cache Compression for Streaming Video Understanding"
title_zh: InfiniPot-V：面向流式视频理解的内存约束KV缓存压缩
authors: "Minsoo Kim, Kyuhong Shim, Jungwook Choi, Simyung Chang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=hFxOZjHyTg"
tags: ["query:long-video"]
score: 8.0
evidence: 流式视频理解中受限于内存的KV缓存压缩
tldr: 多模态大模型处理流式长视频时KV缓存随视频时长线性增长，超出边缘设备内存。本文提出InfiniPot-V，首个无需训练、查询无关的框架，对KV缓存施加固定内存上限。通过时间轴冗余消除和查询无关压缩，在保持推理质量的同时，将缓存大小约束在设定阈值内。在流式视频理解基准上的实验表明，该方法在内存受限场景下优于现有方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1337, \"height\": 824, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1280, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 735, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hfxozjhytg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 707, \"height\": 518, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1240, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1384, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1326, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1260, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1367, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1265, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 759, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 665, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 1659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hfxozjhytg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1442, \"height\": 503, \"label\": \"Table\"}]"
motivation: 流式视频理解中KV缓存线性增长，超出边缘设备的内存限制。
method: 提出无训练、查询无关的框架，通过移除时间冗余强制固定内存上限。
result: 在内存受限场景下保持推理质量，优于现有压缩方案。
conclusion: 为边缘设备上的流式视频理解提供了实用的内存管理方案。
---

## Abstract
Modern multimodal large language models (MLLMs) can reason over hour-long video, yet their key–value (KV) cache grows linearly with time—quickly exceeding the fixed memory of phones, AR glasses, and edge robots. Prior compression schemes either assume the whole video and user query are available offline or must first build the full cache, so memory still scales with stream length. InfiniPot-V is the first training-free, query-agnostic framework that enforces a hard, length-independent memory cap for \textit{streaming} video understanding. During video encoding it monitors the cache and, once a user-set threshold is reached, runs a lightweight compression pass that (i) removes temporally redundant tokens via Temporal-axis Redundancy (TaR) metric and (ii) keeps semantically significant tokens via Value-Norm (VaN) ranking. Across four open-source MLLMs and four long-video and streaming-video benchmarks, InfiniPot-V cuts peak GPU memory by up to 94\%, sustains real-time generation, and matches or surpasses full-cache accuracy—even in multi-turn dialogues. By dissolving the KV cache bottleneck without retraining or query knowledge, InfiniPot-V closes the gap for on-device streaming video assistants.

---

## 论文详细总结（自动生成）

# InfiniPot-V: 内存约束流式视频理解的KV缓存压缩——论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：多模态大模型（MLLM）在流式视频理解（SVU）场景中，KV缓存随视频时长线性增长，很快超出手机、AR眼镜、边缘机器人等设备的固定内存限制。现有压缩方案（帧采样、输入视觉压缩、KV缓存压缩）均假设完整视频和用户查询在推理时可用，或需要先构建完整缓存再压缩，内存仍随流长度增长。
- **背景**：流式视频理解与离线视频理解不同：帧逐帧到达、未来查询未知，要求压缩过程是查询无关（query-agnostic）且内存固定。然而现有方法（如SnapKV、ReKV）要么依赖查询、要么需要完整缓存，无法满足这两种核心需求。
- **动机**：需要一种无需训练、查询无关、能够在固定内存预算下持续处理流式视频的KV缓存压缩框架。

## 2. 方法论
### 核心思想
- **Continual KV Cache Compression (CKV)**：在视频编码过程中持续监测KV缓存大小，当达到用户设定的内存阈值 \(|M|\) 时，执行一次轻量级压缩，将缓存压缩至更小的目标大小 \(|C|\)，释放空间用于新帧。压缩基于两个互补指标：时间轴冗余（TaR）和值范数重要性（VaN）。
- **训练无关**：无需任何训练或微调，即插即用。
- **查询无关**：压缩时不依赖任何用户查询，仅利用键值和值向量的内在属性。

### 关键技术细节
1. **Temporal-axis Redundancy (TaR)**：
   - 将Key嵌入重塑为3D张量（时间×高度×宽度），计算过去帧与最近帧对应块的余弦相似度。
   - 保留与最近帧相似度低的令牌（即时间上新颖、非冗余的令牌），移除静态背景等重复内容。
   - 最近帧（最后 \(r\) 帧）完全保留，确保快速变化内容不丢失。
2. **Value-Norm Importance (VaN)**：
   - 利用值向量 \(V\) 的 \(\ell_2\) 范数作为令牌语义重要性的代理指标。
   - 分析显示，高VaN令牌具有更高熵（信息量更大），且在多种压缩比下保留高VaN令牌能更好保持视频理解精度。
   - 引入**层自适应池化**：根据各层VaN分布的变异系数（CV）动态调整平均池化核大小，低层（高空间局部性）用大核，高层（低局部性）用小核或不做池化。
3. **TaR与VaN结合**：
   - 先分配 \(\alpha |C|\) 个令牌给TaR（优先级更高），剩余 \((1-\alpha)|C|\) 个令牌由VaN选择。默认 \(\alpha=0.5\)。
4. **算法流程**（Algorithm 1 & 2）：
   - 初始化空KV缓存。
   - 不断处理新帧，追加KV到缓存。
   - 当缓存长度 \(\ge |M|\) 时，执行压缩：
     - (a) 提取最近 \(r\) 帧的KV作为保留部分。
     - (b) 对过去帧计算TaR得分，选择得分最高的 \(\alpha|C| - len(K_{\text{recent}})\) 个令牌。
     - (c) 计算VaN得分并应用自适应池化，然后选择剩余 \((1-\alpha)|C|\) 个令牌（同时保证TaR选中的令牌优先级最高）。
     - (d) 将选中的令牌与最近帧令牌拼接，形成压缩缓存。
   - 收到用户查询时，直接用当前压缩缓存生成回答。

## 3. 实验设计
### 数据集/场景
- **离线视频理解（OVU）**：VideoMME、MLVU、LongVideoBench（LVB）、EgoSchema。视频时长从3分钟到2小时以上。
- **流式视频理解（SVU）**：RVS-Ego、RVS-Movie（开放问答，GPT-3.5评估）、OVO-Bench（三种时间推理场景）、StreamingBench（实时视觉理解）。

### 对比方法
- **IVC类**：LongVU（STC）、DyCoke（TTC）——输入视觉压缩。
- **KVC类**：SnapKV（查询依赖）、Uniform Select（均匀选择）、InfiniPot（代理提示方法）、FastV（剪枝）。
- **流式基线**：ReKV（CPU卸载/无卸载）。
- **全缓存（Full KV）** 作为上界。

### 模型
- Qwen-2-VL 7B、Qwen-2.5-VL 3B/7B、LLaVA-Next-Video 7B、LLaVA-OV 7B。

### 评估指标
- 多项选择题准确率（OVU）、GPT评分（SVU）、GPU峰值内存、延迟、吞吐、功耗（边缘设备）。

## 4. 资源与算力
- 论文未明确报告完整训练所需的算力（因为方法无训练），但测量了推理时的资源。
- 主要实验使用**单张 NVIDIA A100 80GB GPU**。
- 边缘设备部署测试使用**NVIDIA Jetson AGX Orin**（32GB共享内存）。
- 流式处理中，压缩开销仅占输入帧处理时间的**0.5%**。

## 5. 实验数量与充分性
- **大量实验**：覆盖4种MLLM、6个长视频/流式基准（OVU 4个 + SVU 3-4个）、多种压缩比（1/16到1/2）、多种内存预算（1.5K/3K/6K/12K/24K）以及消融研究。
- **消融实验**（Table 5）：分别验证TaR、VaN、池化策略、以及两者组合的贡献，并包含反向验证（TaR Reverse、VaN Reverse）以证明有效性。
- **流式场景对比**：与ReKV在1小时视频上比较准确率、显存、CPU卸载开销。
- **边缘设备性能**：在Jetson AGX Orin上测量帧率、吞吐、功耗、峰值内存。
- **多轮对话案例**（附录C）：定性展示查询无关压缩在多轮问答中的优势。
- **充分性**：实验设计较全面，公平性良好（统一框架、统一内存预算、使用官方实现或一致配置），但部分SVU基准仅在单一模型上测试（如OVO-Bench & StreamingBench只用了Qwen-2.5-VL 7B）。

## 6. 主要结论与发现
- InfiniPot-V在**固定内存预算下**实现了**无损或更优的压缩**：例如6K缓存（12.5%的原始50K）在Qwen-2-VL上保持相近精度。
- 相比IVC方法（LongVU、DyCoke）在同等CKV约束下，InfiniPot-V精度高出显著（Table 2）。
- 相比KVC方法（SnapKV、Uniform Select、InfiniPot）在查询无关和内存受限的CKV设置中，InfiniPot-V在所有压缩比和模型上均最佳（Figure 4 & Table A5）。
- 在流式SVU基准上，InfiniPot-V无需CPU卸载即达到或超过ReKV（带卸载）的准确率，且消除了卸载延迟。
- 边缘设备上（Jetson AGX Orin），峰值内存近乎恒定（~10.7GB），而Full KV线性增长至OOM；生成吞吐提升高达7.3倍，功耗降低约2倍。

## 7. 优点
- **训练无关**：即插即用，无需额外训练或微调，兼容现有MLLM。
- **查询无关**：压缩时不依赖用户问题，支持任意查询变化和多轮对话，更适合流式场景。
- **内存固定**：通过持续压缩强制内存上限，与流长度解耦，适合边缘部署。
- **高效轻量**：压缩开销仅0.5%，实时帧处理速率稳定。
- **全面评估**：覆盖多种模型、基准和压缩比，包含消融和边缘设备实测，证据充分。

## 8. 不足与局限
- **当前仅处理视觉令牌**：未扩展到其他模态（如语音、文本），现实流式应用常涉及多模态输入。
- **固定预算分配**：TaR与VaN之间的预算比例 \(\alpha\) 固定为0.5，缺乏根据场景动态调整的能力（如静态场景应侧重时间冗余，动态场景侧重空间语义）。
- **位置编码问题**：流式处理超长视频时，原始位置索引会超出模型最大位置范围，需重新分配索引，可能丢失原有时间/空间位置信息（尤其3D RoPE）。
- **实验覆盖不均衡**：SVU基准（OVO-Bench、StreamingBench）仅在单一模型（Qwen-2.5-VL 7B）上评估，泛化性验证不够充分。
- **未与训练型方法对比**：虽然训练无关是优势，但也限制了极端压缩比下的潜力，未与可训练压缩方法（如LongVU）在训练后相同模型上对比（LongVU本身需要训练）。
- **未讨论潜在偏差或公平性**：论文未分析压缩对不同场景（如快速运动、密集物体、小目标等）的敏感性。

（完）
