---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
Hi, I'm John Alistair Kressel, a final year PhD student at the University of Manchester. My research explores the intersection of single-address-space systems and OSes and systems security. I focus on fundamental system design, specifically investigating novel mechanims and efficient compartmentalization strategies within single address spaces. You can find my list of publications [here](/publications.html).

## Latest Research

### μFork (Published at SOSP'25)
μFork improves the compatibility of single-address-space OSes (SASOSes), allowing them to efficiently and securely support multi-process applications.

Single-Address-Space Operating Systems (SASOS) offer lightweightness and performance benefits over traditional monolithic OSes, including fast IPC and low-latency context switching. This is achieved by colocating the kernel and applications in a unique address space. However, this model is fundamentally incompatible with the POSIX fork() primitive. Since fork relies on creating a new, identical address space for the child process, traditional SASOS designs are unable to support multi-process applications like Nginx and Redis. Prior solutions forced a trade-off: sacrifice performance by re-introducing multiple address spaces, or rely on complex toolchain modifications to attempt to support relative addressing in complex modern applications.

The solution: μFork
We introduced μFork, a novel design that supports POSIX fork transparently within a true single address space. Instead of creating a new address space, μFork duplicates the parent's memory to a different location within the same global address space. This approach introduces two critical systems challenges which we solved using Capability Hardware Enhanced RISC Instructions (CHERI):
- Memory Reference Relocation: Because the child’s memory is at a different virtual address, absolute pointers copied from the parent become invalid (pointing back to the parent's memory). We leverage CHERI's hardware memory tagging to scan for and relocate these pointers efficiently.
- Intra-Address-Space Isolation: We utilize CHERI’s hardware capabilities to enforce strict isolation between "μprocesses" and the kernel, preventing unauthorized access despite sharing a single address space.

To maintain high performance, we redesigned the traditional Copy-on-Write (CoW) mechanism. In a SASOS, standard CoW is insufficient because a child reading a pointer would still see the parent's address. We developed Copy-on-Pointer-Access (CoPA), an optimization that allows memory sharing until a write occurs or until the child loads a pointer.This ensures pointers are relocated lazily only when necessary, significantly reducing fork latency compared to full copying.

We show that μFork is able to outperform traditional monolithic OSes on metrics such as fork latency by an order of magnitude. Find the paper [here](https://jkressel.github.io/files/ufork-sosp2025.pdf).

## Skills & Experience
I have deep experience developing and debugging kernels including Linux on ARM and RISC-V architectures. I am comfortable debugging bare-metal and at the assembly level.
Further, I have designed and implemented userspace and kernel compartmentalization using mechanisms such as CHERI and Intel MPK.

## Contact
If you'd like to reach out and chat about my research, my email is john.kressel (at) manchester.ac.uk
