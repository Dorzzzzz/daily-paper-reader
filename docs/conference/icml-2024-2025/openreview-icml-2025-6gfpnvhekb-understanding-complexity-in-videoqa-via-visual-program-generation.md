---
title: Understanding Complexity in VideoQA via Visual Program Generation
title_zh: 通过视觉程序生成理解VideoQA中的复杂性
authors: "Cristobal Eyzaguirre, Igor Vasiljevic, Achal Dave, Jiajun Wu, Rares Andrei Ambrus, Thomas Kollar, Juan Carlos Niebles, Pavel Tokmakov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6GFPnVHEKB"
tags: ["query:long-video"]
score: 7.0
evidence: 视频问答
tldr: 现有VideoQA基准依赖人类设计难题，但人类难以预测模型实际困难。本文提出基于视觉程序生成的自动查询复杂度分析方法，以生成代码的复杂度代理问题难度，证明该方法与模型性能的相关性显著优于人类估计。进一步设计算法从代码中识别细粒度原语，为理解VideoQA中的查询复杂性提供了新视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1714, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1780, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1746, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1647, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 781, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 846, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 793, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 448, \"height\": 158, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 482, \"height\": 182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 465, \"height\": 88, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 785, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 419, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 842, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 840, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 793, \"height\": 1257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6gfpnvhekb/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 794, \"height\": 1159, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1730, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 962, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1312, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6gfpnvhekb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1356, \"height\": 384, \"label\": \"Table\"}]"
motivation: 人类难以预测哪些问题对机器学习模型困难，需要自动度量查询复杂度。
method: 利用代码生成技术，以生成代码的复杂度作为问题难度的代理，并设计算法提取细粒度原语。
result: 该方法与模型性能的相关性显著优于人类估计。
conclusion: 为VideoQA基准设计提供了数据驱动的复杂性度量工具。
---

## Abstract
We propose a data-driven approach to analyzing query complexity in Video Question Answering (VideoQA). Previous efforts in benchmark design have relied on human expertise to design challenging questions, yet we experimentally show that humans struggle to predict which questions are difficult for machine learning models. Our automatic approach leverages recent advances in code generation for visual question answering, using the complexity of generated code as a proxy for question difficulty. We demonstrate that this measure correlates significantly better with model performance than human estimates. To operationalize this insight, we propose an algorithm for estimating question complexity from code. It identifies fine-grained primitives that correlate with the hardest questions for any given set of models, making it easy to scale to new approaches in the future. Finally, to further illustrate the utility of our method, we extend it to automatically generate complex questions, constructing a new benchmark that is 1.9 times harder than the popular NExT-QA.

---

## 论文详细总结（自动生成）

好的，我将根据您的要求，对这篇论文进行结构化、深入、客观的中文总结。

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：在视频问答（VideoQA）任务中，人类专家和现有基准数据集难以准确预测哪些问题对机器学习模型来说是困难的。作者通过实验证明，人类对问题复杂性的主观判断与模型的实际表现相关性很弱，这导致了基准数据集的设计存在局限性，无法有效推动模型在真正的挑战性问题上取得进步。
- **研究动机**：现有工作大多采用“自上而下”的专家驱动方式，即先假设某些技能是困难的，再针对性地构建数据集。然而，这种方式是静态和启发式的，无法全面覆盖模型的实际失败模式。本文旨在提出一种“自下而上”、数据驱动的自动方法，从数据中发现模型在VideoQA中真正的复杂性来源。
- **整体含义**：通过利用大语言模型（LLM）将自然语言问题转化为可执行的视觉程序，并以生成代码的复杂度作为问题难度的代理，论文首次证明代码复杂度度量与模型性能的相关性显著优于人类估计。这项研究为设计更有效的VideoQA基准、理解模型局限性提供了全新视角和实用工具。

### 2. 方法论

