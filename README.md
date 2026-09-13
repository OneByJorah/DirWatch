<div align="center">

![DC_Status_Dashboard banner](docs/assets/banner.svg)

# DirWatch

Data center status dashboard — monitor server health, network links, power, cooling, and facility metrics in real time.

[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/DC_Status_Dashboard?color=34d399&label=release&logo=github)](https://github.com/OneByJorah/DC_Status_Dashboard/releases)
[![PyPI version](https://img.shields.io/pypi/v/dcstatusdashboard?color=34d399&label=pip&logo=pypi)](https://pypi.org/project/dcstatusdashboard/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![Python 3.11+](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

</div>

![DC_Status_Dashboard screenshot](docs/assets/screenshot.png)

## What This Is

Data center status dashboard — monitor server health, network links, power, cooling, and facility metrics in real time.

Built for operators who want a self-hosted, Docker-deployed solution they control.

## Quick Start

### pip

```bash
pip install dcstatusdashboard
```

### Docker (recommended)

```bash
git clone https://github.com/OneByJorah/DC_Status_Dashboard.git
cd DC_Status_Dashboard
docker compose up -d
```

### From Source

```bash
git clone https://github.com/OneByJorah/DC_Status_Dashboard.git
cd DC_Status_Dashboard
pip install -r requirements.txt
python3 app.py
```

## Install

### pip

```bash
pip install dcstatusdashboard
```

### Docker

```bash
git clone https://github.com/OneByJorah/DC_Status_Dashboard.git
cd DC_Status_Dashboard
docker compose up -d
```

### From Source

```bash
git clone https://github.com/OneByJorah/DC_Status_Dashboard.git
cd DC_Status_Dashboard
pip install -r requirements.txt
python3 app.py
```

## Features

- **Self-hosted** — no cloud dependencies, run on your own hardware
- **Docker Compose** — full stack deployment with one command
- **pip package** — install via PyPI
- **Dark theme** — operational, clean UI

- **Server health monitoring** — CPU, memory, disk, and service status
- **Network link status** — track uplink and interconnect health
- **Power and cooling** — facility infrastructure monitoring
- **Real-time alerts** — threshold-based notifications
- **Docker Compose deployment** — self-hosted dashboard
- **Dark theme** — NOC-style, operational UI

## Tech Stack

- **Backend** — Python 3.11+, pydantic, pyyaml
- **Deployment** — Docker Compose, pip install
- **Configuration** — environment variables, config files

## Package Badges

[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/DC_Status_Dashboard?color=34d399&label=release&logo=github)](https://github.com/OneByJorah/DC_Status_Dashboard/releases)
[![PyPI version](https://img.shields.io/pypi/v/dcstatusdashboard?color=34d399&label=pip&logo=pypi)](https://pypi.org/project/dcstatusdashboard/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

## Contributing

Contributions are welcome. [Open an issue](https://github.com/OneByJorah/DC_Status_Dashboard/issues) to report a bug or request a feature.

## License

MIT — see [LICENSE](LICENSE).
