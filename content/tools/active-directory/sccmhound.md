---
title: sccmhound
description: BloodHound collector for Microsoft Configuration Manager (SCCM / MECM) attack paths and privilege escalation.
tags:
  - active-directory
  - windows
  - sccm
  - bloodhound
  - red-team
  - recon
link: https://github.com/CrowdStrike/sccmhound
---

## Description

Created by CrowdStrike, sccmhound is a C# collector that audits Microsoft Endpoint Configuration Manager (SCCM/MECM) environments. It enumerates site servers, distribution points, client push accounts, and network access accounts (NAAs), converting discovered trust relationships, misconfigurations, and privilege escalation vectors into BloodHound-compatible graph data.
