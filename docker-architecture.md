# Docker Architecture

## Running Containers

This project runs a complete monitoring stack using Docker containers.

| Container | Image | Port | Purpose |
|---|---|---:|---|
| Jenkins | jenkins-demo:9 | 8080 | CI/CD automation |
| Prometheus | prom/prometheus:latest | 9090 | Metrics collection and monitoring |
| Grafana | grafana/grafana:latest | 3000 | Metrics visualization and dashboards |
| cAdvisor | ghcr.io/google/cadvisor:latest | 8081 | Docker container monitoring |

## Monitoring Flow

Docker Containers
        ↓
     cAdvisor
        ↓
    Prometheus
        ↓
      Grafana

Jenkins is used for CI/CD automation and is monitored as part of the Docker environment.

## Infrastructure

- Host: AWS EC2
- Container Platform: Docker
- Monitoring: Prometheus + cAdvisor
- Visualization: Grafana
- CI/CD: Jenkins
- Source Control: Git + GitHub
