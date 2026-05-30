---
title: "Reflection-Bench: Evaluating Epistemic Agency in Large Language Models"
title_zh: Reflection-Bench：评估大型语言模型中的认知主体性
authors: "Lingyu Li, Yixu Wang, Haiquan Zhao, Shuqi Kong, Yan Teng, Chunbo Li, Yingchun Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=eff38SdyvN"
tags: ["query:agent-memory"]
score: 6.0
evidence: 评估LLM智能体的认知主体性，包含记忆维度
tldr: LLM作为智能体认知引擎时，其内在认知主体性（包括记忆）至关重要，论文提出Reflection-Bench，包含七个维度的任务（预测、决策、感知、记忆等），为智能体记忆系统设计提供了评估工具和基准认知框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 711, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1598, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1331, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1331, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1337, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1332, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1326, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1322, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 990, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1345, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1369, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1722, \"height\": 907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 853, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 834, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1306, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 889, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eff38sdyvn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1353, \"height\": 1092, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 778, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 1031, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1605, \"height\": 1033, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1606, \"height\": 1029, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1606, \"height\": 1032, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1620, \"height\": 1030, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1605, \"height\": 1031, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1605, \"height\": 1030, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eff38sdyvn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1849, \"height\": 2344, \"label\": \"Table\"}]"
motivation: 现有研究缺乏对LLM认知主体性（含记忆）的系统评估。
method: 设计包含七个认知维度的基准任务，特别强调记忆维度。
result: 该基准能够评估LLM在动态环境中的信念构建与更新能力。
conclusion: 为构建可靠AI智能体提供了重要的评估手段。
---

## Abstract
With large language models (LLMs) increasingly deployed as cognitive engines for AI agents, the reliability and effectiveness critically hinge on their intrinsic epistemic agency, which remains understudied. Epistemic agency, the ability to flexibly construct, adapt, and monitor beliefs about dynamic environments, represents a base-model-level capacity independent of specific tools, modules, or applications. We characterize the holistic process underlying epistemic agency, which unfolds in seven interrelated dimensions: prediction, decision-making, perception, memory, counterfactual thinking, belief updating, and meta-reflection. Correspondingly, we propose Reflection-Bench, a cognitive-psychology-inspired benchmark consisting of seven tasks with long-term relevance and minimization of data leakage. Through a comprehensive evaluation of 16 models using three prompting strategies, we identify a clear three-tier performance hierarchy and significant limitations of current LLMs, particularly in meta-reflection capabilities. While state-of-the-art LLMs demonstrate rudimentary signs of epistemic agency, our findings suggest several promising research directions, including enhancing core cognitive functions, improving cross-functional coordination, and developing adaptive processing mechanisms. Our code and data are available at https://github.com/AI45Lab/ReflectionBench.

---

## 论文详细总结（自动生成）

# 论文 Reflection-Bench 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：大型语言模型（LLMs）越来越多地被用作 AI 智能体的“认知引擎”，但它们在动态环境中灵活构建、适应和监控信念的能力——即“认知主体性”（epistemic agency）——尚未得到系统评估。现有基准要么关注具体应用，要么考察孤立能力，缺乏对agent-环境交互中完整认知过程的综合评价。此外，现有评估依赖文本密集数据集，存在基准泄露风险。
- **整体含义**：解决这一缺口有助于理解LLMs作为智能体核心的可靠性，并为开发更可信的AI智能体提供指导。通过认知心理学视角，将认知主体性分解为七个相互关联的维度，并提出 Reflection-Bench 基准，旨在评估LLMs在与环境互动中的基础能力，同时通过参数化设计最小化数据污染。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：借鉴人类认知过程中的“反思”循环（预测→决策→感知→记忆→反事实思维→信念更新→元反思），将认知主体性分解为七个维度，每个维度对应一个认知测试。
- **关键技术细节**：
  - **预测**（Weather Prediction Task, WPT）：基于传感器状态和当前天气预测下一日天气，使用随机转移矩阵，性能用估计与真实矩阵的MAE衡量。
  - **决策**（Wisconsin Card Sorting Test, WCST）：文本化卡片分类任务，规则（形状/颜色/数字）每12轮变化，模型需推断并适应规则，以匹配准确率为指标。
  - **感知**（Oddball Paradigm）：在8句序列中插入1句无关句子，让模型自由评论，评估自发性异常检测，采用人工+自动化(embedding相似度)评分。
  - **记忆**（N-back task）：字母序列，要求判断当前字母是否与n步前相同，例如2-back，用准确率衡量。
  - **反事实思维**（Double Choice Iowa Gambling Task, DC-IGT）：四副牌，每轮模型先选一副，观察得失后有机会重新选，评估能否通过反事实思考避免损失。
  - **信念更新**（Probabilistic Reversal Learning Task, PRLT）：两臂赌博机，奖励概率在中间反转，模型需根据反馈更新信念，用移动平均估计与真实概率的MAE评分。
  - **元反思**（Meta-Bandit Task, MBT）：类似PRLT但奖励每n轮固定反转，测试模型识别高阶模式（全局时间结构）的能力。
