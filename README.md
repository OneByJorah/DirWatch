<div align="center">

![DirWatch banner](docs/assets/banner.svg)

# DirWatch

**Lightweight, self-hosted dashboard for Active Directory domain controller health — replication, SYSVOL, LDAP bind, and service status at a glance**

[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/DirWatch?color=3776AB&label=release&logo=github)](https://github.com/OneByJorah/DirWatch/releases)
[![PyPI version](https://img.shields.io/pypi/v/dirwatch?color=3776AB&label=pip&logo=pypi)](https://pypi.org/project/dirwatch/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![Python 3.11](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/Flask-3-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![PowerShell](https://img.shields.io/badge/PowerShell-5.1-5391FE?style=flat-square&logo=powershell&logoColor=white)](https://learn.microsoft.com/powershell/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

</div>

![DirWatch dashboard](docs/assets/screenshot.png)

## What This Is

DirWatch surfaces the health of your Active Directory domain controllers in a single dark-theme dashboard. A PowerShell collector emits a normalized JSON status file (replication state, SYSVOL, LDAP bind, DHCP scope, and service status) and the Flask app renders it as status cards, DC detail, alerts, and trends.

Built for Windows admins who want a quick, dependency-light DC health view without standing up SCOM or a full monitoring stack.

## Quick Start

### pip

```bash
pip install dirwatch
```

### Docker (recommended)

```bash
git clone https://github.com/OneByJorah/DirWatch.git
cd DirWatch
docker compose up -d
```

Open **http://localhost:5000**.

### From Source

```bash
git clone https://github.com/OneByJorah/DirWatch.git
cd DirWatch
pip install -r requirements.txt
python3 app.py
```

Open **http://localhost:5000**.

## Install

### pip

```bash
pip install dirwatch
```

### Docker

```bash
git clone https://github.com/OneByJorah/DirWatch.git
cd DirWatch
docker compose up -d
```

### From Source

```bash
git clone https://github.com/OneByJorah/DirWatch.git
cd DirWatch
pip install -r requirements.txt
python3 app.py
```

## Features

- **DC health at a glance** — replication state, SYSVOL, LDAP bind, DHCP scope, service status
- **PowerShell collector** — emits normalized JSON status file from any Windows domain controller
- **Flask dashboard** — dark-theme status cards, DC detail view, alerts, and trends
- **Self-hosted** — no external dependencies, no cloud required
- **Docker support** — run with `docker compose up -d`
- **Dependency-light** — Flask + PowerShell, no SCOM, no full monitoring stack

## Tech Stack

- **Backend** — Python 3.11, Flask 3
- **Collector** — PowerShell 5.1 (Windows)
- **Deployment** — Docker Compose, pip install
- **Data** — JSON status file (mock_dc_status.json, replaceable with real collector output)

## Package Badges

[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/DirWatch?color=3776AB&label=release&logo=github)](https://github.com/OneByJorah/DirWatch/releases)
[![PyPI version](https://img.shields.io/pypi/v/dirwatch?color=3776AB&label=pip&logo=pypi)](https://pypi.org/project/dirwatch/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

## Configuration

DirWatch reads `mock_dc_status.json` at startup. Swap in your own collector output by mounting a real file at the same path.

The included `collectors/mock_dc_collector.ps1` generates sample data for testing.

| File | Description |
|------|-------------|
| `mock_dc_status.json` | DC status data (replace with real collector output) |
| `collectors/mock_dc_collector.ps1` | Sample PowerShell collector |
| `app.py` | Flask application entry point |

## Architecture

```
PowerShell Collector (collectors/mock_dc_collector.ps1)
        │
        ▼
  mock_dc_status.json (normalized JSON)
        │
        ▼
  Flask App (app.py) ──▶ Dark-theme dashboard (http://localhost:5000)
```

## Contributing

Contributions are welcome. [Open an issue](https://github.com/OneByJorah/DirWatch/issues) to report a bug or request a feature.

## License

MIT — see [LICENSE](LICENSE).
