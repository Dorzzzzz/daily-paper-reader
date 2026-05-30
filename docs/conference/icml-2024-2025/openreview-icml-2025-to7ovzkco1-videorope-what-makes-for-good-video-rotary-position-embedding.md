---
title: "VideoRoPE: What Makes for Good Video Rotary Position Embedding?"
title_zh: VideoRoPE：什么因素构成好的视频旋转位置嵌入？
authors: "Xilin Wei, Xiaoran Liu, Yuhang Zang, Xiaoyi Dong, Pan Zhang, Yuhang Cao, Jian Tong, Haodong Duan, Qipeng Guo, Jiaqi Wang, Xipeng Qiu, Dahua Lin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tO7OVZkCo1"
tags: ["query:long-video"]
score: 9.0
evidence: 设计视频旋转位置嵌入用于长视频理解
tldr: 针对视频中复杂的时空结构，现有RoPE扩展未充分考虑关键特性，论文VideoRoPE通过分析提出视频RoPE的四个关键特性，并引入带干扰物的视觉大海捞针任务V-NIAH-D，证明合理的时域分配对长视频理解至关重要，为长视频位置编码设计提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 792, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1688, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 802, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1691, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1659, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 608, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 612, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 157, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 605, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 600, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-to7ovzkco1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1331, \"height\": 2198, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 879, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 887, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1124, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1362, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1063, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 981, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-to7ovzkco1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 795, \"height\": 338, \"label\": \"Table\"}]"
motivation: 现有RoPE扩展至视频时缺乏对时空结构的全面分析，导致长视频理解性能受限。
method: 理论分析视频RoPE的四个关键特性，并提出V-NIAH-D评估任务。
result: V-NIAH-D任务表明先前变体因时域分配不当易被干扰物误导。
conclusion: 合理的时域维度分配是视频RoPE成功的关键。
---

## Abstract
While Rotary Position Embedding (RoPE) and its variants are widely adopted for their long-context capabilities, the extension of the 1D RoPE to video, with its complex spatio-temporal structure, remains an open challenge.
This work first introduces a comprehensive analysis that identifies four key characteristics essential for the effective adaptation of RoPE to video, which have not been fully considered in prior work.
As part of our analysis, we introduce a challenging V-NIAH-D (Visual Needle-In-A-Haystack with Distractors) task, which adds periodic distractors into V-NIAH.
The V-NIAH-D task demonstrates that previous RoPE variants, lacking appropriate temporal dimension allocation, are easily misled by distractors.
Based on our analysis, we introduce VideoRoPE, with a 3D structure designed to preserve spatio-temporal relationships.
VideoRoPE features low-frequency temporal allocation to mitigate periodic oscillations, a diagonal layout to maintain spatial symmetry, and adjustable temporal spacing to decouple temporal and spatial indexing.
VideoRoPE consistently surpasses previous RoPE variants, across diverse downstream tasks such as long video retrieval, video understanding, and video hallucination.
Our code and model weights will be publicly released.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：将原本为1D文本序列设计的旋转位置编码（RoPE）有效扩展到具有复杂时空结构的视频数据中，是一个尚未解决的开放挑战。现有RoPE变体（如Vanilla RoPE、TAD-RoPE、M-RoPE）未能同时满足视频位置编码应具备的四个关键特性：**2D/3D结构**、**频率分配**、**空间对称性**和**时间索引缩放**。
- **动机**：视频大语言模型（Video LLMs）需要同时建模时间（t）、水平（x）和垂直（y）三个维度的位置关系。已有的3D RoPE变体（如M-RoPE）在长视频检索任务中表现不佳，尤其是在存在视觉干扰物时容易被误导。论文希望通过系统分析，设计出更优的视频位置编码方案，以提升长视频理解、检索和抗幻觉能力。
- **整体含义**：提出了**VideoRoPE**，通过低频率时域分配、对角布局和可调时间间隔三个设计，全面满足上述四个关键特性，从而显著提升模型在多种视频任务上的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于对视频RoPE应满足的四个特性分析，设计一种3D位置编码方案，使得时间维度使用低频旋转角度（避免周期性振荡导致“哈希碰撞”），空间维度使用高频旋转角度，并通过对角布局保持空间对称性，通过可调时间间隔解耦时间和空间索引。

- **关键技术细节**：
  - **Low-frequency Temporal Allocation (LTA)**：将特征维度中**较高的维度（对应更低频率）**分配给时间轴（t），而将**较低的维度（对应更高频率）**分配给空间轴（x和y），并且x和y的维度采用**交错分配**（interleaved），以保持两者相似性。这样时间位置编码具有更宽的单调区间，避免因周期性振荡导致远距离位置嵌入相同，从而对干扰物更鲁棒。
  - **Diagonal Layout (DL)**：在3D空间中，将视觉和文本令牌的位置沿对角线排列，使得相邻帧对应空间位置之间的索引增量与相邻文本令牌的增量一致，同时保持视觉令牌之间的相对位置关系，实现空间对称性（前后文本对视觉的影响均衡）。
  - **Adjustable Temporal Spacing (ATS)**：引入超参数δ（论文推荐δ=2），用于缩放视频帧的时间索引相对于文本索引的步长。具体地，对视频部分的t索引施加缩放因子δ，从而区分帧索引和文本索引的粒度，提高对齐效果。

