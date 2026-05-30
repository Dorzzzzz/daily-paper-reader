---
title: "MemSim: A Bayesian Simulator for Evaluating Memory of LLM-based Personal Assistants"
title_zh: MemSim：用于评估LLM个人助手记忆能力的贝叶斯模拟器
authors: "Zeyu Zhang, Quanyu Dai, Luyu Chen, Zeren Jiang, Rui Li, Jieming Zhu, Xu Chen, Yi Xie, Zhenhua Dong, Ji-Rong Wen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vAT2xlaWJY"
tags: ["query:agent-memory"]
score: 7.0
evidence: 用于评估LLM个人助手记忆能力的贝叶斯模拟器
tldr: LLM智能助手的记忆能力缺少客观评估方法。MemSim提出贝叶斯模拟器，通过贝叶斯关系网络和因果生成机制从用户消息中自动构建可靠的问答对，减少幻觉影响，实现记忆能力的自动评估。该工具为记忆系统设计提供了重要的评测手段。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vat2xlawjy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 752, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 765, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1465, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1444, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1447, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1443, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1445, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1446, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1447, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1443, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1445, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1446, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1441, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1439, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1478, \"height\": 1821, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1439, \"height\": 1314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vat2xlawjy/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1425, \"height\": 993, \"label\": \"Table\"}]"
motivation: 现有方法缺乏对LLM智能助手记忆能力的客观自动评估。
method: 提出贝叶斯关系网络和因果生成机制，自动从用户消息构建可靠问答对进行评估。
result: MemSim生成的高质量问答对有效评估了智能助手的记忆能力。
conclusion: 该模拟器为智能体记忆系统的评估提供了标准化工具。
---

## Abstract
LLM-based agents have been widely applied as personal assistants, capable of memorizing information from user messages and responding to personal queries. However, there still lacks an objective and automatic evaluation on their memory capability, largely due to the challenges in constructing reliable questions and answers (QAs) according to user messages. In this paper, we propose MemSim, a Bayesian simulator designed to automatically construct reliable QAs from generated user messages, simultaneously keeping their diversity and scalability. Specifically, we introduce the Bayesian Relation Network (BRNet) and a causal generation mechanism to mitigate the impact of LLM hallucinations on factual information, facilitating the automatic creation of an evaluation dataset. Based on MemSim, we generate a dataset in the daily-life scenario, named MemDaily, and conduct extensive experiments to assess the effectiveness of our approach. We also provide a benchmark for evaluating different memory mechanisms in LLM-based agents with the MemDaily dataset.

---

## 论文详细总结（自动生成）

# MemSim：用于评估LLM个人助手记忆能力的贝叶斯模拟器 - 中文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：LLM驱动的个人助手需要记忆用户历史消息中的事实信息，以提供个性化回复。但目前缺乏**客观、自动**的评估方法来衡量其记忆能力。
- **挑战**：传统方法依赖人工标注（成本高、可扩展性差）或LLM直接生成问答对（LLM幻觉导致ground truth可靠性低，尤其在复杂场景下正确率可能低于40%）；同时LLM倾向于生成“最可能”的用户档案，缺乏多样性。
- **整体贡献**：提出MemSim，一个基于贝叶斯模拟器的自动化评测工具，能够从生成用户消息中自动构建可靠的问答对，兼顾可靠性、多样性和可扩展性，并基于此构建了日常生活场景数据集MemDaily及基准评测。

## 2. 论文提出的方法论
- **核心思想**：通过**贝叶斯关系网络（BRNet）** 建模用户实体与属性的概率分布，采样出多样化的用户档案；再通过**因果生成机制**从档案中提取结构化提示（hints），基于同一hints同时生成用户消息和问答对，确保事实一致性并消除LLM幻觉对ground truth的影响。
- **关键技术细节**：
  - **BRNet**：有向无环图（DAG），节点为属性（如年龄、职业），边为因果依赖关系。假设满足局部马尔可夫性，通过祖先采样（Ancestral Sampling）从条件概率分布中高效采样属性值，无需计算高维联合概率。
  - **因果生成机制**：
    - 从用户档案中选择目标实体和属性，形成hints列表 \( H = \{ (A^{(j)}, K^{(j)}, v^{(j)}) \} \)。
    - 每个hint由LLM重写为一条用户消息（仅做语法改写，不添加新事实）。
    - 基于hints构建五种类型的QA（单跳、多跳、比较、聚合、后处理），同时生成文本答案、选择题选项和检索目标。
    - 注入两种噪声（实体侧噪声、属性侧噪声）模拟真实场景。
  - **公式/算法**（文字说明）：
    - BRNet的联合概率分解：\( P(X_1,...,X_{|X|}) = \prod_{X_t} P(X_t \mid \text{par}(X_t)) \)。
    - 祖先采样：按拓扑序依次采样 \( \tilde{x}_t \sim P(X_t \mid \text{par}(\tilde{x}_t)) \)，等价于联合分布采样。
    - 因果机制中，hints是消息和QA的共同“原因”，LLM仅负责重写，保证事实链条的可靠性。

