---
title: "Absolute Zero: Reinforced Self-play Reasoning with Zero Data"
authors: "Andrew Zhao, Yiran Wu, Yang Yue, Tong Wu, Quentin Xu, Yang Yue, Matthieu Lin, Shenzhi Wang, Qingyun Wu, Zilong Zheng, Gao Huang"
date: 2025
pdf: "https://papers.neurips.cc/paper_files/paper/2025/file/9837dc00ff67d176373268ed48042d49-Paper-Conference.pdf"
tags: ["query:recursive-ai"]
score: 7
source: NeurIPS-2025-Accepted
selection_source: long-range
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
id: openreview-neurips-2025-nezsgqhxda
canonical_id: "work:38db5d84ab066b4648d218b9"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
Reinforcement learning with verifiable rewards (RLVR) has shown promise in enhancing the reasoning capabilities of large language models by learning directly from rule-based outcome rewards. Recent RLVR works that operate under the zero setting avoid supervision in labeling the reasoning process, but still depend on manually curated collections of questions and answers for training. The scarcity of high-quality, human-produced examples raises concerns about the long-term scalability of relying on human supervision, a challenge already evident in the domain of language model pretraining. Furthermore, in a hypothetical future where AI surpasses human intelligence, tasks provided by humans may offer limited learning potential for a superintelligent system. To address these concerns, we propose a new RLVR paradigm called Absolute Zero, in which a single model learns to propose tasks that maximize its own learning progress and improves reasoning by solving them, without relying on any external human or distillation data. Under this paradigm, we introduce the Absolute Zero Reasoner (AZR), a system that self-evolves its training curriculum and reasoning ability. AZR uses a code executor to both validate self-proposed code reasoning tasks and verify answers, serving as an unified source of verifiable feedback to guide open-ended yet grounded learning. Despite being trained entirely without external data, AZR achieves overall SOTA performance on coding and mathematical reasoning tasks, outperforming existing zero-setting models that rely on tens of thousands of in-domain human-curated examples. Furthermore, we demonstrate that AZR can be effectively applied across different model scales and is compatible with various model classes.

## 专题评审

专题相关性评分：7/10。

模型自提议任务并自我进化、减少人类依赖，但未涉及递归设计更强后继系统。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
