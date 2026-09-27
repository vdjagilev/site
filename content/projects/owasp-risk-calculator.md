---
title: OWASP Risk Calculator
description: An interactive web application implementing the OWASP Risk Rating Methodology with mitigation modeling and radar chart visualization.
tags:
  - svelte
  - typescript
  - owasp
  - risk-assessment
  - appsec
  - security-tools
link: https://github.com/vdjagilev/owasp-risk-calculator
---

## Description

**OWASP Risk Calculator** is an interactive web-based risk assessment utility built to calculate and visualize security risk based on the official [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology). In addition to computing standard inherent risk levels, it features a mitigation modeling workflow displayed on an interactive radar chart to compare raw risk against residual risk after controls are applied.

### Core Methodology

The calculator evaluates risk based on standard OWASP factors:

$$\text{Risk} = \text{Likelihood} \times \text{Impact}$$

- **Likelihood Assessment**:
  - **Threat Agent Factors**: Skill Level, Motive, Opportunity, and Size.
  - **Vulnerability Factors**: Ease of Discovery, Ease of Exploit, Awareness, and Intrusion Detection.
- **Impact Assessment**:
  - **Technical Impact**: Loss of Confidentiality, Integrity, Availability, and Accountability.
  - **Business Impact**: Financial Damage, Reputation Damage, Non-compliance, and Privacy Violation.

### Key Capabilities

- **Mitigation Modeling**: Define compensatory security controls and measure residual risk reduction alongside inherent risk.
- **Radar Chart Visualization**: Dynamic multi-axis radar chart displaying risk profiles and visual mitigation overlays in real-time.
- **Interactive Breakdown**: Instant severity calculation (Critical, High, Medium, Low, Note) across likelihood and impact dimensions.
- **Modern Lightweight Stack**: Developed with SvelteKit, TypeScript, and Vite for fast client-side performance and responsive layouts across desktop and mobile.

### Live Application

Access the live calculator directly in your browser:

- 🌐 **Live Tool**: [OWASP Risk Calculator App](https://vdjagilev.github.io/owasp-risk-calculator/)

### Links

- **GitHub Repository**: [vdjagilev/owasp-risk-calculator](https://github.com/vdjagilev/owasp-risk-calculator)
- **Methodology Reference**: [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology)
