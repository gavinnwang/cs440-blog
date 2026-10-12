---
layout: post
title: "No Signal to Rule Them All: A Systematic Analysis of In-Network Congestion Signals"
date: 2026-10-15
paper_authors: "Sarah McClure, Nandita Dukkipati, Sylvia Ratnasamy, Scott Shenker"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.12"
week: 4
tags: [congestion-control, telemetry, datacenter]
---

## Key Idea

The [paper](https://doi.org/10.4230/OASIcs.NINeS.2026.12) asks which in-network signals best support datacenter congestion control. Using R+, an extension of Remy, the authors learn controllers for different signals and throughput-delay objectives, then evaluate them in ns-3. Average performance with telemetry is generally within 3% of end-to-end performance, although link utilization tends to favor low delay and queue measurements favor throughput.

## Critique

Training a controller for each signal set makes the comparison more convincing because it reduces dependence on one algorithm's design. However, the conclusions still depend on R+'s ability to find strong controllers and on relatively simple simulated topologies. I would want stronger evidence that telemetry's benefits under extreme loads justify its deployment cost, particularly when applications care about tail latency or flows have competing objectives.

## Connections

Like my [Raha post]({{ '/2026/10/06/raha-wan-degradation/' | relative_url }}), this paper shows why average network performance can hide important behavior under difficult conditions. It also connects to the [Internet invariants reading]({{ '/2026/09/24/internet-invariants/' | relative_url }}) by questioning whether conclusions hold when workloads and design assumptions change.
