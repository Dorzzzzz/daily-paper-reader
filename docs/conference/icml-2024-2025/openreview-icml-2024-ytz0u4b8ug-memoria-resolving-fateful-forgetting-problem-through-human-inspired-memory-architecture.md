---
title: "Memoria: Resolving Fateful Forgetting Problem through Human-Inspired Memory Architecture"
title_zh: Memoria：通过类人记忆架构解决命运性遗忘问题
authors: "Sangjun Park, JinYeong Bak"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=yTz0u4B8ug"
tags: ["query:agent-memory"]
score: 9.0
evidence: 类人记忆架构
tldr: 神经网络长期记忆遗忘是一个关键问题。本文受人类记忆机制启发，设计了Memoria记忆系统，融合多种神经科学与心理学理论。实验证明Memoria在排序、语言建模和分类任务上优于传统方法，且印迹分析显示其具有首因效应、近因效应和时间邻近效应，为智能体长期记忆系统提供了生物启发式解决方案。
source: ICML-2024-Public
selection_source: conference_retrieval
motivation: 神经网络长期记忆遗忘问题，现有方法仅关注短期记忆。
method: 受人类记忆理论启发，设计包含多种认知机制的Memoria记忆系统。
result: 在多个任务上超越传统方法，表现出类人记忆特征。
conclusion: 为智能体长期记忆系统设计提供了有效架构。
---

## Abstract
Making neural networks remember over the long term has been a longstanding issue. Although several external memory techniques have been introduced, most focus on retaining recent information in the short term. Regardless of its importance, information tends to be fatefully forgotten over time. We present Memoria, a memory system for artificial neural networks, drawing inspiration from humans and applying various neuroscientific and psychological theories. The experimental results prove the effectiveness of Memoria in the diverse tasks of sorting, language modeling, and classification, surpassing conventional techniques. Engram analysis reveals that Memoria exhibits the primacy, recency, and temporal contiguity effects which are characteristics of human memory.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：神经网络（尤其是Transformer）在处理长序列时面临“命运性遗忘”（Fateful Forgetting）问题——现有外部记忆方法大多优先保留新信息，容量固定，导致旧信息被移除或稀释。这与人类能长期保留重要记忆的能力形成鲜明对比。
- **整体含义**：本文旨在设计一个受人类记忆系统启发的通用记忆模块，使神经网络能够像人类一样实现选择性、永久性的记忆存储，解决长期依赖任务中的遗忘问题。

## 2. 方法论

- **核心思想**：借鉴多存储模型（Multi-Store Model）、搜索联想记忆模型（SAM）和赫布理论（Hebbian Theory），构建三级记忆架构：工作记忆、短时记忆和长时记忆。
- **关键技术细节**：
  - **印迹（Engram）**：记忆的最小单元，包含嵌入向量、寿命和连接权重。
  - **工作记忆（WM）**：队列结构，固定大小，存储当前时刻的新印迹，作为检索线索。
  - **短时记忆（STM）**：队列结构，固定容量，存储近期印迹，采用位移机制（旧信息被新信息替换）。
  - **长时记忆（LTM）**：容量无限，存储从早期到近期的所有印迹，通过衰减（trace decay）和检索强化寿命。
  - **记忆图**：有向加权图，边权重表示条件概率 \( E_{i→j} = \frac{Count_{i,j}}{Count_{i,i}} \)，遵循“同时放电、同时连接”的赫布原则。
- **算法流程（三阶段）**：
  1. **检索阶段**：用工作记忆作为线索，计算与STM和LTM印迹的相关性权重（基于L2距离的高斯核），选出Top-K；再通过记忆图进行深度优先搜索（DFS），探索关联印迹。
  2. **利用阶段**：模型通过交叉注意力机制使用检索到的印迹辅助任务解决，并记录每个印迹的贡献权重（注意力权重）。
  3. **记忆与遗忘阶段**：检索到的印迹根据贡献获得额外寿命增量 \( Inc_i = \frac{w_i}{\sum w_k} \times |M^{rem}| \times \alpha \)；所有印迹寿命减1；寿命归零的印迹被移除；工作记忆转至STM，满溢的STM印迹转至LTM。

## 3. 实验设计

