<h1 id="top" align="center">Core Grafana</h1>

<br>

<div align="center">
    <img height=200 src="assets/banner/banner.png">
</div>

<br>

## 🔍 Table of Contents

- [About Project](#intro)
- [Dashboard](#dashboard)
- [Technologies](#technologies)
- [Features](#features)
- [Releases](#releases)
- [System Startup](#system-startup)
- [Contributors](#contributors)

<br/>

<h2 id="intro">📌 About Project</h2>

This project simplifies the deployment of Grafana with pre-configured settings, including persistent data storage, predefined admin password, email alert support and , dashboard JSON template, all managed via Docker Compose.

<br/>

<h2 id="dashboard">🔥 Dashboard</h2>

<div align="center">
    <img width=800 src="assets/dashboard/dashboard.png">
</div>

<br/>

<h2 id="technologies">☄️ Technologies</h2>

&nbsp; [![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com)

&nbsp; [![Grafana](https://img.shields.io/badge/Grafana-F2F4F9?style=for-the-badge&logo=grafana&logoColor=orange&labelColor=F2F4F9)](https://grafana.com)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Persistent Data:** Utilizes bind mounts to persist data on the host machine, preventing data loss during container restarts.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Prometheus Integration:** Seamlessly integrates with Prometheus to visualize real-time monitoring data.
- **Dashboard Template:** Comes with a prepared JSON dashboard that can be imported automatically.
- **Email Alerts Support:** Configure email alerts via `.env` file for monitoring important system metrics.
- **Predefined Admin Credentials:** Allows the use of a predefined admin password stored in a `.env` file.

<br/>

<h2 id="releases">🚢 Releases</h2>

&nbsp; [![.](https://img.shields.io/badge/1.0.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/core-grafana/tree/v1.0.0)

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `core`.

```
mkdir core
cd core
```

- Clone project.

```
git clone https://github.com/ahmettoguz/core-grafana
```

- Create `.env` file based on the `.env.example` file with credentails.

```
cp .env.example .env
```

- Create `network-core` network if not exists.

```
docker network create network-core
```

- Run Container.

```
docker stop                           core-grafana-c
docker rm                             core-grafana-c
docker compose -p core up --build -d  grafana
docker compose -p core up -d          grafana
docker logs -f                        core-grafana-c
```

```
curl -vkL https://micro-local.net/prometheus/api/v1/query?query=up
curl -vkL https://micro-local.net/prometheus/api/v1/metadata
```

- Check [`prometheus`](https://github.com/ahmettoguz/core-prometheus) repository to integrate prometheus to grafana

- Add prometheus data source with docker service name as `http://prometheus:9090/prometheus`.

<br/>

<h2 id="contributors">👥 Contributors</h2>

<a href="https://github.com/ahmettoguz" target="_blank"><img width=60 height=60 src="https://avatars.githubusercontent.com/u/101711642?v=4"></a>

### [🔝](#top)
