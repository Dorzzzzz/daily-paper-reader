---
title: "4DGT: Learning a 4D Gaussian Transformer Using Real-World Monocular Videos"
title_zh: 4DGT：利用真实世界单目视频学习4D高斯Transformer
authors: "Zhen Xu, Zhengqin Li, Zhao Dong, Xiaowei Zhou, Richard Newcombe, Zhaoyang Lv"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=qMRFNxioPC"
tags: ["query:long-video"]
score: 5.0
evidence: 面向长视频处理的4D重建方法
tldr: 动态场景重建通常需要优化过程，难以处理长视频序列。本文提出4DGT，基于4D高斯基元Transformer，以滚动窗口方式处理64帧连续视频，实现前馈推理。训练时采用密度控制策略，使模型能够处理更长时空输入。在真实单目视频上训练后，4DGT可将重建时间从数小时缩短至数秒，且有效扩展到长视频序列。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qmrfnxiopc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qmrfnxiopc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qmrfnxiopc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 1402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qmrfnxiopc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qmrfnxiopc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 1363, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 735, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 899, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 708, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 527, \"height\": 97, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1091, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qmrfnxiopc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1197, \"height\": 178, \"label\": \"Table\"}]"
motivation: 现有动态场景重建方法依赖优化，处理长视频时效率低。
method: 提出4DGT模型，以滚动窗口方式处理64帧，采用密度控制策略。
result: 重建时间从小时级降至秒级，且有效处理长序列。
conclusion: 为长视频动态场景重建提供了高效的前馈方案。
---

## Abstract
We propose 4DGT, a 4D Gaussian-based Transformer model for dynamic scene reconstruction, trained entirely on real-world monocular posed videos. Using 4D Gaussian as an inductive bias, 4DGT unifies static and dynamic components, enabling the modeling of complex, time-varying environments with varying object lifespans. We proposed a novel density control strategy in training, which enables our 4DGT to handle longer space-time input. Our model processes 64 consecutive posed frames in a rolling-window fashion, predicting consistent 4D Gaussians in the scene. Unlike optimization-based methods, 4DGT performs purely feed-forward inference, reducing reconstruction time from hours to seconds and scaling effectively to long video sequences. Trained only on large-scale monocular posed video datasets, 4DGT can outperform prior Gaussian-based networks significantly in real-world videos and achieve on-par accuracy with optimization-based methods on cross-domain videos.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：从真实世界单目视频中重建动态场景，传统优化方法（如NeRF、3DGS优化变体）非常耗时（数小时），难以扩展到长视频序列，且依赖多视角同步捕捉或深度输入，限制了实际应用。
- **研究动机**：现有前馈重建模型多针对静态场景或合成数据，对真实世界复杂动态场景泛化差；而基于优化的动态高斯重建需要手动标注、专家先验，无法快速推理。
- **整体含义**：本文提出4DGT，首个仅使用真实单目视频训练、通过前馈方式预测4D高斯表示（4DGS）的Transformer模型，实现秒级重建，并支持实时渲染。它融合了静态与动态分量，利用寿命参数统一建模，能够处理长视频中的复杂时空变化。

### 2. 论文提出的方法论
- **核心思想**：将动态场景建模为4D高斯（4DGS）集合，每个高斯具有空间位置、尺度、旋转、颜色、不透明度以及**时域属性**（时间中心、寿命、速度、角速度）。采用Transformer架构输入连续64帧带位姿的单目图像，前馈预测所有高斯参数，在滚动窗口下输出一致的世界坐标系4DGS。
- **关键技术细节**：
  - **输入编码**：每帧图像被切分为patch，与Plücker坐标、时间戳、DINOv2特征拼接，形成Transformer的输入token。
  - **特征融合**：使用12层全自注意力Transformer（ViT变体）处理所有token，无需额外位置嵌入。
  - **动态高斯解码**：MLP解码器从每个patch的特征预测完整的动态高斯参数（包括运动参数）。寿命控制不透明度随时间的高斯衰减；速度/角速度控制位置/旋转随时间的变化。
  - **密度控制（两阶段训练）**：
    - **第一阶段**：在低分辨率、少帧数下训练至收敛。
    - **第二阶段**：通过计算每个patch内高斯不透明度的激活直方图，**剪枝**掉80%的低活化高斯；同时**密化**空间和时间采样率（分辨率×2，帧数×4），使实际高斯数量仅增加1倍而时空采样率提升16倍。
  - **多级时空注意力**：将输入帧分成若干组，每组内在不同级别（不同空间分辨率与时间窗口）计算注意力，将计算复杂度从O(n²)降至约O(2n²/M)，约2倍加速。
  - **损失函数**：包含渲染MSE、LPIPS、SSIM损失；加上速度、角速度、寿命的正则化损失（鼓励长寿命、低速度）；以及深度（DepthAnythingV2）和法线（StableNormal）的伪监督损失，以缓解单目视频的时空歧义。