- **任务与数据集**：
  - **排序任务**：合成数据，序列长度1K~32K，符号频率排序，评估长期依赖保留能力。
  - **语言建模**：WikiText-103（词级）、PG-19（词级）、Enwik8（字符级）。
  - **文本分类**：Hyperpartisan（长文档二分类）。
- **基准方法**：
  - Transformer、Transformer-XL、Compressive Transformer、∞-former（排序和语言建模）；BERT、RoBERTa、BigBird、Longformer（分类）。
- **对比方式**：所有模型在相同条件下训练（从零训练或微调），使用相同的评估指标（准确率、困惑度、F1分数）。

## 4. 资源与算力

- **文中说明**：训练使用一块或多块NVIDIA A100或A6000 GPU，优化器为Adam，学习率线性调度，梯度裁剪为1.0。
- **未明确说明**：未给出具体GPU数量、训练总时长、能耗等细节，仅提及“一个或多个NVIDIA A100或A6000 GPU”。

## 5. 实验数量与充分性

- **主要实验**：排序任务（3种segment长度×4种序列长度×多种baseline），语言建模（3个数据集×5个模型），分类（3个预训练模型对比+消融）。另外包含：
  - **消融实验**：分别移除工作记忆、短时记忆、长时记忆，以及随机连接 vs. 赫布连接 vs. 全LTM搜索。
  - **超参数敏感性实验**：变化初始寿命、α、搜索深度、重置周期等。
  - **心理效应分析**：首因/近因效应、时间邻近效应、检索练习效应。
- **充分性评价**：实验覆盖多种任务类型（合成、语言、分类），消融设计全面，量化了各组件贡献；控制了训练公平性（相同架构、优化器、学习率）；心理分析验证了类人记忆特征。但缺少在更大规模LLM（如GPT-3级别）上的实验，且未与RAG类方法对比（作者解释了原因）。

## 6. 主要结论与发现

1. Memoria在排序任务中随序列长度增加性能下降最慢，有效缓解命运性遗忘。
2. 语言建模在所有三个数据集上取得最佳困惑度/字符级熵，优于Transformer-XL、Compressive Transformer等。
3. 分类任务中，Memoria RoBERTa在Hyperpartisan上达到最高F1和准确率，统计显著优于Longformer和BigBird。
4. 长时记忆检索印迹的平均年龄随时间稳步上升，表明模型持续引用旧信息。
5. 心理学效应复现：留下的印迹密度呈现首因和近因效应；印迹间边权重随创建时间差减小而增大（时间邻近效应）；检索事件呈现高自相关（检索练习效应）。
6. 赫布连接比随机连接带来更显著的性能提升，且图搜索在保持性能的同时大幅降低计算成本。

## 7. 优点

- **生物启发性强**：系统融合多存储模型、SAM、赫布理论、衰减理论、位移机制等，具有坚实的心理学/神经科学基础。
- **模块化设计**：作为独立模块，可方便地与多种Transformer架构（解码器/编码器）集成，无需修改原模型核心。
- **解决根本问题**：直接针对命运性遗忘，通过动态容量和选择性保留机制，而非仅扩展上下文窗口。
- **理论分析完整**：证明了赫布学习六条属性（局部性、协同性、突触抑制、有界性、竞争性、长期稳定性）。
- **分析深入**：不仅报告性能指标，还通过印迹年龄分布、连接权重等可视化揭示内在工作机理。

## 8. 不足与局限

- **计算开销**：检索阶段时间复杂度为 \( O(N^{rem}_{stm} \times N_{ltm} \times N_{depth}) \)，在大规模长期记忆下可能成为瓶颈；空间复杂度由于邻接矩阵为 \( O((N_{wm}+C_{stm}+N_{ltm})^2) \)。
- **实验覆盖有限**：仅测试了排序、语言建模、分类三类任务，未在强化学习、对话系统等更复杂的智能体场景中验证。
- **预训练模型依赖**：分类实验基于预训练BERT/RoBERTa，未从头训练，可能受预训练质量影响。
- **遗忘机制简化**：仅采用位移和衰减，未纳入干扰理论（interference theory）等更精细的遗忘模型，与真实人类记忆仍有差距。
- **隐私风险**：长期记忆可能积累用户隐私信息，论文仅提及需要谨慎处理，未提出具体保护机制。
- **与RAG比较缺失**：作者解释了两者目标不同，但实际应用中RAG也可用于长序列处理，缺少系统性对比可能削弱说服力。

（完）
