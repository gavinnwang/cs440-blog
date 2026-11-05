---
layout: "post"
title: "Exploring the Benefits of Carbon-Aware Routing"
date: "2026-11-05"
class_date: "2026-11-03"
paper_authors: "Sawsan El-Zahr, Paul Gunning, Noa Zilberman"
paper_venue: "CoNEXT 2023"
paper_url: "https://eng.ox.ac.uk/media/jwpbeeab/elzahr23benefits.pdf"
week: 6
---

## Key idea

This paper examines whether routing decisions can reduce network carbon emissions using electricity carbon intensity and equipment power consumption. Its CATE heuristic combines carbon-aware traffic engineering with disabling selected links, recognizing that moving traffic alone may save little when equipment consumes substantial power while idle.

## Critique

The distinction between reducing traffic and reducing actual power consumption is the strongest part of the argument, because a greener-looking route is not automatically a lower-emissions network. However, CATE is evaluated as a periodic, offline optimization that depends on traffic estimates and power models. The operational question is whether predicted savings survive sudden demand changes, link failures, and the need to restore disabled capacity, especially when resilience requirements leave little redundant equipment available to switch off.

## Connections

Like [Raha](https://gavinnwang.github.io/cs440-blog/2026/10/06/raha-wan-degradation/), this paper shows that traffic engineering must be judged against more than normal-case throughput. Raha motivates testing degraded conditions, while carbon-aware routing adds another objective that should be evaluated alongside capacity, delay, and the ability to recover from failures.

AI assistance: AI was used to help draft and organize this post.
