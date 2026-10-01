---
layout: post
title: "Raha: A General Tool to Analyze WAN Degradation"
date: 2026-10-06
paper_authors: "B. Arzani, S. Taheri, P. Namyar, R. Beckett, S. K. R. Kakarla, E. Jalilipour"
paper_venue: "SIGCOMM 2025"
paper_url: "https://doi.org/10.1145/3718958.3754348"
week: 2
tags: [wan, traffic-engineering, resilience]
---

## Key Idea

Raha is a tool that proactively searches for combinations of link failures and traffic-demand changes that cause severe degradation in a traffic-engineered WAN. Given a network's topology, capacities, demand, and traffic-engineering algorithm, it uses optimization to generate adversarial scenarios instead of relying on operators to guess which failures to test.

## Critique

The most convincing result is that Raha finds scenarios with at least twice as much degradation as methods limited to one or two link failures. This shows that conventional testing can seriously underestimate a WAN's vulnerability, especially when rerouted traffic overloads another link. Clustering makes the search practical on large networks, although dividing the topology may miss interactions between clusters and therefore may not always find the true worst case. Raha also depends on how accurately its inputs represent real traffic and failure probabilities.

## Connections

Raha extends the traffic-engineering ideas in B4 by testing whether a centrally managed WAN remains effective under hostile conditions. It also connects to partial reachability: both papers reject a simple working-versus-failed model and instead study how failures can leave a network operating with substantially reduced or uneven service.
