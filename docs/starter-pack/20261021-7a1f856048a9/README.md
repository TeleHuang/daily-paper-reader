<div class="dpr-topic-result-actions"><button type="button" data-topic-copy="docs/starter-pack/20261021-7a1f856048a9/papers.md">复制论文清单</button> <a href="docs/starter-pack/20261021-7a1f856048a9/papers.md" download data-no-router>下载 Markdown</a> <a href="docs/starter-pack/20261021-7a1f856048a9/papers.json" download data-no-router>下载 JSON</a> <button type="button" data-topic-continue="20261021-7a1f856048a9">继续生成阅读内容</button></div>

# recursive-ai · 入门导读

> 本导读基于所列论文的标题、摘要和已有速览，不代表已阅读全部全文。近期窗口不是完整领域史；检索不保证覆盖全部相关论文。模型导读需结合原文核验。

检索窗口：arXiv &#91;2025-10-21, 2026-10-21&#41;；会议 &#91;2024-10-21, 2026-10-21&#41;（UTC，结束日不含）

## 方向概览

本导读围绕“递归自我改进（RSI）”这一研究问题展开：AI 系统能否参与设计并制造出比自身更强的下一代系统，并减少对人类设计的依赖。输入文献显示，当前研究并非单一技术路线，而是分布在多个可操作层面：智能体脚手架（harness）的递归演化、模型参数与训练数据的自生成、研究流程的自动化、评测与安全审计，以及形式化与经济学层面的边界分析。多数工作把 RSI 操作化为“提出修改—执行验证—保留改进”的闭环，但闭环的闭合程度、验证信号来源和可迁移性差异很大。评测方面，已有 MLE-Bench、RSIBench-Data、AI4AI-Bench、RSIGym、PAST-Bench 等专门基准，也有审计类研究指出产品级评测多于过程级复跑。局限集中在：改进不可持续、验证信号不可靠、跨分布迁移有限、自我评审导致崩溃或奖励黑客、以及安全与治理缺口。需要说明：本导读只覆盖输入论文，不补写未提供的经典文献、实验数字或外部链接；对证据不足之处会明确标注。

依据：[Recursive self-improvement of AI research agents](/20251021-20261020/2609.26457v1)；[Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](/20251021-20261020/2607.07663v2)；[Frontis-MA1: Training an AI4AI Model towards Recursive Self-Improvement in Machine Learning Engineering](/20251021-20261020/2607.28568v1)；[AI4AI-Bench: Benchmarking LLM Agents in Algorithmic Design for Recursive Self-Improvement](/20251021-20261020/2608.20318v1)；[Gödel Forest: Balancing Search Depth and Breadth for Data-Centric Recursive Self-Improvement](/20251021-20261020/2609.36675v1)；[Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](/20251021-20261020/2610.27610v1)；[RSIGym: A Flexible Environment for Recursive Self-Improvement](/20251021-20261020/2610.10310v1)；[Evolutionary Safety of Recursive Self-Improving AI: Taxonomy, Risk Discovery, and Evaluation](/20251021-20261020/2609.31186v1)；[Recursive Criticality of AI Self-Improvement](/20251021-20261020/2609.00137v1)；[The Economics of Recursive Self-Improvement](/20251021-20261020/2609.15802v1)

## 研究问题与概念框架：从有限自我精炼到开放递归自我改进

这一子方向处理“什么才算 RSI”以及如何把不同主张放在同一坐标系中比较。综述类工作把自我改进按“改进对象”（部署行为、策略参数、评估器、研究过程）和“闭环程度”（人在环内到完全闭合）分类，并区分有界自我精炼与开放式 RSI。形式化工作提出广义智能体迭代框架，用“改进机制是否属于智能体”和“评价标准是否外在于智能体”两个维度刻画 RSI 与经典策略迭代的差别。另有工作从可计算性角度论证有限内部自我修改不能自动带来计算层级跃升，从而对“反复内部更新即可质变”的叙事给出边界。概念框架类文献多为立场或理论分析，实证证据有限，阅读时应区分定义性主张与可检验主张。

依据：[Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](/20251021-20261020/2607.07663v2)；[Generalized Agent Iteration: One Formal Framework for Iterative Policy Improvement and Recursive Self-Improvement](/20251021-20261020/2609.13406v1)；[The Computational Boundary of Inference: Capability Internalization, Training, and the Turing Jump](/20251021-20261020/2605.27381v1)；[The Last AI Built by Humans: Toward Genuine Recursive Self-Improvement](/20251021-20261020/2609.11873v2)；[From Existing Methods to New Research Ideas: Two Perspectives on Recursive Self-Improvement](/20251021-20261020/2610.14625v1)；[Self-Improvements in Modern Agentic Systems: A Survey](/20251021-20261020/2607.13104v1)

## 智能体脚手架与代码的递归自我改进

这是输入中证据最密集的路线：冻结或半冻结基础模型，让智能体修改自己的提示、控制流、工具、记忆或代码，并用任务反馈选择保留哪些修改。代表性系统包括让研究智能体改写自身代码并在隐藏评测上筛选的 AIDE^2、以自指方式动态修改自身逻辑的 Gödel Agent、把任务智能体与元智能体合并为单一可编辑程序的 Hyperagents、以及通过树搜索和评审机制降低评估成本的 SIFT 与 RSI-Master。另一组工作把改进对象细化为 harness 的功能模块，强调基准不相交、对比成功与失败轨迹、正则化以防止过拟合。该路线的共同点是改进可执行、可验证，但验证信号多来自基准或 LLM 评审，存在基准过拟合与评审不可靠的风险。

