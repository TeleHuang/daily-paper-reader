---
title: Self-Verification Provably Prevents Model Collapse in Recursive Synthetic Training
authors: "Shi Fu, Yingjie Wang, Yuzhu Chen, Li Shen, Dacheng Tao"
date: 2025
pdf: "https://papers.neurips.cc/paper_files/paper/2025/file/3380e8116452e0efbf36f35d95e88c94-Paper-Conference.pdf"
tags: ["query:recursive-ai"]
score: 6
source: NeurIPS-2025-Accepted
selection_source: long-range
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
id: openreview-neurips-2025-x5hk8ams6w
canonical_id: "work:2d09e363373dcdce1295c358"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
Large generative models are increasingly trained on synthetic data from earlier generations, raising concerns about *model collapse*, a progressive performance decline consistently observed in empirical studies. However, theoretical understanding of recursive training dynamics and their failure modes remains limited. In this work, we theoretically show that recursive training inherently leads to exponential error growth unless mitigated by sufficient real data.  Addressing the growing scarcity of real data, we introduce a self-verification mechanism enabling models to filter their outputs based on internal confidence scores without external validation. Through rigorous analysis, we derive finite-sample error bounds demonstrating that self-verification alone can prevent collapse, even in fully synthetic training regimes. Our theoretical framework extends to large language models (LLMs), characterizing the conditions under which recursive training can maintain stability without performance degradation.

## 专题评审

专题相关性评分：6/10。

研究递归合成训练中的模型崩溃与自验证，属递归训练但非递归自我改进系统设计。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
