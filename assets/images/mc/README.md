# Web ABAP SAST screenshots

Upload PNGs here with these exact filenames. They are referenced by `index.md`.

| File | What to capture |
|---|---|
| `01-projects.png` | ABAP Code Security page: projects list with per-project vulnerability counts |
| `02-run-scan.png` | Creating a project / starting a scan: select target system(s) + scan profile |
| `03-vulnerabilities.png` | Vulnerabilities table: severity, CVSS, status, object columns |
| `04-finding-detail.png` | One finding opened: description, severity/CVSS, confidence + explanation, code location, remediation |
| `05-retest.png` | Cross-system retest dialog and/or retest history table |
| `06-report.png` | Exported report (or export dialog / scheduled-scans view) |

## Guidelines
- **Format:** PNG, ~1400-1800 px wide, light theme, tight crop (trim browser chrome).
- **Redact** anything sensitive: real hostnames, system IDs, tokens, emails, keys.
- Positioned as **SAST**; the finding fields are labelled **confidence** and **explanation**.
- Keep a consistent look across shots (same sample data).