## 3. 实验设计
- **数据集/场景**：
  - 生成**MemDaily**数据集：日常生活场景，包含11个实体（用户本人、同事、亲属、事件、地点、物品等）、73个属性，共生成6个子数据集（Simple, Conditional, Comparative, Aggregative, Post-processing, Noisy），总计2,954条轨迹（每条轨迹包含多条用户消息+一个QA），26,003条消息。
  - 基准测试中使用的**MemDaily-vanilla**（原始）和**MemDaily-η**（通过插入无关帖子增加难度，η=10,50,100,200）。
- **Benchmark**：
  - **用户档案评估**：对比方法为JointPL（联合生成）、SeqPL（顺序生成）、IndePL（独立生成）；指标为合理性（人工评分R-Human、GPT评分R-GPT）和多样性（Shannon-Wiener Index SWI-R/SWI-O/SWI-A）。
  - **用户消息评估**：对比方法为ZeroCons（无约束）、PartCons（部分约束）、SoftCons（软约束）；指标为流畅性、合理性、自然性、信息量（人工评分）和实体多样性（SWI-P）。
  - **问答可靠性评估**：人工抽样20%轨迹检查文本答案、选择题答案、检索目标的正确率。
  - **记忆机制Benchmark**：
    - 记忆机制：FullMem（全部消息）、RetrMem（FAISS检索Top-5）、ReceMem（最近k条）、NonMem（无记忆）、NoisyMem（仅无关消息）、OracleMem（仅目标消息）。
    - 基础模型：GLM-4-9B（主要）、Qwen2.5-7B（补充）。
    - 指标：Accuracy、Recall@5、Response Time、Adaptation Time。

## 4. 资源与算力
- **未明确说明**：文中没有提及使用的GPU型号、数量、训练时长等具体算力信息。仅提到使用GLM-4-9B和Qwen2.5-7B进行推理，并采用Llama-160m进行嵌入检索。数据集生成过程也未说明硬件配置。

## 5. 实验数量与充分性
- **实验数量**：涵盖了档案评估、消息评估、问答可靠性评估、基准测试等多个维度，每个实验均报告了均值与标准差（多次运行）。基准测试包括6个子数据集 × 2种难度（vanilla和η=100） × 6~7种记忆机制，并额外做了η=10/50/200的扩展实验以及Qwen2.5-7B的补充实验。消融实验通过BRNet与无先验方法对比体现其有效性。
- **充分性**：
  - 客观上：评估了生成数据的多个侧面（档案合理性/多样性、消息质量、问答正确率），并用人工+GPT双重验证。
  - 公平性：基线方法覆盖了主流生成策略和无记忆/有记忆机制，统计指标完备（准确率、召回率、时间开销）。
  - 局限：数据集仅基于合成用户档案，未在真实用户交互数据上验证；仅评估事实记忆，未覆盖偏好、情感等抽象记忆。

## 6. 论文的主要结论与发现
- **档案与消息质量**：MemSim在用户档案的合理性（R-Human=4.91）和多样性（SWI-A=3.05）上显著优于其他基线；消息生成在高约束条件下仍保持高流畅性和合理性（均≈4.9），并具有最高实体多样性。
- **问答可靠性**：人工验证显示文本答案正确率99.8%、选择题正确率99.5%、检索目标正确率99.8%，证明了因果机制有效抑制了LLM幻觉。
- **记忆机制基准**：
  - FullMem和RetrMem在准确性上整体最优，但FullMem在上下文极长时响应时间显著增加；RetrMem在召回上在长上下文下优于LLM直接召回。
  - 聚合类（Aggregative）问题对所有方法都困难（准确率约32%），表明LLM在数值聚合推理上存在瓶颈。
  - OracleMem显示即使检索准确，聚合类问题仍难，说明推理瓶颈而非检索瓶颈。
  - 噪声环境下，ReceMem在MemDaily-100中准确率大幅下降（0.5→0.5），而RetrMem保持稳定。

## 7. 优点
- **创新性**：首次提出针对LLM个人助手记忆能力的**客观、自动化评估框架**，解决了手动标注成本高和LLM幻觉导致数据不可靠的问题。
- **方法设计亮点**：
  - BRNet通过DAG建模属性间的因果依赖，结合祖先采样，既保证了合理性又提升了多样性。
  - 因果生成机制将消息和QA的生成“绑定”在同一hints上，切断LLM幻觉向ground truth传播的路径，从而保障事实准确性。
  - 自动生成五种类型的QA（包括比较、聚合、后处理等复杂类型）并注入噪声，覆盖了现实场景的多样性需求。
- **实用性**：开源了MemDaily数据集和代码，提供了标准化的基准，方便社区进行公平比较和后续研究。

## 8. 不足与局限
- **评估范围有限**：仅评估了**事实信息**的记忆能力，未涉及用户偏好、情感、意图等更高层次的抽象信息；也未包含**对话形式**（多轮交互），评估场景局限于单轮QA。
- **合成数据偏差**：所有数据基于人工定义的11个实体和73个属性生成，可能与真实用户交互的分布存在差异，外推到其他场景（如专业领域、多语言）需验证。
- **LLM重写风险**：尽管设计了因果机制，但LLM在“重写”过程中仍可能引入微小偏差（如信息丢失或语法变化），导致极少数case的ground truth不精确（约0.2%错误率）。
- **可扩展性验证不足**：BRNet的扩展（增加实体、属性、新场景）仅理论说明，未做实证测试。
- **伦理考量**：未讨论数据集可能被用于生成虚假个人档案或隐私泄露风险，也未提供使用限制或安全措施。

（完）
