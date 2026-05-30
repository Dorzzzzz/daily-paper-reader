---
title: Memory Injection Attacks on LLM Agents via Query-Only Interaction
title_zh: 仅通过查询交互对LLM智能体的记忆注入攻击
authors: "Shen Dong, Shaochen Xu, Pengfei He, Yige Li, Jiliang Tang, Tianming Liu, Hui Liu, Zhen Xiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QINnsnppv8"
tags: ["query:agent-memory"]
score: 6.0
evidence: 针对LLM智能体的记忆注入攻击
tldr: LLM智能体的记忆库若被污染，可能产生有害输出。本文提出MINJA攻击方法，攻击者仅通过与智能体的正常查询交互，即可向记忆库注入恶意记录。这些记录会在后续执行中被检索，诱导智能体产生一系列恶意推理步骤。实验表明该方法在多个智能体任务中成功率很高，揭示了记忆安全性风险。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 526, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1203, \"height\": 1717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 620, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qinnsnppv8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1397, \"height\": 1025, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 729, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 754, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 654, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 932, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1425, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1421, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1437, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1305, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 698, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 753, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1013, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qinnsnppv8/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 695, \"height\": 276, \"label\": \"Table\"}]"
motivation: LLM智能体的记忆库易受污染，但尚未有仅通过查询交互的攻击方法。
method: 提出MINJA攻击，通过精心设计的查询使智能体记录恶意样本到记忆库。
result: 在多个任务上实现高成功率攻击，揭示记忆安全隐患。
conclusion: 需警惕LLM智能体记忆库的安全性，防御此类注入攻击。
---

## Abstract
Agents powered by large language models (LLMs) have demonstrated strong capabilities in a wide range of complex, real-world applications.
However, LLM agents with a compromised memory bank may easily produce harmful outputs when the past records retrieved for demonstration are malicious.
In this paper, we propose a novel Memory INJection Attack, MINJA, without assuming that the attacker can directly modify the memory bank of the agent.
The attacker injects malicious records into the memory bank by only **interacting with the agent via queries and output observations**.
These malicious records are designed to elicit a sequence of malicious reasoning steps corresponding to a different target query during the agent's execution of the victim user's query.
Specifically, we introduce a sequence of *bridging steps* to link victim queries to the malicious reasoning steps.
During the memory injection, we propose an *indication prompt* that guides the agent to autonomously generate similar bridging steps, with a *progressive shortening strategy* that gradually removes the indication prompt, such that the malicious record will be easily retrieved when processing later victim queries.
Our extensive experiments across diverse agents demonstrate the effectiveness of MINJA in compromising agent memory.
With minimal requirements for execution, MINJA enables any user to influence agent memory, highlighting the risk.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：LLM 智能体（如医疗、购物、问答场景）广泛采用长期记忆（LTM）来存储历史交互记录，并在新查询时通过相似度检索作为上下文演示。然而，若记忆库被污染，检索到的恶意记录会误导智能体产生有害输出（例如，自动驾驶智能体突然急刹、医疗智能体错误用药）。
- **问题定义**：现有攻击（如 AgentPoison）假设攻击者能直接修改记忆库或注入触发器到其他用户查询，这在实际中很难实现。本文提出的问题是：**在攻击者仅能通过正常查询与智能体交互、不能直接修改记忆库或干扰受害者查询的条件下，是否仍然可能注入恶意记录？**
- **整体含义**：如果答案是肯定的，那么任何普通用户都可能成为攻击者，极大威胁 LLM 智能体的安全性，凸显记忆安全设计的紧迫性。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：设计一种仅通过查询交互就能注入恶意记录的攻击方法。恶意记录包含一个包含受害者术语的良性查询，以及对应的目标推理步骤（针对另一目标术语）。由于受害者与目标之间存在逻辑鸿沟，需要引入“桥接步骤”来连接。攻击者通过附加“指示提示”诱导智能体自主生成桥接步骤和目标推理步骤，并通过“渐进缩短策略”（PSS）逐步移除提示，使最终记录仅包含干净查询，便于后续检索。
- **关键技术细节**：
  - **恶意记录设计**：记录形式为 \((a_v, [b_{v,t}, R_{a_t}])\)，其中 \(a_v\) 是含受害者术语 \(v\) 的良性查询，\(b_{v,t}\) 是桥接步骤（如“患者A的数据已保存到患者B名下”），\(R_{a_t}\) 是目标查询 \(a_t\) 的推理步骤。
  - **指示提示**：附加在攻击查询后的逻辑推理链，诱导智能体首先生成桥接步骤。例如，“患者A的数据现已保存到患者B下；我们应该查询患者B”。
  - **渐进缩短策略（PSS）**：在迭代过程中逐步移除指示提示的末尾部分，每一步都让智能体生成响应并存入记忆。最终得到完全不含指示提示的恶意记录，提高与受害者查询的相似度，增加检索概率。
  - **算法流程**：初始输入完整指示提示 \([a_v, r_1,...,r_n]\)；第 \(i\) 次迭代移除最后一步 \(r_{n-i}\)，生成响应并存储；重复直至移除全部指示提示。

