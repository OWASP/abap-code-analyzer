---
layout: col-sidebar
title: OWASP ABAP Code Scanner
tags: abap sap security sast static-analysis code-scanner
level: 2
type: tool
pitch: Static Application Security Testing (SAST) for SAP ABAP - from a free open-source CLI to a web scanner that connects directly to your SAP systems.
---

[![OWASP Incubator](https://img.shields.io/badge/OWASP-Incubator-blue.svg)](https://owasp.org/projects/)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/OWASP/abap-code-scanner/blob/main/LICENSE)
[![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-blue.svg)](https://www.python.org/)
[![GitHub stars](https://img.shields.io/github/stars/OWASP/abap-code-scanner?style=social)](https://github.com/OWASP/abap-code-scanner)

## SAST for SAP ABAP

Custom **ABAP** (Advanced Business Application Programming) code runs the business logic of most SAP systems - and is rarely security-reviewed, making it a common source of injection, path-traversal and hard-coded-secret vulnerabilities.

The **OWASP ABAP Code Scanner** is a **Static Application Security Testing (SAST)** tool that analyses ABAP source code for security vulnerabilities so teams can fix them before they reach production. It is available in editions that share the same scanning engine - the newest connects directly to your SAP systems.

## New version: web-based ABAP SAST

The latest version runs as a web application. Instead of exporting code, it **connects directly to your SAP systems over SAP JCo (RFC)** and statically analyses ABAP in place, then presents findings in a modern web UI.

<!-- SCREENSHOT 1 -> assets/images/mc/01-projects.png
     Capture: the ABAP Code Security page - projects list with per-project vulnerability counts. -->
![ABAP SAST - projects overview](assets/images/mc/01-projects.png)

### What it does

- **Direct SAP connection (SAP JCo / RFC)** - scan ABAP straight from the system; no manual export.
- **Projects** - organise scans by mapping target **systems** to **scan profiles** (for example *OWASP Top 10* or *Critical issues only*).
- **Scheduled scans** - run recurring scans automatically.
- **Vulnerability dashboard** - findings ranked by **severity** and **CVSS**, each with a **confidence score** and a plain-language **explanation**.
- **Cross-system retest** - re-verify a finding across systems, with full retest history.
- **Reports & export** - export findings for triage and audit.
- **Enterprise access** - single sign-on and role-based access control.

<!-- SCREENSHOT 2 -> assets/images/mc/02-run-scan.png
     Capture: creating a project / starting a scan - selecting target system(s) and a scan profile. -->
![Create a project and run a scan](assets/images/mc/02-run-scan.png)

### Findings and triage

Each finding identifies the affected ABAP object and location, with a severity, a CVSS score, a confidence score and a plain-language explanation, plus a status you manage from the browser.

<!-- SCREENSHOT 3 -> assets/images/mc/03-vulnerabilities.png
     Capture: the vulnerabilities table - severity, CVSS, status and object columns. -->
![Vulnerability findings](assets/images/mc/03-vulnerabilities.png)

<!-- SCREENSHOT 4 -> assets/images/mc/04-finding-detail.png
     Capture: a single finding opened - description, severity/CVSS, confidence + explanation, code location, remediation. -->
![Finding detail](assets/images/mc/04-finding-detail.png)

### Retest across systems

Re-run a specific finding against one or more systems to confirm whether it is still present, and keep a history of every retest.

<!-- SCREENSHOT 5 -> assets/images/mc/05-retest.png
     Capture: the cross-system retest dialog and/or the retest history table. -->
![Cross-system retest with history](assets/images/mc/05-retest.png)

### Reporting

Export findings to a report for distribution and audit.

<!-- SCREENSHOT 6 -> assets/images/mc/06-report.png
     Capture: an exported report, or the export dialog / scheduled-scans view. -->
![Export a report](assets/images/mc/06-report.png)

### Get access

The web-based version is a commercial product by [RedRays](https://redrays.io/). To request a demo or a trial, visit [redrays.io/abap-scanner](https://redrays.io/abap-scanner/) or contact `support@redrays.io`.

## Other editions

- **Open-source CLI** (free, MIT) - the heart of this OWASP project; scans exported ABAP source locally or in CI. See [the open-source CLI](open-source-cli.md) and the [README](https://github.com/OWASP/abap-code-scanner#readme).
- **Cloud Edition for SAP BTP** - a SaaS that reads ABAP over BTP destinations. See [the BTP edition](btp-edition.md).

## Getting involved

You do not need to be a security expert to help: [open an issue](https://github.com/OWASP/abap-code-scanner/issues) for a bug or a new check idea, or send a pull request. See [CONTRIBUTING.md](https://github.com/OWASP/abap-code-scanner/blob/main/CONTRIBUTING.md).

## Licensing

The OWASP ABAP Code Scanner project (the open-source CLI) is free and released under the [MIT License](https://github.com/OWASP/abap-code-scanner/blob/main/LICENSE). The web-based and BTP editions are commercial products by [RedRays](https://redrays.io/); the OWASP project itself is, and remains, free and open source.