- **公式/算法流程**（文字说明）：
  - 位置索引(t, x, y)的生成规则：对于起始文本令牌，所有三个维度均取令牌序号τ；对于视频令牌（第τ帧，第w,h个patch），t = Ts + δ×(τ - Ts)，x = t + (w - W/2)，y = t + (h - H/2)；对于后续文本令牌，t = τ + (δ - 1)×Tv，x和y相同。其中Ts、Tv分别为文本和视频的令牌数，W、H为帧内patch网格大小。
  - 这一公式确保视觉与文本的索引连续增长，同时保持空间对称性和时间可调性。

## 3. 实验设计

- **使用的数据集/场景**：
  - 训练数据：LLaVA-Video-178k的子集，共约1.3M QA对（136k短于2分钟的视频 + 18k 2-3分钟的视频）。
  - 评估基准：
    - **长视频理解**：LongVideoBench（8秒-1小时）、MLVU（3分钟-2小时，7个多选子任务）、Video-MME（11秒-60分钟）。
    - **长视频检索**：V-NIAH（原始针草任务）及论文提出的**V-NIAH-D**（带周期性干扰物的增强版，基于RoPE基频计算周期）。
    - **视频幻觉**：VideoHallucer（分5个子类型：对象关系、时间、语义细节、外在事实、外在非事实）。

- **对比方法**：
  - Vanilla RoPE（原始1D RoPE，展平视频帧）
  - TAD-RoPE（时间感知双RoPE，1D变体）
  - M-RoPE（Qwen2-VL使用的3D RoPE，按[t...x...y...]顺序分配维度）
  - 所有方法基于相同模型架构（Qwen2-VL-7B初始化，LLM部分使用Qwen2-7B）进行微调。

- **评估方式**：在4个上下文长度（8k、16k、32k、64k）下分别评测，并额外进行128k外推实验。

## 4. 资源与算力

- 文中明确提到：**704 Nvidia-A100 GPU hours**，具体GPU数量未说明，但结合批次大小128、上下文长度8192等配置，推测使用约8-16块A100进行训练。
- 未提及推理阶段的计算资源。

## 5. 实验数量与充分性

- **实验数量**：共进行了**4大类基准**（长视频理解×3、长视频检索×2、视频幻觉×1，其中V-NIAH-D为新增）的完整对比，涵盖4种上下文长度（共约4×5=20组主实验）。此外还进行了：
  - 三个模块（LTA、DL、ATS）的逐步消融实验（表5）
  - 缩放因子δ的消融（0.5/1/2/3，表6）
  - 空间维度x,y分配方式消融（顺序vs交错，表7）
  - 对角布局DL在其他基准上的消融（表8）
  - 不同频率分配策略的对比（表9）
  - 128k外推实验（表10）
- **充分性评估**：实验设计较为充分：
  - 对比了所有主流RoPE变体，且在同一训练设置下公平比较。
  - 覆盖了多种视频任务类型（理解、检索、幻觉），且包含长上下文外推测试。
  - 消融实验系统验证了每个模块的贡献。
  - **不足之处**：仅与RoPE变体对比，未与完整的先进Video LLMs（如Qwen2-VL本身、LLaVA-Video等）进行整体性能对比；训练数据仅为完整数据集的一个子集，可能影响泛化性；干扰物周期基于RoPE基频计算，可能不够自然。

## 6. 论文的主要结论与发现

- **VideoRoPE在所有基准上一致优于现有RoPE变体**：
  - 长视频理解（64k）：LongVideoBench +2.91，MLVU +4.46，Video-MME +1.66（对比M-RoPE）。
  - 长视频检索：V-NIAH +12.44，V-NIAH-D +12.44（对比M-RoPE）。
  - 视频幻觉：平均提升11.9分，尤其时间幻觉提升29.5%。
- **V-NIAH-D任务揭示**：现有M-RoPE因时域使用高频，易受周期性干扰物误导；VideoRoPE的低频时域分配有效缓解这一问题。
- **关键设计**：低频时域分配、对角布局、可调时间间隔三者缺一不可，且最佳缩放因子δ=2。

## 7. 优点（方法或实验设计亮点）

- **系统性分析**：首次明确视频RoPE应满足的四个关键特性，并设计对应方案，而非简单经验调参。
- **诊断性任务V-NIAH-D**：基于RoPE基频周期插入干扰物，精准暴露频率分配缺陷，为位置编码评估提供新工具。
- **方法简洁有效**：仅修改位置编码方式，不改变模型架构或训练数据，即获得显著提升，易于迁移到其他Video LLM。
- **实验全面公平**：统一初始化、训练数据、超参数，仅改变位置编码，确保对比公平；消融实验验证每个模块作用；外推测试验证鲁棒性。
- **开源代码**：承诺开放代码，便于复现。

## 8. 不足与局限

- **对比范围局限**：仅与RoPE系列变体对比，未与模型整体（如Qwen2-VL、LLaVA-Video等）进行端到端性能比较，难以判断VideoRoPE相对于其他位置编码（如ALiBi、绝对位置编码等）的优势。
- **训练数据覆盖有限**：仅使用了LLaVA-Video-178k的子集，未使用更全的数据（如ShareGPT4Video等），可能影响模型上限。
- **V-NIAH-D干扰物设计**：采用数学周期插入，与真实场景中语义相似干扰物的分布可能不一致，降低了任务的自然性。
- **未在更大模型上验证**：实验基于7B模型，能否推广到13B/70B等更大规模未知。
- **应用限制**：VideoRoPE需要为每个视觉patch计算三维位置索引，可能带来额外内存和计算开销，且对角布局对分辨率变化的适应性尚未讨论。

（完）
