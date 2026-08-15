# Prometheus Monitoring

Prometheus collects and stores metrics from the Docker environment.

## Metrics Monitored

- Container CPU usage
- Container memory usage
- Network receive traffic
- Network transmit traffic
- Target availability

## PromQL Queries Tested

### Target Availability

up

### Container Memory

sum by (name) (container_memory_usage_bytes{name!=""})

### Container CPU

sum by (name) (rate(container_cpu_usage_seconds_total{name!=""}[5m]))

### Network Receive

sum by (name) (rate(container_network_receive_bytes_total{name!=""}[5m]))

### Network Transmit

sum by (name) (rate(container_network_transmit_bytes_total{name!=""}[5m]))

## Data Flow

Docker Containers → cAdvisor → Prometheus → Grafana

## Verification

Prometheus metrics were successfully queried through Grafana Explore for Jenkins, Grafana, Prometheus and cAdvisor.
