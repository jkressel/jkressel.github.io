---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
Hi, I'm John Alistair Kressel, a final year PhD student at the University of Manchester. My advisors are [Pierre Olivier](https://sites.google.com/view/pierreolivier) and [Hugo Lefeuvre](https://owl.eu.com/). My research explores the intersection of single-address-space systems and OSes and systems security. I focus on fundamental system design, specifically investigating novel mechanims and efficient compartmentalization strategies within single address spaces. You can find my list of publications [here](/publications.html).

## Latest Research

### μFork (Published at SOSP'25)
μFork enables Single-Address-Space Operating Systems (SASOS) to support multi-process applications using the POSIX fork() primitive without sacrificing performance. It achieves this by duplicating a parent process's memory to a new location within the same address space, rather than creating a separate address space as traditional.

To make this feasible and secure, μFork leverages CHERI hardware capabilities two solve memory reference relocation and inter-process isolation.

We show that μFork is able to outperform traditional monolithic OSes on metrics such as fork latency by an order of magnitude. Find the paper [here](https://jkressel.github.io/files/ufork-sosp2025.pdf).

### MicrOS (Ongoing)
I am currently porting noMMU Linux to the RISC-V CHERI Codasip X730 platform. The goal of this project is to ask "what if we remove the MMU?" - can features which rely on the MMU such as paging and copy-on-write be efficiently supported allowing the overhead and indeterminacy of the MMU to be eliminated from the critical path.

## Skills & Experience
I have deep experience developing and debugging kernels including Linux, on ARM and RISC-V architectures. I am comfortable debugging bare-metal and at the assembly level.
Further, I have designed and implemented userspace and kernel compartmentalization using mechanisms such as CHERI and Intel MPK.

## News
[10/2025] Our paper on μFork has been published at SOSP'25! Find the paper [here](https://jkressel.github.io/files/ufork-sosp2025.pdf).

## Contact
If you'd like to reach out and chat about my research, my email is john.kressel (at) manchester.ac.uk
