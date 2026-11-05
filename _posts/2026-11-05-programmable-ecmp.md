---
layout: "post"
title: "Unlocking ECMP Programmability for Precise Traffic Control"
date: "2026-11-05"
class_date: "2026-10-08"
paper_authors: "Yadong Liu et al."
paper_venue: "NSDI 2025"
paper_url: "https://www.usenix.org/system/files/nsdi25-liu-yadong.pdf"
week: 3
---

## Key idea

P-ECMP exposes controlled path selection on commodity switches by using ECMP groups, a compiler, and a runtime instead of repeatedly changing flow identifiers and hoping for a useful hash result. An operator specifies topology and traffic-control policies, and end hosts use selectors to apply those policies to particular flows while ordinary traffic continues using ECMP.

## Critique

The production failover deployment is strong evidence that the idea has practical value beyond a simulation, particularly when repeated random attempts create a long recovery tail. However, programmable selection still depends on correct topology information, coordinated updates, and available header and switch resources. The broader use cases should therefore be assessed separately from the deployed failover case, with attention to simultaneous failures and resource limits rather than assuming every advertised policy is equally mature.

## Connections

[Raha](https://gavinnwang.github.io/cs440-blog/2026/10/06/raha-wan-degradation/) identifies WAN conditions that make traffic engineering perform poorly; P-ECMP instead provides a more precise mechanism for acting on path problems within a datacenter. Together, they separate two important tasks: discovering a harmful condition and executing a reliable response.

AI assistance: AI was used to help draft and organize this post.
