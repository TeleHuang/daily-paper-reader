---
title: "Mind the Gap: Examining the Self-Improvement Capabilities of Large Language Models"
authors: "Yuda Song, Hanlin Zhang, Carson Eisenach, Sham M. Kakade, Dean Foster, Udaya Ghai"
date: 2025
pdf: "https://proceedings.iclr.cc/paper_files/paper/2025/file/63943ee9fe347f3d95892cf87d9a42e6-Paper-Conference.pdf"
tags: ["query:recursive-ai"]
score: 6
source: ICLR-2025-Accepted
selection_source: long-range
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
id: openreview-iclr-2025-mtjsmcf3ek
canonical_id: "work:1403eac4ab945d77d5c9ad6c"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
Self-improvement is a mechanism in Large Language Model (LLM) pre-training, post-training and test-time inference. We explore a framework where the model verifies its own outputs, filters or reweights data based on this verification, and distills the filtered data.  Despite several empirical successes, a fundamental understanding is still lacking. In this work, we initiate a comprehensive, modular and controlled study on LLM self-improvement. We provide a mathematical formulation for self-improvement, which is largely governed by a quantity which we formalize as the **generation-verification gap**. Through experiments with various model families and tasks, we discover a scaling phenomenon of self-improvement -- a variant of the generation-verification gap scales monotonically with the model pre-training flops. We also examine when self-improvement is possible, an iterative self-improvement procedure, and ways to improve its performance. Our findings not only advance understanding of LLM self-improvement with practical implications, but also open numerous avenues for future research into its capabilities and boundaries.

## 专题评审

专题相关性评分：6/10。

该文研究LLM自我改进机制与生成-验证差距，属实质邻近但非递归构建更强后继系统。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