### 3. 实验设计
- **训练数据集**：真实单目视频，包括Project Aria（EgoExo4D、Nymeria、Hot3D、AEA）、Epic-Fields、Cop3D、ARKitTrack等，共计数百小时，位姿由SLAM或COLMAP提供。
- **评估基准/数据集**：
  - ADT（具有真实深度）、DyCheck（极端视角评测）、TUM-SLAM（动态场景）、以及从EgoExo4D/AEA/Hot3D中留出的**Aria测试集**。
- **对比方法**：
  - L4GM（基于合成数据训练的4D高斯模型）
  - Static-LRM（静态场景前馈模型，使用2DGS）
  - MonST3R（动态点云方法）
  - **Shape of Motion (SoM)**（优化基准方法，需手动分割+多专家模型）
  - 单目专家模型（DepthAnythingV2+StableNormal）
- **实验数量与充分性**：
  - 主要定量实验包括：
    - **表1**：在4个数据集上的渲染质量（PSNR/LPIPS）和深度/法线精度对比，含误差棒。
    - **表2a/b**：第一阶段和第二阶段训练各组件消融（数据集规模、损失项、密度控制、多级注意力等）。
    - **表2c**：动态前景区域专门评估，显示4DGT远优于Static-LRM。
    - **表2d**：运动分割质量（mIoU），与MegaSaM对比。
    - **表3**：使用ADT数据集与SoM及SoM+2DGS增强版对比，并展示微调10秒后的进一步提升。
    - **附录表4**：剪枝策略选择（共享vs实时计算）对比。
  - 定性结果包括多视角渲染、深度/法线可视化、光流、运动分割等（图3、图5及附录视频）。
  - 实验覆盖了不同域（合成ADT、真实Aria、室内TUM、极端视角DyCheck），消融完整，比较了学习方法和优化方法，公平性较好（统一分辨率、相似设置）。

### 4. 资源与算力
- 训练：使用 **64块NVIDIA H100 GPU**，第一阶段100k步约 **9天**，第二阶段30k步约 **6天**，总约15天。
- 推理：单块 **80GB A100 GPU**，每帧 **25 ms**（即40 FPS）。
- 文中报告了各baseline的推理时间：SoM 60,000 ms/f，L4GM 200 ms/f，MonST3R 4500 ms/f，专家模型350 ms/f。

### 5. 实验数量与充分性
- 实验数量充足：主要表格4个，消融实验覆盖所有关键设计（第一阶段：数据集规模、静态LRM/逐帧基线、正则化项；第二阶段：密度控制、多级注意力、混合数据集）。额外有动态前景评估、运动分割评估、与优化方法的上界对比、微调效果等。
- 公平性：所有方法在相同分辨率（504×504）和相同帧数下评估；SoM作为优化上界，但包含预处理时间；消融中控制变量。
- 客观性：主要指标均带误差棒（标准差），区分了“渲染PSNR”和“深度RMSE”，并在不同域测试以验证泛化。

### 6. 论文的主要结论与发现
- 4DGT在真实视频上的重建质量**显著优于**前馈基线（L4GM、Static-LRM、MonST3R），在多数指标上**接近优化方法SoM**，但速度**快2,400倍**（纯前馈）或350倍（微调10秒后甚至超越SoM）。
- 提出的密度控制策略（剪枝+密化）有效降低80%高斯数量，同时实现16倍时空采样率，使得训练可行。
- 多级时空注意力减少约一半计算成本而不显著损失质量。
- 混合多个真实数据集训练可提升跨域泛化能力。
- 模型无需明确监督即可从4D运动参数中涌现运动分割能力（mIoU 81.2 vs 优化方法MegaSaM的77.4）。
- 使用4DGT的输出初始化优化方法（微调10秒）可进一步提升质量，成为实际部署的高效方案。

### 7. 优点
- **前馈快速**：秒级重建，适合长视频实时应用。
- **4D高斯表示统一静/动态**：寿命参数自然区分静态背景和运动物体。
- **数据驱动**：仅使用真实单目视频训练，无需合成数据或多视角标注。
- **密度控制策略**：借鉴3DGS的剪枝思想，创新性地应用于前馈模型，平衡计算与细节。
- **多级注意力**：降低Transformer在长序列上的计算开销。
- **有效利用专家先验**：深度/法线伪监督帮助几何学习，且4DGT重建的几何一致性优于专家模型本身。
- **开源友好**：计划发布模型，附带项目页面和补充视频。

### 8. 不足与局限
- **依赖高质量标定**：训练和推理都需可靠的位姿/内参，对未见过设备（如不同手机）的泛化会因度量尺度误差而下降。
- **训练数据域局限**：主要集中在Aria头戴设备、iPhone及GoPro数据，未涵盖广泛“野外”视频，存在域差异。
- **极端视角伪影**：从远离输入轨迹的角度渲染时仍有模糊和伪影，这是单目重建的固有问题。
- **快速运动模糊**：在剧烈或快速运动时细节不清晰。
- **未利用光流专家**：作者指出直接使用RAFT等光流模型会因循环一致误差导致训练不稳定，故未采用，未来可加入更一致的跟踪专家。
- **算力需求大**：训练需要64块H100，消耗15天，不适合小规模团队复现；但推理非常高效。

（完）
