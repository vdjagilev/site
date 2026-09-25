---
title: DeadPotato
description: Windows privilege escalation utility abusing SeImpersonatePrivilege to elevate from service accounts to SYSTEM.
tags:
  - lpe
  - windows
  - potato-exploit
  - red-team
link: https://github.com/lypd0/DeadPotato
---

## Description

DeadPotato is a Windows local privilege escalation utility belonging to the Potato family of exploits. It leverages `SeImpersonatePrivilege` or `SeAssignPrimaryTokenPrivilege` (commonly held by service accounts such as `IIS_IUSRS` or `LOCAL SERVICE`) to spoof DCOM/RPC tokens and execute arbitrary payloads with `NT AUTHORITY\SYSTEM` privileges.
