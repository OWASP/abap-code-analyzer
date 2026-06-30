<div align="center">

<img src="assets/images/logo.svg" alt="OWASP ABAP Code Scanner" width="112">

# OWASP ABAP Code Scanner

**Static Application Security Testing (SAST) for SAP ABAP.**
Find security vulnerabilities in custom ABAP code - from a free open-source CLI to a web scanner that connects directly to your SAP systems.

[![OWASP Incubator](https://img.shields.io/badge/OWASP-Incubator-blue.svg)](https://owasp.org/projects/)
[![License: MIT](https://img.shields.io/github/license/OWASP/abap-code-scanner)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-blue.svg)](https://www.python.org/)
[![Stars](https://img.shields.io/github/stars/OWASP/abap-code-scanner?style=social)](https://github.com/OWASP/abap-code-scanner/stargazers)
[![Issues](https://img.shields.io/github/issues/OWASP/abap-code-scanner)](https://github.com/OWASP/abap-code-scanner/issues)

</div>

---

## Editions

| Edition | What it is | Where |
|---|---|---|
| **Web (newest)** | Web-based ABAP SAST that connects to SAP over JCo / RFC | [Below](#web-version-abap-sast) |
| **Cloud (SAP BTP)** | SaaS that reads ABAP over BTP destinations | [btp-edition.md](btp-edition.md) |
| **Open-source CLI** | Free, MIT tool for scanning exported ABAP locally or in CI | [Below](#open-source-cli) |

## Web version: ABAP SAST

The newest version runs as a web application and **connects directly to your SAP systems over SAP JCo (RFC)** - no manual export. It:

- organises scans into **projects** (target systems + scan profiles such as *OWASP Top 10* or *Critical issues only*);
- runs **scheduled scans**;
- ranks findings by **severity** and **CVSS**, each with a **confidence score** and a plain-language **explanation**;
- supports **cross-system retest** with full history;
- exports **reports** for triage and audit;
- uses **single sign-on and role-based access control**.

<div align="center">
  <img src="assets/images/mc/01-projects.png" alt="ABAP SAST - projects overview" width="760">
  <img src="assets/images/mc/04-finding-detail.png" alt="Finding detail" width="760">
</div>

> The web version is a commercial product by [RedRays](https://redrays.io/). Request a demo or trial at [redrays.io/abap-scanner](https://redrays.io/abap-scanner/).

## Open-source CLI

The free, MIT-licensed CLI is the heart of this OWASP project. It statically analyses **exported** ABAP source **offline** - no SAP connection, no agent, no telemetry - and writes an XLSX report you can act on. Drop it into CI to gate pull requests.

### Quick start

> Requires **Python 3.9+** and `pip`.

```bash
git clone https://github.com/OWASP/abap-code-scanner.git
cd abap-code-scanner
pip install -r requirements.txt

python main.py path/to/abap/source
```

When the scan finishes you will find **`abap_security_scan_report.xlsx`** in the project folder:

<div align="center">
  <img src="assets/images/screenshot.png" alt="Example XLSX report" width="760">
</div>

### CLI options

| Option | Description | Default |
|---|---|---|
| `path` | Directory of ABAP source to scan | _(required)_ |
| `-c`, `--config` | Path to the YAML config file | `config.yml` |

### Configuration

The scanner reads a YAML file (default `config.yml`, override with `-c`). Pick the checks to run, the file extensions to include, and patterns to exclude:

```yaml
checks:
  - CheckCrossSiteScripting
  - CheckSQLInjection
  - CheckDirectoryTraversal

file_extensions:
  - .abap
  - .txt

exclude_patterns:
  - "**/test/**"
```

### Writing a custom check

1. Create a new Python file in the `checks/` directory.
2. Define a class that inherits from the base check class.
3. Implement the required methods, including the main `run` method.
4. Add the class name to the `checks:` list in your config file.

### Running the tests

```bash
# Unix-like
./run_tests.sh

# Windows
run_tests.bat
```

## Roadmap

- [ ] Data-flow / taint analysis (sources to sinks) to cut false positives
- [ ] SARIF output for GitHub code scanning
- [ ] JSON output
- [ ] More checks mapped to the OWASP Top 10 and SAP secure-coding guidance

## Contributing

Pull requests are welcome - new checks, test cases, bug fixes and docs all help. See [CONTRIBUTING.md](CONTRIBUTING.md) and please follow the OWASP Code of Conduct.

## Security

Found a vulnerability in the scanner itself? Please follow the responsible-disclosure process in [SECURITY.md](SECURITY.md) - do **not** open a public issue for security reports.

## License

[MIT](LICENSE). Originally contributed and maintained by [RedRays](https://redrays.io/). The web and [SAP BTP](btp-edition.md) editions are commercial products; this OWASP project (the open-source CLI) is free and open source.

---

<div align="center"><sub>An <a href="https://owasp.org/">OWASP</a> Incubator Project.</sub></div>
