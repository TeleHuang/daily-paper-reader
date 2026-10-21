---
title: "Better than Your Teacher: LLM Agents that learn from Privileged AI Feedback"
authors: "Sanjiban Choudhury, Paloma Sodhi"
date: 2025
pdf: "https://proceedings.iclr.cc/paper_files/paper/2025/file/1c60ed2b01120d383eebf12dc7a0e138-Paper-Conference.pdf"
tags: ["query:recursive-ai"]
score: 6
source: ICLR-2025-Accepted
selection_source: long-range
publication_date: 2025
publication_date_precision: year
publication_date_source: conference year only; exact release date unverified
publication_date_kind: unknown
id: openreview-iclr-2025-st7xqfgbah
canonical_id: "work:433b52967578eb9245ca7ce9"
research_run_id: 20261021-7a1f856048a9
research_mode: starter
reading_status: pending
---

## Abstract
While large language models (LLMs) show impressive decision-making abilities, current methods lack a mechanism for automatic self-improvement from errors during task execution. We propose LEAP, an iterative fine-tuning framework that continually improves LLM agents using feedback from AI expert teachers. Our key insight is to equip the expert teachers with a privileged state -- information available during training but hidden at test time. This allows even weak experts to provide precise guidance, significantly improving the student agent's performance without access to privileged information at test time.
We evaluate LEAP on multiple decision-making benchmarks, including text-based games (ALFWorld), web navigation (WebShop), and interactive coding (Intercode Bash). Our experiments show that LEAP (1) outperforms behavior cloning and ReAct baselines (2) enables weak student models (e.g., Llama3-8B) to exceed performance of strong teacher models (GPT-4o), and (3) allows weak models to self-improve using privileged versions of themselves. 
We provide a theoretical analysis showing that LEAP's success hinges on balancing privileged information with student’s realizability, which we empirically validate. Our code is available at \url{https://leap-llm.github.io}.

## 专题评审

专题相关性评分：6/10。

研究LLM智能体通过AI教师反馈迭代自我改进，但未涉及递归设计并构建更强后继系统。

<!-- research-reading-pending -->
中文总结与全文内容待生成；当前仅提供原始论文元数据与摘要。
<!-- /research-reading-pending -->
