---
title: "AgentPoison: Red-teaming LLM Agents via Poisoning Memory or Knowledge Bases"
title_zh: AgentPoison：通过毒化记忆或知识库对LLM智能体进行红队测试
authors: "Zhaorun Chen, Zhen Xiang, Chaowei Xiao, Dawn Song, Bo Li"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Y841BRW9rY"
tags: ["query:agent-memory"]
score: 7.0
evidence: 通过毒化记忆或知识库对智能体进行红队测试
tldr: LLM智能体依赖记忆或知识库，但其安全性存疑。AgentPoison提出首个针对通用RAG智能体的后门攻击，通过毒化记忆或知识库操纵智能体行为。该工作揭示了记忆系统设计中的安全隐患，为防御提供了重要参考。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 692, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1431, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1462, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1460, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1232, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1456, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1418, \"height\": 2063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1440, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y841brw9ry/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 623, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 1003, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1233, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1080, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 719, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y841brw9ry/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 649, \"label\": \"Table\"}]"
motivation: 智能体依赖外部知识库，但其安全性未得到充分检验。
method: 提出后门攻击方法，通过向记忆或知识库注入恶意样本来操纵智能体行为。
result: 实验证明攻击在多个任务上成功率极高。
conclusion: 记忆系统的安全性是智能体应用的重要考量。
---

## Abstract
LLM agents have demonstrated remarkable performance across various applications, primarily due to their advanced capabilities in reasoning, utilizing external knowledge and tools, calling APIs, and executing actions to interact with environments. Current agents typically utilize a memory module or a retrieval-augmented generation (RAG) mechanism, retrieving past knowledge and instances with similar embeddings from knowledge bases to inform task planning and execution. However, the reliance on unverified knowledge bases raises significant concerns about their safety and trustworthiness. To uncover such vulnerabilities, we propose a novel red teaming approach AgentPoison, the first backdoor attack targeting generic and RAG-based LLM agents by poisoning their long-term memory or
RAG knowledge base. In particular, we form the trigger generation process as a constrained optimization to optimize backdoor triggers by mapping the triggered instances to a unique embedding space, so as to ensure that whenever a user instruction contains the optimized backdoor trigger, the malicious demonstrations are retrieved from the poisoned memory or knowledge base with high probability. In the meantime, benign instructions without the trigger will still maintain normal performance. Unlike conventional backdoor attacks, AgentPoison requires no additional model training or fine-tuning, and the optimized backdoor trigger exhibits superior transferability, resilience, and stealthiness. Extensive experiments demonstrate AgentPoison's effectiveness in attacking
three types of real-world LLM agents: RAG-based autonomous driving agent, knowledge-intensive QA agent, and healthcare EHRAgent. We inject the poisoning instances into the RAG knowledge base and long-term memories of these agents, respectively, demonstrating the generalization of AgentPoison. On each agent, AgentPoison achieves an average attack success rate of $\ge$ 80% with minimal
impact on benign performance ($\le$ 1%) with a poison rate < 0.1%. The code and data is available at https://github.com/BillChan226/AgentPoison.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
LLM 智能体在自动驾驶、医疗、知识问答等安全关键场景中广泛应用，它们通常依赖记忆模块或检索增强生成（RAG）机制从外部知识库中检索历史经验来辅助规划与执行。然而，这些知识库可能被不可信来源污染，现有对 LLM 的 jailbreak（如 GCG）和 backdoor（如 BadChain）攻击在 RAG 智能体上效果差，因为检索过程的弹性和知识库的多样性削弱了攻击效果。为此，作者提出 **AgentPoison**——首个针对通用 RAG 智能体的后门攻击，通过向长期记忆或知识库注入极少量恶意样本，使含优化触发器的用户指令高概率检索到这些样本，从而诱导智能体执行预设恶意动作，同时保证无触发器的正常查询性能几乎不受影响。该工作揭示了 RAG 智能体记忆系统的安全漏洞，为后续防御研究提供了重要参照。

## 2. 方法论

### 核心思想
将触发器优化建模为**约束优化问题**，联合最大化三个目标：
- **检索有效性**：含触发器的查询能被映射到嵌入空间中与良性查询分离的**唯一且紧凑**的区域，从而高概率检索到注入的恶意样本。
- **目标生成**：在检索到恶意样本后，LLM 智能体能输出预设的恶意动作（如自动驾驶的“急停”）。
- **文本连贯性**：含触发器的查询应保持自然、难以被检测（如低困惑度）。

### 关键技术细节
定义四个损失函数：
- **唯一性损失 L_uni**：使含触发器的查询嵌入远离所有良性查询的聚类中心，降低与良性样本的相似度。
- **紧凑性损失 L_cpt**：使不同含触发器的查询嵌入彼此靠近，形成紧凑簇，提升检索稳定性。
- **目标生成损失 L_tar**：最大化 LLM 输出恶意动作的概率（通过交叉熵或近似采样）。
- **连贯性损失 L_coh**：通过小型语言模型（如 GPT-2）计算触发器的语言建模困惑度，保证可读性。

### 算法流程
采用**梯度引导的束搜索**迭代优化离散触发器：
1. **初始化**：用 LLM 生成任务相关的初始触发器作为束候选。
2. **梯度近似**：对每个束，随机选一个 token，计算当前损失对 token 嵌入的梯度，生成替换候选集。
3. **约束过滤**：先按 L_coh 采样，再通过 soft 约束（L_tar 单调递增或低于阈值）筛选候选。
4. **替换与迭代**：选择使总损失下降的 token 替换，更新束，直至收敛。