- **核心思想**：利用代码生成模型（如ViperGPT）将视频问题转换为可执行的Python程序。这些程序的结构化、模块化特征能够比原始自然语言问题更有效地捕获问题固有的复杂性。论文借鉴Kolmogorov复杂性的概念，认为问题的复杂性可以用其最短程序描述的长度来衡量。
- **关键技术细节与算法流程**：
    1.  **程序生成**：对于给定问题 \(q\)，使用LLM生成对应的视觉程序 \(z = \pi(q)\)。程序会调用预定义的视觉API（如帧描述、目标检测、关系问答等）来执行。
    2.  **基础复杂度度量**：先验证两种经典软件工程度量标准：代码行数（LoC）和圈复杂度（Cyclomatic Complexity），作为结构复杂度的指标。
    3.  **CodePlexity算法**（核心贡献）：
        - **抽象语法树（AST）解析**：将每个程序 \(z\) 解析为AST树 \(T\)，提取其逻辑结构和层次关系。
        - **子例程挖掘**：从所有程序的AST集合中，挖掘出所有有效的子例程（子树）\(S\)，并通过合并共现的冗余子例程得到最终的紧凑子例程集合 \(S_{merged}(D)\)。
        - **特征编码**：对于每个问题，通过子图同构判断其AST是否包含每个子例程，从而构建一个one-hot编码的特征向量 \(x_i\)。
        - **模型训练**：以特征向量 \(x_i\) 为输入，以多个VideoQA模型（训练集模型）在对应问题上的平均成功/失败结果（软标签）为监督信号，训练一个逻辑回归模型。最终得到的模型可以预测问题被模型正确回答的概率。
        - **复杂度计算**：CodePlexity分数 \(C(z) = -\hat{y}_i\)，即模型预测失败概率的相反数，分数越高表示问题越复杂。
    4.  **子例程分析**：通过统计假设检验，识别出那些与所有模型性能下降显著相关的子例程集合 \(S^*\)。这些子例程揭示了模型共同的失败模式（例如，需要多帧时序推理的程序模式或需要细粒度物体识别的模式）。
    5.  **自动生成困难问题（CodePlex-QA基准）**：
        - 输入：视频的紧凑描述（由已有场景图数据集自动生成）。
        - 过程：使用LLM基于描述生成候选问题-答案对；接着用训练好的CodePlexity模型过滤出复杂度最高的前10%的问题；最后进行少量人工审查以保证答案可回答性。

### 3. 实验设计

- **数据集与基准**：
    - **主要分析数据集**：NExT-QA (val set)，因其规模、问题多样性和对时空推理的侧重。
    - **泛化性评估数据集**：MVBench。
    - **自动生成基准**：CodePlex-QA，基于MOMA、ActivityNet和Action Genome三个场景图数据集构建。
- **对比方法**：
    - **人类基线**：招募30名受试者对150个问题排序，通过Elo分数计算人类估计的复杂度。
    - **文本基线**：依赖解析树最大深度、GPT-4直接评分、Fine-tune BERT预测模型成功率。
    - **代码基线**：代码行数（LoC）、圈复杂度（Cyclomatic Complexity）。
    - **VideoQA模型**：共9个代表性模型，分为训练集和验证集。
        - **训练集**：VIOLET, SeViLA, ViperGPT, ATP。
        - **验证集**：HGA, SeViLA-ZS, InternVideo, Tarsier, LLaVa-Video。
        - **额外评估模型（MVBench）**：VideoChat2, LLaVA-NeXT。
- **主要指标**：**性能极端差距（PEG, Performance Extremity Gap）** 及其均值 **mPEG**。该指标衡量模型在最易和最难的 \(\alpha\%\) 问题上的性能差异，差异越大说明复杂度度量越有效。
- **生成代码模型**：ViperGPT（主要），RVP（消融实验）。

### 4. 资源与算力

- 论文**并未明确说明**实验所使用的具体GPU型号、数量或训练时长。文中提及使用了预训练模型（如ViperGPT、SeViLA等）进行推理和少量fine-tune，但未报告详细算力开销。对于CodePlexity模型的训练（逻辑回归）以及数据集生成（调用GPT-4），算力需求相对较小。因此，**本文在算力报告方面不透明**，无法量化。

### 5. 实验数量与充分性

