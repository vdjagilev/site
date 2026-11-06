---
title: Joern
description: Open-source code analysis platform for analyzing source code and bytecode using code property graphs.
tags:
  - blue-team
  - appsec
  - sast
  - cpg
  - scala
  - java
  - c
  - python
link: https://github.com/joernio/joern
---

## Description

Joern is an open-source code analysis and vulnerability discovery platform based on **Code Property Graphs (CPGs)**. Originally developed through academic research into graph-based vulnerability discovery, Joern merges abstract syntax trees (ASTs), control flow graphs (CFGs), and program dependence graphs (PDGs) into a unified, queryable property graph stored in a graph database.

By parsing C/C++, Java, JVM bytecode, JavaScript, TypeScript, Python, Kotlin, Go, PHP, and binary executables (via Ghidra), Joern empowers AppSec engineers, security auditors, and researchers to conduct deep static application security testing (SAST), taint analysis, data-flow tracking, and variant analysis across large codebases using its interactive query language (CPGQL) or Python/Scala scripting.
