---
layout: "post"
title: "Revisiting RDMA Reliability for Lossy Fabrics"
date: "2026-11-05"
class_date: "2026-10-27"
paper_authors: "Wenxue Li et al."
paper_venue: "SIGCOMM 2025"
paper_url: "https://gaoxiong.site/files/sigcomm25-dcp.pdf"
week: 5
---

## Key idea

DCP rethinks RDMA reliability by allowing payload packets to be lost while preserving small control information in the network. Switches trim congested packets into header-only notifications, and redesigned RNICs use that information for fast retransmission and packet tracking while accommodating packet-level load balancing.

## Critique

The P4-switch and FPGA-RNIC prototypes are convincing because the proposal changes both sides of the network interface, rather than assuming a transport-only fix is sufficient. However, replacing broad losslessness with a protected control plane does not eliminate assumptions about reliable delivery: the paper still includes a coarse timeout fallback when control information is lost. A useful deployment question is how often that fallback activates under correlated failures, and whether the extra switch and RNIC changes are acceptable operationally.

## Connections

Compared with the [Simulate Before Sending reading](https://gavinnwang.github.io/cs440-blog/2026/10/22/simulate-before-sending/), DCP makes losses cheaper to repair rather than primarily trying to prevent data loss through advance probes. It also complements our Justitia project: fabric reliability and isolation between applications sharing a NIC address different sources of poor performance.

AI assistance: AI was used to help draft and organize this post.
