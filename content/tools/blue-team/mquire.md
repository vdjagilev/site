---
title: mquire
description: Linux physical memory forensics tool by Trail of Bits that operates without external kernel debug symbols.
tags:
  - blue-team
  - forensics
  - memory-analysis
  - dfir
  - linux
link: https://github.com/trailofbits/mquire
---

## Description

Created by Trail of Bits, mquire simplifies Linux memory forensics by eliminating the requirement for exact kernel debug profiles (DWARF/System.map). It dynamically discovers kernel data structures and walks process lists, open file descriptors, and network sockets directly from raw physical memory dumps.
