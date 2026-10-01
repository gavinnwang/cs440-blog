---
layout: post
title: "Understanding Partial Reachability in the Internet Core"
date: 2026-10-01
paper_authors: "G. Baltra, T. Saluja, Y. Pradkin, J. Heidemann"
paper_venue: "NINeS 2026"
paper_url: "https://nines-conference.org/papers/p004-Baltra.pdf"
week: 2
tags: [routing, reachability, internet-core]
---

## Key Idea

The paper argues that Internet connectivity is not simply “up” or “down.” A network may be reachable from some vantage points but not others, creating a “peninsula,” while an “island” is completely disconnected from the Internet core. Using Taitao and Chiloe with several measurement datasets, the authors find that partial-reachability events occur at least as often as complete outages.

## Critique

The most convincing result is that disagreement between monitors can reflect a real network condition rather than measurement error. I also found the paper’s majority-based definition of the Internet core useful because it avoids relying on services such as Google or Cloudflare. However, identifying the precise causes of long-lived peninsulas remains difficult: routing policy, peering decisions, firewalls, and configuration problems can produce similar observations.

## Connections

The paper complicates the usual binary model of connectivity: the better question is not simply whether a network is reachable, but **from whom**. Its finding that 7% of events account for roughly 90% of time spent in peninsula states also shows that persistent policy problems may matter more than short routing transients.
