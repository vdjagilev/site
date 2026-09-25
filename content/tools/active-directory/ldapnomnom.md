---
title: ldapnomnom
description: Anonymously bruteforce Active Directory usernames at insane speeds by abusing LDAP Ping (cLDAP) requests.
tags:
  - ldap
  - active-directory
  - brute-force
  - go
  - red-team
link: https://github.com/lkarlslund/ldapnomnom
---

## Description

`ldapnomnom` quietly and anonymously bruteforces Active Directory usernames at high speeds from Domain Controllers by abusing connectionless LDAP (cLDAP) Ping requests over UDP port 389. Because cLDAP does not require authentication or create logon failure event logs (Event ID 4625), it enables covert username enumeration without locking accounts.
