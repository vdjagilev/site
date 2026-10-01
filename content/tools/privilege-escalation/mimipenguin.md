---
title: mimipenguin
description: Post-exploitation tool to dump cleartext login passwords from Linux desktop memory.
tags:
  - privilege-escalation
  - cred-access
  - linux
  - post-exploitation
  - red-team
link: https://github.com/huntergregal/mimipenguin
---

## Description

Inspired by Windows Mimikatz, mimipenguin searches the memory space of target Linux processes (such as `gnome-keyring-daemon`, `gdm-password`, `lightdm`, and `vsftpd`) to dump cleartext credentials and passwords stored by desktop display managers and authentication daemons.
