---
title: Interceptor
description: CLI-driven agent-control tool and MCP server for real browser sessions and native macOS apps.
tags:
  - browser-automation
  - ai-agents
  - mcp
  - macOS
link: https://github.com/Hacker-Valley-Media/Interceptor
---

## Description

Interceptor is a CLI-driven agent-control tool and MCP server designed for real browser sessions and native macOS applications. Instead of starting an isolated, detectable headless browser via CDP, Interceptor operates inside your existing Chrome, Brave, or Safari sessions with cookies, logins, and tabs intact.

### Key Capabilities

* **Passive Network Observability:** Intercepts `fetch()`, `XMLHttpRequest`, `EventSource` (SSE), and WebSockets without triggering browser infobanners or CDP hooks.
* **Synthetic Trusted Input:** Pre-load `userActivation` overrides and event markers satisfy `isTrusted` checks for rich editors, canvas design tools, and complex forms.
* **Dual-Surface Control:** Provides browser-level automation (`interceptor open`, `interceptor act`) alongside native macOS accessibility-tree automation (`interceptor macos tree`, `interceptor macos act`).
* **MCP Integration:** Registers as an MCP server for AI clients (Claude Code, Gemini CLI, Cursor) with safety-gated execution profiles.
