---
title: "Agentic Plan Caching: Test-Time Memory for Fast and Cost-Efficient LLM Agents"
title_zh: 智能体计划缓存：面向LLM智能体的快速且低成本的测试时记忆
authors: "Qizheng Zhang, Michael Wornow, Kunle Olukotun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=n4V3MSqK77"
tags: ["query:agent-memory"]
score: 9.0
evidence: 通过计划缓存为LLM智能体提供测试时记忆
tldr: LLM智能体在复杂工作流中因大量规划和推理导致高成本与延迟。现有缓存技术不适用于智能体场景。本文提出智能体计划缓存（APC），在测试阶段提取、存储并复用规划阶段的计划模板作为记忆。与传统语义缓存不同，APC提取结构化的计划模板，在语义相似任务间共享，显著降低服务成本与延迟，同时保持任务完成质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n4v3msqk77/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n4v3msqk77/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 975, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n4v3msqk77/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 695, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n4v3msqk77/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1251, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n4v3msqk77/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1390, \"height\": 382, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1308, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n4v3msqk77/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 611, \"label\": \"Table\"}]"
motivation: LLM智能体因规划推理导致高昂成本与延迟，现有缓存不适用。
method: 提出APC，提取并复用计划阶段的结构化模板作为测试时记忆。
result: 在多个智能体任务上显著降低延迟与成本，保持性能。
conclusion: 为LLM智能体的高效服务提供了有效的记忆缓存机制。
---

## Abstract
LLM-based agent applications have shown increasingly remarkable capabilities in complex workflows but incur substantial costs and latency due to extensive planning and reasoning requirements. 
Existing LLM caching techniques (like context caching and semantic caching), primarily designed for serving chatbots, are insufficient for agent applications where outputs depend on external data and environmental contexts. 
We propose **Agentic Plan Caching (APC)**, a novel **test-time memory** that extracts, stores, adapts, and reuses structured plan templates from planning stages of agent applications across semantically similar tasks to reduce the cost and latency of serving. 
Unlike traditional semantic caching, our system extracts plan templates from completed agent executions at test-time, employs keyword extraction to match new requests against cached plans, and utilizes lightweight models to adapt these templates to task-specific plans with contexts. 
Evaluation across multiple real-world agent applications shows that our system can reduce costs by 50.31\% and latency by 27.28\% on average while maintaining performance, offering a more efficient solution for serving LLM-based agents that complements existing LLM serving infrastructures.

---

## 论文详细总结（自动生成）

# Agentic Plan Caching 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

LLM-based agent 应用（如代码生成、网页导航、数据推理等）通常采用“Plan-Act”两阶段循环（类似于 ReAct），其中 **规划阶段（Plan）** 依赖昂贵的 LLM（如推理模型）进行多轮推理，导致服务成本高、延迟大。现有缓存技术（如上下文缓存 Context Caching、语义缓存 Semantic Caching）主要针对聊天机器人设计，存在三大局限：  
- **模型特定约束**：上下文缓存依赖 KV cache，无法跨模型复用；  
- **数据依赖输出**：智能体的输出依赖于外部数据或动态环境，而不仅仅是输入文本，语义缓存无法处理此类变化；  
- **适应性有限**：无法应对输入中的细微变化（如数值、变量名）。

因此，论文提出**智能体计划缓存（Agentic Plan Caching, APC）**，一种新型**测试时记忆**机制，从已完成智能体执行的规划阶段提取结构化计划模板，在语义相似的任务间复用，以降低服务成本和延迟，同时保持任务完成质量。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
将缓存从“查询级”（适合聊天）转向“任务级”（面向智能体），缓存的是**计划模板**而非完整的输入-输出对。

### 关键技术步骤
1. **关键词提取**：使用轻量模型（如 GPT-4o-mini）从输入查询中提取反映高层意图的关键词（如 `"working capital ratio"`），而非使用查询语义相似度（实验证明后者假阳性/假阴性率高）。
2. **缓存匹配**：采用**精确关键词匹配**（避免模糊匹配引入的阈值问题和延迟开销），在缓存中检索对应的计划模板。
3. **缓存命中** → **计划自适应**：使用小模型（如 LLaMa-3.1-8B）根据当前任务上下文（如公司名、年份）调整缓存模板，生成具体计划。
4. **缓存未命中** → **全模型生成 & 模板提取**：使用大模型（如 GPT-4o）生成新计划并执行；执行成功后，通过规则过滤 + 轻量LLM过滤生成通用模板（去除实体名称、数值等），连同关键词存入缓存。
5. **缓存更新**：生成的结构化模板包含“计划→演员响应→下一步计划”等步骤，保持可复用性。

### 算法流程（文字说明）
- 输入：查询 q，上下文 ctx，缓存 C  
- 1. 提取关键词  
- 2. 若关键词在缓存中 → 缓存命中：用小模型适配模板，执行计划-演员循环直到输出  
- 3. 若关键词不在缓存中 → 缓存未命中：用大模型生成计划，迭代执行；完成后从执行日志生成模板并存入缓存  
- 输出：最终结果和更新后的缓存

## 3. 实验设计：数据集、基准、对比方法

### 数据集与场景（5个）
- **FinanceBench**：金融数据推理（长文本数值问答），200个问题  
- **QASPER**：研究论文信息检索问答  
- **TabMWP**（Table Math Word Problems）：表格数学推理，200个问题  
- **AIME 2024 / 2025**：美国数学邀请赛（数学推理）  
- **GAIA**：通用AI助手（多步骤推理与工具使用）  

