---
layout: "post"
title: "DistTrain: Addressing Model and Data Heterogeneity with Disaggregated Training for Multimodal Large Language Models"
date: "2026-11-05"
class_date: "2026-10-29"
paper_authors: "Zili Zhang et al."
paper_venue: "SIGCOMM 2025"
paper_url: "https://arxiv.org/html/2408.04275v4"
week: 6
---

## Key idea

DistTrain argues that multimodal training wastes resources when encoders, the language-model backbone, and generators must share the same resource and parallelism choices. It separates their orchestration and moves data preprocessing out of the training process, enabling independent resource allocation and data reordering to reduce pipeline bubbles and stragglers.

## Critique

The production-scale evaluation is a strength: the paper reports 54.7% model FLOPs utilization for a 72B model on 1,172 GPUs, and throughput improvements of up to 2.2 times over Megatron-LM. However, the improvement depends on both model structure and infrastructure, so the maximum speedup should not be treated as universal. A useful extension would test how the tradeoff changes when inter-node bandwidth is limited or a workload changes enough to make the selected allocation less effective.

## Connections

The [Simulate Before Sending reading](https://gavinnwang.github.io/cs440-blog/2026/10/22/simulate-before-sending/) also targets training stragglers, but focuses on communication losses instead of heterogeneous computation and preprocessing. Together, they suggest that optimizing a training job requires identifying the actual source of waiting, rather than assuming every slowdown is a network bottleneck.

AI assistance: AI was used to help draft and organize this post.
