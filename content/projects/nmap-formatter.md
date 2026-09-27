---
title: nmap-formatter
description: A versatile CLI tool and Go library to convert Nmap XML scan results into HTML, CSV, JSON, Markdown, SQLite, Excel, Graphviz, and D2 formats.
tags:
  - go
  - nmap
  - recon
  - reporting
  - security-tools
  - pentest
link: https://github.com/vdjagilev/nmap-formatter
---

## Description

**nmap-formatter** is an open-source command-line tool and Go library created to parse Nmap XML output and convert it into various structured, human-readable, and machine-readable formats. It simplifies post-scan reporting, data aggregation, automation, and visualization for penetration testers, security engineers, and red teams.

### Supported Output Formats

- **HTML**: Standalone, clean HTML report for executive summaries and walkthroughs.
- **Markdown**: Formatted markdown tables suitable for documentation, Obsidian digital gardens, and GitHub issues.
- **JSON**: Normalized JSON structures for ingestion into databases or downstream pipelines.
- **CSV**: Tabular comma-separated output for spreadsheet analysis.
- **Excel (`.xlsx`)**: Formatted multi-column spreadsheets.
- **SQLite**: Direct export to a local SQLite database (`.sqlite`) for relational SQL queries.
- **Graphviz (`.dot`)**: Visual representation of hosts, ports, and topologies renderable via Graphviz.
- **D2**: Modern declarative diagram output renderable with the D2 engine.

### Key Capabilities

- **Flexible Input Methods**: Can process output files directly via path arguments or ingest streamed XML data via standard input (`stdin`).
- **Filtering & Host Management**: Filter down hosts (`--skip-down-hosts`), control verbosity, and tune formatting options.
- **Go Library Integration**: Can be imported directly into external Go applications (`github.com/vdjagilev/nmap-formatter/v3`) for native programmatic parsing of Nmap scan data.
- **Cross-Platform**: Distributed as standalone prebuilt binaries for Linux, macOS (AMD64 & ARM64), and Windows, as well as Docker containers.

### Quick Start

```bash
# Install via Go
go install github.com/vdjagilev/nmap-formatter/v3@latest

# Convert Nmap XML to HTML report
nmap-formatter html scan-results.xml > report.html

# Stream from stdin to JSON
cat scan-results.xml | nmap-formatter json

# Export to SQLite database
nmap-formatter sqlite --sqlite-dsn results.sqlite scan-results.xml

# Generate D2 architecture diagram
cat scan-results.xml | nmap-formatter d2 | d2 - network-map.png
```

### Links

- **GitHub Repository**: [vdjagilev/nmap-formatter](https://github.com/vdjagilev/nmap-formatter)
- **Documentation & Wiki**: [Installation & Usage Wiki](https://github.com/vdjagilev/nmap-formatter/wiki)
- **Releases**: [GitHub Releases](https://github.com/vdjagilev/nmap-formatter/releases)
