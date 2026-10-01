---
title: SockTail
description: Lightweight binary that joins a device to a Tailscale network using embedded tsnet to expose a SOCKS5 proxy.
tags:
  - network-pivoting
  - socks5
  - proxy
  - tailscale
  - red-team
  - tunneling
link: https://github.com/Yeeb1/SockTail
---

## Description

SockTail embeds Tailscale's userspace networking library (`tsnet`) into a single self-contained binary. When executed on an engaged target, it joins a Tailnet as an ephemeral node without requiring root/admin privileges, kernel TUN devices, or persistent daemons, instantly exposing a local SOCKS5 proxy for inbound traffic pivoting.
