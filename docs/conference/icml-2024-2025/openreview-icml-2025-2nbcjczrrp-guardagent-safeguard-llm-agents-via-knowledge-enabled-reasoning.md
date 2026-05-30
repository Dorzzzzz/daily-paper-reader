---
title: "GuardAgent: Safeguard LLM Agents via Knowledge-Enabled Reasoning"
title_zh: GuardAgent：通过知识驱动推理保障LLM智能体安全
authors: "Zhen Xiang, Linzhi Zheng, Yanjie Li, Junyuan Hong, Qinbin Li, Han Xie, Jiawei Zhang, Zidi Xiong, Chulin Xie, Carl Yang, Dawn Song, Bo Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2nBcjCZrrP"
tags: ["query:agent-memory"]
score: 8.0
evidence: 用于LLM智能体安全的记忆模块
tldr: 针对大型语言模型智能体面临的安全问题，本文提出GuardAgent，首个通过知识驱动推理保护目标智能体的护栏智能体。它分析安全请求生成任务计划并映射为可执行代码，其中LLM作为推理组件，并利用记忆模块存储过往任务的上下文示例以增强推理。该方法在保障代理安全方面展示了有效性与确定性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 1328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1707, \"height\": 1434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 750, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 639, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1756, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1674, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1776, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1791, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1778, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1742, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 894, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1753, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1784, \"height\": 1308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1777, \"height\": 1602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2nbcjczrrp/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 896, \"height\": 1126, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1634, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 797, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1006, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1224, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1277, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 931, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2nbcjczrrp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1130, \"height\": 176, \"label\": \"Table\"}]"
motivation: LLM智能体的安全性日益重要，缺乏动态检查行为是否符合安全约束的机制。
method: 提出GuardAgent，将安全请求转为任务计划，再映射为护栏代码执行，并利用记忆模块检索过往经验。
result: GuardAgent能准确执行安全防护任务，在多种场景下有效阻止违规行为。
conclusion: 记忆增强的推理方法能显著提升智能体安全防护的可靠性和泛化能力。
---

## Abstract
The rapid advancement of large language model (LLM) agents has raised new concerns regarding their safety and security. In this paper, we propose GuardAgent, the first guardrail agent to protect target agents by dynamically checking whether their actions satisfy given safety guard requests. Specifically, GuardAgent first analyzes the safety guard requests to generate a task plan, and then maps this plan into guardrail code for execution. By performing the code execution, GuardAgent can deterministically follow the safety guard request and safeguard target agents. In both steps, an LLM is utilized as the reasoning component, supplemented by in-context demonstrations retrieved from a memory module storing experiences from previous tasks. In addition, we propose two novel benchmarks: EICU-AC benchmark to assess the access control for healthcare agents and Mind2Web-SC benchmark to evaluate the safety policies for web agents. We show that GuardAgent effectively moderates the violation actions for different types of agents on these two benchmarks with over 98% and 83%
guardrail accuracies, respectively. Project page: https://guardagent.github.io/

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：随着LLM智能体（如医疗助手、网页代理）在金融、医疗、自动驾驶等领域广泛应用，其安全与隐私风险日益突出。现有安全措施要么是硬编码到特定智能体（无法泛化），要么仅针对LLM的纯文本输出（无法处理智能体多样的动作模态和复杂的安全请求）。
- **核心目标**：提出首个面向LLM智能体的通用护栏框架，能够动态检查目标智能体的行为是否满足用户指定的安全请求（如访问控制、安全策略），并阻止违规操作。

## 2. 论文提出的方法论

- **核心思想**：将安全请求“翻译”为可执行代码，通过代码执行提供确定性的护栏检查。利用LLM的推理能力，结合从记忆模块检索的过往经验，完成任务规划与代码生成。
- **关键技术细节**：
  - **两阶段流程**：
    1. **任务规划**：输入包括安全请求 \( I_r \)、目标智能体规格 \( I_s \)、用户输入 \( I_i \)、输出日志 \( I_o \)。LLM根据这些信息生成逐步的动作计划 \( P \)。为增强推理，从记忆模块中检索与当前案例最相似（基于Levenshtein距离）的 \( k \) 个演示（包含过往的输入、输出、计划、代码）。
    2. **护栏代码生成与执行**：LLM根据动作计划 \( P \) 和一组可调用的函数列表 \( F \)（可扩展工具箱），生成Python代码 \( C \)。代码在指定引擎上执行，产生标签 \( O_l \)（是否违规）和原因 \( O_d \)。若执行出错，启动调试机制（由LLM分析错误信息）。
  - **记忆模块**：存储过往案例的完整记录（输入、输出、计划、代码）。检索基于Levenshtein距离，使GuardAgent能利用少量演示实现强泛化。
  - **无需训练**：全部基于LLM的上下文学习，无需微调。

## 3. 实验设计

