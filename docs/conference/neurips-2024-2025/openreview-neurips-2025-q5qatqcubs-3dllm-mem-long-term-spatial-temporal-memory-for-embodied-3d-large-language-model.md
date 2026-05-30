---
title: "3DLLM-Mem: Long-Term Spatial-Temporal Memory for Embodied 3D Large Language Model"
title_zh: 3DLLM-Mem：具身3D大语言模型的长期时空记忆
authors: "Wenbo Hu, Yining Hong, Yanjun Wang, Leison Gao, Zibu Wei, Xingcheng Yao, Nanyun Peng, Yonatan Bitton, Idan Szpektor, Kai-Wei Chang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=q5QaTQcUbS"
tags: ["query:agent-memory"]
score: 8.0
evidence: 为具身3D大语言模型智能体设计长期时空记忆
tldr: 该论文针对大语言模型在动态多房间3D环境中规划和行动困难的问题，指出缺乏恰当的3D时空记忆建模是关键。为此提出了3DLLM-Mem，一种动态记忆管理与融合模型，并构建了3DMem-Bench基准。实验表明，该记忆机制显著提升了智能体在长期任务中的空间-时序推理和动作能力，填补了具身智能体长期记忆研究的空白。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 1154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1156, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-q5qatqcubs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1404, \"height\": 1496, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-q5qatqcubs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q5qatqcubs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q5qatqcubs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q5qatqcubs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-q5qatqcubs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1226, \"height\": 1781, \"label\": \"Table\"}]"
motivation: 现有LLM在动态3D环境中缺乏长期时空记忆，导致规划与行动能力不足。
method: 提出3DLLM-Mem动态记忆管理与融合模型，结合空间-时间信息进行推理与动作。
result: 在3DMem-Bench上，3DLLM-Mem在问答和具身任务中优于无记忆基线。
conclusion: 长期时空记忆是提升具身LLM智能体在3D环境中性能的关键。
---

## Abstract
Humans excel at performing complex tasks by leveraging long-term memory across temporal and spatial experiences. In contrast, current Large Language Models (LLMs) struggle to effectively plan and act in dynamic, multi-room 3D environments. 
We posit that part of this limitation is due to the lack of proper 3D spatial-temporal memory modeling in LLMs. 
To address this, we first introduce 3DMem-Bench, a comprehensive benchmark comprising over 26,000 trajectories and 2,892 embodied tasks, question-answering and captioning, designed to evaluate an agent's ability to reason over long-term memory in 3D environments.
Second, we propose 3DLLM-Mem, a novel dynamic memory management and fusion model for embodied spatial-temporal reasoning and actions in LLMs. 
Our model uses working memory tokens, which represents current observations, as queries to selectively attend to and fuse the most useful spatial and temporal features from episodic memory, which stores past observations and interactions. Our approach allows the agent to focus on task-relevant information while maintaining memory efficiency in complex, long-horizon environments.
Experimental results demonstrate that 3DLLM-Mem achieves state-of-the-art performance across various tasks, outperforming the strongest baselines by 16.5\% in success rate on 3DMem-Bench's  most challenging in-the-wild embodied tasks.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有大语言模型（LLM）在动态、多房间的3D环境中难以有效规划与行动，根本原因在于缺乏对3D空间-时间（spatial-temporal）长期记忆的恰当建模。人类能够自然地将工作记忆（当前观察）与情景记忆（过往经验）结合，进行推理和决策，而当前的具身3D-LLM智能体面临两大挑战：① 无法在长时间、多视觉场景（如多个房间）的任务中维持长记忆链；② 空间记忆与时间记忆纠缠，难以跟踪物体位置随时间的变化。
- **整体含义**：该论文旨在通过引入明确的长期记忆机制，填补具身智能体在3D场景中空间-时序推理能力的空白，使LLM能够更好地完成需跨房间、跨时间步的复杂具身任务。

## 2. 论文提出的方法论

- **核心思想**：受人类认知结构启发，设计双记忆系统——工作记忆（Working Memory）和情景记忆（Episodic Memory），并通过注意力融合机制动态整合二者信息。
- **模型架构**：基于LLaVA-3D（使用多视图图像+3D位置编码构建3D patch tokens），扩展上下文窗口至8192 tokens。
- **关键技术细节**：
  - **情景记忆管理**：每个时间步的观测经MLP投影到记忆特征空间，并加入正弦时间位置编码，存入记忆库（Memory Bank）。
  - **记忆融合模块**：
    - 以当前时间步的工作记忆 tokens 作为查询（query）特征 \( f_Q^t \in \mathbb{R}^{N \times M} \)。
    - 从情景记忆库中检索对应的键（key）\( f_K \in \mathbb{R}^{T \times N \times M} \) 和值（value）\( f_V \in \mathbb{R}^{T \times N \times M} \)。
    - 计算记忆交叉注意力：
      \[
      f_{Q_{\text{fuse}}} = \text{Softmax}\left(\frac{f_Q^t (f_K)^\top}{\sqrt{C}}\right) f_V
      \]
    - 将融合特征与工作记忆特征拼接得到最终记忆增强表示：
      \[
      f_M = \text{Concat}\left( [f_{Q_{\text{fuse}}}; f_Q^t] \right)
      \]
  - **记忆更新**：当智能体移动到新环境时，当前工作记忆转入情景记忆；若对应环境已被修改，则在记忆库中更新条目，保持动态性。
