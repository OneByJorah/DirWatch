# DirWatch

> Lightweight self-hosted Active Directory domain-controller health dashboard — replication, SYSVOL, LDAP bind, and service status rendered from a PowerShell collector JSON feed.

[![License](https://img.shields.io/github/license/OneByJorah/DirWatch?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/DirWatch)
[![Top Language](https://img.shields.io/github/languages/top/OneByJorah/DirWatch?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/DirWatch)
[![Stars](https://img.shields.io/github/stars/OneByJorah/DirWatch?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/DirWatch/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/OneByJorah/DirWatch?style=for-the-badge&color=FFB300&labelColor=0a0a09)](https://github.com/OneByJorah/DirWatch/commits)
[![CI](https://img.shields.io/github/actions/workflow/status/OneByJorah/DirWatch/ci.yml?style=for-the-badge&color=FFB300&labelColor=0a0a09&label=ci)](https://github.com/OneByJorah/DirWatch/actions/workflows/ci.yml)

![DirWatch dashboard](docs/assets/screenshot.png)

## What This Is

DirWatch surfaces the health of your AD domain controllers in a single dark-theme dashboard. A PowerShell collector emits a normalized JSON status file covering replication state, SYSVOL, LDAP bind, DHCP scope, and service status; the Flask app renders it as per-DC status cards, detail views, alerts, and trends. Built for Windows admins who want a quick DC health view without standing up SCOM or a full monitoring stack.

## Quick Start

```bash
git clone https://github.com/OneByJorah/DirWatch.git
cd DirWatch
pip install -r requirements.txt
python3 app.py
```

Open **http://localhost:5000**. Or run in Docker with `docker compose up -d`. The app reads `mock_dc_status.json` at startup; mount a real collector output at the same path to go live.

## Features

- Per-DC status cards with health, replication, SYSVOL, and LDAP bind state.
- Replication monitoring between controllers.
- DNS, DHCP, and ADWS service state per DC.
- Severity-coded alert feed (critical / warning / info).
- `/public` endpoint returning a simple "all systems operational" string.
- PowerShell collectors with Teams/Telegram notification placeholders.
- Production image runs gunicorn as a non-root user.

## Architecture

```
PowerShell collector ──▶ mock_dc_status.json ──▶ Flask app (:5000) ──▶ Browser
                                                     │
                                                     ├──▶ Dashboard (/)
                                                     └──▶ Public status (/public)
```

The status file is loaded once at startup and rendered through Jinja2 templates; refresh it by regenerating the file with a collector.

## Stack

Python 3.11 · Flask 3 · Jinja2 · gunicorn · PowerShell 5.1 collectors · Docker Compose.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). [Open an issue](https://github.com/OneByJorah/DirWatch/issues) to report a bug or request a feature.

## License

MIT — see [LICENSE](LICENSE).