**无需额外模型训练**，仅需白盒访问查询编码器（实验表明触发器可转移至黑盒编码器如 OpenAI-ADA）。

## 3. 实验设计

### 数据集/场景
- **Agent-Driver**（自动驾驶）：23k 条经验记忆，测试集 250 条。
- **ReAct-StrategyQA**（知识密集型问答）：10k 条 Wikipedia 片段，测试集 229 条。
- **EHRAgent**（医疗记录管理）：初始 4 条经验，人工扩展至 700 条，测试集 100 条。

### Benchmark
对比基线包括：
- **GCG**（通用 jailbreak）
- **AutoDAN**（可读性 jailbreak）
- **CPA**（语料毒化攻击）
- **BadChain**（后门链式提示）

### 评估指标
- **ASR-r**：检索成功率（所有检索结果均为恶意样本）
- **ASR-a**：条件目标动作成功率（在成功检索下生成恶意动作）
- **ASR-t**：端到端目标影响成功率（对环境的实际恶意后果，如轨迹偏差、错误答案、删除操作）
- **ACC**：良性准确率（无触发器时智能体性能）

### 实验设置
- 针对每种智能体设计了特定的恶意目标和后门策略（如自动驾驶的“急停”对应轨迹偏差阈值）。
- 毒化比例均 < 0.1%（Agent-Driver 注入 20 条，ReAct 4 条，EHRAgent 2 条）。
- 触发器长度分别为 6、5、2 个 token。

## 4. 资源与算力
论文**未明确说明**使用的 GPU 型号、数量或训练时长。但代码已开源（GitHub），且方法无需训练 LLM 本身，主要开销在于触发器优化中的梯度计算和束搜索。

## 5. 实验数量与充分性

- **主实验**（Table 1）：覆盖 4 种 LLM 骨干（GPT-3.5、LLaMA-3-70b）与 2 种检索器（端到端、对比学习）的 3 个智能体，共 12 个设置，每个设置与 4 个基线对比。
- **消融实验**（Table 2）：逐一移除 L_uni、L_cpt、L_tar、L_coh，分析各组件贡献。
- **韧性实验**（Table 3）：对触发器进行字母插入、单词插入、语义改写三种扰动，测量性能变化。
- **防御实验**（Table 4 & Fig. 5）：测试困惑度过滤和查询重写两种防御下的 ASR-t，并对比查询困惑度分布。
- **转移性实验**（Fig. 3, 7, 8）：在 5 种不同编码器（DPR、ANCE、BGE、REALM、ORQA）及 OpenAI-ADA 之间验证触发器可迁移性。
- **参数分析**（Fig. 4）：改变注入样本数量和触发器 token 数量，观察 ASR-r 和 ACC 变化。
- **优化过程可视化**（Fig. 11）：展示迭代中嵌入空间分布逐渐分离并紧凑。

**充分性评价**：实验覆盖了多种智能体、检索器类型、基线方法，并进行了消融、韧性和防御评估，设计较为全面。但未涉及多模态智能体或更多样化的查询分布，且所有测试基于公开数据集，场景有限。

## 6. 主要结论与发现

- AgentPoison 在所有智能体上均达到**平均 ASR ≥ 80%**，而良性 ACC 下降 ≤ 1%，且毒化率 < 0.1%。
- 与基线相比，AgentPoison 在 ASR-r 和 ACC 的平衡上显著优于其他方法（Fig. 6 散点图显示处于右上角）。
- 优化的触发器具有**高转移性**：在不同编码器间（甚至从开源编码器转移到闭源 OpenAI-ADA）仍保持较高 ASR。
- 触发器对扰动（单词插入、语义改写）具有**韧性**，且困惑度分布与良性查询高度重合，能有效逃避基于困惑度的防御。
- 独特性和紧凑性损失对高检索成功率和良性维护至关重要；连贯性损失虽略降性能但极大提升隐蔽性。

## 7. 优点

- **首次针对 RAG 智能体的后门攻击**：填补了对记忆系统安全研究的空白，且自动化程度高。
- **无需模型训练**：仅需优化触发器，计算成本低，实用性强。
- **高度可转移**：攻击者可利用开源编码器训练触发器，再攻击闭源智能体。
- **隐蔽性强**：触发器的困惑度与正常查询难以区分，且对多种扰动鲁棒。
- **实验设计全面**：覆盖多个智能体、检索器、基线及消融/防御测试，结果置信度较高。

## 8. 不足与局限

- **假设白盒访问编码器**：虽然转移性实验部分缓解了该限制，但初始优化仍需编码器信息，对完全黑盒场景仍需验证。
- **实验场景有限**：仅测试三种智能体（驾驶、问答、医疗），未覆盖多模态智能体或更大规模的工业级系统。
- **未评估工程化防御**：虽然测试了困惑度过滤和重写，但未检验更先进的鲁棒检索防御（如隔离-聚合）。
- **攻击后门策略单一**：本文主要使用“虚假关联”（直接修改输出或利用已有目标动作），未探索更复杂的推理级后门。
- **计算开销未量化**：触发器优化中的束搜索和梯度近似可能需要一定 GPU 时间，但论文未提供具体资源消耗数字。

（完）
