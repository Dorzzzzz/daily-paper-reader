---
title: Self-Generated In-Context Examples Improve LLM Agents for Sequential Decision-Making Tasks
title_zh: 自生成上下文示例提升LLM智能体的序列决策能力
authors: "Vishnu Sarukkai, Zhiqiang Xie, Kayvon Fatahalian"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WdL3O58gde"
tags: ["query:agent-memory"]
score: 7.0
evidence: 自生成轨迹作为智能体记忆
tldr: "LLM智能体在序列决策中通常需要人工定制提示与示例。本文提出一种自动方法，智能体将自身成功轨迹存入数据库，并在未来任务中作为上下文示例复用。无需人工干预，该方法在ALFWorld、Wordcraft和InterCode-SQL三大基准上分别取得73%到89%、55%到64%、75%到79%的性能提升，超越了现有基于人类演示的方法。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 515, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 931, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 924, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wdl3o58gde/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 465, \"height\": 451, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1321, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1171, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 977, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1275, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1565, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1170, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1181, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wdl3o58gde/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1315, \"height\": 409, \"label\": \"Table\"}]"
motivation: LLM智能体依赖人工定制知识，缺乏自动从自身经验中学习的方法。
method: 构建自生成轨迹数据库，作为未来任务的上下文示例。
result: 在三个基准上均取得显著性能提升，超越人类演示方法。
conclusion: 自生成经验记忆是一种高效、无需人工的智能体提升策略。
---

## Abstract
Improving Large Language Model (LLM) agents for sequential decision-making tasks typically requires extensive task-specific knowledge engineering—custom prompts, curated examples, and specialized observation/action spaces. We investigate a different approach where agents automatically improve by learning from their own successful experiences without human intervention. Our method constructs and refines a database of self-generated trajectories that serve as in-context examples for future tasks. Even naive accumulation of successful trajectories yields substantial performance gains across three diverse benchmarks: ALFWorld (73\% to 89\%), Wordcraft (55\% to 64\%), and InterCode-SQL (75\% to 79\%). These improvements exceed those achieved by upgrading from gpt-4o-mini to gpt-4o and match the performance of allowing multiple attempts per task. We further enhance this approach with two innovations: database-level curation using population-based training to propagate high-performing example collections, and exemplar-level curation that selectively retains trajectories based on their empirical utility as in-context examples. With these enhancements, our method achieves 93\% success on ALFWorld—surpassing approaches that use more powerful LLMs and hand-crafted components. Our trajectory bootstrapping technique demonstrates that agents can autonomously improve through experience, offering a scalable alternative to labor-intensive knowledge engineering.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的LLM智能体（agent）在完成序列决策任务（如导航、交互式编程、合成游戏）时，往往依赖大量人工知识工程——包括定制提示（prompt tuning）、人工编写上下文示例、设计专门的观测/动作空间。这些方法将智能体性能的提升与人力投入直接挂钩，缺乏自动化和可扩展性。
- **研究动机**：探索一种替代路径——让LLM智能体通过自身成功经验自动提升性能，无需人工干预。核心思想是利用上下文学习（in-context learning），将智能体自己成功完成的轨迹作为未来任务的示例，从而实现自举（bootstrapping）。
- **整体含义**：论文证明，即便是简单积累成功轨迹就能带来显著性能提升，配合数据库级和示例级的策展策略，可使智能体性能超越使用更强大LLM和手工组件的现有方法。这为智能体自主进化提供了数据驱动的低成本方案。

## 2. 论文提出的方法论

### 核心思想
- 采用ReAct风格的智能体架构（含初始规划、推理、行动三个步骤），在每一步通过检索（Retrieve）从轨迹数据库中选择最相关的上下文示例。
- 智能体通过不断尝试训练任务，收集自身成功轨迹，存入数据库，供未来任务检索使用。形成“成功→积累→更多成功”的正反馈循环。

### 关键技术细节

#### 2.1 Traj-Bootstrap（基础自举方法）
- 初始化数据库：少量人工示例（或可为空）。
- 智能体依次尝试训练任务，仅将成功轨迹（s=1）加入数据库。
- 失败轨迹被丢弃，避免误导。
- 检索方式：多键KNN检索，使用平均余弦相似度；支持轨迹级检索（用于规划）和状态级检索（用于推理和行动），并采用滑动窗口提供上下文。

#### 2.2 +DB-Curation（数据库级策展）
- 维护N个并行数据库实例（论文取N=5）。
- 每次数据库大小翻倍时，根据近期任务成功率评估每个数据库性能，用表现最好的数据库替换表现最差的。
- 目的是传播优质数据库的整体属性（覆盖度、多样性、互补性），消除随机性带来的性能波动。

#### 2.3 +Exemplar-Curation（示例级策展）
- 为每个训练任务，从所有N个数据库的成功轨迹中，选择**经验效用最高的**单条轨迹存入复合数据库。
- 效用度量Q(τ)定义为轨迹被检索时关联任务的成功率加权平均（公式1）：
  \[
  Q(\tau) = \frac{\sum_{i \in R(\tau)} o_i \cdot f_i(\tau)}{\sum_{i \in R(\tau)} f_i(\tau)}
  \]
  其中 \(R(\tau)\) 是检索到该轨迹的任务集合，\(o_i\) 是任务结果（0/1），\(f_i(\tau)\) 是任务i中的检索频率。

#### 2.4 组合策略
- 将两个策展方法结合：先进行数据库级策展，再在得到的多个数据库上执行示例级策展，选出最佳轨迹。

## 3. 实验设计

