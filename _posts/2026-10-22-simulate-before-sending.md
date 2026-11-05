---
layout: post
title: "Simulate Before Sending: Rethinking Transport in Datacenter Networks"
date: 2026-10-22
paper_authors: "Dan Straussman, Isaac Keslassy, Alexander Shpiner, Liran Liss"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.19"
week: 5
tags: [datacenter, transport, ai-training]
updated: 2026-11-05
class_date: 2026-10-22
---

## Key idea

dcSim sends a small probe along a candidate path before releasing its corresponding data packet, aiming to avoid losses that create stragglers in training collectives. Separate probe and data queues, rate-limited probe priority, and a fixed delay between probe and data are designed to make probe outcomes predict whether the larger packet can traverse the path.

## Critique

The proposal is compelling because it shifts effort from recovering dropped data to avoiding those drops, and the evaluation reports low collective completion times with very little loss. However, the paper also gives a multistage counterexample where a successful probe does not guarantee data delivery. That qualification matters: the practical result depends on scheduling and timing assumptions, so a convincing deployment study should examine failures, mixed traffic, and the capacity consumed by probe traffic rather than calling the network strictly lossless.

## Connections

This extends the [No Signal to Rule Them All reading](https://gavinnwang.github.io/cs440-blog/2026/10/15/no-signal-to-rule-them-all/) by making the congestion signal an advance experiment along a path. Both readings raise the question of how much control a sender can obtain from information that is necessarily incomplete or delayed.

AI assistance: AI was used to help draft and organize this post.