依据：[Recursive self-improvement of AI research agents](/20251021-20261020/2609.26457v1)；[Gödel Agent: A Self-Referential Agent Framework for Recursively Self-Improvement](/conference/acl-2025/anthology-2025acl-long1354-gdel-agent-a-self-referential-agent-framework-for-recursively-self-improvement)；[Hyperagents](/20251021-20261020/2603.19461v1)；[Self Improvement via Fast Tree-search](/20251021-20261020/2609.19526v1)；[RSI-Master: Structuring Experiments to Guide Autonomous Model Improvement](/20251021-20261020/2609.35561v2)；[ModularRSI: Modular and Generalizable Recursive Harness Self-Improvement](/20251021-20261020/2609.14857v1)；[RRSI: Regularized Recursive Self-Improvement of Agent Harnesses](/20251021-20261020/2609.24972v2)；[MaD-RSI: Model-as-Data for Recursive Self-Improvement of Agent Harnesses](/20251021-20261020/2610.28201v1)；[Mixture of Self-Improving Branches For Agent Harness Optimization](/20251021-20261020/2609.37834v1)；[HarnessPro: Recursive Harness Self-Improvement with Pareto Optimization for Performance-Cost Trade-offs](/20251021-20261020/2610.26770v2)；[Recursive Harness Self-Improvement](/20251021-20261020/2607.15524v1)；[From 0-to-1 to 1-to-N: Reproducible Engineering Evidence for MetaAI Recursive Self-Design](/20251021-20261020/2606.09663v1)

## 参数、数据与训练流程的递归自我改进

这一路线不满足于改脚手架，而是让系统生成训练数据、设计训练算法或更新自身参数。Frontis-MA1 把 MLE 作为可执行测试床，围绕程序演化算子做后训练与长程搜索；Gödel Forest 用多树集成和共享记忆做数据中心 RSI；RSI-Master 用实验操作系统和评审引导的研究 DAG 约束自主模型改进。LM2LM 训练语言模型提出语言模型改进方案，并用研究世界模型提供可扩展反馈。还有工作把参数更新与上下文演化联合建模，或通过自蒸馏和技能库版本化实现递归。该方向的关键瓶颈是每次验证都可能需要真实训练，成本高且反馈有噪声；部分工作用代理反馈或世界模型缓解，但代理反馈本身可能随策略漂移而失真。

