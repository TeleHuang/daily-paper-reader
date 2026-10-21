---
title: "Self-Improvement in Language Models: The Sharpening Mechanism"
authors: "Audrey Huang, Adam Block, Dylan J Foster, Dhruv Rohatgi, Cyril Zhang, Max Simchowitz, Jordan T. Ash, Akshay Krishnamurthy"
date: 2025
pdf: "https://proceedings.iclr.cc/paper_files/paper/2025/file/bee8c2bc757f6bbc3efd7cf1b979f0c9-Paper-Conference.pdf"
tags: ["query:recursive-ai"]
score: 6
source: ICLR-2025-Accepted
selection_source: long-range
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
id: openreview-iclr-2025-wjaukwci9o
canonical_id: "work:c53aa13df6f521985368adfc"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
Recent work in language modeling has raised the possibility of “self-improvement,” where an LLM evaluates and refines its own generations to achieve higher performance without external feedback. It is impossible for this self-improvement to create information that is not already in the model, so why should we expect that this will lead to improved capabilities? We offer a new theoretical perspective on the capabilities of self-improvement through a lens we refer to as “sharpening.” Motivated by the observation that language models are often better at verifying response quality than they are at generating correct responses, we formalize self-improvement as using the model itself as a verifier during post-training in order to ‘sharpen’ the model to one placing large mass on high-quality sequences, thereby amortizing the expensive inference-time computation of generating good sequences. We begin by introducing a new statistical framework for sharpening in which the learner has sample access to a pre-trained base policy. Then, we analyze two natural families of self improvement algorithms based on SFT and RLHF. We find that (i) the SFT-based approach is minimax optimal whenever the initial model has sufficient coverage, but (ii) the RLHF-based approach can improve over SFT-based self- improvement by leveraging online exploration, bypassing the need for coverage. We view these findings as a starting point toward a foundational understanding that can guide the design and evaluation of self-improvement algorithms.

## 专题评审

专题相关性评分：6/10。

研究语言模型自我评估与精炼的理论机制，属自我改进但非递归构建更强后继系统。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
