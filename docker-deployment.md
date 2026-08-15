# Docker Deployment

## Environment

The monitoring stack was deployed on an AWS EC2 Ubuntu instance using Docker.

## Containers

The following containers were deployed:

- Jenkins
- Prometheus
- Grafana
- cAdvisor

## Verification

Container status was verified using:

```bash
docker ps

| Service    | Port |
| ---------- | ---: |
| Jenkins    | 8080 |
| Prometheus | 9090 |
| Grafana    | 3000 |
| cAdvisor   | 8081 |


Monitoring Architecture

Docker Containers
↓
cAdvisor
↓
Prometheus
↓
Grafana
↓
Monitoring Dashboard