- **算法流程（文字说明）**：智能体在每个时间步收集RGB-D观测及相机位姿 → 编码为3D patch tokens → 当前观测作为工作记忆 → 使用工作记忆查询过去情景记忆，通过注意力融合获得增强特征 → 与语言指令一起输入LLM生成下一步行动（如导航、抓取、放置等）→ 交互后更新记忆。

## 3. 实验设计

- **数据集与场景**：
  - 基础环境：Habitat-Matterport 3D（HM3D）语义数据集，筛选后包含182个3D场景、2602个房间。
  - 交互物体：从Objaverse添加800K个3D物体，增强任务多样性。
  - 任务轨迹生成：使用Gemini（大型语言模型）基于框-演示-指令提示生成，并通过模拟管线验证（约24%通过率）。
- **所提基准：3DMem-Bench**：
  - 具身任务：1860个测试任务，分为简单（3个房间）、中等（5个房间）、困难（10个房间）；包含域内和域外（in-the-wild）设置。
  - 长记忆EQA：空间推理、长期目标导航、比较推理、多房间布局理解、语义计数（共865个问题）。
  - 字幕任务：167个长场景字幕。
  - 总计：26k+训练轨迹。
- **对比方法**：
  - 3D-LLM（微调版）
  - Everything in Context（全部观测放上下文，仅小场景可行）
  - Most Recent Memory（仅保留最近观测）
  - Retrieval-Augmented Memory（基于检索的记忆）
  - 3D-Mem（基于GPT-4o/Gemini的3D场景记忆框架，仅用于EQA和字幕，无具身动作支持）
  - 提出的3DLLM-Mem

## 4. 资源与算力

- **训练硬件**：8个Google Cloud TPU v5p核心，批次大小256，训练1000步，约耗时1天。
- **超参数**：Adam优化器，学习率2e-5（线性预热3%步数至1e-5，随后余弦退火），无权重衰减。
- **实验开销**：文中未报告详细的总计算量（如PFLOPS），但指出由于训练成本高，未多次运行计算误差条。

## 5. 实验数量与充分性

- **实验组数**：
  - 表2a：具身任务（3个难度 × 域内/野外 × 7种方法）—— 共42个条件。
  - 表2b：集成所有任务（具身、EQA五子类、字幕）—— 共6种方法，报告多个指标。
  - 表3：消融实验（3种查询初始化设计 × 3个难度 × 域内/野外）—— 共18个条件。
  - 此外，还有定性示例、EQA的LLM-as-judge评估。
- **充分性与公平性**：
  - 对比了多种代表性基线，包括无记忆、最近记忆、检索增强记忆以及现有3D-LLM和3D-Mem。
  - 域内和域外（in-the-wild）场景划分公平，域外任务还引入了未见物体和新挑战。
  - **不足**：未报告多次运行的误差条（仅单次实验），可能影响统计稳定性；消融仅针对查询初始化，未深入分析记忆容量、注意力机制变体等。

## 6. 论文的主要结论与发现

- 3DLLM-Mem在所有任务上显著优于现有方法：在最具挑战的域外困难具身任务中，成功率（SR）达27.8%，而最强基线（Retrieval-Augmented Memory）仅约4.8%。
- 在EQA任务中，3DLLM-Mem在空间关系、导航、比较、布局和计数等子类上均取得最佳成绩（如空间关系62.8% vs 最近记忆27.5%）。
- 字幕任务中，3DLLM-Mem也取得最高BLEU和METEOR分数。
- 实验表明，使用工作记忆作为融合查询比使用最近情景记忆或可学习零参数更有效。
- 随着任务难度增加，其他方法性能急剧下降，而3DLLM-Mem保持相对稳定，证明了长期记忆表示的可扩展性和有效性。

## 7. 优点

- **方法创新**：首次尝试将密集3D表示作为具身LLM的长期记忆，并设计端到端可学习的记忆融合机制，能根据当前任务选择性聚焦相关信息。
- **基准全面性**：3DMem-Bench覆盖具身任务（含多房间长序列）、EQA（时空变化推理）和字幕，支持细粒度难度（简单/中/难）及域外泛化评估，填补了先前基准的空白。
- **实验设计合理**：评估了多种记忆策略（全上下文、最近、检索），并与专用3D-Mem和3D-LLM对比，验证了记忆融合的有效性。
- **泛化能力**：在in-the-wild场景下显著优于所有基线，表明模型不仅记忆能容量强，且能适应未见环境。

## 8. 不足与局限

- **低级控制空缺**：模型仅使用预定义高级动作（如`<GO TO ROOM>`、`<PICK UP>`），不涉及低级导航和底层控制策略。作者承认这与记忆研究正交，但限制了直接部署到真实机器人。
- **记忆更新依赖预收集数据**：环境变化对应的观测在训练/推理前已预存，未实现在线重建或实时更新，可能影响动态场景适应。
- **单物体持有限制**：智能体一次只能持有一个物体，与现实复杂操作不符。
- **计算资源限制**：训练仅运行一次，未报告置信区间；消融实验仅改变查询初始化，缺乏对记忆容量、注意力头数、时间编码方式等的系统分析。
- **继承风险**：基于LLaVA-3D和CLIP，可能继承幻觉、偏见等问题（论文在附录A中承认）。
- **评估规模**：EQA和字幕任务的样本数相对较小（865和167），但具身任务（1860）较为充分。

（完）
