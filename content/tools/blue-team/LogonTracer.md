---
title: LogonTracer
description: Visualizes Windows Active Directory event logs to identify anomalous logon chains and credential abuse.
tags:
  - blue-team
  - active-directory
  - dfir
  - incident-response
  - visualization
  - windows
link: https://github.com/JPCERTCC/LogonTracer
---

## Description

Created by JPCERT/CC, LogonTracer parses Windows security event logs (such as Event ID 4624, 4625, and 4768) and constructs a visual graph using Neo4j. By mapping logon relationships, RDP sessions, and Kerberos ticket requests, it enables defenders to visually detect Pass-the-Hash, Pass-the-Ticket, and lateral movement across Active Directory domains.