- **参数化设计**：所有任务（除Oddball）均可调整难度参数（如转移概率、反转步长等），以保证长期有效性并减少数据泄露风险。

## 3. 实验设计：数据集/场景、Benchmark、对比方法
- **数据集/场景**：无外部数据集，所有任务均为参数化生成的交互式认知测试，每个任务有“Easy”和“Hard”两套参数配置。
- **Benchmark**：Reflection-Bench，包含上述7个任务。
- **对比方法**：
  - 16个模型（按规模分组）：大型推理模型（o1-preview, o1-mini, DeepSeek-R1, QwQ-32B-Preview）、主流LLMs（GPT-4o, Claude-3.5-Sonnet, Grok-2, Gemini-2.0-flash, DeepSeek-V3, Llama-3.3-70B, GPT-4o-mini, Claude-3.5-Haiku）、Qwen 2.5系列（72B/32B/14B/7B）。
  - 三种提示策略：直接生成、自由输出、零样本CoT。
  - 额外：Centaur（用人类认知测试数据微调）及基础模型Llama-3.1-70B-Instruct作为对照，验证抗数据污染能力。
  - 随机模拟（100万次）获得各任务95分位数机会水平阈值。

## 4. 资源与算力
- 文中未明确说明使用的GPU型号、数量或训练时长。所有评估均通过相应模型的API完成（包括OpenAI、Anthropic、xAI、Google、DeepSeek、Meta、Qwen等），不涉及本地训练或微调。因此算力消耗主要取决于API调用次数，但具体资源未量化。

## 5. 实验数量与充分性
- **实验数量**：
  - 在Easy设置下，16个模型×3种策略（大型推理模型仅两种策略），共44个模型-策略组合，每个任务重复2次（Oddball重复3次）。
  - Hard设置下，16个模型使用直接生成策略，重复相同次数。
  - 抗污染验证：Centaur vs. base模型在Easy/Hard下均做直接生成。
  - 随机模拟100万次获取机会水平。
- **充分性**：实验覆盖了多种规模、多种类型的模型和三种提示策略，任务维度全面（7个维度），且有难度变化。但是：
  - 未能覆盖多模态或具身环境。
  - 缺少跨模型协作场景。
  - 存在提示策略不一致（大型推理模型未测CoT）。
  - 但仍可认为实验设计较为充分、客观，且与机会水平对比保证了统计显著性。

## 6. 论文的主要结论与发现
- **性能分层**：清晰的三层等级——顶级模型（>60分）：Claude-3.5-Sonnet, o1-preview, DeepSeek-R1等；中等模型（50-60分）：Llama-3.3-70B, GPT-4o-mini等；低等级（<50分）：Qwen-2.5-7B。
- **关键短板**：所有模型在元反思（MBT）上完全失败，无法识别简单的2步反转全局模式。预测（WPT）、决策（WCST）等维度也存在显著局限，多数模型仅在局部适应（如“赢-留-输-换”策略），缺乏全局理解。
- **提示策略差异**：CoT和自由输出整体优于直接生成，但效果因任务和模型而异，尤其对DC-IGT和N-back影响大，对PRLT和Oddball影响小。
- **长期有效性**：Hard设置下所有模型得分下降，证明基准未饱和且可区分。
- **抗污染性**：Centaur与基础模型表现无差异，证实参数化设计有效。
- **行为模式**：WCST中普遍“形状沉没”现象；WPT中只有少数模型正确学到两个转移矩阵；DC-IGT中多数模型过度“坚持有收益选择”。

## 7. 优点
- **创新框架**：首次将认知心理学中的“反思”循环系统映射到LLM评估，覆盖七个相互关联的认知维度，较之孤立评估更完整。
- **参数化设计**：通过调整任务参数避免数据泄露，并支持未来升级，具备长期有效性。
- **多维度分析**：不仅给出总分，还深入分析了每项任务的行为模式（如WCST规则组、DC-IGT切换行为、PRLT信念更新曲线等），提供丰富洞察。
- **对比全面**：涵盖16个模型、3种策略、Easy/Hard两种难度，并设置机会水平和抗污染对照实验。
- **自动化评分**：Oddball任务提出基于embedding的自动评分方法，与人工评分高度相关（r=0.87），提升可重复性。
- **开源**：代码和数据公开，便于复现和扩展。

## 8. 不足与局限
- **评估范围窄**：仅关注基础LLM的认知主体性，未涉及多模型协作、多模态或具身场景，生态效度可能有限。
- **任务设计限制**：所有任务均为结构化回合式交互，反馈信号明确，与开放对话或模糊指令环境有差距。
- **提示策略不一致**：大型推理模型因上下文长度限制未测试CoT，可能导致比较偏差。
- **缺少消融研究**：未分析各维度间的交互影响或不同任务难度的边际效益。
- **计算资源未记录**：虽通过API调用，但未报告总调用次数或成本，不利于复现资源需求。
- **模型时效性**：评估截止于2025年初，新模型（如o3、Claude-4）未涵盖，基准需定期更新。
- **元反思任务设计单一**：MBT只有一种反转模式，未测试更复杂高阶模式，不足以全面反映元认知能力。

（完）
