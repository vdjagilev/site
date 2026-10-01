---
title: Furtex
description: Linux post-exploitation and EDR evasion research toolkit built around raw io_uring operations and eBPF.
tags:
  - privilege-escalation
  - linux
  - rootkit
  - edr-evasion
  - ebpf
  - io-uring
link: https://github.com/MatheuZSecurity/Furtex
---

## Description

Furtex is an advanced Linux post-exploitation toolkit designed for kernel-level research and defensive testing. Built entirely on raw `io_uring` system calls and eBPF without relying on external libraries (such as `liburing`), it provides stealthy persistence, asynchronous process inspection, and execution primitives that circumvent user-space and syscall monitoring hooks.