### 使用的数据集/场景
- **ALFWorld**：文本环境的导航与物体操作任务（6类子任务），训练集3500个任务，测试集134个。
- **InterCode-SQL**：交互式SQL查询生成，基于Spider数据集，训练800个，测试234个。
- **Wordcraft**：组合元素合成游戏（类似Little Alchemy），训练4000个，测试500个。

### 基准方法
- **Fixed-DB**：仅使用固定的人工初始示例，不增长数据库。
- **Traj-Bootstrap**（本文基础方法）。
- **+DB-Curation**（数据库级策展）。
- **+Exemplar-Curation**（示例级策展）。
- **+DB+Exemplar-Curation**（两者组合）。
- **外部对比**：Autoguide、AutoManual（含手工观测/动作空间）、GameSQL（手工代理）、GPT-4o升级、pass@k（多次尝试）等。

### 实验结果概要
- 简单积累成功轨迹（Traj-Bootstrap）即在三个基准上分别提升16、9、4个百分点。
- 组合策展在ALFWorld上达到93%，超越AutoManual（使用更强LLM和手工组件）。
- 性能增益相当于将Fixed-DB的LLM从gpt-4o-mini升级到gpt-4o，或允许2~3次尝试。

## 4. 资源与算力

- **GPU**：1块NVIDIA A5000（24GB显存）用于嵌入计算；推理主要使用OpenAI API。
- **内存**：64GB RAM。
- **API调用量**：
  - ALFWorld：约200万次API调用。
  - InterCode-SQL：约20万次。
  - Wordcraft：约50万次。
- **总费用**：约3000美元（主要为GPT-4o-mini API费用）。
- **训练时长**：论文未给出具体训练时间，但提供了成本估算：完整配置（5个并行数据库，3500个训练任务）最坏情况数据库构建成本$600；测试时每个任务成本$0.034（ALFWorld）。
- **注意**：论文仅说明主要计算在API调用，嵌入和检索占比<5%。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验覆盖3个基准，每种方法重复5个随机种子，报告平均值和标准差。
  - 消融实验：有无初始人类示例（Wordcraft）、不同策展变体、数据库大小影响。
  - 额外实验：跨模型迁移（GPT-4o-mini收集的数据库用于Mixtral 8x7B）、微调对比（ReAct-Finetune）、成功率预测分类器（InterCode-SQL和Wordcraft）。
  - 对比实验：pass@k、模型升级、与外部方法（Autoguide、AutoManual、GameSQL）的比较。
- **充分性与公平性**：
  - 实验设计较为全面，覆盖多种维度。
  - 对比方法包括更强基线（如AutoManual使用gpt-4-turbo结合手工组件），论文方法仍表现更好。
  - 跨模型迁移实验验证了方法的通用性。
  - 但仅限三个benchmark，其他类型任务（如网页浏览、QA）未测试；且训练/测试集划分可能影响泛化。

## 6. 论文的主要结论与发现

1. **自生成轨迹积累有效**：简单Traj-Bootstrap即可在三个基准上显著提升成功率，且性能随数据库规模增加而提升（呈现边际递减）。
2. **策展策略进一步优化**：数据库级策展提升ALFWorld性能，示例级策展提升InterCode-SQL和Wordcraft；两者组合在ALFWorld和InterCode-SQL上达到最佳。
3. **性能超越人工方法**：使用gpt-4o-mini加上自生成数据库，在ALFWorld上超过使用gpt-4-turbo和手工组件的AutoManual。
4. **等效于测试时计算扩展**：单次尝试的性能相当于Fixed-DB进行2~3次尝试；策展后接近4~5次。
5. **可迁移性**：数据库可跨模型迁移（GPT-4o-mini → Mixtral 8x7B），仍获大幅提升，表明捕捉到任务结构而非模型特有人工痕迹。
6. **可用于微调**：自收集轨迹也可用于微调模型，性能与上下文方法相当或更好。
7. **成本优势**：长期部署下，训练一次性成本低于持续使用大模型或多次尝试，可节省大量费用。

## 7. 优点

- **自动化程度高**：无需人工编写示例或定制提示，智能体自主收集经验，降低了人力成本。
- **方法简洁有效**：基于上下文学习，无需修改模型参数，易于部署和迁移。
- **创新性策展**：数据库级和示例级策展机制有效提升数据库质量，且两者可互补。
- **全面的成本分析**：包括训练成本、推理成本、与替代方案的盈亏平衡点，证明了经济可行性。
- **跨模型泛化**：验证了数据库的通用性，不仅限于特定LLM。
- **实验设计严谨**：多随机种子、多维度对比、消融、迁移、微调等，结果可靠。

## 8. 不足与局限

- **依赖初始人工示例**：虽然可空数据库启动，但实验表明初始人类示例显著影响最终性能，未能完全摆脱人工依赖。
- **样本效率低**：需要大量训练任务（数千个）才能获得显著提升，小样本场景可能不适用。
- **性能波动**：训练过程中成功率非单调递增，存在波动；数据库级策展在早期因样本不足可能引入噪声。
- **失败轨迹未充分利用**：仅保留成功轨迹，失败轨迹虽用于策展的检索统计，但未用于信用分配或主动学习。
- **基准覆盖有限**：仅测试三个文本/代码类任务，未涉及更复杂的多模态、真实网页等场景。
- **计算成本**：训练阶段因多数据库并行而增加N倍成本，对于资源受限场景可能不友好。
- **缺乏理论保证**：方法基于经验，未提供收敛性或最优性理论分析。
- **可能过拟合**：在固定训练任务集上策展，可能对未出现过的测试分布泛化不足（但跨模型实验部分缓解此担忧）。

（完）