- **数据集与场景**：
  - **EICU-AC**：面向医疗智能体EHRAgent的访问控制基准，基于EICU数据集构建。包含316个样本，涉及3种角色（医生、护士、行政人员），每样本有用户身份、问题、所需数据库/列、二进制标签（是否应拒绝访问）。
  - **Mind2Web-SC**：面向网页智能体SeeAct的安全策略基准，基于Mind2Web构建。包含200个样本（各100个正负例），定义了6条安全规则（如未接种疫苗不能订机票、未成年人不能订酒店等），每样本有用户画像、任务、标签。
- **对比方法**：
  - **Model-Guarding-Agent**：直接用LLM（GPT-4、Llama3等）进行自然语言安全判断，无代码生成。
  - **Hardcoded Safety Rules**：将安全规则硬编码入目标智能体的系统提示词。
  - **LlamaGuard**：专为LLM内容安全训练的模型。
- **评估指标**：标签预测准确率（LPA）、精确率（LPP）、召回率（LPR）、解释准确率（EA，检查是否准确列出所有违规原因）、最终响应准确率（FRA，不影响目标智能体任务性能）。

## 4. 资源与算力

- 论文**未明确说明**具体GPU型号、数量或训练时长。实验中使用了GPT-4（通过API）、Llama3-70B、Llama3.1-70B、Llama3.3-70B作为基础模型，均为现成LLM，无需额外训练。但未报告API调用次数或本地部署的硬件细节。

## 5. 实验数量与充分性

- **主要实验**：在EICU-AC和Mind2Web-SC上，使用4种基础LLM，对比3种基线，报告了LPA、LPP、LPR、EA、FRA全部指标。每个设置下均为全数据集测试。
- **消融实验**：
  - 角色/规则细分：检验GuardAgent在EICU-AC中三个角色和Mind2Web-SC中六条规则上的表现。
  - 记忆数量影响：将 \( k \) 从0变到3+，观察LPA/EA变化。
  - 工具箱影响：移除相关函数与代码演示，测试代码可执行率与准确率下降。
  - 代码趋势分析：当移除所有代码相关指令时，LLM自发生成代码的倾向。
- **额外实验**：在CSQA常识问答数据集上添加伪安全规则，检验GuardAgent处理非二进制、风险等级输出的能力。
- **充分性评价**：实验覆盖了多种场景（医疗/网页）、多种LLM、广泛的消融，并补充了通用QA场景。但缺乏对其他类型智能体（如自动驾驶、金融）的测试；未进行大规模多轮对话或复杂多步动作的验证。总体较为充分、客观。

## 6. 论文的主要结论与发现

- **GuardAgent在两个基准上均优于所有基线**：
  - EICU-AC：LPAs >98%（最高99.1%），EAs >95%。
  - Mind2Web-SC：LPAs >83%（最高93%），EAs >68%。
- **代码生成比纯自然语言更可靠**：避免了LLM在推理中“自动脑补”错误信息（如错误地认为护士有权访问诊断数据库）。
- **完全不影响目标智能体任务性能**（FRA=100%），因为GuardAgent非侵入式地并联部署。
- **记忆模块至关重要**：减少演示数量会降低性能；最相似检索比最不相似检索效果更好。
- **工具箱可扩展且必要**：移除工具箱后性能下降，但GuardAgent能够自主定义所需函数，展现出适应性。
- **LlamaGuard不适用于智能体护栏**，其准确率接近随机。

## 7. 优点

- **首创性**：第一个专门为LLM智能体设计的护栏框架，填补了空白。
- **确定性**：通过代码执行提供确定性结果，避免LLM自然语言模糊性。
- **灵活性**：可扩展工具箱与记忆模块，能适应新型智能体和安全请求。
- **低开销**：无需训练，仅需少量演示（1-3 shot）即可工作。
- **全面评估**：提出两个高质量基准，包含多样化的安全规则，评估指标涵盖准确率、解释质量、任务影响等。

## 8. 不足与局限

- **智能体类型覆盖有限**：仅测试了医疗（EHRAgent）和网页（SeeAct）两类，未涉及自动驾驶、金融、多代理协作等场景。
- **依赖强大LLM**：需要具备较强编码和推理能力的模型（如GPT-4、70B级Llama），较弱模型可能无法有效生成代码和复杂推理。
- **手工定义的函数与演示**：工具箱和初始演示需要用户手动构建，限制了自动化程度。
- **代码生成失败风险**：虽然调试机制存在，但语法错误、逻辑错误仍可能发生（尤其在无工具箱时）。
- **未讨论计算成本与延迟**：未分析GuardAgent本身引入的时间开销（相比基线，平均45.4秒 vs 8.5秒，见附录），也未评估对系统整体延迟的影响。
- **缺乏多轮交互测试**：所有实验均为单次查询，未考虑目标智能体多步执行中的实时护栏需求。
- **潜在偏差风险**：EICU-AC的权限由ChatGPT与专家共同制定，可能引入主观偏差；Mind2Web-SC规则相对简单，未涵盖更复杂的法律合规场景。

（完）
