---
title: SCShell
description: Fileless lateral movement and command execution using ChangeServiceConfigA against existing Windows services.
tags:
  - privilege-escalation
  - lateral-movement
  - windows
  - red-team
  - smb
link: https://github.com/Mr-Un1k0d3r/SCShell
---

## Description

SCShell is an evasion-focused lateral movement utility that executes commands on remote Windows machines using DCE/RPC. Instead of creating a new service (which generates Windows Event 7045 and triggers EDR alarms), it temporarily modifies the binary path of an existing, stopped service via `ChangeServiceConfigA`, executes the desired payload, and restores the original path.
