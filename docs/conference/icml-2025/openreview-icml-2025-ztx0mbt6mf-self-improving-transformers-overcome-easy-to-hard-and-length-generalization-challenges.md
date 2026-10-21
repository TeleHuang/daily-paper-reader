---
title: Self-Improving Transformers Overcome Easy-to-Hard and Length Generalization Challenges
authors: "Nayoung Lee, Ziyang Cai, Avi Schwarzschild, Kangwook Lee, Dimitris Papailiopoulos"
date: 2025-10-06
pdf: "https://raw.githubusercontent.com/mlresearch/v267/main/assets/lee25d/lee25d.pdf"
tags: ["query:recursive-ai"]
score: 7
source: ICML-2025-Accepted
selection_source: long-range
publication_date: 2025-10-06
publication_date_precision: day
publication_date_source: "https://raw.githubusercontent.com/mlresearch/v267/gh-pages/_config.yml"
publication_date_kind: proceedings
id: openreview-icml-2025-ztx0mbt6mf
canonical_id: "work:9c5d4d2cd1020d5dad51d91c"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
Large language models often struggle with length generalization and solving complex problem instances beyond their training distribution. We present a self-improvement approach where models iteratively generate and learn from their own solutions, progressively tackling harder problems while maintaining a standard transformer architecture. Across diverse tasks including arithmetic, string manipulation, and maze solving, our method enables models to solve problems far beyond their initial training distribution—for instance, generalizing from 10-digit to 100-digit addition without apparent saturation. We observe that filtering for correct self-generated examples leads to exponential improvements in out-of-distribution performance across training rounds. Additionally, starting from pretrained models significantly accelerates this self-improvement process for several tasks. Our results demonstrate how controlled weak-to-strong curricula can systematically expand model capabilities while preserving architectural simplicity.

## 专题评审

专题相关性评分：7/10。

研究模型通过自生成解答迭代提升能力，属自我改进但未涉及递归设计并构建更强后继系统。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
