---
title: Internal Monologue
description: Steals NetNTLM challenge-response hashes from memory without injecting code or touching LSASS.
tags:
  - active-directory
  - ntlm
  - red-team
  - pentest
  - lsass
  - windows
link: https://github.com/eladshamir/Internal-Monologue
---

## Description

The Internal Monologue attack retrieves NetNTLM challenge-response hashes by interacting with Security Support Provider Interface (SSPI) packages from within the security context of the current user process. Because it negotiates authentication locally without injecting into or dumping LSASS memory, it bypasses credential-theft protections and endpoint detections that monitor access to LSASS.
