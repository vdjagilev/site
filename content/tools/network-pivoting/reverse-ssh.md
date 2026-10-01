---
title: reverse_ssh
description: SSH-based reverse shell server with dynamic SOCKS5 forwarding, native SCP/SFTP, and multi-transport support.
tags:
  - network-pivoting
  - ssh
  - reverse-shell
  - red-team
  - tunneling
  - socks5
link: https://github.com/NHAS/reverse_ssh
---

## Description

reverse_ssh turns standard OpenSSH clients into full-featured reverse shell handlers. Compromised targets connect outbound back to the controller via SSH, providing dynamic/local/remote port forwarding, full interactive PTYs on Windows and Linux, native SCP/SFTP file transfers, and fallback transports over HTTP, WebSockets, or TLS.
