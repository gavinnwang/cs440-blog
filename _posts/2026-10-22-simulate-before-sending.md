---
layout: post
title: "Simulate Before Sending: Rethinking Transport in Datacenter Networks"
date: 2026-10-22
paper_authors: "Dan Straussman, Isaac Keslassy, Alexander Shpiner, Liran Liss"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.19"
week: 5
tags: [datacenter, transport, ai-training]
---

## Key Idea

TODO: write in your own words.

- Problem: AI training collectives (All-Reduce, All-to-All) are bursty, especially with MoE models; on lossy commodity datacenter networks a few dropped packets create stragglers that blow up collective completion time (CCT).
- Idea: a shadow network running at 1/100th the rate with 100x smaller packets. A tiny Sim packet probes a random path first; if it survives, the real Data packet sent later on the same path should survive too.
- Approximation on commodity switches: separate Sim/Data queues via traffic class partitioning, Sim queue at strict priority but token-bucket rate-limited, tiny buffers (B=12, 64-byte Sims vs 9KB jumbo Datas). Failed Sim means re-probe a new path; Data goes out a fixed RTTmax after its Sim.
- Results: faster CCTs, small queues, virtually zero loss, holds up under oversubscription.

## Critique

TODO: write in your own words.

- What is convincing, what is not, what is missing? Consider: the capacity traded for Sims, the RTTmax assumption, and that Sim success makes Data loss unlikely rather than impossible. Contrast with pHost/dcPIM (receiver tokens, no network visibility) and ExpressPass/Harmony (need non-commodity switch features).

## Connections

TODO: link to earlier posts where relevant.
