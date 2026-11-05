---
layout: "post"
title: "OpenFLAME: A Federated Spatial Naming Infrastructure"
date: "2026-11-05"
class_date: "2026-11-05"
paper_authors: "Sagar Bharadwaj et al."
paper_venue: "NINeS 2026"
paper_url: "https://drops.dagstuhl.de/storage/01oasics/oasics-vol139-nines2026/html/OASIcs.NINeS.2026.20/OASIcs.NINeS.2026.20.html"
week: 7
---

## Key idea

OpenFLAME lets independent organizations operate maps and discover map servers for a physical region, rather than requiring one provider to own the entire map. It builds spatial discovery on DNS using geographic names, delegation, and support for overlapping regions, then combines services such as routing and localization across independently managed maps.

## Critique

The working prototype and evaluation make the architectural proposal concrete, while caching helps limit discovery overhead as users move. However, federation carries a measurable cost: the evaluated sharded routes are 12% longer at the median, and routing queries take about twice as long as centralized queries. Those results make map-selection quality and the handling of overlapping authorities important questions, rather than assuming decentralization automatically improves the user experience.

## Connections

This connects to the [partial-reachability reading](https://gavinnwang.github.io/cs440-blog/2026/10/01/partial-reachability/): service availability depends on which independently operated components a client can discover and contact. It also extends the naming discussion by separating the discovery of an authority from the data and services that authority provides.

AI assistance: AI was used to help draft and organize this post.
