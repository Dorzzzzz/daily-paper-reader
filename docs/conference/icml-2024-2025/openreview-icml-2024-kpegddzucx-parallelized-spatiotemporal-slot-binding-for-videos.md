---
title: Parallelized Spatiotemporal Slot Binding for Videos
title_zh: 视频的并行化时空槽绑定
authors: "Gautam Singh, Yue Wang, Jiawei Yang, Boris Ivanovic, Sungjin Ahn, Marco Pavone, Tong Che"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=KpeGdDzucX"
tags: ["query:long-video"]
score: 7.0
evidence: 提出了可并行化的时空槽绑定方法，用于长视频分析
tldr: 针对现有面向序列的物体中心模型依赖RNN导致训练不稳定、难以处理长序列的问题，提出了PSB，首个时间上可并行的槽学习架构。PSB通过固定层数的因果注意力并行细化所有时间步的初始槽，生成物体中心表示。实验表明，PSB在长视频序列上训练更稳定，且性能优于RNN基线，为长视频理解提供了高效的表示学习方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1697, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 820, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 829, \"height\": 1012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 1372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 764, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1706, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1719, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1736, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1702, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 693, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1561, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1775, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 890, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kpegddzucx/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1590, \"height\": 500, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1142, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 981, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 980, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1071, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1421, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1146, \"height\": 1063, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1145, \"height\": 1592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 439, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 633, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 566, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 567, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kpegddzucx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 557, \"height\": 1092, \"label\": \"Table\"}]"
motivation: 现有物体中心模型在处理长视频序列时因依赖RNN而训练不稳定、容量受限。
method: 提出PSB架构，通过并行化槽学习与因果注意力，同时处理所有时间步的物体表示。
result: 在长视频序列上实现更稳定的训练和更优的物体中心表示质量。
conclusion: PSB为长视频理解提供了一种高效的并行化表示学习方案。
---

## Abstract
While modern best practices advocate for scalable architectures that support long-range interactions, object-centric models are yet to fully embrace these architectures. In particular, existing object-centric models for handling sequential inputs, due to their reliance on RNN-based implementation, show poor stability and capacity and are slow to train on long sequences. We introduce Parallelizable Spatiotemporal Binder or PSB, the first temporally-parallelizable slot learning architecture for sequential inputs. Unlike conventional RNN-based approaches, PSB produces object-centric representations, known as slots, for all time-steps in parallel. This is achieved by refining the initial slots across all time-steps through a fixed number of layers equipped with causal attention. By capitalizing on the parallelism induced by our architecture, the proposed model exhibits a significant boost in efficiency. In experiments, we test PSB extensively as an encoder within an auto-encoding framework paired with a wide variety of decoder options. Compared to the state-of-the-art, our architecture demonstrates stable training on longer sequences, achieves parallelization that results in a 60% increase in training speed, and yields performance that is on par with or better on unsupervised 2D and 3D object-centric scene decomposition and understanding.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- 现有面向序列输入的**物体中心模型**（object-centric models）几乎全部采用**RNN（循环神经网络）** 作为时序编码器，例如 SAVi、STEVE 等。  
- RNN 存在固有问题：**梯度爆炸/消失**导致长序列训练不稳定；**时间串行**导致训练速度随序列长度线性增长，难以扩展到长视频。  
- 为突破这一瓶颈，本文提出 **PSB（Parallelizable Spatiotemporal Binder）**——**首个时间上可并行的槽（slot）学习架构**，通过并行处理所有时间步的物体表示，提升效率、稳定性和容量。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：用**堆叠的并行注意力层**替代 RNN 顺序迭代，使所有时间步的槽同时被推理出来。  
- **PSB Block 的结构（Algorithm 1）**：  
  1. **Bottom-Up Attention（交叉注意力）**：每个时间步的槽同时关注所有历史输入特征（可加因果掩码），使用**倒置注意力 + 重归一化**（inverted attention + renormalization）增强槽间竞争，并采用**相对位置偏置**保证平移不变性。  
  2. **Slot Interaction（槽间交互）**：分为两步：  
     - **时间轴自注意力**：相同槽索引的向量沿时间维自注意力（独立于其他槽），模拟物体独立演化。  
     - **对象轴自注意力**：同一时间步下不同槽之间自注意力。  
  3. **MLP**：全连接层处理整合后的信息。  
  所有操作均使用残差连接和层归一化，支持深层堆叠。  
- **初始化**：可学习参数初始化或从高斯分布随机采样（广播到所有时间步）。  
- **应用框架**：  
  - **2D 视频**：CNN 提取每帧特征 → PSB 编码 → Alpha‑mixture 解码器（简单场景）或自回归图像 Transformer 解码器（复杂场景）。  
  - **3D 多相机视频**：先通过 Set Latent Scene Representation (SLSR) 骨干提取每时刻特征 → PSB 编码 → NeRF 或 SlotMixer 解码器。

