---
layout: post
title: "Waiting for QUIC: Passive Measurements to Understand QUIC Deployments"
date: 2026-10-20
paper_authors: "Jonas Mücke, Marcin Nawrocki, Raphael Hiesgen, Patrick Sattler, Johannes Zirngibl, Georg Carle, Jan Luxemburk, Thomas C. Schmidt, Matthias Wählisch"
paper_venue: "CoNEXT 2025"
paper_url: "https://doi.org/10.1145/3768988"
week: 5
tags: [quic, measurement, hypergiants]
---

## Key Idea

TODO: write in your own words.

- Passive measurement of QUIC's rollout over five years since its 2021 standardization, using backscatter traffic from the UCSD network telescope.
- Four findings: Meta, Google, and Cloudflare tune QUIC very differently (max retransmissions, timeouts); off-net hypergiant deployments can be fingerprinted from packet features (connection IDs, packet coalescence, packet lengths); configurations change across measurement periods; connection IDs reveal load balancer structure (about 95% of host IDs appear within 1,000 connections).
- Results cross-checked with passive QUIC flow recording and active probing.

## Critique

TODO: write in your own words.

- What is convincing, what is not, what is missing? Consider: what backscatter coverage can and cannot show, and what passive measurement misses.

## Connections

TODO: link to earlier posts where relevant.
