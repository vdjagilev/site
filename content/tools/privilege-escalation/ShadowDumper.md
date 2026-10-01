---
title: ShadowDumper
description: Stealthy LSASS memory dumper leveraging Volume Shadow Copy Service (VSS) and handle duplication.
tags:
  - privilege-escalation
  - cred-access
  - lsass
  - windows
  - red-team
  - evasion
link: https://github.com/Offensive-Panda/ShadowDumper
---

## Description

ShadowDumper dumps the memory of the Local Security Authority Subsystem Service (LSASS) without raising alerts from standard API hooks. It combines Volume Shadow Copy snapshots, process handle duplication, and unhooked system calls to acquire memory dumps for offline password hash extraction while evading modern endpoint detection rules.
