# Docker Monitoring & Alerting with Prometheus and Grafana

## Overview

This project demonstrates a Docker monitoring and alerting setup using:

- Docker
- Jenkins
- Prometheus
- Grafana
- cAdvisor
- Email alerts

The setup monitors Docker container CPU usage and sends an email notification when the configured CPU threshold is exceeded.

## Architecture

Jenkins
   |
   v
Docker Containers
   |
   +--> cAdvisor
   |       |
   |       v
   |   Prometheus
   |       |
   |       v
   |    Grafana
   |       |
   |       v
   +--> Email Alert

## Components

| Component | Purpose |
|---|---|
| Jenkins | CI/CD automation |
| Docker | Container platform |
| cAdvisor | Collects container metrics |
| Prometheus | Stores and queries metrics |
| Grafana | Visualization and alerting |
| Gmail SMTP | Sends alert notifications |

## Prometheus

Prometheus collects container metrics from cAdvisor.

Example PromQL query:

```promql
sum by (name) (
  rate(container_cpu_usage_seconds_total{name!=""}[5m])
) * 100
Grafana Alert

The project contains a Grafana alert named:

Container CPU High

The alert monitors container CPU usage and changes to the Firing state when the configured threshold is exceeded.

Email notifications are configured through Gmail SMTP.

Docker Services

##The monitoring stack contains:

prometheus
grafana
cadvisor
monitoring-app
Useful Commands

*Check running containers:

docker ps

*Check CPU and memory usage:

docker stats

*View Grafana logs:

docker logs grafana

*View Prometheus logs:

docker logs prometheus

*Restart Grafana:

docker restart grafana

*Restart the monitoring application:

docker restart monitoring-app
Security

SMTP credentials are stored in .env and are excluded from Git using .gitignore.

Never commit Gmail passwords or API credentials to GitHub.

Project Goal

The goal of this project is to demonstrate practical DevOps skills including:

1>Docker containerization
2>CI/CD with Jenkins
3>Monitoring with Prometheus
4>Visualization with Grafana
5>Container metrics with cAdvisor
6>Grafana alerting
7>Email notifications
8>Git and GitHub
9>PromQL


Save:

**Ctrl + O → Enter → Ctrl + X**

### Step 2 — Commit the README

Run:

```bash
git add README.md