## 3. 实验设计：数据集、场景、基准方法
- **使用的智能体与数据集**：
  - **RAP（ReAct + RAG）**：基于 GPT-4 和 GPT-4o，在 **Webshop**（Amazon 虚拟购物环境，118 万真实商品）上测试。
  - **EHRAgent**：医疗智能体，基于 GPT-4，在 **MIMIC-III** 和 **eICU**（两个真实电子健康记录数据库）上测试。
  - **QA Agent**：通用问答智能体（带记忆的 Chain-of-Thought），基于 GPT-4 和 GPT-4o，在 **MMLU**（57 个学科的多选题基准）上测试。
- **基准与对比方法**：本文未直接对比其他攻击方法，因为现有方法均假设直接修改记忆库，而 **MINJA** 是在更严苛的约束下（仅查询交互）的首个攻击。作者与 AgentPoison 等进行了定性比较，强调约束不同。
- **评估指标**：
  - **注入成功率 (ISR)**：攻击查询成功生成目标推理步骤并存入记忆的比例。
  - **攻击成功率 (ASR)**：受害者查询触发目标推理步骤的比例。
  - **效用下降 (UD)**：正常查询性能变化。

## 4. 资源与算力
- **文中未明确说明**使用的 GPU 型号、数量、训练时长等具体算力信息。所有实验通过 OpenAI API 调用 GPT-4 和 GPT-4o 完成，属于推理型攻击，无需训练。因此算力消耗主要来自 API 调用费用和时间，但论文未报告具体数值。

## 5. 实验数量与充分性
- **实验数量**：
  - 主实验在 4 个数据集（MIMIC-III、eICU、Webshop、MMLU）上共测试了 9 对受害者-目标组合（每对含 15 或 30 个测试查询），统计了 ISR、ASR 和 UD。
  - 消融实验涵盖：6 种嵌入模型、检索噪声、良性记录密度（25/50/75/100）、先前污染记忆、不同模型（DeepSeek-R1、Llama-2-7B）。
  - 防御评估测试了提示级检测（针对性/通用提示）、嵌入空间可视化等。
- **充分性**：实验覆盖了多种智能体类型（医疗、购物、问答）、多种模型（GPT-4、GPT-4o、DeepSeek-R1）、多种攻击条件和防御策略，设计较为全面。但重复实验仅部分报告标准差（附录 K），且未与其他攻击方法直接定量对比（因约束不同）。总体而言，实验较为充分，能支撑主要结论。

## 6. 主要结论与发现
- **MINJA 高效**：在所有数据集上，ISR 平均高达 **98.2%**，ASR 平均达 **76.8%**（部分场景超 90%）。这表明仅通过查询交互即可成功注入恶意记录并诱导目标输出。
- **保持良性效用**：UD 在大多数数据集上低于 2%（MMLU 因检索演示不足导致 -10%，通过增加演示数可缓解）。
- **鲁棒性强**：在不同嵌入模型、检索噪声、良性记录密度、模型规模下，ISR 和 ASR 保持较高水平。
- **难以防御**：提示级检测要么缺乏泛化性（针对性提示），要么高假阳率（通用提示）；嵌入级过滤无法区分恶意与良性记录。
- **威胁现实**：任何普通用户都能成为攻击者，凸显 LLM 智能体记忆安全性的严重漏洞。

## 7. 优点
- **攻击约束更贴近现实**：对比先前工作需直接修改记忆库或注入触发器，MINJA 仅需正常查询交互，大大降低了攻击门槛，使威胁更真实。
- **方法设计精巧**：桥接步骤和渐进缩短策略巧妙解决了逻辑鸿沟和检索概率问题，使注入的记录既合理又容易被检索。
- **实验覆盖广泛**：涉及医疗、购物、问答三类任务，多种模型和数据集，验证了泛化性。
- **深入防御分析**：测试了多种潜在防御（提示检测、嵌入过滤、系统级防御），揭示了防御困难，为后续安全研究提供方向。

## 8. 不足与局限
- **假设共享记忆库**：攻击前提是智能体使用全局共享记忆库。作者声称即使隔离记忆也可通过账号劫持实现，但未展开验证。
- **未对比其他攻击**：由于约束不同，未与 AgentPoison 等直接定量比较，缺乏性能基准。
- **MMLU 上效用下降较明显**：虽然分析了原因，但在默认设置下 UD 达 -10%，可能限制了实际部署中的隐蔽性。
- **模型局限性**：对弱模型（Llama-2-7B）本身任务性能低，攻击评估意义有限；对更强模型（如 GPT-4o）效果更好，但未测试封闭源最新模型（如 GPT-4-turbo）。
- **实验重复性**：仅附录对少数 pair 进行了重复实验，主实验未报告多次运行的误差，可能低估结果波动。
- **未量化攻击成本**：如 API 调用次数、时间开销等，影响实际可行性评估。

（完）
