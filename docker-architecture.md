# Docker Architecture

## AWS EC2

The monitoring environment is deployed on an AWS EC2 instance running Ubuntu Linux.

## Docker Containers

The project currently runs the following containers:

| Container | Port | Purpose |
|---|---:|---|
| Jenkins | 8080 | CI/CD automation |
| Prometheus | 9090 | Metrics collection |
| Grafana | 3000 | Metrics visualization |
| cAdvisor | 8081 | Docker container metrics |

## Monitoring Architecture

```text
                    AWS EC2
                       |
                     Docker
                       |
       +---------------+---------------+
       |               |               |
    Jenkins         cAdvisor       Prometheus
       |               |               |
       |               +-------+-------+
       |                       |
       |                    Metrics
       |                       |
       |                    Grafana
       |                       |
       +------------- Monitoring