### 智能体架构
- 主要基于 **Minion 架构**（图1a）：规划LLM（大模型）+ 执行LLM（小模型），迭代协作。  
- 额外在 **Open Deep Research**（Hugging Face smolagents）上进行验证。

### 对比方法
- **Accuracy-Optimal**（无缓存，始终使用大规划模型）  
- **Cost-Optimal**（无缓存，始终用小规划模型）  
- **Semantic Caching**（基于查询语义相似度，阈值 0.8/0.85/0.9）  
- **Full-History Caching**（缓存完整执行日志作为上下文示例）  
- **Agentic Plan Caching (APC)**（提出的方法）

### 评估指标
- **准确率**：使用 GPT-4o 作为评估模型（LLM-as-a-Judge）  
- **成本**：基于 API 定价（输入/输出 token）  
- **延迟**：端到端运行时间

## 4. 资源与算力

论文主要使用商业 API 进行实验（OpenAI, TogetherAI, Anthropic），未提及具体的 GPU 型号、数量或训练时长。原型系统运行在 Runpod 服务器上（双路 Intel Xeon Gold 6342，96 vCPU，503GB RAM），但所有模型推理均通过第三方 API 完成，本地仅运行缓存逻辑和轻量模型（如 LLaMa-3.1-8B）的 API 调用。未说明训练过程（不涉及模型微调）。

## 5. 实验数量与充分性

- **主实验**：在 5 个数据集（FinanceBench, TabMWP, QASPER, AIME 2024, AIME 2025, GAIA）上进行了对比，覆盖从简单数值推理到复杂多步骤工具使用。  
- **消融实验与分析**：  
  - 与语义缓存（3个阈值）、全历史缓存对比；  
  - 缓存命中/未命中准确率对比；  
  - 成本分解（关键词提取、缓存生成占比仅 1.04%）；  
  - 延迟分析（总延迟降低 27.28%）；  
  - 缓存大小影响（从1到100个条目）；  
  - 精确匹配 vs 模糊匹配（精确匹配O(1)延迟，模糊匹配慢多个数量级）；  
  - 冷启动行为（模拟缓存逐渐预热）；  
  - 模型敏感性分析（更换大规划模型为 Claude 3.5 Sonnet，小规划模型为 Qwen-2.5-7B 或 Llama-3.2-3B，执行模型为不同变体）。  
- **实验充分性评价**：实验设计较全面，涵盖了多种场景、多种对比基线、多种模型组合，并分析了缓存机制各个方面的开销与权衡，结果客观可重复。但主要使用 API 实验，可能受 API 价格波动和网络延迟影响。

## 6. 论文的主要结论与发现

1. **成本降低**：APC 平均降低智能体服务成本 **50.31%**（在 FinanceBench 上从 $4.03 降至 $1.86）。  
2. **延迟降低**：平均降低端到端延迟 **27.28%**（在 FinanceBench 上从约 1959s 降至 1425s）。  
3. **准确率保持**：平均达到最优准确率的 **96.61%**（在 FinanceBench 上从 91% 降至 85.5%）。  
4. **与传统缓存对比**：语义缓存因假阳性严重损害准确率（如阈值0.9时缓存命中准确率下降 32%-56%）；全历史缓存因小模型处理长上下文不佳，准确率和成本均不如 APC。  
5. **开销极小**：缓存本身的成本（关键词提取+模板生成）仅占总成本的 1.04%（即使在最坏零命中率下也仅 1.31%）。  
6. **可扩展性**：精确匹配延迟极低（< 100 μs 在百万级缓存规模）；模糊匹配虽然可提升命中率但牺牲准确率和速度。  
7. **适用性**：不仅在 Minion 架构有效，在 Open Deep Research 上同样显著（成本降低 76.42%，准确率仅降 0.61%）。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：将缓存从查询级提升到任务级，专门针对 Plan-Act 智能体设计，填补了现有技术在智能体场景的空白。  
- **实用性**：系统设计兼顾成本、延迟和准确率，且兼容现有 LLM 服务框架和缓存技术，可直接集成。  
- **完整的实验分析**：不仅报告平均收益，还详细分析了冷启动、缓存大小、匹配策略、模型敏感性等实际部署中关键因素。  
- **低成本智能化**：使用轻量模型处理关键词提取和模板生成，避免引入过多开销。  
- **与 Case-Based Planning 的区分**：明确区别于传统符号规划，自动从无约束 LLM 生成中提取模板，更适应神经智能体。

## 8. 不足与局限

1. **智能体架构局限**：主要针对简单的两阶段 Plan-Act 架构，复杂的多智能体系统可能带来缓存一致性挑战。  
2. **动态负载场景**：对于频繁变化的任务（多样性高、重复少），缓存收益会下降。  
3. **冷启动问题**：缓存初始为空时，前几个查询需完整执行，成本/延迟较高（论文已分析并可预填充缓解）。  
4. **评估偏重成本**：主要关注成本（美元），对延迟、吞吐量、计算资源开销的分析相对较少。  
5. **依赖商业 API**：实验基于特定模型定价，成本降低的绝对值可能随 API 价格变化而不同；且未在开源模型本地运行环境下全面评估。  
6. **安全与隐私**：未深入讨论缓存包含敏感信息时的隐私泄露风险或缓存共享的安全问题。  
7. **基准覆盖**：虽然覆盖了多个数据集，但 GAIA 上的准确率绝对值不高（~37%），可能说明 APC 对高度异构的任务效果有限。  
8. **模板提取质量**：依赖执行成功才能生成模板，若初始执行有误则可能缓存错误模板（但论文假设正确执行后可利用）。

---

（完）
