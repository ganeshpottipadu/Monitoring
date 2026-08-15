# Grafana Monitoring Dashboard

Grafana is used to visualize container metrics collected by Prometheus.

## Prometheus Data Source

Grafana is connected to Prometheus as the data source.

## Metrics Visualized

- Container network receive traffic
- Container network transmit traffic
- Container performance metrics
- Container-level monitoring

## PromQL Queries

### Network Receive

sum by (name) (rate(container_network_receive_bytes_total{name!=""}[5m]))

### Network Transmit

sum by (name) (rate(container_network_transmit_bytes_total{name!=""}[5m]))

## Containers Monitored

- Jenkins
- Grafana
- Prometheus
- cAdvisor

## Monitoring Flow

Docker Containers → cAdvisor → Prometheus → Grafana Dashboard

## Verification

Metrics were successfully queried and visualized using Grafana Explore.