- **实验数量丰富**：论文包含了大量的定量和定性实验，涵盖：
    - 不同复杂度度量（人类、文本、代码）对比。
    - 在多个数据集（NExT-QA, MVBench, CodePlex-QA）上验证。
    - 对多个VideoQA模型进行验证，并区分训练集和验证集。
    - 多项消融实验：代码生成正确性影响、不同代码模型（ViperGPT vs RVP）影响、视频源影响（使用VidOR控制变量）、问题选择算法有效性、CodePlex-QA微调效果。
- **充分性与公平性**：
    - **优势**：实验设计较为完善，特别是区分模型为训练集和验证集，使得CodePlexity在未见过的模型上测试其泛化能力，避免了过拟合。消融实验涵盖了方法的主要组成部分。
    - **潜在不足**：验证集模型（如Tarsier, LLaVa-Video）在论文发表时可能仍是最新的，但实验覆盖的模型数量（9个）相对于整个领域而言仍然有限。此外，人类基线实验规模较小（150个问题），可能影响其代表性和统计稳定性。

### 6. 主要结论与发现

1.  **人类难以预测模型难度**：人类对问题复杂性的主观判断与模型实际表现的相关性非常弱，甚至出现反直觉现象（如人类认为简单的问题对模型反而困难）。
2.  **代码复杂度是更好的代理**：代码行数（LoC）和圈复杂度等简单代码度量，与模型性能的相关性显著强于人类估计和自然语言基线。
3.  **CodePlexity显著优于基线**：通过学习子例程与模型性能的关联，CodePlexity在mPEG指标上全面超越了所有文本和代码基线，并在未见过的模型上表现良好，证明其泛化能力。
4.  **识别共同失败模式**：子树分析揭示了当前VideoQA模型的共同弱点：**精细化的时序推理**（如需要理解事件顺序）和**细粒度的空间-物体中心化表示**（如需要识别特定物体的精确位置或关系）。
5.  **自动生成更难的数据集**：利用CodePlexity自动构建的CodePlex-QA基准，对所有测试模型的挑战性都显著高于人工标注的NExT-QA（平均难度高1.9倍），验证了该工具在基准设计中的实用价值。

### 7. 优点

- **新颖性**：首次将代码复杂度用于VideoQA问题难度分析，是一种“自下而上”、数据驱动的创新视角，区别于传统的“自上而下”专家假设。
- **可解释性与实用性**：CodePlexity不仅能输出数值分数，还能通过子树分析揭示模型失败的**具体编程原语模式**，为模型改进提供了可操作的见解（如强化时序推理能力）。同时，它能被轻松扩展应用到新的模型和数据集上。
- **自动化程度高**：从复杂度估计到自动生成更具挑战性的数据集，整个流程高度自动化，减少了对人工标注的依赖。
- **实验设计严谨**：通过训练/验证模型分离、多数据集验证、多维度消融实验，有力地证明了所提方法的有效性和泛化能力。

### 8. 不足与局限

- **对代码生成的依赖**：方法核心依赖于代码生成模型（如ViperGPT）的质量。虽然消融实验表明CodePlexity对代码错误有一定鲁棒性，但代码生成失败（如生成无法执行或逻辑有误的程序）仍会降低度量精度。
- **偏差风险**：CodePlexity的训练数据来源于一组特定模型（VIOLET, SeViLA等），这些模型可能共享某些共同偏差（如CLIP视觉编码器的偏见）。因此，学习到的“困难”模式可能仅限于这类模型的共性弱点，而无法覆盖所有未来模型的独特缺陷。生成的数据集CodePlex-QA也继承了原始场景图数据集（MOMA等）的偏差。
- **遗漏非代码可表达性复杂性**：代码结构无法直接捕获某些复杂性，例如由社会偏见、视觉幻觉、或者涉及模糊、常识性问题的挑战。这些复杂度可能无法通过视觉API调用来表示。
- **实验规模局限**：人类基线实验样本量相对较小。虽然推理了大量问题，但主要在NExT-QA一个主要数据集上进行深度分析，在MVBench上的分析相对浅层。鲁棒性评估更多聚焦于代码生成错误，对模型训练数据分布漂移等情况讨论不足。
- **算力开销不透明**：未报告任何GPU使用详情，这对于复现和评估方法的资源需求带来了困难。

（完）
