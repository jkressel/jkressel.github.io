---
title: "μFork: Supporting POSIX fork Within a Single-Address-Space OS"
collection: publications
category: manuscripts
permalink: /publication/13-10-2025-ufork-jkressel-sosp
excerpt: 'Single-address-space operating systems have well-known lightweightness benefits that result from their central design idea: the kernel and applications share a unique address space. This model makes these operating systems (OSes) incompatible by design with a large class of software: multiprocess POSIX applications. Indeed, the semantics of the primitive used to create POSIX processes, fork, are inextricably tied to the existence of multiple address spaces. Prior approaches addressing this issue trade off lightweightness, compatibility and/or isolation. We propose μFork, a single-address-space operating system design supporting POSIX fork on modern hardware without compromising on any of these key objectives. μFork emulates POSIX processes (μprocesses) and achieves fork by creating for the child a copy of the parent μprocess&#39; memory at a different location within a single address space. This approach presents two challenges: relocating the child&#39;s absolute memory references (pointers), as well as providing user/kernel and μprocesses isolation without impacting lightweightness. We address them using CHERI. We implement μFork and evaluate it upon three real-world use-cases: Redis snapshots, Nginx multi-worker deployments, and Zygote FaaS worker warm-up. μFork outperforms previous work and traditional monolithic OSes on key lightweightness metrics by an order of magnitude, e.g. it can offer a fork-bound FaaS function throughput 24% higher than that of a monolithic OS, and can fork a μprocess in 54 μs, 3.7× faster than a traditional fork.'
date: 2025-10-13
venue: 'SOSP&#39;25'
paperurl: 'https://jkressel.github.io/files/ufork-sosp2025.pdf'
bibtexurl: 'https://jkressel.github.io/files/ufork-sosp2025.bib'
citation: 'John Alistair Kressel, Hugo Lefeuvre, and Pierre Olivier. 2025. µFork:Supporting POSIX fork Within a Single-Address-Space OS. In ACMSIGOPS 31st Symposium on Operating Systems Principles (SOSP ’25)'
---