### 3. 实验设计：数据集、基准、对比方法

- **2D 视频**：  
  - 数据集：MOVi‑A / B / C / D / E（仅使用 RGB 帧，无额外监督）。  
  - 对比方法：  
    - 简单场景（MOVi‑A/B）：**SAVi**（RNN 基线） + 空间广播解码器。  
    - 复杂场景（MOVi‑C/D/E）：**STEVE**（SAVi+自回归 Transformer 解码器）。  
  - 指标：视频级 FG‑ARI、重建 PSNR、线性探测性能（R² 或分类准确率）。  
- **3D 视频**：  
  - 数据集：自行合成的 **Dynamic 3D CLEVR‑Simple** 和 **Dynamic 3D CLEVR‑Natural‑Ego**（包含物理动态、多相机、运动自我中心观察）。  
  - 对比方法：  
    - RNN 基线：**SAVi**。  
    - 静态 3D 模型：**uORF**（Slot Attention + NeRF）、**OSRT**（Slot Attention + SlotMixer）。  
  - 指标：线性探测、新视角合成 PSNR、多维度 FG‑ARI（跨相机/跨时间）。

### 4. 资源与算力

- 论文中**未明确说明使用 GPU 的具体型号与数量**。  
- 训练配置：优化器 AdamW（β₁=0.9, β₂=0.95），峰值学习率 3e‑4，线性预热 30k 步后指数衰减，总训练步数 300k。  
- Batch size = 24 个片段（每个片段 6 个时间步）。  
- 根据速度对比实验（图 3），在单次训练步耗时上 PSB 比 SAVi **快约 1.6 倍**（长序列下优势明显）。

### 5. 实验数量与充分性

- **覆盖 7 个数据集**（5 个 2D + 2 个 3D），同时考虑简单和复杂视觉场景。  
- **对比 3 类基线**（RNN 型 SAVi/STEVE、静态 3D 模型 uORF/OSRT）。  
- **消融实验**（附录 B、5.3 节）：  
  - 学习 vs. 随机槽初始化  
  - 解耦 vs. 联合槽交互（时间/对象轴）  
  - 移除倒置注意力  
  - 静态‑动态场解耦（NeRF 解码器）  
  - 序列长度泛化（训练 6 帧，测试 6/12/18/24 帧）  
- **公平性保证**：在 2D 和 3D 对比中，**保持解码器、SLSR 骨干、隐藏维度等完全相同**，仅替换编码器。  
- 实验设计**充分、客观、公平**，支持结论的可靠性。

### 6. 主要结论与发现

- **并行化有效**：PSB 在长序列上训练稳定，而 SAVi 在小幅延长序列长度后（如 6→12）即出现剧烈震荡（图 3）。  
- **速度提升**：训练速度（每步耗时）快约 1.6 倍（长序列更显著）。  
- **2D 场景**：FG‑ARI 提升 14.7%–26.8%，PSNR 提升 2.9–7.6%（对比 SAVi）；线性探测中形状等复杂因子提升明显。  
- **3D 场景**：线性探测（R²/准确率）提升 7.3%–121%；新视角合成 PSNR 提升 4–8%（对比 SAVi/静态模型）。  
- **解码器兼容性**：与 Alpha‑mixture、自回归 Transformer、NeRF、SlotMixer 多种解码器配合均达到或超越基线。  
- **消融洞察**：学习初始化优于随机；倒置注意力对分解质量重要；解耦时间/对象轴注意力的内存优势明显；静态‑动态场解耦对复杂 3D 场景有益。

### 7. 优点

1. **首次实现槽学习的完全时间并行化**，彻底摆脱 RNN 的限制。  
2. **兼容性强**：可即插即用，替换现有方法中的编码器，仅调整较少超参数。  
3. **多维度验证**：覆盖 2D/3D、简单/复杂场景、多种解码器，实验全面。  
4. **实用性强**：训练稳定性与速度优势对长视频（如自动驾驶、机器人）应用至关重要。

### 8. 不足与局限

1. **注意力复杂度**：PSB 采用全注意力机制，内存复杂度为 O(NT²)，比 RNN 线性复杂度更高（图 14 显示 FLOPs 更大）。  
2. **超长序列泛化**：当测试序列长度明显超过训练长度（如 6→24）时，PSB 的 FG‑ARI 下降，需依赖滑窗策略（附录 B.4），效果略逊于 SAVi。  
3. **真实场景缺失**：仅在合成数据集（MOVi、CLEVR）上实验，未在自然场景视频（如 Kinetics、YouTube‑VIS）上验证。  
4. **解码器依赖**：整体性能仍受解码器质量影响（如 NeRF 解码器需额外静态‑天空头），但本文聚焦编码器，实验已尽量解耦。  
5. **计算资源未公开**：论文未提供具体 GPU 型号与数量，复现成本不透明。

（完）