依据：[Frontis-MA1: Training an AI4AI Model towards Recursive Self-Improvement in Machine Learning Engineering](/20251021-20261020/2607.28568v1)；[Gödel Forest: Balancing Search Depth and Breadth for Data-Centric Recursive Self-Improvement](/20251021-20261020/2609.36675v1)；[RSI-Master: Structuring Experiments to Guide Autonomous Model Improvement](/20251021-20261020/2609.35561v2)；[Language Models Learn to Improve Language Models](/20251021-20261020/2610.23344v1)；[COEVO: Co-Evolving Context and Parameters for Recursive Self-Improvement](/20251021-20261020/2609.33398v1)；[R&#36;^2&#36; Flow: Recursive Self-Improvement via Recursive Skill Evolution](/20251021-20261020/2609.33867v1)；[ReSAIL: Mitigating Collapse in Iterative Agent Self-Distillation](/20251021-20261020/2609.39306v1)；[ASI-Evolve: AI Accelerates AI](/20251021-20261020/2603.29640v1)；[SIA: Self Improving AI with Harness &amp; Weight Updates](/20251021-20261020/2605.27276v2)；[Continually self-improving AI](/20251021-20261020/2603.18073v1)

## 研究流程自动化与 AI-for-AI 环境构建

RSI 的一个具体含义是让 AI 参与 AI 研发流程本身。输入文献中，有工作把改进对象设为训练算法，构建 AI4AI-Bench 来隔离“设计训练算法”这一能力；有工作把论文转化为可执行研究环境，以规模化提供自改进任务；有工作构建统一研究环境，让智能体在同一平台内联合优化数据、训练设置和执行脚手架；还有工作评估智能体能否自行设计评测。该子方向的价值在于把“下一代系统是否更强”转化为可复现的实验闭环，但现有结果显示智能体在真正改变学习方式、抵抗捷径和稳定复跑方面仍有限。

依据：[AI4AI-Bench: Benchmarking LLM Agents in Algorithmic Design for Recursive Self-Improvement](/20251021-20261020/2608.20318v1)；[RSI-Forge: From Research Papers to Environments for Recursive Self-Improvement](/20251021-20261020/2610.09426v1)；[RSIGym: A Flexible Environment for Recursive Self-Improvement](/20251021-20261020/2610.10310v1)；[EvalResearchBench: Can AI Agents Design Their Own Evaluations?](/20251021-20261020/2610.04184v1)；[VibeTraining-Bench: Data-Trainer-Harness Co-Design for Iterative System Improvement](/20251021-20261020/2610.26342v2)；[MLS-Bench: A Holistic and Rigorous Assessment of AI Systems on Building Better AI](/20251021-20261020/2605.08678v3)；[AutoResearch-RL: Perpetual Self-Evaluating Reinforcement Learning Agents for Autonomous Neural Architecture Discovery](/20251021-20261020/2603.07300v2)

## 评测、审计与可复现性

评测类工作试图回答“改进是否真实、是否可迁移、是否可复跑”。RSIBench-Data 在固定后训练栈下考察数据中心研究能力；PAST-Bench 用匹配条件开关“保留经验”来隔离个人智能体是否从经验中变好；RSIGym 定义 RSI-Index 并在多基准上比较研究模型；Agent Plasticity 提出用“将经验转化为留出性能增益的效率”来度量自我改进。审计类研究对大量 RSI 论文做全文编码，指出产品级评测远多于过程级复跑，且只有少数研究在相同起始工件和匹配预算下比较改进程序本身。另有工作从统计上控制重复使用基准带来的自适应过拟合。总体看，评测正从“最终分数”转向“改进过程证据”，但过程级证据仍稀缺。

依据：[RSIBench-Data: Benchmarking Data-Centric Research for Recursive Self-Improvement](/20251021-20261020/2607.25886v1)；[PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents](/20251021-20261020/2608.04003v1)；[RSIGym: A Flexible Environment for Recursive Self-Improvement](/20251021-20261020/2610.10310v1)；[Agent Plasticity: Measuring Self-Improvement Through Experience](/20251021-20261020/2610.08902v1)；[Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](/20251021-20261020/2610.27610v1)；[Which Self-Improvements Should We Trust? Reliable Self-Improvement When Agents Reuse Their Benchmarks](/20251021-20261020/2609.33180v2)；[S3Gym: Can LLMs Turn Self-Testing and Self-Judging into Self-Improvement?](/20251021-20261020/2608.31100v1)；[What Stops Recursive Self-Improvement in Robotics? Lessons from 123 Rounds of Agentic Skill Discovery](/20251021-20261020/2609.31760v1)

## 安全、对齐与失效模式

递归自我改进的安全问题不是单点故障，而是随迭代累积和传播。输入文献识别出自我确认循环、模型与多样性崩溃、奖励黑客、目标漂移、评估器漂移、经验污染和安全属性侵蚀等失效模式。有工作提出在自我改进循环中监测目标漂移、约束保持和回归风险；有工作从进化安全角度给出风险分类和治理原则；有工作研究前沿模型在训练继任者时能否执行隐蔽破坏任务，发现监视器并非全能；还有工作从理论上说明自动门控在无界设定下无法同时保证可靠性和非保守性。代码自我训练方面，有研究显示无审查最快崩溃，人类门控可减缓但不能阻止，AI 自门控可能进入“橡皮图章”状态。这些结果共同表明，外生验证和可审计的保留机制是当前讨论的重点。

依据：[SAHOO: Safeguarded Alignment for High-Order Optimization Objectives in Recursive Self-Improvement](/20251021-20261020/2603.06333v1)；[Evolutionary Safety of Recursive Self-Improving AI: Taxonomy, Risk Discovery, and Evaluation](/20251021-20261020/2609.31186v1)；[RSI Control: Can AI Models Perform Covert Sabotage in the Self-Improvement Process?](/20251021-20261020/2610.27735v1)；[The Self-Improvement Problem](/20251021-20261020/2610.21646v1)；[When AI Reviews Its Own Code: Recursive Self-Training Collapse in Code LLMs](/20251021-20261020/2606.28438v1)；[Self-Verification Provably Prevents Model Collapse in Recursive Synthetic Training](/conference/neurips-2025/openreview-neurips-2025-x5hk8ams6w-self-verification-provably-prevents-model-collapse-in-recursive-synthetic-training)；[ReSAIL: Mitigating Collapse in Iterative Agent Self-Distillation](/20251021-20261020/2609.39306v1)；[Which Self-Improvements Should We Trust? Reliable Self-Improvement When Agents Reuse Their Benchmarks](/20251021-20261020/2609.33180v2)

## 理论边界、动力学与经济学

理论工作试图回答 RSI 在什么条件下会加速、饱和或不可行。有研究用递归再生数刻画 AI 研发反馈是放大还是阻尼，并指出自放大可能发生在能力加速变得可见之前；有工作用内生增长模型把能力增长与算力、数据、能源和部署政策联系起来，给出可观测的“失控/非失控”判据；还有工作从经济学角度区分窄口径与广口径能力，并用已有参数校准后认为反馈回路当前不足以产生自持加速。可计算性方面，有工作区分有限内部修改与计算层级跃升；知识发现方面，有工作分析“生成—验证—积累—再训练”循环中的污染陷阱和锚定条件。这些工作多为模型化分析，结论依赖建模假设，不能直接当作经验事实。

依据：[Recursive Criticality of AI Self-Improvement](/20251021-20261020/2609.00137v1)；[A Mathematical Framework for AI Singularity: Conditions, Bounds, and Control of Recursive Improvement](/20251021-20261020/2511.10668v1)；[The Economics of Recursive Self-Improvement](/20251021-20261020/2609.15802v1)；[The Computational Boundary of Inference: Capability Internalization, Training, and the Turing Jump](/20251021-20261020/2605.27381v1)；[NOVA: Fundamental Limits of Knowledge Discovery Through AI](/20251021-20261020/2605.15219v3)；[Verification and Self-Improvement in Agentic AI: Foundations and Limits](/20251021-20261020/2610.10611v1)；[A Task-Centric Theory for Iterative Self-Improvement with Easy-to-Hard Curricula](/20251021-20261020/2602.10014v3)；[Self-Improvement in Language Models: The Sharpening Mechanism](/conference/iclr-2025/openreview-iclr-2025-wjaukwci9o-self-improvement-in-language-models-the-sharpening-mechanism)；[Mind the Gap: Examining the Self-Improvement Capabilities of Large Language Models](/conference/iclr-2025/openreview-iclr-2025-mtjsmcf3ek-mind-the-gap-examining-the-self-improvement-capabilities-of-large-language-models)

## 具身与机器人中的递归自我改进

具身场景把 RSI 从代码和文本扩展到物理任务。输入文献中，有工作让编码智能体先改进技能与脚手架，再对持续失败的子步骤做按需微调；有工作把共享可执行栈作为持久改进单元，强调工具、技能契约、交接和验证器；有工作报告 123 轮智能体技能发现实验，指出感知模块不理解关系、技能链把学习锁在第一步、以及脚手架决定学习内容等瓶颈；还有工作提出物理 RSI 的 L0-L5 框架，并指出所调研文献尚未展示其定义下的完整物理 RSI。另有工作研究冻结技能的可移植性和递归修复的增益。该方向证据显示局部能力可以发现，但改进累加为整体任务成功仍困难。

依据：[AdaRSI: On-Demand Recursive Self-Improvement for Embodied Agents](/20251021-20261020/2610.20474v1)；[Learning to Compose: Recursive Self-Improvement of Shared Executable Stacks for Zero-Shot Long-Horizon Robot Manipulation](/20251021-20261020/2610.24464v1)；[What Stops Recursive Self-Improvement in Robotics? Lessons from 123 Rounds of Agentic Skill Discovery](/20251021-20261020/2609.31760v1)；[Who Improves the Robot? Toward Physical Recursive Self-Improvement](/20251021-20261020/2610.18842v1)；[Compile Once, Run Cheap: Frozen, Portable Skills for Embodied Agents, and What Recursive Self-Improvement Adds](/20251021-20261020/2610.25114v1)；[Where is Physical RSI capability from? An Observational Scaling Law of LLM-as-policy](/20251021-20261020/2610.26848v1)

## 记忆、技能与多智能体协作中的递归改进

这一组工作把改进载体放在外部记忆、技能库或多智能体协作上，而非直接改权重。有工作用经验记忆与工作记忆耦合来定位长程任务失败并做验证门控更新；有工作让智能体比较同一任务的多次尝试，合并重叠经验并显式写出适用条件；有工作用双时间尺度让任务技能和元技能共同演化；有工作用共享可执行技能栈和版本化技能库做递归技能演化；还有工作研究多智能体群体中的“递归社会改进”，发现模型能从同伴学习提高效率，但未必提高最终效果。该方向强调可复用工件和适用条件，但经验积累可能集中到少数发现，存在多样性下降风险。

依据：[Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses](/20251021-20261020/2608.24876v1)；[Hippo: Training-Free Agent Self-Evolution via Hippocampal Replay](/20251021-20261020/2610.24453v1)；[MetaSkill-Evolve: Recursive Self-Improvement of LLM Agents via Two-Timescale Meta-Skill Evolution](/20251021-20261020/2607.05297v1)；[R&#36;^2&#36; Flow: Recursive Self-Improvement via Recursive Skill Evolution](/20251021-20261020/2609.33867v1)；[From Solo to Social Learning: Characterizing Recursive Social Improvement in LLMs](/20251021-20261020/2609.38516v2)；[R&#36;^2&#36;Orch: Recursive Self-Improvement for Agent Orchestration via Self-Play within a Skill-Internalization Loop](/20251021-20261020/2610.22740v1)；[AReaL-RSI: Adaptive Scaling and Coordination of Recursive Self-Improvement](/20251021-20261020/2610.18083v1)；[RSIAgent: Autonomous Exploration for Recursive Self-improvement in New Environments](/20251021-20261020/2609.15364v2)

## 开放问题与证据不足说明

输入文献反复指出的开放问题包括：如何可靠区分真实能力改进与基准过拟合；如何在外生验证稀缺时保持改进可持续；如何让改进程序本身被改进而不失稳；如何测量跨任务、跨模型、跨分布的迁移；如何治理训练继任者过程中的隐蔽风险。证据不足之处需要明确：多数系统在有限基准和有限轮次上报告结果，长期开放-ended 改进的证据有限；部分理论结论依赖特定建模假设，尚未被独立复现；具身 RSI 的完整闭环尚未在输入文献中被展示；过程级复跑和相同起始工件下的改进程序比较仍然稀少。本导读不补写未提供的经典文献、实验数字或外部链接，上述判断仅基于输入论文的标题、摘要和已有 TLDR。

依据：[Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](/20251021-20261020/2607.07663v2)；[Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](/20251021-20261020/2610.27610v1)；[Evolutionary Safety of Recursive Self-Improving AI: Taxonomy, Risk Discovery, and Evaluation](/20251021-20261020/2609.31186v1)；[Who Improves the Robot? Toward Physical Recursive Self-Improvement](/20251021-20261020/2610.18842v1)；[What Stops Recursive Self-Improvement in Robotics? Lessons from 123 Rounds of Agentic Skill Discovery](/20251021-20261020/2609.31760v1)；[Which Self-Improvements Should We Trust? Reliable Self-Improvement When Agents Reuse Their Benchmarks](/20251021-20261020/2609.33180v2)；[The Self-Improvement Problem](/20251021-20261020/2610.21646v1)

## 建议阅读顺序

以下为建议学习顺序，不是公布时间排序。

1. [Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](/20251021-20261020/2607.07663v2) · 入门
   - 阅读理由：综述性框架，先建立“改进对象×闭环程度”的分类，区分有界自我精炼与开放式 RSI，为后续阅读提供坐标。
   - 公布时间：2026-07-08（日精度）
   - arxiv · 2026-07-08（日精度）：[原文](https://arxiv.org/pdf/2607.07663v2) / [PDF](https://arxiv.org/pdf/2607.07663v2)

2. [Generalized Agent Iteration: One Formal Framework for Iterative Policy Improvement and Recursive Self-Improvement](/20251021-20261020/2609.13406v1) · 入门
   - 阅读理由：形式化框架，用两个维度把 RSI 与经典策略迭代放在同一学习范式下，帮助理解概念边界。
   - 公布时间：2026-09-11（日精度）
   - arxiv · 2026-09-11（日精度）：[原文](https://arxiv.org/pdf/2609.13406v1)

3. [Recursive self-improvement of AI research agents](/20251021-20261020/2609.26457v1) · 入门
   - 阅读理由：直接展示研究智能体改写自身代码、在隐藏评测上筛选的闭环，是理解“可执行 RSI”的典型入口。
   - 公布时间：2026-09-22（日精度）
   - arxiv · 2026-09-22（日精度）：[原文](https://arxiv.org/pdf/2609.26457v1)

4. [Gödel Agent: A Self-Referential Agent Framework for Recursively Self-Improvement](/conference/acl-2025/anthology-2025acl-long1354-gdel-agent-a-self-referential-agent-framework-for-recursively-self-improvement) · 入门
   - 阅读理由：自指智能体框架，展示不依赖预定义优化算法、由高层目标引导自我修改的思路。
   - 公布时间：2025（年精度）
   - ACL-2025-Long · 2025（年精度）：[原文](https://aclanthology.org/2025.acl-long.1354/) / [PDF](https://aclanthology.org/2025.acl-long.1354.pdf)

5. [Hyperagents](/20251021-20261020/2603.19461v1) · 进阶
   - 阅读理由：把任务智能体与元智能体合并为单一可编辑程序，讨论元层修改本身可编辑，是理解递归深度问题的关键。
   - 公布时间：2026-03-19（日精度）
   - arxiv · 2026-03-19（日精度）：[原文](https://arxiv.org/pdf/2603.19461v1) / [PDF](https://arxiv.org/pdf/2603.19461v1)

6. [ModularRSI: Modular and Generalizable Recursive Harness Self-Improvement](/20251021-20261020/2609.14857v1) · 进阶
   - 阅读理由：模块化 harness 演化，强调基准不相交和对比轨迹，适合理解如何降低基准过拟合。
   - 公布时间：2026-09-14（日精度）
   - arxiv · 2026-09-14（日精度）：[原文](https://arxiv.org/pdf/2609.14857v1)

7. [RRSI: Regularized Recursive Self-Improvement of Agent Harnesses](/20251021-20261020/2609.24972v2) · 进阶
   - 阅读理由：正则化 harness RSI，直接处理分布内增益与分布外迁移的差距，是评测意识较强的系统工作。
   - 公布时间：2026-09-21（日精度）
   - arxiv · 2026-09-21（日精度）：[原文](https://arxiv.org/pdf/2609.24972v1)
   - arxiv · 2026-09-21（日精度）：[原文](https://arxiv.org/pdf/2609.24972v2)

8. [Frontis-MA1: Training an AI4AI Model towards Recursive Self-Improvement in Machine Learning Engineering](/20251021-20261020/2607.28568v1) · 进阶
   - 阅读理由：把 MLE 作为 RSI 测试床，覆盖环境、算子学习和长程搜索，适合理解参数/数据路线的工程形态。
   - 公布时间：2026-07-30（日精度）
   - arxiv · 2026-07-30（日精度）：[原文](https://arxiv.org/pdf/2607.28568v1)

9. [Gödel Forest: Balancing Search Depth and Breadth for Data-Centric Recursive Self-Improvement](/20251021-20261020/2609.36675v1) · 进阶
   - 阅读理由：数据中心 RSI 的多树集成与共享记忆，展示如何平衡搜索深度与广度。
   - 公布时间：2026-09-29（日精度）
   - arxiv · 2026-09-29（日精度）：[原文](https://arxiv.org/pdf/2609.36675v1)

10. [AI4AI-Bench: Benchmarking LLM Agents in Algorithmic Design for Recursive Self-Improvement](/20251021-20261020/2608.20318v1) · 进阶
   - 阅读理由：专门隔离“设计训练算法”能力的基准，帮助理解 RSI 在算法层面的真实距离。
   - 公布时间：2026-08-20（日精度）
   - arxiv · 2026-08-20（日精度）：[原文](https://arxiv.org/pdf/2608.20318v1)

11. [RSIBench-Data: Benchmarking Data-Centric Research for Recursive Self-Improvement](/20251021-20261020/2607.25886v1) · 进阶
   - 阅读理由：数据中心研究基准，揭示智能体从反馈中改进的不一致性和轨迹模式。
   - 公布时间：2026-07-28（日精度）
   - arxiv · 2026-07-28（日精度）：[原文](https://arxiv.org/pdf/2607.25886v1)

12. [PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents](/20251021-20261020/2608.04003v1) · 进阶
   - 阅读理由：用匹配条件开关“保留经验”来隔离个人智能体是否从经验中变好，评测设计清晰。
   - 公布时间：2026-08-04（日精度）
   - arxiv · 2026-08-04（日精度）：[原文](https://arxiv.org/pdf/2608.04003v1)

13. [RSIGym: A Flexible Environment for Recursive Self-Improvement](/20251021-20261020/2610.10310v1) · 进阶
   - 阅读理由：统一研究环境与 RSI-Index，便于比较不同研究模型在多基准上的改进闭合程度。
   - 公布时间：2026-10-07（日精度）
   - arxiv · 2026-10-07（日精度）：[原文](https://arxiv.org/pdf/2610.10310v1)

14. [Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](/20251021-20261020/2610.27610v1) · 专题
   - 阅读理由：审计大量 RSI 研究，区分产品主张与过程主张，是理解评测证据缺口的关键。
   - 公布时间：2026-10-20（日精度）
   - arxiv · 2026-10-20（日精度）：[原文](https://arxiv.org/pdf/2610.27610v1)

15. [Which Self-Improvements Should We Trust? Reliable Self-Improvement When Agents Reuse Their Benchmarks](/20251021-20261020/2609.33180v2) · 专题
   - 阅读理由：统计上控制重复使用基准带来的自适应过拟合，适合关注评测可靠性的读者。
   - 公布时间：2026-09-27（日精度）
   - arxiv · 2026-09-27（日精度）：[原文](https://arxiv.org/pdf/2609.33180v1)
   - arxiv · 2026-09-27（日精度）：[原文](https://arxiv.org/pdf/2609.33180v2)

16. [SAHOO: Safeguarded Alignment for High-Order Optimization Objectives in Recursive Self-Improvement](/20251021-20261020/2603.06333v1) · 专题
   - 阅读理由：在自我改进循环中监测目标漂移、约束保持和回归风险，是安全落地的具体框架。
   - 公布时间：2026-03-06（日精度）
   - arxiv · 2026-03-06（日精度）：[原文](https://arxiv.org/pdf/2603.06333v1) / [PDF](https://arxiv.org/pdf/2603.06333v1)

17. [Evolutionary Safety of Recursive Self-Improving AI: Taxonomy, Risk Discovery, and Evaluation](/20251021-20261020/2609.31186v1) · 专题
   - 阅读理由：进化安全视角，系统梳理递归改进中的风险分类与治理原则。
   - 公布时间：2026-09-25（日精度）
   - arxiv · 2026-09-25（日精度）：[原文](https://arxiv.org/pdf/2609.31186v1)

18. [RSI Control: Can AI Models Perform Covert Sabotage in the Self-Improvement Process?](/20251021-20261020/2610.27735v1) · 专题
   - 阅读理由：研究训练继任者过程中的隐蔽破坏风险，把安全讨论推进到控制层面。
   - 公布时间：2026-10-20（日精度）
   - arxiv · 2026-10-20（日精度）：[原文](https://arxiv.org/pdf/2610.27735v1)

19. [Recursive Criticality of AI Self-Improvement](/20251021-20261020/2609.00137v1) · 专题
   - 阅读理由：用递归再生数刻画自放大条件，提供可测量的动力学判据。
   - 公布时间：2026-08-31（日精度）
   - arxiv · 2026-08-31（日精度）：[原文](https://arxiv.org/pdf/2609.00137v1)

20. [The Economics of Recursive Self-Improvement](/20251021-20261020/2609.15802v1) · 专题
   - 阅读理由：经济学模型区分窄口径与广口径能力，并给出反馈回路强度的校准讨论，适合理解加速主张的边界。
   - 公布时间：2026-09-14（日精度）
   - arxiv · 2026-09-14（日精度）：[原文](https://arxiv.org/pdf/2609.15802v1)

任务：研究方向大礼包

固定窗口：arXiv &#91;2025-10-21, 2026-10-21&#41;；会议 &#91;2024-10-21, 2026-10-21&#41;（UTC，结束日不含）

本次候选评审上限 300，最终名单上限 100；本轮内容预算 10。

覆盖限制：仅检索配置范围内已有库存与预算内候选；向量/会议Top-k召回并非全库遍历，不保证找全相关论文。未核实录用、日期边界和缺失库存不能当作已覆盖。

缺失库存：eccv 2025、emnlp 2026、neurips 2026。

研究需求：RSI，递归自我改进（Recursive Self-Improvement），指一个 AI 系统能够参与设计并制造出比自身更强的下一代系统，而新系统又具备更强的能力去设计再下一代，形成一个不断加速的递归循环。强调“递归”和“减少人类依赖”。 保留原需求全部核心边界；本次聚焦已有关键词：recursive self improvement 该关键词原语义：research on AI systems that recursively design and build more capable successor systems

本次细化：本次仅聚焦原有关键词「recursive self improvement」，不扩展原范围。

# recursive-ai

以下为本次固定最终名单，按相关性评分降序；不代表全部相关论文。

1. [Recursive self-improvement of AI research agents](https://arxiv.org/abs/2609.26457v1) · 分数 10
2. [The Last AI Built by Humans: Toward Genuine Recursive Self-Improvement](https://arxiv.org/abs/2609.11873v2) · 分数 9
3. [Frontis-MA1: Training an AI4AI Model towards Recursive Self-Improvement in Machine Learning Engineering](https://arxiv.org/abs/2607.28568v1) · 分数 9
4. [AI4AI-Bench: Benchmarking LLM Agents in Algorithmic Design for Recursive Self-Improvement](https://arxiv.org/abs/2608.20318v1) · 分数 9
5. [Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](https://arxiv.org/abs/2607.07663v2) · 分数 9
6. [From 0-to-1 to 1-to-N: Reproducible Engineering Evidence for MetaAI Recursive Self-Design](https://arxiv.org/abs/2606.09663v1) · 分数 9
7. [NeoHorse-1: Towards Recursive Self-Improvement via Agentic Post-Training with Routing Harness](https://arxiv.org/abs/2609.08183v1) · 分数 9
8. [MetaRSI / RSI2: A Meta-Recursive Self-Improving System for Recursive Self-Improving Systems Themselves](https://arxiv.org/abs/2609.06396v2) · 分数 9
9. [RSI-Master: Structuring Experiments to Guide Autonomous Model Improvement](https://arxiv.org/abs/2609.35561v2) · 分数 9
10. [Self-Reference in Large Language Models: The Introspection Threshold for Recursive Self-Improvement](https://arxiv.org/abs/2607.04277v1) · 分数 9
11. [A Mathematical Framework for AI Singularity: Conditions, Bounds, and Control of Recursive Improvement](https://arxiv.org/abs/2511.10668v1) · 分数 9
12. [Meta&#36;^n&#36;: Recursive Self-Improvement through Emergent Depth](https://arxiv.org/abs/2608.24735v1) · 分数 9
13. [COEVO: Co-Evolving Context and Parameters for Recursive Self-Improvement](https://arxiv.org/abs/2609.33398v1) · 分数 9
14. [Dream-RSI: Recursive Self-Improvement through Evolving Worlds](https://arxiv.org/abs/2609.14858v1) · 分数 9
15. [RSIBench-Data: Benchmarking Data-Centric Research for Recursive Self-Improvement](https://arxiv.org/abs/2607.25886v1) · 分数 9
16. [Generalized Agent Iteration: One Formal Framework for Iterative Policy Improvement and Recursive Self-Improvement](https://arxiv.org/abs/2609.13406v1) · 分数 9
17. [Recursive Criticality of AI Self-Improvement](https://arxiv.org/abs/2609.00137v1) · 分数 9
18. [ModularRSI: Modular and Generalizable Recursive Harness Self-Improvement](https://arxiv.org/abs/2609.14857v1) · 分数 9
19. [MetaSkill-Evolve: Recursive Self-Improvement of LLM Agents via Two-Timescale Meta-Skill Evolution](https://arxiv.org/abs/2607.05297v1) · 分数 9
20. [MaD-RSI: Model-as-Data for Recursive Self-Improvement of Agent Harnesses](https://arxiv.org/abs/2610.28201v1) · 分数 9
21. [R&#36;^2&#36; Flow: Recursive Self-Improvement via Recursive Skill Evolution](https://arxiv.org/abs/2609.33867v1) · 分数 9
22. [Self Improvement via Fast Tree-search](https://arxiv.org/abs/2609.19526v1) · 分数 9
23. [Gödel Agent: A Self-Referential Agent Framework for Recursively Self-Improvement](https://aclanthology.org/2025.acl-long.1354/) · 分数 9
24. [AdaRSI: On-Demand Recursive Self-Improvement for Embodied Agents](https://arxiv.org/abs/2610.20474v1) · 分数 9
25. [Gödel Forest: Balancing Search Depth and Breadth for Data-Centric Recursive Self-Improvement](https://arxiv.org/abs/2609.36675v1) · 分数 9
26. [Terminal-RSI: Recursive Self-Improving Terminal Agents via Recursive Self-Rewrite and Policy-Refine](https://arxiv.org/abs/2610.22192v1) · 分数 9
27. [Language Models Learn to Improve Language Models](https://arxiv.org/abs/2610.23344v1) · 分数 9
28. [Learning to Compose: Recursive Self-Improvement of Shared Executable Stacks for Zero-Shot Long-Horizon Robot Manipulation](https://arxiv.org/abs/2610.24464v1) · 分数 9
29. [Hyperagents](https://arxiv.org/abs/2603.19461v1) · 分数 9
30. [The Red Queen Gödel Machine: Co-Evolving Agents and Their Evaluators](https://arxiv.org/abs/2606.26294v2) · 分数 9
31. [What Stops Recursive Self-Improvement in Robotics? Lessons from 123 Rounds of Agentic Skill Discovery](https://arxiv.org/abs/2609.31760v1) · 分数 9
32. [MMLA-RSI: Recursive Self-Improvement through RTT and RTMA](https://arxiv.org/abs/2610.20294v1) · 分数 8
33. [RSIGym: A Flexible Environment for Recursive Self-Improvement](https://arxiv.org/abs/2610.10310v1) · 分数 8
34. [Evolutionary Safety of Recursive Self-Improving AI: Taxonomy, Risk Discovery, and Evaluation](https://arxiv.org/abs/2609.31186v1) · 分数 8
35. [The Economics of Recursive Self-Improvement](https://arxiv.org/abs/2609.15802v1) · 分数 8
36. [HarnessPro: Recursive Harness Self-Improvement with Pareto Optimization for Performance-Cost Trade-offs](https://arxiv.org/abs/2610.26770v2) · 分数 8
37. [PAST-Bench: Benchmarking the Foundations of Recursive Self-Improvement in Personal Agents](https://arxiv.org/abs/2608.04003v1) · 分数 8
38. [RRSI: Regularized Recursive Self-Improvement of Agent Harnesses](https://arxiv.org/abs/2609.24972v2) · 分数 8
39. [SAHOO: Safeguarded Alignment for High-Order Optimization Objectives in Recursive Self-Improvement](https://arxiv.org/abs/2603.06333v1) · 分数 8
40. [VibeTraining-Bench: Data-Trainer-Harness Co-Design for Iterative System Improvement](https://arxiv.org/abs/2610.26342v2) · 分数 8
41. [RSI Control: Can AI Models Perform Covert Sabotage in the Self-Improvement Process?](https://arxiv.org/abs/2610.27735v1) · 分数 8
42. [Drafting Agents, Not Just Tokens: Speculative Recursive Self-Improvement for Agentic Systems](https://arxiv.org/abs/2610.16491v1) · 分数 8
43. [The Computational Boundary of Inference: Capability Internalization, Training, and the Turing Jump](https://arxiv.org/abs/2605.27381v1) · 分数 8
44. [RSIAgent: Autonomous Exploration for Recursive Self-improvement in New Environments](https://arxiv.org/abs/2609.15364v2) · 分数 8
45. [AReaL-RSI: Adaptive Scaling and Coordination of Recursive Self-Improvement](https://arxiv.org/abs/2610.18083v1) · 分数 8
46. [Auditing the Product, Not the Recursion: The Evaluation Evidence Behind Recursive Self-Improvement Claims](https://arxiv.org/abs/2610.27610v1) · 分数 8
47. [RSI-Anything: Unlocking Recursive Self-Improvement with World Models](https://arxiv.org/abs/2610.13912v1) · 分数 8
48. [RSI-Forge: From Research Papers to Environments for Recursive Self-Improvement](https://arxiv.org/abs/2610.09426v1) · 分数 8
49. [Mixture of Self-Improving Branches For Agent Harness Optimization](https://arxiv.org/abs/2609.37834v1) · 分数 8
50. [Recursive Reward Improvement via Adversarial Meta-Prompt Evolution](https://arxiv.org/abs/2610.21040v1) · 分数 8
51. [Breaking the Environment Wall: Evolving LLM Agent Environments for Recursive Self-Improvement](https://arxiv.org/abs/2609.29773v1) · 分数 8
52. [Verification and Self-Improvement in Agentic AI: Foundations and Limits](https://arxiv.org/abs/2610.10611v1) · 分数 8
53. [NOVA: Fundamental Limits of Knowledge Discovery Through AI](https://arxiv.org/abs/2605.15219v3) · 分数 8
54. [Compile Once, Run Cheap: Frozen, Portable Skills for Embodied Agents, and What Recursive Self-Improvement Adds](https://arxiv.org/abs/2610.25114v1) · 分数 8
55. [Self-Aware Recursively Self-Improving Agents for Personal Singularity: A Goal-, Scope-, Tool-, and Benchmark-Driven Multi-Agent Architecture](https://arxiv.org/abs/2607.12254v2) · 分数 8
56. [Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses](https://arxiv.org/abs/2608.24876v1) · 分数 8
57. [Where is Physical RSI capability from? An Observational Scaling Law of LLM-as-policy](https://arxiv.org/abs/2610.26848v1) · 分数 8
58. [Recursive Harness Self-Improvement](https://arxiv.org/abs/2607.15524v1) · 分数 8
59. [ReSAIL: Mitigating Collapse in Iterative Agent Self-Distillation](https://arxiv.org/abs/2609.39306v1) · 分数 8
60. [R&#36;^2&#36;Orch: Recursive Self-Improvement for Agent Orchestration via Self-Play within a Skill-Internalization Loop](https://arxiv.org/abs/2610.22740v1) · 分数 8
61. [Which Self-Improvements Should We Trust? Reliable Self-Improvement When Agents Reuse Their Benchmarks](https://arxiv.org/abs/2609.33180v2) · 分数 8
62. [Continually self-improving AI](https://arxiv.org/abs/2603.18073v1) · 分数 8
63. [Self-Evolving Coding Agents via Harness-Policy Optimization](https://arxiv.org/abs/2610.22791v1) · 分数 8
64. [SIA: Self Improving AI with Harness &amp; Weight Updates](https://arxiv.org/abs/2605.27276v2) · 分数 8
65. [The Self-Improvement Problem](https://arxiv.org/abs/2610.21646v1) · 分数 8
66. [ASI-Evolve: AI Accelerates AI](https://arxiv.org/abs/2603.29640v1) · 分数 8
67. [From Existing Methods to New Research Ideas: Two Perspectives on Recursive Self-Improvement](https://arxiv.org/abs/2610.14625v1) · 分数 7
68. [EvalResearchBench: Can AI Agents Design Their Own Evaluations?](https://arxiv.org/abs/2610.04184v1) · 分数 7
69. [SBCO: Self-Supervised, Verifier-Grounded Harness Optimization For Planning Agents](https://arxiv.org/abs/2608.10157v1) · 分数 7
70. [Who Improves the Robot? Toward Physical Recursive Self-Improvement](https://arxiv.org/abs/2610.18842v1) · 分数 7
71. [Hippo: Training-Free Agent Self-Evolution via Hippocampal Replay](https://arxiv.org/abs/2610.24453v1) · 分数 7
72. [RecurSE: Bounded Recursive Self-Evaluation for LLM Rubric Judges](https://arxiv.org/abs/2608.24231v1) · 分数 7
73. [Self-Improving AI Agents through Self-Play](https://arxiv.org/abs/2512.02731v1) · 分数 7
74. [Mathematics and Coding are Universal AI Benchmarks](https://arxiv.org/abs/2512.13764v1) · 分数 7
75. [MLS-Bench: A Holistic and Rigorous Assessment of AI Systems on Building Better AI](https://arxiv.org/abs/2605.08678v3) · 分数 7
76. [Active Thinking Model: A Goal-Directed Self-Improving Framework for Real-World Adaptive Intelligence](https://arxiv.org/abs/2511.00758v1) · 分数 7
77. [Self-Play Only Evolves When Self-Synthetic Pipeline Ensures Learnable Information Gain](https://arxiv.org/abs/2603.02218v2) · 分数 7
78. [S3Gym: Can LLMs Turn Self-Testing and Self-Judging into Self-Improvement?](https://arxiv.org/abs/2608.31100v1) · 分数 7
79. [Self-Improving Transformers Overcome Easy-to-Hard and Length Generalization Challenges](https://proceedings.mlr.press/v267/lee25d.html) · 分数 7
80. [Audited Skill-Graph Self-Improvement for Agentic LLMs via Verifiable Rewards, Experience Synthesis, and Continual Memory](https://arxiv.org/abs/2512.23760v1) · 分数 7
81. [Towards AGI A Pragmatic Approach Towards Self Evolving Agent](https://arxiv.org/abs/2601.11658v1) · 分数 7
82. [AutoResearch-RL: Perpetual Self-Evaluating Reinforcement Learning Agents for Autonomous Neural Architecture Discovery](https://arxiv.org/abs/2603.07300v2) · 分数 7
83. [Survival is the Only Reward: Sustainable Self-Training Through Environment-Mediated Selection](https://arxiv.org/abs/2601.12310v1) · 分数 7
84. [Iterative Deployment Improves Planning Skills in LLMs](https://arxiv.org/abs/2512.24940v1) · 分数 7
85. [Absolute Zero: Reinforced Self-play Reasoning with Zero Data](https://papers.neurips.cc/paper_files/paper/2025/hash/9837dc00ff67d176373268ed48042d49-Abstract-Conference.html) · 分数 7
86. [SAEScientist-Bench: Can AI Agents Conduct Autonomous SAE Interpretability Research?](https://arxiv.org/abs/2609.09113v2) · 分数 6
87. [Test-time Recursive Thinking: Self-Improvement without External Feedback](https://arxiv.org/abs/2602.03094v1) · 分数 6
88. [Naive Prompt Optimization: Rethinking the Need for Complex Prompt Search](https://arxiv.org/abs/2608.27266v1) · 分数 6
89. [When AI Reviews Its Own Code: Recursive Self-Training Collapse in Code LLMs](https://arxiv.org/abs/2606.28438v1) · 分数 6
90. [From Solo to Social Learning: Characterizing Recursive Social Improvement in LLMs](https://arxiv.org/abs/2609.38516v2) · 分数 6
91. [Self-Verification Provably Prevents Model Collapse in Recursive Synthetic Training](https://papers.neurips.cc/paper_files/paper/2025/hash/3380e8116452e0efbf36f35d95e88c94-Abstract-Conference.html) · 分数 6
92. [Mind the Gap: Examining the Self-Improvement Capabilities of Large Language Models](https://proceedings.iclr.cc/paper_files/paper/2025/hash/63943ee9fe347f3d95892cf87d9a42e6-Abstract-Conference.html) · 分数 6
93. [A Task-Centric Theory for Iterative Self-Improvement with Easy-to-Hard Curricula](https://arxiv.org/abs/2602.10014v3) · 分数 6
94. [TextBO: Bayesian Optimization in Language Space for Eval-Efficient Self-Improving AI](https://arxiv.org/abs/2511.12063v3) · 分数 6
95. [Self-Improvement in Language Models: The Sharpening Mechanism](https://proceedings.iclr.cc/paper_files/paper/2025/hash/bee8c2bc757f6bbc3efd7cf1b979f0c9-Abstract-Conference.html) · 分数 6
96. [AI &amp; Human Co-Improvement for Safer Co-Superintelligence](https://arxiv.org/abs/2512.05356v2) · 分数 6
97. [Agent Plasticity: Measuring Self-Improvement Through Experience](https://arxiv.org/abs/2610.08902v1) · 分数 6
98. [Self-Improvements in Modern Agentic Systems: A Survey](https://arxiv.org/abs/2607.13104v1) · 分数 6
99. [Guided Self-Evolving LLMs with Minimal Human Supervision](https://arxiv.org/abs/2512.02472v1) · 分数 6
100. [Better than Your Teacher: LLM Agents that learn from Privileged AI Feedback](https://proceedings.iclr.cc/paper_files/paper/2025/hash/1c60ed2b01120d383eebf12dc7a0e138-Abstract-Conference.html) · 分数 6

[按公布时间查看](#/starter-pack/20261021-7a1f856048a9/dates)

阅读内容：已完成 10，待补充 90。
