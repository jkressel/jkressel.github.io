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

To make this feasible and secure, μFork leverages CHERI hardware capabilities two solve the following problems:

- Memory Reference Relocation: Because the child’s memory is at a different virtual address, absolute pointers copied from the parent become invalid (pointing back to the parent's memory). We leverage CHERI's hardware memory tagging to scan for and relocate these pointers efficiently.
- Intra-Address-Space Isolation: We utilize CHERI’s hardware capabilities to enforce strict isolation between "μprocesses" and the kernel, preventing unauthorized access despite sharing a single address space.

We show that μFork is able to outperform traditional monolithic OSes on metrics such as fork latency by an order of magnitude. Find the paper [here](https://jkressel.github.io/files/ufork-sosp2025.pdf).

## Skills & Experience
I have deep experience developing and debugging kernels including Linux on ARM and RISC-V architectures. I am comfortable debugging bare-metal and at the assembly level.
Further, I have designed and implemented userspace and kernel compartmentalization using mechanisms such as CHERI and Intel MPK.

## Contact
If you'd like to reach out and chat about my research, my email is john.kressel (at) manchester.ac.uk
