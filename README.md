<h1 id="top" align="center">Monitor Grafana <br/> 🚢 v1.0.0 🚢</h1>

<br>

<div align="center">
    <img height=150 src="assets/banner/banner.png">
</div>

<br>

## 🔍 Table of Contents

- [Features](#features)
- [System Startup](#system-startup)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Persistent Data:** Utilizes bind mounts to persist data on the host machine, preventing data loss during container restarts.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Prometheus Integration:** Seamlessly integrates with Prometheus to visualize real-time monitoring data.
- **Dashboard & Datasource Provisioning:** Comes with a prepared JSON dashboard and predefined data sources, automatically loaded using provisioning files.
- **Pre-configured Dashboards:** Comes with ready-to-use dashboards for Traefik, Docker, and Node Exporter, offering instant insights into system performance.
- **Email Alerts Support:** Configure email alerts via `.env` file for monitoring important system metrics.
- **Predefined Admin Credentials:** Allows the use of a predefined admin password stored in a `.env` file.

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `monitor`.

```
mkdir monitor
cd monitor
```

- Clone project.

```
git clone https://github.com/ahmettoguz/monitor-grafana
```

- Create `.env` file based on the `.env.example` file with credentails.

```
cp .env.example .env
```

- Check `provisioning` directory for further dashboard and datasource configuration.

- Create `network-monitor` network if not exists.

```
docker network create network-monitor
```

- Run container.

```
docker stop                             monitor-grafana-c
docker rm                               monitor-grafana-c
docker compose -p monitor up --build -d grafana
docker compose -p monitor up -d         grafana
docker logs -f                          monitor-grafana-c
```

- Refer to [`cAdvisor`](https://github.com/ahmettoguz/monitor-cadvisor) repository to expose contianer metrics.

- Refer to [`Node-Export`](https://github.com/ahmettoguz/monitor-node-export) repository to expose node metrics.

- Refer to [`Prometheus`](https://github.com/ahmettoguz/monitor-prometheus) repository to integrate prometheus to scrap data.

- Refer to [`Traefik`](https://github.com/ahmettoguz/core-traefik) repository to expose traefik metrics and also launch reverse proxy.

<br/>

### [🔝](#top)
